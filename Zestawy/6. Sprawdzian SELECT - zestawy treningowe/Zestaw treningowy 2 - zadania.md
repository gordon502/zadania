# Zestaw treningowy 2 — zapytania SELECT (przed sprawdzianem)

**Baza:** `sklep` (sklep internetowy) | **Narzędzie:** phpMyAdmin → baza `sklep` → zakładka **SQL**
**Odpowiedzi:** plik `Zestaw treningowy 2 - odpowiedzi.md` — zaglądaj dopiero **po** rozwiązaniu zadania.

Na sprawdzianie będzie **ta sama baza** i około 30 zadań podobnych do tych — ale z innymi pytaniami
i innymi wartościami. Odpowiedzi nie da się wyczytać z tabel „na oko”: trzeba napisać zapytanie.
Zadania są ułożone **od najłatwiejszych do najtrudniejszych**, tematy są wymieszane — tak jak na sprawdzianie.
Chcesz poćwiczyć więcej? Na tej samej bazie jest też `Zestaw treningowy 1 - zadania.md` — z innymi zadaniami.

| Poziom | Zadania | Co jest potrzebne |
|---|---|---|
| ★ Rozgrzewka — jedna tabela | 1–20 | `SELECT`, `WHERE`, `ORDER BY`, `LIMIT`, `DISTINCT`, `LIKE`, `IS NULL`, `COUNT`, `AVG` |
| ★★ Funkcje, grupowanie i pierwsze złączenia | 21–45 | aliasy, `CONCAT`, `ROUND`, `YEAR`, `MONTH`, obliczenia, `GROUP BY`, `HAVING`, `JOIN` 2 tabel |
| ★★★ Złączenia z grupowaniem | 46–70 | `JOIN` 2–3 tabel z `GROUP BY` / `HAVING`, wartość zamówień, pierwszy `LEFT JOIN` |
| ★★★★ Kilka tabel, raporty i LEFT JOIN | 71–89 | `JOIN` 3–5 tabel, raporty, `LEFT JOIN … IS NULL`, `COUNT(DISTINCT …)` |
| ★★★★★ Poziom egzaminacyjny | 90–100 | wszystko naraz + typowe pułapki |

## Baza `sklep`

| Tabela | Wierszy | Kolumny | Klucze obce (do `ON`) |
|---|---|---|---|
| `kategorie` | 11 | `id`, `nazwa` | — |
| `producenci` | 25 | `id`, `nazwa`, `kraj` | — |
| `produkty` | 119 | `id`, `nazwa`, `id_kategorii`, `id_producenta`, `cena`, `cena_promocyjna`, `stan_magazynowy`, `data_dodania` | `id_kategorii` → `kategorie.id`, `id_producenta` → `producenci.id` |
| `klienci` | 320 | `id`, `imie`, `nazwisko`, `email`, `telefon`, `miasto`, `data_urodzenia`, `data_rejestracji`, `newsletter` | — |
| `zamowienia` | 1492 | `id`, `id_klienta`, `data_zamowienia`, `status`, `sposob_dostawy`, `sposob_platnosci`, `koszt_dostawy` | `id_klienta` → `klienci.id` |
| `pozycje_zamowienia` | 3087 | `id_zamowienia`, `id_produktu`, `ilosc`, `cena_jednostkowa` | `id_zamowienia` → `zamowienia.id`, `id_produktu` → `produkty.id` |
| `opinie` | 859 | `id`, `id_produktu`, `id_klienta`, `ocena`, `tresc`, `data_opinii` | `id_produktu` → `produkty.id`, `id_klienta` → `klienci.id` |

**Jak połączone są tabele:**

```
kategorie ──< produkty >── producenci
                 │
                 ├──< pozycje_zamowienia >── zamowienia >── klienci
                 │                                            │
                 └──< opinie >────────────────────────────────┘
```

`──<` czytamy „jeden do wielu”: jedna kategoria ma wiele produktów, jeden klient ma wiele zamówień.
`pozycje_zamowienia` to **tabela łącząca** zamówienia z produktami (jedno zamówienie = kilka produktów).

**Co warto wiedzieć o danych:**
- `status`: `nowe`, `oplacone`, `wyslane`, `dostarczone`, `anulowane`;
  `sposob_dostawy`: `kurier`, `paczkomat`, `odbior osobisty`; `sposob_platnosci`: `blik`, `karta`, `przelew`, `pobranie`
  (wszystko małymi literami, bez polskich znaków),
- `newsletter`: `T` = klient zgodził się na newsletter, `N` = nie,
- `NULL` oznacza brak wartości: klient nie podał telefonu, produkt nie jest w promocji, opinia nie ma komentarza,
- `cena_jednostkowa` to cena w chwili zakupu — czasem promocyjna, więc **nie zawsze** równa `produkty.cena`,
- zamówienia od 300 zł i odbiór osobisty mają darmową dostawę (`koszt_dostawy` = 0.00).

## Zasady

- **Wartość / przychód / wydatki** = `SUM(ilosc * cena_jednostkowa)` z tabeli `pozycje_zamowienia`
  (bez kosztów dostawy, chyba że zadanie mówi inaczej).
- Zamówienia **anulowane** liczymy wszędzie tam, gdzie zadanie nie mówi „bez anulowanych”.
- **Nie wpisuj numerów `id` „z głowy”.** Jeśli zadanie mówi o kategorii *Książki* albo producencie *Apple*,
  połącz tabele i filtruj po **nazwie**. Wyjątek: numer zamówienia podany w treści.
- Przy łączeniu tabel zawsze pisz, z której tabeli jest kolumna (`p.nazwa`, `k.miasto`) — najlepiej z aliasami.
- Liczbę wierszy wyniku odczytasz z komunikatu phpMyAdmina nad tabelą:
  *Wyświetlanie wierszy 0 - 24 (25 wszystkich…)*.
- Po każdym zadaniu zapisz odpowiedź z linijki **➜ Zapisz** i porównaj ją z plikiem odpowiedzi.
  Jeśli się nie zgadza — najpierw szukaj błędu sam, potem zajrzyj do podpowiedzi, a na końcu do odpowiedzi.

---

## ★ Poziom 1 · Rozgrzewka — jedna tabela

### Zadanie 1

Wyświetl całą zawartość tabeli `producenci`.

**➜ Zapisz:** ilu jest producentów.

<details><summary>Podpowiedź</summary>

`SELECT * FROM …;`

</details>

### Zadanie 2

Wyświetl imię, nazwisko i datę rejestracji klientów — od osoby, która zarejestrowała się **najwcześniej**.

**➜ Zapisz:** imię i nazwisko pierwszej osoby oraz datę jej rejestracji.

<details><summary>Podpowiedź</summary>

Najwcześniejsza data to najmniejsza wartość — sortowanie rosnące.

</details>

### Zadanie 3

Wyświetl imiona, nazwiska i miasta klientów, którzy **nie** mieszkają w Warszawie.

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

Operator „różne od” to `<>`.

</details>

### Zadanie 4

Policz funkcją `COUNT` wszystkie produkty w sklepie. Kolumna wyniku ma mieć nagłówek `LiczbaProduktow`.

**➜ Zapisz:** liczbę produktów.

<details><summary>Podpowiedź</summary>

`SELECT COUNT(*) AS … FROM …;`

</details>

### Zadanie 5

Wyświetl nazwy produktów i stany magazynowe dla produktów, których w magazynie jest **co najmniej 140** sztuk.

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

„Co najmniej” to `>=`.

</details>

### Zadanie 6

W jakich miastach mieszkają klienci, którzy **nie podali telefonu**? Każde miasto tylko raz, alfabetycznie.

**➜ Zapisz:** ile jest takich miast i które jest pierwsze.

<details><summary>Podpowiedź</summary>

`SELECT DISTINCT miasto … WHERE telefon IS NULL ORDER BY miasto`.

</details>

### Zadanie 7

Wyświetl **10 ostatnio dodanych** do sklepu produktów: nazwę i datę dodania.

**➜ Zapisz:** nazwę produktu z **10.** miejsca listy.

<details><summary>Podpowiedź</summary>

Najnowsze = największa data: `ORDER BY data_dodania DESC LIMIT 10`.

</details>

### Zadanie 8

Ilu klientów **podało** numer telefonu? Użyj `COUNT(telefon)` — **bez** `WHERE`.

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

`COUNT(kolumna)` liczy tylko te wiersze, w których kolumna **nie jest** `NULL`.

</details>

### Zadanie 9

Wyświetl nazwy i ceny produktów, w których nazwie występuje słowo **Samsung**.

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

Słowo może stać w środku nazwy — `%` z obu stron.

</details>

### Zadanie 10

Wyświetl zamówienia z **pierwszego kwartału 2026** roku (od 1 stycznia do 31 marca 2026).

**➜ Zapisz:** ile było takich zamówień.

<details><summary>Podpowiedź</summary>

`BETWEEN '2026-01-01' AND '2026-03-31'`.

</details>

### Zadanie 11

Wyświetl nazwy i ceny produktów, które kosztują **mniej niż 100 zł**.

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

„Mniej niż” to `<`, nie `<=`.

</details>

### Zadanie 12

Wyświetl zamówienia, których status **nie jest** ani `dostarczone`, ani `anulowane` (czyli zamówienia jeszcze w realizacji).

**➜ Zapisz:** ile jest takich zamówień.

<details><summary>Podpowiedź</summary>

`WHERE status NOT IN ('…', '…')`.

</details>

### Zadanie 13

Wyświetl zamówienia dostarczane **kurierem**, które były opłacone **kartą lub BLIK-iem**.

**➜ Zapisz:** ile jest takich zamówień.

<details><summary>Podpowiedź</summary>

`AND` ma pierwszeństwo przed `OR`. Weź warunki z `OR` w **nawiasy**.

</details>

### Zadanie 14

Wyświetl klientów, których imię ma **dokładnie 3 litery** (np. Jan).

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

Znak `_` w `LIKE` oznacza **dokładnie jeden** dowolny znak.

</details>

### Zadanie 15

Wyświetl nazwę, stan magazynowy i cenę wszystkich produktów. Posortuj po stanie magazynowym **rosnąco**, a przy takim samym stanie — po cenie **malejąco**.

**➜ Zapisz:** nazwę produktu z pierwszego wiersza.

<details><summary>Podpowiedź</summary>

`ORDER BY stan_magazynowy ASC, cena DESC` — każda kolumna ma własny kierunek.

</details>

### Zadanie 16

Kiedy zarejestrował się **najnowszy** klient? Użyj funkcji agregującej.

**➜ Zapisz:** datę.

<details><summary>Podpowiedź</summary>

`MAX(data_rejestracji)`.

</details>

### Zadanie 17

Który produkt jest **drugi** pod względem ceny (drugi najdroższy)? Użyj `LIMIT` i `OFFSET`.

**➜ Zapisz:** nazwę i cenę produktu.

<details><summary>Podpowiedź</summary>

Posortuj malejąco, pomiń 1 wiersz i pokaż 1: `LIMIT 1 OFFSET 1`.

</details>

### Zadanie 18

Ile **sztuk** wszystkich produktów leży łącznie w magazynie?

**➜ Zapisz:** liczbę sztuk.

<details><summary>Podpowiedź</summary>

`SUM(stan_magazynowy)`.

</details>

### Zadanie 19

Ile opinii z oceną **4 lub 5** wystawiono w **2026** roku?

**➜ Zapisz:** liczbę opinii.

<details><summary>Podpowiedź</summary>

Dwa warunki: `ocena >= 4` i data z przedziału `'2026-01-01'`–`'2026-12-31'`.

</details>

### Zadanie 20

Ile zamówień miało **płatną** dostawę (koszt dostawy większy od zera)?

**➜ Zapisz:** liczbę zamówień.

<details><summary>Podpowiedź</summary>

`WHERE koszt_dostawy > 0`.

</details>

---

## ★★ Poziom 2 · Funkcje, grupowanie i pierwsze złączenia

### Zadanie 21

Przygotuj listę wysyłkową newslettera dla klientów z **Gdyni**: jedna kolumna `Adresat` w postaci `Imię Nazwisko <email>` (np. `Jan Nowak <jan.nowak@wp.pl>`). Tylko osoby z `newsletter` = `'T'`, alfabetycznie po nazwisku.

**➜ Zapisz:** pierwszy wiersz wyniku.

<details><summary>Podpowiedź</summary>

`CONCAT` przyjmuje dowolnie wiele argumentów: `CONCAT(imie, ' ', nazwisko, ' <', email, '>')`.

</details>

### Zadanie 22

Ile zamówień opłacono każdym sposobem płatności? Posortuj od **najrzadziej** wybieranego.

**➜ Zapisz:** najrzadziej wybierany sposób płatności i liczbę zamówień.

<details><summary>Podpowiedź</summary>

`GROUP BY sposob_platnosci ORDER BY … ASC`.

</details>

### Zadanie 23

Wyświetl nazwę kategorii, nazwę produktu i cenę promocyjną dla wszystkich produktów **w promocji**. Posortuj po nazwie kategorii, a w kategorii — po nazwie produktu.

**➜ Zapisz:** kategorię i produkt z pierwszego wiersza.

<details><summary>Podpowiedź</summary>

`produkty` + `kategorie`, warunek `cena_promocyjna IS NOT NULL`.

</details>

### Zadanie 24

Ilu klientów zgodziło się na newsletter, a ilu nie? (jedno zapytanie, grupowanie po kolumnie `newsletter`)

**➜ Zapisz:** liczbę klientów z `T`.

<details><summary>Podpowiedź</summary>

`GROUP BY newsletter`.

</details>

### Zadanie 25

Ceny w sklepie są cenami brutto (z 23% VAT). Dla produktów droższych niż **5000 zł** wyświetl nazwę, cenę i cenę **netto** = cena / 1.23, zaokrągloną do 2 miejsc, jako kolumnę `Netto`. Posortuj od najdroższego.

**➜ Zapisz:** cenę netto najdroższego produktu.

<details><summary>Podpowiedź</summary>

`ROUND(cena / 1.23, 2) AS Netto`.

</details>

### Zadanie 26

Ile **różnych** produktów zostało kiedykolwiek zamówionych?

**➜ Zapisz:** liczbę produktów.

<details><summary>Podpowiedź</summary>

Tabela `pozycje_zamowienia`, `COUNT(DISTINCT id_produktu)`.

</details>

### Zadanie 27

Ilu klientów ma urodziny w **listopadzie**?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

`MONTH(data_urodzenia) = 11`.

</details>

### Zadanie 28

Lista klientów jest posortowana po nazwisku, a przy tym samym nazwisku — po imieniu. Na stronie mieści się **25** osób. Wyświetl **5. stronę**.

**➜ Zapisz:** imię i nazwisko pierwszej osoby na 5. stronie.

<details><summary>Podpowiedź</summary>

Ile wierszy zajmują strony 1–4? Tyle trzeba pominąć w `OFFSET`.

</details>

### Zadanie 29

Wyświetl opinie klientów z **Torunia**: imię, nazwisko, ocenę i datę opinii. Posortuj od najstarszej opinii.

**➜ Zapisz:** ile jest takich opinii i jaką ocenę ma pierwsza z nich.

<details><summary>Podpowiedź</summary>

`opinie` + `klienci`, warunek na miasto.

</details>

### Zadanie 30

Dla każdego **statusu** zamówienia podaj średni koszt dostawy (2 miejsca po przecinku) i najwyższy koszt dostawy.

**➜ Zapisz:** średni koszt dostawy dla zamówień anulowanych.

<details><summary>Podpowiedź</summary>

Dwie funkcje agregujące w jednym `SELECT`, `GROUP BY status`.

</details>

### Zadanie 31

Ilu klientów zarejestrowało się w każdym roku? Posortuj od roku z największą liczbą rejestracji.

**➜ Zapisz:** rok z największą liczbą rejestracji i tę liczbę.

<details><summary>Podpowiedź</summary>

`GROUP BY YEAR(data_rejestracji)`.

</details>

### Zadanie 32

Które produkty (wystarczy `id_produktu`) sprzedały się w łącznej liczbie **co najmniej 100 sztuk**? Wyświetl `id_produktu` i liczbę sztuk.

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

Jedna tabela: `pozycje_zamowienia`. `GROUP BY id_produktu HAVING SUM(ilosc) >= 100`.

</details>

### Zadanie 33

Wyświetl wszystkie pozycje zamówienia nr **700**: `id_produktu`, ilość, cenę jednostkową i wartość pozycji (ilość × cena) jako kolumnę `Wartosc`. Posortuj od największej wartości.

**➜ Zapisz:** wartość najdroższej pozycji.

<details><summary>Podpowiedź</summary>

Jedna tabela, mnożenie w `SELECT`.

</details>

### Zadanie 34

Ile zamówień złożono w **pierwszym tygodniu** miesiąca (dni 1–7, dowolny miesiąc i rok)?

**➜ Zapisz:** liczbę zamówień.

<details><summary>Podpowiedź</summary>

`DAY(data)` zwraca dzień miesiąca (1–31).

</details>

### Zadanie 35

Wyświetl zamówienia klientów z **Łodzi** płacone **za pobraniem**: imię, nazwisko, datę zamówienia i koszt dostawy.

**➜ Zapisz:** ile jest takich zamówień.

<details><summary>Podpowiedź</summary>

`klienci` + `zamowienia`, dwa warunki w `WHERE`.

</details>

### Zadanie 36

Ile łącznie klienci zapłacili za **dostawę** w **2025** roku?

**➜ Zapisz:** kwotę.

<details><summary>Podpowiedź</summary>

`SUM(koszt_dostawy)` z warunkiem na rok.

</details>

### Zadanie 37

Jednym zapytaniem podaj cenę **najtańszego** i **najdroższego** produktu spośród tych, których **nie ma w magazynie**.

**➜ Zapisz:** obie ceny.

<details><summary>Podpowiedź</summary>

Brak w magazynie = `stan_magazynowy = 0`. `MIN` i `MAX` w jednym `SELECT`.

</details>

### Zadanie 38

Ilu klientów ma adres e-mail **poza** domenami `gmail.com` i `wp.pl`?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

Dwa warunki `NOT LIKE` połączone `AND`.

</details>

### Zadanie 39

Ile zamówień złożono w każdym miesiącu kalendarzowym (niezależnie od roku)? Posortuj od miesiąca z **najmniejszą** liczbą.

**➜ Zapisz:** numer najsłabszego miesiąca i liczbę zamówień.

<details><summary>Podpowiedź</summary>

`GROUP BY MONTH(data_zamowienia)`.

</details>

### Zadanie 40

Wyświetl **5 najnowszych** opinii: datę, nazwę produktu i ocenę. Opinie z tego samego dnia ułóż alfabetycznie po nazwie produktu.

**➜ Zapisz:** nazwę produktu z 5. wiersza.

<details><summary>Podpowiedź</summary>

`opinie` + `produkty`, `ORDER BY o.data_opinii DESC, p.nazwa LIMIT 5`.

</details>

### Zadanie 41

W które **dni** złożono **co najmniej 8** zamówień? Wyświetl datę i liczbę zamówień.

**➜ Zapisz:** ile było takich dni.

<details><summary>Podpowiedź</summary>

Grupujemy po samej dacie: `GROUP BY data_zamowienia HAVING COUNT(*) >= 8`.

</details>

### Zadanie 42

Ilu **różnych** klientów złożyło zamówienie w **październiku 2026**?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

`COUNT(DISTINCT id_klienta)` z warunkiem na daty.

</details>

### Zadanie 43

Dla produktów **w promocji** podaj średnią cenę regularną i średnią cenę promocyjną (obie zaokrąglone do 2 miejsc).

**➜ Zapisz:** obie średnie.

<details><summary>Podpowiedź</summary>

`ROUND(AVG(…), 2)` dwa razy, warunek `cena_promocyjna IS NOT NULL`.

</details>

### Zadanie 44

Którzy klienci z **Krakowa** choć raz wybrali **odbiór osobisty**? Wyświetl imię i nazwisko — każdą osobę raz.

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

`klienci` + `zamowienia`, `SELECT DISTINCT`.

</details>

### Zadanie 45

Ilu klientów kończy w **2026** roku **więcej niż 60 lat**? (wiek = 2026 − rok urodzenia)

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

W `WHERE` można liczyć: `2026 - YEAR(data_urodzenia) > 60`.

</details>

---

## ★★★ Poziom 3 · Złączenia z grupowaniem

### Zadanie 46

Ile produktów **w promocji** ma każdy producent? Wyświetl nazwę producenta i liczbę, od największej.

**➜ Zapisz:** ilu producentów ma choć jeden produkt w promocji oraz którzy producenci mają ich najwięcej.

<details><summary>Podpowiedź</summary>

`produkty` + `producenci`, warunek `IS NOT NULL` w `WHERE`, potem `GROUP BY pr.nazwa`.

</details>

### Zadanie 47

Jaka jest średnia cena produktu w każdej kategorii (2 miejsca)? Posortuj od najtańszej kategorii.

**➜ Zapisz:** kategorię z najniższą średnią ceną i tę średnią.

<details><summary>Podpowiedź</summary>

`produkty` + `kategorie`, `ROUND(AVG(p.cena), 2)`.

</details>

### Zadanie 48

Które **5 produktów** przyniosło największy przychód w całej historii sklepu (bez zamówień anulowanych)?

**➜ Zapisz:** nazwę produktu z 5. miejsca i kwotę.

<details><summary>Podpowiedź</summary>

`produkty` + `pozycje_zamowienia` + `zamowienia` (status).

</details>

### Zadanie 49

Ile klient musiał zapłacić **łącznie** za zamówienie nr **1103** (towary + dostawa)?

**➜ Zapisz:** kwotę do zapłaty.

<details><summary>Podpowiedź</summary>

`zamowienia` + `pozycje_zamowienia`. Dostawę dodaj **raz**, poza `SUM`: `SUM(…) + z.koszt_dostawy`, a w `GROUP BY` wpisz `z.id, z.koszt_dostawy`.

</details>

### Zadanie 50

W stylu egzaminu (tabele po przecinku, warunek łączenia w `WHERE`) wyświetl nazwę kategorii i nazwę produktu dla produktów, których **nie ma w magazynie**. Posortuj po nazwie kategorii, potem po nazwie produktu.

**➜ Zapisz:** liczbę wierszy i kategorię z pierwszego wiersza.

<details><summary>Podpowiedź</summary>

`FROM produkty, kategorie WHERE produkty.id_kategorii = kategorie.id AND …`.

</details>

### Zadanie 51

Wyświetl **wszystkich** producentów z liczbą ich produktów (także 0) i pozostaw tylko tych, którzy mają **mniej niż 3** produkty.

**➜ Zapisz:** ilu jest takich producentów.

<details><summary>Podpowiedź</summary>

`producenci LEFT JOIN produkty`, `COUNT(p.id)`, warunek w `HAVING`.

</details>

### Zadanie 52

Którzy klienci kupili **Konsolę Sony PlayStation 5 Slim**? Wyświetl imię i nazwisko — każdą osobę raz.

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

`klienci` → `zamowienia` → `pozycje_zamowienia` → `produkty`; warunek na nazwę produktu.

</details>

### Zadanie 53

W których kategoriach średnia cena produktu przekracza **800 zł**? Wyświetl nazwę kategorii i średnią (2 miejsca).

**➜ Zapisz:** nazwy tych kategorii.

<details><summary>Podpowiedź</summary>

`HAVING AVG(p.cena) > 800`.

</details>

### Zadanie 54

Ile zamówień złożono w każdym miesiącu każdego roku? Wyświetl rok, miesiąc i liczbę zamówień, od miesiąca z największą liczbą.

**➜ Zapisz:** liczbę wierszy i rekordowy miesiąc (rok i numer miesiąca).

<details><summary>Podpowiedź</summary>

`GROUP BY YEAR(…), MONTH(…)`.

</details>

### Zadanie 55

Ile opinii wystawił każdy klient z **Gdańska**? Wyświetl imię, nazwisko i liczbę opinii, od największej.

**➜ Zapisz:** osobę z 1. miejsca i liczbę jej opinii.

<details><summary>Podpowiedź</summary>

`opinie` + `klienci`, grupuj po `k.id`.

</details>

### Zadanie 56

Ile zamówień z **2025** roku dostarczono **paczkomatem lub kurierem** i miało **darmową** dostawę?

**➜ Zapisz:** liczbę zamówień.

<details><summary>Podpowiedź</summary>

Trzy warunki; ten z `OR` w nawiasach (albo `IN`).

</details>

### Zadanie 57

Jaki przychód (bez zamówień anulowanych) przyniosły zamówienia opłacone każdym **sposobem płatności**?

**➜ Zapisz:** przychód z zamówień opłaconych BLIK-iem.

<details><summary>Podpowiedź</summary>

`zamowienia` + `pozycje_zamowienia`, `GROUP BY z.sposob_platnosci`.

</details>

### Zadanie 58

Ile produktów ma każdy producent w każdej kategorii? Wyświetl nazwę kategorii, nazwę producenta i liczbę produktów, od największej liczby.

**➜ Zapisz:** liczbę wierszy wyniku oraz parę kategoria–producent z 1. miejsca.

<details><summary>Podpowiedź</summary>

`produkty` + `kategorie` + `producenci`, `GROUP BY kat.nazwa, pr.nazwa`.

</details>

### Zadanie 59

Dla każdego produktu marki **Samsung** podaj średnią ocenę (2 miejsca) i liczbę opinii. Posortuj od najwyższej średniej, przy równej — od większej liczby opinii.

**➜ Zapisz:** produkt z 1. miejsca i jego średnią.

<details><summary>Podpowiedź</summary>

`opinie` → `produkty` → `producenci`.

</details>

### Zadanie 60

Ile produktów sprzedało się w liczbie **co najmniej 50 sztuk** i pojawiło się w **co najmniej 40 zamówieniach**? Wyświetl nazwę produktu, liczbę sztuk i liczbę zamówień.

**➜ Zapisz:** liczbę takich produktów.

<details><summary>Podpowiedź</summary>

`pozycje_zamowienia` + `produkty`; `HAVING SUM(pz.ilosc) >= 50 AND COUNT(*) >= 40`.

</details>

### Zadanie 61

Ilu klientów **nie wystawiło żadnej** opinii?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

`klienci LEFT JOIN opinie … WHERE o.id IS NULL`.

</details>

### Zadanie 62

Które produkty dodane do sklepu **przed 2025** rokiem nie mają **żadnej** opinii?

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

`produkty LEFT JOIN opinie`, w `WHERE` dwa warunki: `o.id IS NULL` i data dodania.

</details>

### Zadanie 63

Który produkt ma **najwięcej opinii z komentarzem** (treść nie jest `NULL`)?

**➜ Zapisz:** nazwę produktu i liczbę takich opinii.

<details><summary>Podpowiedź</summary>

`opinie` + `produkty`, `WHERE o.tresc IS NOT NULL`, grupowanie, sortowanie, `LIMIT 1`.

</details>

### Zadanie 64

Klientka o adresie e-mail `monika.sadowska@gmail.com`: ile złożyła zamówień i ile wydała łącznie (bez zamówień anulowanych)?

**➜ Zapisz:** obie liczby.

<details><summary>Podpowiedź</summary>

`klienci` → `zamowienia` → `pozycje_zamowienia`. Zamówienia policz przez `COUNT(DISTINCT z.id)` — po złączeniu z pozycjami jedno zamówienie występuje kilka razy.

</details>

### Zadanie 65

Jaka jest średnia ocena produktów według **kraju producenta**? Pokaż tylko kraje z **co najmniej 50** opiniami, od najwyższej średniej (2 miejsca).

**➜ Zapisz:** kraj z 1. miejsca i średnią.

<details><summary>Podpowiedź</summary>

`opinie` → `produkty` → `producenci`, `GROUP BY pr.kraj`.

</details>

### Zadanie 66

Jaka jest cena **najtańszego** produktu każdego producenta z **USA**?

**➜ Zapisz:** cenę najtańszego produktu firmy **Apple**.

<details><summary>Podpowiedź</summary>

`MIN(p.cena)`, warunek na kraj, grupowanie po nazwie producenta.

</details>

### Zadanie 67

Klienci z których **3 miast** wystawili najwięcej opinii? Wyświetl miasto i liczbę opinii.

**➜ Zapisz:** miasto z 3. miejsca i liczbę opinii.

<details><summary>Podpowiedź</summary>

`opinie` + `klienci`, `GROUP BY k.miasto`.

</details>

### Zadanie 68

Ile produktów ma cenę promocyjną niższą niż **80%** ceny regularnej (czyli obniżkę większą niż 20%)?

**➜ Zapisz:** liczbę produktów.

<details><summary>Podpowiedź</summary>

W warunku można liczyć: `cena_promocyjna < 0.8 * cena`.

</details>

### Zadanie 69

Ile pozycji zamówień dotyczyło produktu kupionego w **tym samym roku**, w którym pojawił się on w sklepie (rok zamówienia = rok dodania produktu)?

**➜ Zapisz:** liczbę pozycji.

<details><summary>Podpowiedź</summary>

`zamowienia` → `pozycje_zamowienia` → `produkty`. Funkcja może stać po obu stronach porównania: `YEAR(z.data_zamowienia) = YEAR(p.data_dodania)`.

</details>

### Zadanie 70

W stylu egzaminu (tabele po przecinku) wyświetl imię i nazwisko klienta, nazwę produktu i ilość dla wszystkich pozycji zamówień złożonych **1 maja 2026**. Posortuj po nazwisku.

**➜ Zapisz:** liczbę wierszy.

<details><summary>Podpowiedź</summary>

Cztery tabele po przecinku: `klienci, zamowienia, pozycje_zamowienia, produkty` — więc **trzy** warunki łączenia w `WHERE`.

</details>

---

## ★★★★ Poziom 4 · Kilka tabel, raporty i LEFT JOIN

### Zadanie 71

Wyświetl wszystko, co kupiła **Anna Nowak z Gdańska** (w bazie jest też Anna Nowak z Krakowa!): datę zamówienia, nazwę produktu, ilość i cenę jednostkową.

**➜ Zapisz:** liczbę wierszy i nazwę produktu z pierwszego wiersza (sortuj po dacie i nazwie produktu).

<details><summary>Podpowiedź</summary>

Trzy warunki na kliencie: imię, nazwisko **i miasto**. Tabele: `klienci` → `zamowienia` → `pozycje_zamowienia` → `produkty`.

</details>

### Zadanie 72

Którzy **5 klientów** wydało najwięcej w **2025** roku (bez zamówień anulowanych)? Wyświetl imię, nazwisko i kwotę.

**➜ Zapisz:** osobę z 5. miejsca i kwotę.

<details><summary>Podpowiedź</summary>

`klienci` → `zamowienia` → `pozycje_zamowienia`, grupuj po `k.id`.

</details>

### Zadanie 73

Którzy **3 producenci** przynieśli sklepowi największy przychód (bez zamówień anulowanych)?

**➜ Zapisz:** producenta z 3. miejsca i kwotę.

<details><summary>Podpowiedź</summary>

`producenci` → `produkty` → `pozycje_zamowienia` → `zamowienia`.

</details>

### Zadanie 74

W bazie jest **dwóch** klientów o imieniu i nazwisku **Piotr Wiśniewski**. Dla każdego z nich osobno podaj miasto, liczbę zamówień i datę **pierwszego** zamówienia.

**➜ Zapisz:** dane obu osób.

<details><summary>Podpowiedź</summary>

Grupuj po `k.id`. Pierwsze zamówienie = `MIN(z.data_zamowienia)`.

</details>

### Zadanie 75

Dla **każdego** produktu marki **Fiskars** podaj, w ilu zamówieniach się pojawił — także jeśli w **żadnym**.

**➜ Zapisz:** nazwę produktu z 0 zamówień.

<details><summary>Podpowiedź</summary>

`produkty` + `producenci` (`JOIN`) i `LEFT JOIN pozycje_zamowienia`. Licz `COUNT(pz.id_zamowienia)`.

</details>

### Zadanie 76

Ilu **różnych** klientów z **Warszawy** kupiło coś z kategorii **AGD** (bez zamówień anulowanych)?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

Pięć tabel: `klienci`, `zamowienia`, `pozycje_zamowienia`, `produkty`, `kategorie`.

</details>

### Zadanie 77

Które produkty przyniosły w **2026** roku przychód **powyżej 15 000 zł** (bez zamówień anulowanych)? Wyświetl nazwę i przychód, od największego.

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

Warunek na rok i status w `WHERE`, próg kwoty w `HAVING`.

</details>

### Zadanie 78

Ile zamówień miało **płatną** dostawę, choć wartość towarów przekraczała **250 zł**? Wyświetl numer zamówienia, wartość towarów i koszt dostawy.

**➜ Zapisz:** liczbę takich zamówień.

<details><summary>Podpowiedź</summary>

`zamowienia` + `pozycje_zamowienia`; warunek na koszt dostawy w `WHERE` (przed grupowaniem), warunek na wartość w `HAVING`.

</details>

### Zadanie 79

Ilu klientów **złożyło** co najmniej jedno zamówienie, ale **nie wystawiło** żadnej opinii?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

`klienci` `JOIN zamowienia` (tylko kupujący) i `LEFT JOIN opinie` z `o.id IS NULL`. Klient ma wiele zamówień — licz `COUNT(DISTINCT k.id)`.

</details>

### Zadanie 80

Którzy klienci z **Poznania** nie wystawili **żadnej** opinii? Wyświetl imię i nazwisko.

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

Jak w zadaniu 61, z dodatkowym warunkiem na miasto.

</details>

### Zadanie 81

W których miesiącach **2025** roku zamówienia złożyło **ponad 55 różnych** klientów? Wyświetl miesiąc i liczbę klientów.

**➜ Zapisz:** numery tych miesięcy.

<details><summary>Podpowiedź</summary>

Jedna tabela: `zamowienia`. `HAVING COUNT(DISTINCT id_klienta) > 55`.

</details>

### Zadanie 82

Jaki przychód (bez zamówień anulowanych) przyniosły produkty z każdego **kraju producenta**? Posortuj od największego.

**➜ Zapisz:** kraj z 1. miejsca i kwotę.

<details><summary>Podpowiedź</summary>

`producenci` → `produkty` → `pozycje_zamowienia` → `zamowienia`, `GROUP BY pr.kraj`.

</details>

### Zadanie 83

Ilu **różnych** klientów kupiło w **2026** roku jakikolwiek produkt marki **Apple** (bez zamówień anulowanych)?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

`zamowienia` → `pozycje_zamowienia` → `produkty` → `producenci`.

</details>

### Zadanie 84

Jaki sposób płatności wybierają **najczęściej** klienci urodzeni w **2000 roku lub później**?

**➜ Zapisz:** sposób płatności i liczbę zamówień.

<details><summary>Podpowiedź</summary>

`klienci` + `zamowienia`, warunek na rok urodzenia, `GROUP BY z.sposob_platnosci`.

</details>

### Zadanie 85

Ile zamówień zawierało łącznie **co najmniej 6 sztuk** towarów (suma ilości we wszystkich pozycjach)?

**➜ Zapisz:** liczbę zamówień.

<details><summary>Podpowiedź</summary>

`pozycje_zamowienia`, `GROUP BY id_zamowienia HAVING SUM(ilosc) >= 6`.

</details>

### Zadanie 86

Jaka jest średnia ocena opinii wystawianych przez klientów z poszczególnych **miast**? Pokaż tylko miasta z **co najmniej 30** opiniami, od **najniższej** średniej (2 miejsca).

**➜ Zapisz:** miasto z najniższą średnią i tę średnią.

<details><summary>Podpowiedź</summary>

`opinie` + `klienci`, `GROUP BY k.miasto`, `HAVING COUNT(*) >= 30`.

</details>

### Zadanie 87

Z której **kategorii** sprzedano najwięcej **sztuk** w **grudniu 2025** (bez zamówień anulowanych)?

**➜ Zapisz:** kategorię i liczbę sztuk.

<details><summary>Podpowiedź</summary>

`kategorie` → `produkty` → `pozycje_zamowienia` → `zamowienia`, daty w `WHERE`.

</details>

### Zadanie 88

Ilu klientów zarejestrowanych w **2026** roku nie złożyło jeszcze **żadnego** zamówienia?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

`klienci LEFT JOIN zamowienia … WHERE z.id IS NULL AND …`.

</details>

### Zadanie 89

Dla każdej **kategorii** podaj liczbę **różnych klientów**, którzy coś w niej kupili, oraz liczbę **różnych zamówień** z produktami tej kategorii. Posortuj po nazwie kategorii.

**➜ Zapisz:** obie liczby dla kategorii **Audio**.

<details><summary>Podpowiedź</summary>

`kategorie` → `produkty` → `pozycje_zamowienia` → `zamowienia`. Obie liczby przez `COUNT(DISTINCT …)`.

</details>

---

## ★★★★★ Poziom 5 · Poziom egzaminacyjny

### Zadanie 90

**Raport producentów.** Dla każdego producenta wyświetl: nazwę, kraj, liczbę **różnych** sprzedanych produktów, liczbę sprzedanych sztuk i przychód (bez zamówień anulowanych). Pokaż tylko producentów z przychodem **powyżej 50 000 zł**, od największego przychodu.

**➜ Zapisz:** ilu jest takich producentów oraz liczbę sztuk producenta z 1. miejsca.

<details><summary>Podpowiedź</summary>

Cztery tabele, trzy agregaty, próg w `HAVING`.

</details>

### Zadanie 91

Dla **każdego** klienta z **Katowic** — także takiego, który niczego nie zamówił — podaj liczbę zamówień i liczbę opinii. Posortuj od największej liczby zamówień, przy równej — od największej liczby opinii, a potem po nazwisku.

**➜ Zapisz:** liczbę wierszy, ilu klientów ma 0 zamówień oraz ile opinii ma osoba z 1. wiersza.

<details><summary>Podpowiedź</summary>

`klienci` `LEFT JOIN zamowienia` `LEFT JOIN opinie` (obie tabele dołączasz do klienta). Każda opinia powtarza się tyle razy, ile klient ma zamówień — licz przez `COUNT(DISTINCT z.id)` i `COUNT(DISTINCT o.id)`.

</details>

### Zadanie 92

**Raport klientów z Gdyni.** Dla każdego klienta z Gdyni, który coś zamówił, wyświetl: imię, nazwisko, liczbę zamówień, liczbę kupionych sztuk, łączne wydatki i datę **ostatniego** zamówienia (wszystkie zamówienia, także anulowane). Posortuj od największych wydatków.

**➜ Zapisz:** dane z pierwszego wiersza.

<details><summary>Podpowiedź</summary>

`COUNT(DISTINCT z.id)`, `SUM(pz.ilosc)`, `SUM(pz.ilosc * pz.cena_jednostkowa)`, `MAX(z.data_zamowienia)`.

</details>

### Zadanie 93

Ilu klientów korzystało **zarówno z kuriera, jak i z paczkomatu** (w różnych zamówieniach)?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

Weź tylko zamówienia kurierem lub paczkomatem (`WHERE … IN`), pogrupuj po kliencie i zostaw tych, u których `COUNT(DISTINCT sposob_dostawy) = 2`.

</details>

### Zadanie 94

Którzy klienci wystawili opinie o produktach z **co najmniej 5 różnych kategorii**? Wyświetl imię, nazwisko, liczbę kategorii i liczbę opinii, od największej liczby kategorii.

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

`opinie` → `klienci` i `opinie` → `produkty` (kategoria to `p.id_kategorii`). `HAVING COUNT(DISTINCT p.id_kategorii) >= 5`.

</details>

### Zadanie 95

**Średnie wydatki na klienta** w mieście = przychód z zamówień klientów z tego miasta / liczba różnych kupujących z tego miasta. Policz to dla miast, w których kupowało **co najmniej 10** klientów (bez zamówień anulowanych), zaokrąglij do 2 miejsc i posortuj od największej wartości.

**➜ Zapisz:** miasto z 1. miejsca i średnie wydatki na klienta.

<details><summary>Podpowiedź</summary>

W `SELECT` można dzielić wyniki funkcji agregujących: `SUM(…) / COUNT(DISTINCT k.id)`.

</details>

### Zadanie 96

Którzy producenci sprzedali w **2026** roku swoje produkty **co najmniej 40 różnym** klientom (bez zamówień anulowanych)? Wyświetl nazwę i liczbę klientów, od największej.

**➜ Zapisz:** ilu jest takich producentów i kto jest na 1. miejscu.

<details><summary>Podpowiedź</summary>

`producenci` → `produkty` → `pozycje_zamowienia` → `zamowienia`; `HAVING COUNT(DISTINCT z.id_klienta) >= 40`.

</details>

### Zadanie 97

Którzy **3 klienci** zaoszczędzili najwięcej na **promocjach**? Oszczędność = (aktualna cena − cena jednostkowa) × ilość, liczona tylko dla pozycji kupionych taniej niż aktualna cena. Wyświetl imię, nazwisko i oszczędność.

**➜ Zapisz:** osobę z 1. miejsca i kwotę.

<details><summary>Podpowiedź</summary>

`klienci` → `zamowienia` → `pozycje_zamowienia` → `produkty`; w `WHERE` `pz.cena_jednostkowa < p.cena`.

</details>

### Zadanie 98

Które produkty kupiło **co najmniej 30 różnych** klientów, a ich średnia cena zakupu (`AVG(cena_jednostkowa)`) była **niższa** niż aktualna cena? Wyświetl nazwę, liczbę klientów, średnią cenę zakupu (2 miejsca) i aktualną cenę.

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

`zamowienia` → `pozycje_zamowienia` → `produkty`. Grupuj po `p.id, p.nazwa, p.cena` — wtedy `p.cena` można użyć w `HAVING`.

</details>

### Zadanie 99

Dla klientów z **Gdańska**, którzy wystawili **co najmniej 3** opinie, wyświetl: imię, nazwisko, liczbę opinii i liczbę zamówień. Posortuj od największej liczby opinii, a przy równej — po nazwisku.

**➜ Zapisz:** ilu jest takich klientów i liczbę opinii oraz zamówień osoby z 1. wiersza.

<details><summary>Podpowiedź</summary>

Dołączasz do klienta **dwie** tabele „wiele” (`opinie` i `zamowienia`), więc każda opinia powtarza się tyle razy, ile klient ma zamówień. Obie liczby licz przez `COUNT(DISTINCT …)` — także w `HAVING`.

</details>

### Zadanie 100

Którzy **3 klienci** kupili najwięcej **różnych** produktów z kategorii **Akcesoria komputerowe** (bez zamówień anulowanych)? Wyświetl imię, nazwisko, liczbę różnych produktów i wydaną na nie kwotę. Przy równej liczbie produktów wyżej jest osoba, która wydała więcej.

**➜ Zapisz:** osobę z 1. miejsca, liczbę produktów i kwotę.

<details><summary>Podpowiedź</summary>

Pięć tabel. Sortowanie po dwóch kolumnach: `ORDER BY Produktow DESC, Wydatki DESC`.

</details>
