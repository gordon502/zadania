# Zestaw treningowy 1 — zapytania SELECT (przed sprawdzianem)

**Baza:** `sklep` (sklep internetowy) | **Narzędzie:** phpMyAdmin → baza `sklep` → zakładka **SQL**
**Odpowiedzi:** plik `Zestaw treningowy 1 - odpowiedzi.md` — zaglądaj dopiero **po** rozwiązaniu zadania.

Na sprawdzianie będzie **ta sama baza** i około 30 zadań podobnych do tych — ale z innymi pytaniami
i innymi wartościami. Odpowiedzi nie da się wyczytać z tabel „na oko”: trzeba napisać zapytanie.
Zadania są ułożone **od najłatwiejszych do najtrudniejszych**, tematy są wymieszane — tak jak na sprawdzianie.
Chcesz poćwiczyć więcej? Na tej samej bazie jest też `Zestaw treningowy 2 - zadania.md` — z innymi zadaniami.

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

Wyświetl całą zawartość tabeli `kategorie`.

**➜ Zapisz:** ile jest kategorii.

<details><summary>Podpowiedź</summary>

`SELECT * FROM …;` — liczbę wierszy odczytasz z komunikatu nad wynikiem.

</details>

### Zadanie 2

Wyświetl nazwy i ceny wszystkich produktów, od najdroższego do najtańszego.

**➜ Zapisz:** nazwę najdroższego produktu i jego cenę.

<details><summary>Podpowiedź</summary>

Sortowanie malejące: `ORDER BY cena DESC`.

</details>

### Zadanie 3

Wyświetl imiona i nazwiska klientów, którzy mieszkają w **Krakowie**.

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

Tekst w warunku zapisujemy w apostrofach: `WHERE miasto = '…'`.

</details>

### Zadanie 4

Policz funkcją `COUNT` wszystkie zamówienia w sklepie. Nadaj kolumnie nagłówek `LiczbaZamowien`.

**➜ Zapisz:** liczbę zamówień.

<details><summary>Podpowiedź</summary>

`SELECT COUNT(*) AS … FROM …;`

</details>

### Zadanie 5

Wyświetl nazwy produktów, których **nie ma w magazynie** (stan magazynowy równy 0).

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

Kolumna `stan_magazynowy` w tabeli `produkty`.

</details>

### Zadanie 6

Z jakich krajów pochodzą producenci? Każdy kraj ma się pojawić **tylko raz**, w kolejności alfabetycznej.

**➜ Zapisz:** ile jest różnych krajów i który jest pierwszy na liście.

<details><summary>Podpowiedź</summary>

`SELECT DISTINCT kolumna FROM … ORDER BY kolumna;`

</details>

### Zadanie 7

Wyświetl nazwy i ceny **5 najtańszych** produktów.

**➜ Zapisz:** nazwę i cenę **piątego** produktu na liście.

<details><summary>Podpowiedź</summary>

Sortuj rosnąco po cenie i ogranicz wynik: `LIMIT 5`.

</details>

### Zadanie 8

Wyświetl imiona, nazwiska i e-maile klientów, którzy **nie podali numeru telefonu**.

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

Brak wartości to `NULL`. Uwaga: `= NULL` nie działa — potrzebny jest specjalny operator.

</details>

### Zadanie 9

Wyświetl wszystkie produkty, których nazwa **zaczyna się** od słowa `Laptop`.

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

`LIKE` i znak `%` (dowolny ciąg znaków) na końcu wzorca.

</details>

### Zadanie 10

Wyświetl zamówienia złożone w **listopadzie 2025** roku (od 1 do 30 listopada).

**➜ Zapisz:** ile było takich zamówień.

<details><summary>Podpowiedź</summary>

Daty zapisujemy jako tekst w formacie `'RRRR-MM-DD'`. Przyda się `BETWEEN … AND …`.

</details>

### Zadanie 11

Wyświetl nazwy i ceny produktów, które kosztują **od 100 do 500 zł włącznie**.

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

`BETWEEN` obejmuje obie granice.

</details>

### Zadanie 12

Wyświetl imiona, nazwiska i miasta klientów z **Gdańska, Gdyni lub Sopotu**.

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

Zamiast trzech warunków połączonych `OR` możesz użyć `IN ('…', '…', '…')`.

</details>

### Zadanie 13

Wyświetl zamówienia, które zostały **anulowane** i były opłacane **BLIK-iem**.

**➜ Zapisz:** ile jest takich zamówień.

<details><summary>Podpowiedź</summary>

Dwa warunki połączone `AND`. Wartości w kolumnach `status` i `sposob_platnosci` są pisane małymi literami bez polskich znaków.

</details>

### Zadanie 14

Wyświetl imiona, nazwiska i e-maile klientów, którzy mają skrzynkę w domenie **gmail.com**.

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

Adres kończy się na `@gmail.com` — znak `%` stawiamy na **początku** wzorca.

</details>

### Zadanie 15

Wyświetl produkty, które są **w promocji** (mają wpisaną cenę promocyjną): nazwę, cenę i cenę promocyjną. Posortuj alfabetycznie po nazwie.

**➜ Zapisz:** ile jest takich produktów i który jest pierwszy na liście.

<details><summary>Podpowiedź</summary>

Produkt bez promocji ma w kolumnie `cena_promocyjna` wartość `NULL`.

</details>

### Zadanie 16

Kto jest **najstarszym** klientem sklepu? Wyświetl imię, nazwisko i datę urodzenia.

**➜ Zapisz:** imię, nazwisko i datę urodzenia.

<details><summary>Podpowiedź</summary>

Najstarszy = urodzony **najwcześniej**, czyli najmniejsza data.

</details>

### Zadanie 17

Wyświetl listę miast, w których mieszkają klienci — każde miasto raz, w odwrotnej kolejności alfabetycznej (od Z do A).

**➜ Zapisz:** ile jest miast i które jest pierwsze na liście.

<details><summary>Podpowiedź</summary>

`DISTINCT` + `ORDER BY … DESC`.

</details>

### Zadanie 18

Jaka jest **średnia ocena** ze wszystkich opinii w sklepie?

**➜ Zapisz:** średnią ocenę (wystarczą 2 miejsca po przecinku).

<details><summary>Podpowiedź</summary>

Funkcja `AVG(kolumna)` w tabeli `opinie`.

</details>

### Zadanie 19

Wyświetl nazwy, ceny i stany magazynowe produktów, które kosztują **więcej niż 1000 zł**, a w magazynie jest ich **mniej niż 20** sztuk.

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

Dwa warunki z operatorami `>` i `<`, połączone `AND`.

</details>

### Zadanie 20

Ile opinii zawiera **samą ocenę**, bez żadnego komentarza (treść jest pusta, czyli `NULL`)?

**➜ Zapisz:** liczbę takich opinii.

<details><summary>Podpowiedź</summary>

`COUNT(*)` z warunkiem `WHERE … IS NULL`.

</details>

---

## ★★ Poziom 2 · Funkcje, grupowanie i pierwsze złączenia

### Zadanie 21

Dla klientów z **Lublina** wyświetl jedną kolumnę o nazwie `Klient`, zawierającą imię i nazwisko oddzielone spacją. Posortuj alfabetycznie po nazwisku, a przy takim samym nazwisku — po imieniu.

**➜ Zapisz:** pierwszy wiersz wyniku i liczbę wierszy.

<details><summary>Podpowiedź</summary>

`CONCAT(imie, ' ', nazwisko) AS Klient`. Sortować można po kolumnach, których nie wyświetlamy.

</details>

### Zadanie 22

Ilu klientów mieszka w **każdym** mieście? Posortuj od miasta z największą liczbą klientów.

**➜ Zapisz:** miasto, które jest na drugim miejscu, i liczbę jego klientów.

<details><summary>Podpowiedź</summary>

`SELECT miasto, COUNT(*) … GROUP BY miasto ORDER BY … DESC`.

</details>

### Zadanie 23

Wyświetl nazwę produktu, jego cenę i **nazwę kategorii** dla produktów droższych niż **5000 zł**. Posortuj od najdroższego.

**➜ Zapisz:** ile jest takich produktów i do jakiej kategorii należy najdroższy z nich.

<details><summary>Podpowiedź</summary>

Łączysz `produkty` z `kategorie`: `JOIN kategorie ON produkty.id_kategorii = kategorie.id`.

</details>

### Zadanie 24

Ile zamówień ma **każdy status** (nowe, opłacone, …)?

**➜ Zapisz:** ile jest zamówień anulowanych.

<details><summary>Podpowiedź</summary>

Grupujemy po kolumnie `status`.

</details>

### Zadanie 25

Dla produktów w promocji wyświetl nazwę i **kwotę obniżki** (cena minus cena promocyjna) jako kolumnę `Obnizka`. Posortuj od największej obniżki.

**➜ Zapisz:** produkt z największą obniżką i kwotę tej obniżki.

<details><summary>Podpowiedź</summary>

W `SELECT` można odejmować kolumny: `cena - cena_promocyjna AS Obnizka`. Nie zapomnij o warunku na promocję.

</details>

### Zadanie 26

Ilu **różnych** klientów złożyło przynajmniej jedno zamówienie?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

W tabeli `zamowienia` ten sam klient występuje wiele razy. `COUNT(DISTINCT id_klienta)`.

</details>

### Zadanie 27

Ilu klientów urodziło się w roku **2000 lub później**? Użyj funkcji `YEAR`.

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

`YEAR(data_urodzenia)` zwraca sam rok jako liczbę.

</details>

### Zadanie 28

Sklep wyświetla listę produktów posortowaną **alfabetycznie**, po **20 produktów na stronie**. Wyświetl produkty z **3. strony**.

**➜ Zapisz:** nazwę pierwszego produktu na 3. stronie.

<details><summary>Podpowiedź</summary>

Strona 1 to wiersze 1–20, strona 2 to 21–40. Ile wierszy trzeba pominąć? `LIMIT … OFFSET …`.

</details>

### Zadanie 29

Wyświetl nazwy i ceny produktów marki **Apple**. Nie sprawdzaj wcześniej, jaki numer `id` ma Apple — połącz tabele i filtruj po **nazwie** producenta. Posortuj od najtańszego.

**➜ Zapisz:** ile jest takich produktów i który jest najtańszy.

<details><summary>Podpowiedź</summary>

`produkty` + `producenci`, warunek `WHERE pr.nazwa = 'Apple'`.

</details>

### Zadanie 30

Dla każdego **sposobu dostawy** podaj liczbę zamówień oraz średni koszt dostawy zaokrąglony do 2 miejsc po przecinku.

**➜ Zapisz:** średni koszt dostawy kurierem.

<details><summary>Podpowiedź</summary>

`ROUND(AVG(koszt_dostawy), 2)`, grupowanie po `sposob_dostawy`.

</details>

### Zadanie 31

Ile jest opinii z każdą oceną (1, 2, 3, 4, 5)? Posortuj według oceny rosnąco.

**➜ Zapisz:** ile jest opinii z oceną 5.

<details><summary>Podpowiedź</summary>

Grupujemy po kolumnie `ocena`.

</details>

### Zadanie 32

Wyświetl numery (`id_klienta`) klientów, którzy złożyli **co najmniej 20** zamówień, i liczbę ich zamówień.

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

Warunek dotyczący `COUNT(*)` piszemy w `HAVING`, nie w `WHERE`.

</details>

### Zadanie 33

Dla każdego produktu oblicz **wartość towaru w magazynie** (cena × stan magazynowy) jako kolumnę `WartoscMagazynu`. Posortuj od największej.

**➜ Zapisz:** produkt z największą wartością towaru w magazynie i tę wartość.

<details><summary>Podpowiedź</summary>

Mnożenie kolumn w `SELECT`, sortowanie po aliasie.

</details>

### Zadanie 34

Ile zamówień złożono w **grudniu** (w dowolnym roku)?

**➜ Zapisz:** liczbę zamówień.

<details><summary>Podpowiedź</summary>

`MONTH(data)` zwraca numer miesiąca (1–12).

</details>

### Zadanie 35

Wyświetl wszystkie zamówienia klientów z **Zakopanego**: imię, nazwisko, datę zamówienia i status. Posortuj od najstarszego zamówienia.

**➜ Zapisz:** ile jest takich zamówień i jaki status ma najnowsze z nich.

<details><summary>Podpowiedź</summary>

`klienci` + `zamowienia` (`zamowienia.id_klienta = klienci.id`).

</details>

### Zadanie 36

Ile **sztuk** produktów łącznie sprzedał sklep (wszystkie pozycje wszystkich zamówień)?

**➜ Zapisz:** liczbę sztuk.

<details><summary>Podpowiedź</summary>

Liczba sztuk jest w kolumnie `ilosc` tabeli `pozycje_zamowienia`. Liczba **wierszy** to coś innego!

</details>

### Zadanie 37

Jednym zapytaniem wyświetl datę **pierwszego** i **ostatniego** zamówienia w sklepie.

**➜ Zapisz:** obie daty.

<details><summary>Podpowiedź</summary>

`MIN(…)` i `MAX(…)` działają także na datach.

</details>

### Zadanie 38

Ile klientek ma nazwisko kończące się na **-ska** (np. Kowalska)?

**➜ Zapisz:** liczbę klientek.

<details><summary>Podpowiedź</summary>

`LIKE '%ska'` — znak `%` tylko na początku.

</details>

### Zadanie 39

Ile zamówień złożono w każdym roku?

**➜ Zapisz:** liczbę zamówień z roku 2025.

<details><summary>Podpowiedź</summary>

Grupować można po wyniku funkcji: `GROUP BY YEAR(data_zamowienia)`.

</details>

### Zadanie 40

Wyświetl opinie z oceną **1**: nazwę produktu, treść opinii i datę. Posortuj od najnowszej opinii.

**➜ Zapisz:** ile jest takich opinii i jakiego produktu dotyczy najnowsza.

<details><summary>Podpowiedź</summary>

`opinie` + `produkty`, warunek na `ocena`.

</details>

### Zadanie 41

Które miasta mają **co najmniej 10** klientów? Wyświetl miasto i liczbę klientów.

**➜ Zapisz:** ile jest takich miast.

<details><summary>Podpowiedź</summary>

`GROUP BY miasto HAVING COUNT(*) >= 10`.

</details>

### Zadanie 42

Z ilu **różnych** miast pochodzą klienci zapisani na newsletter (kolumna `newsletter` = `'T'`)?

**➜ Zapisz:** liczbę miast.

<details><summary>Podpowiedź</summary>

`COUNT(DISTINCT miasto)` z warunkiem w `WHERE`.

</details>

### Zadanie 43

Jednym zapytaniem wyświetl: najniższą cenę, najwyższą cenę i średnią cenę produktów (średnia zaokrąglona do 2 miejsc).

**➜ Zapisz:** średnią cenę produktu.

<details><summary>Podpowiedź</summary>

Trzy funkcje agregujące w jednym `SELECT`.

</details>

### Zadanie 44

Wyświetl nazwy i ceny książek (kategoria **Książki**), które kosztują **mniej niż 50 zł**. Posortuj od najtańszej.

**➜ Zapisz:** ile jest takich książek i która jest najtańsza.

<details><summary>Podpowiedź</summary>

`produkty` + `kategorie`, dwa warunki w `WHERE`.

</details>

### Zadanie 45

Ilu klientów zarejestrowało się w sklepie w roku **2024**?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

`YEAR(data_rejestracji) = 2024` albo `BETWEEN '2024-01-01' AND '2024-12-31'`.

</details>

---

## ★★★ Poziom 3 · Złączenia z grupowaniem

### Zadanie 46

Ile produktów jest w każdej kategorii? W wyniku ma być **nazwa** kategorii. Posortuj od największej liczby.

**➜ Zapisz:** kategorię z największą liczbą produktów, tę liczbę oraz liczbę wierszy wyniku.

<details><summary>Podpowiedź</summary>

`JOIN` + `GROUP BY kat.nazwa`. Porównaj liczbę wierszy z liczbą kategorii z zadania 1.

</details>

### Zadanie 47

Dla każdego producenta **z Polski** podaj średnią cenę jego produktów (zaokrągloną do 2 miejsc). Posortuj od najwyższej średniej.

**➜ Zapisz:** producenta z najwyższą średnią ceną i tę średnią.

<details><summary>Podpowiedź</summary>

Warunek na kraj w `WHERE` (przed grupowaniem), potem `GROUP BY pr.nazwa`.

</details>

### Zadanie 48

Ile sztuk każdego produktu sprzedano? Wyświetl nazwę produktu i liczbę sztuk. Pokaż tylko **3 najlepiej sprzedające się** produkty.

**➜ Zapisz:** nazwę produktu z 3. miejsca i liczbę sztuk.

<details><summary>Podpowiedź</summary>

`pozycje_zamowienia` + `produkty`, `SUM(pz.ilosc)`, `ORDER BY … DESC LIMIT 3`.

</details>

### Zadanie 49

Jaka jest **wartość towarów** w zamówieniu nr **1000**? Wartość pozycji = ilość × cena jednostkowa.

**➜ Zapisz:** wartość zamówienia.

<details><summary>Podpowiedź</summary>

Wszystko jest w tabeli `pozycje_zamowienia`: `SUM(ilosc * cena_jednostkowa)`.

</details>

### Zadanie 50

Zapisz zapytanie **w stylu egzaminu INF.03**: tabele po przecinku w `FROM`, warunek łączenia w `WHERE`. Wyświetl nazwę produktu i nazwę producenta dla producentów z **Japonii**. Posortuj alfabetycznie po nazwie produktu.

**➜ Zapisz:** ile jest takich produktów i który jest pierwszy na liście.

<details><summary>Podpowiedź</summary>

`FROM produkty, producenci WHERE produkty.id_producenta = producenci.id AND …`.

</details>

### Zadanie 51

Popraw zadanie 46 tak, żeby w wyniku były **wszystkie** kategorie, a kategoria bez produktów miała liczbę **0**.

**➜ Zapisz:** nazwę kategorii, która ma 0 produktów, i liczbę wierszy wyniku.

<details><summary>Podpowiedź</summary>

Zacznij od tabeli `kategorie` i użyj `LEFT JOIN produkty`. Licz `COUNT(p.id)`, a nie `COUNT(*)`.

</details>

### Zadanie 52

Jakie produkty zamówiono w **Wigilię 2025** (24 grudnia 2025)? Wyświetl nazwy produktów **bez powtórzeń**, alfabetycznie.

**➜ Zapisz:** ile jest różnych produktów.

<details><summary>Podpowiedź</summary>

`zamowienia` → `pozycje_zamowienia` → `produkty` (dwa `JOIN`-y). Data jest w `zamowienia`, nazwa w `produkty`.

</details>

### Zadanie 53

Którzy producenci mają w ofercie **co najmniej 8** produktów? Wyświetl nazwę producenta i liczbę produktów.

**➜ Zapisz:** nazwy tych producentów.

<details><summary>Podpowiedź</summary>

`HAVING COUNT(*) >= 8` po `GROUP BY pr.nazwa`.

</details>

### Zadanie 54

Ile zamówień złożono w każdym miesiącu **2026** roku? Posortuj od miesiąca z największą liczbą zamówień.

**➜ Zapisz:** numer miesiąca rekordowego i liczbę zamówień w nim.

<details><summary>Podpowiedź</summary>

Filtr roku w `WHERE`, grupowanie po `MONTH(data_zamowienia)`.

</details>

### Zadanie 55

Ile zamówień złożył każdy klient z **Bydgoszczy**? Wyświetl imię, nazwisko i liczbę zamówień, od największej.

**➜ Zapisz:** klienta z największą liczbą zamówień i tę liczbę.

<details><summary>Podpowiedź</summary>

Grupuj po `k.id` i dopisz `k.imie, k.nazwisko` — dwie różne osoby mogą się tak samo nazywać.

</details>

### Zadanie 56

Ile zamówień wysłanych **kurierem** i opłaconych **kartą** miało **darmową dostawę** (koszt 0)?

**➜ Zapisz:** liczbę zamówień.

<details><summary>Podpowiedź</summary>

Jedna tabela, trzy warunki połączone `AND`.

</details>

### Zadanie 57

Jaki był **przychód** sklepu (wartość sprzedanych towarów, bez kosztów dostawy) w każdym roku? Nie licz zamówień **anulowanych**.

**➜ Zapisz:** przychód w roku 2025.

<details><summary>Podpowiedź</summary>

`zamowienia` + `pozycje_zamowienia`; `SUM(pz.ilosc * pz.cena_jednostkowa)`; status w `WHERE`.

</details>

### Zadanie 58

Ile zamówień przypada na każdą parę **sposób dostawy + sposób płatności**? Posortuj od najczęstszej pary.

**➜ Zapisz:** najczęstszą parę i liczbę zamówień.

<details><summary>Podpowiedź</summary>

`GROUP BY sposob_dostawy, sposob_platnosci`.

</details>

### Zadanie 59

Dla każdego produktu z kategorii **Laptopy** podaj średnią ocenę (2 miejsca po przecinku) i liczbę opinii. Posortuj od najwyższej średniej, a przy równej średniej — od większej liczby opinii.

**➜ Zapisz:** laptop, który jest na 1. miejscu, jego średnią i liczbę opinii.

<details><summary>Podpowiedź</summary>

`opinie` + `produkty` + `kategorie`, grupowanie po produkcie. Sortowanie po dwóch kolumnach: `ORDER BY Srednia DESC, Opinii DESC`.

</details>

### Zadanie 60

Które produkty mają **co najmniej 15 opinii** i średnią ocenę **co najmniej 4.0**? Wyświetl nazwę, liczbę opinii i średnią (2 miejsca).

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

Oba warunki dotyczą funkcji agregujących, więc oba idą do `HAVING` (połączone `AND`).

</details>

### Zadanie 61

Którzy producenci **nie mają żadnego** produktu w sklepie?

**➜ Zapisz:** nazwę producenta (lub nazwy).

<details><summary>Podpowiedź</summary>

Wzór: `FROM producenci pr LEFT JOIN produkty p ON … WHERE p.id IS NULL`.

</details>

### Zadanie 62

Którzy klienci **nie złożyli żadnego** zamówienia? Wyświetl imię, nazwisko i datę rejestracji.

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

`klienci` `LEFT JOIN zamowienia` i szukamy wierszy, w których strona zamówień jest pusta.

</details>

### Zadanie 63

Kto wystawił **najwięcej opinii**? Wyświetl imię, nazwisko, miasto i liczbę opinii.

**➜ Zapisz:** imię i nazwisko tej osoby oraz liczbę jej opinii.

<details><summary>Podpowiedź</summary>

`opinie` + `klienci`, `GROUP BY k.id`, sortowanie malejąco i `LIMIT 1`.

</details>

### Zadanie 64

W ilu **zamówieniach** pojawiła się `Żarówka Philips LED E27` i ile **sztuk** łącznie sprzedano?

**➜ Zapisz:** obie liczby.

<details><summary>Podpowiedź</summary>

`pozycje_zamowienia` + `produkty`, w jednym `SELECT`: `COUNT(*)` i `SUM(pz.ilosc)`.

</details>

### Zadanie 65

Jaka jest średnia ocena produktów każdego **producenta**? Pokaż tylko producentów, którzy mają **co najmniej 30 opinii**. Wyświetl nazwę producenta, liczbę opinii i średnią (2 miejsca), od najwyższej średniej.

**➜ Zapisz:** producenta z najwyższą średnią i tę średnią.

<details><summary>Podpowiedź</summary>

`opinie` → `produkty` → `producenci`.

</details>

### Zadanie 66

Jaka jest cena **najdroższego** produktu w każdej kategorii? Wyświetl nazwę kategorii i cenę.

**➜ Zapisz:** cenę najdroższego produktu w kategorii **Sport**.

<details><summary>Podpowiedź</summary>

`MAX(p.cena)` z grupowaniem po nazwie kategorii.

</details>

### Zadanie 67

Klienci z których miast złożyli **najwięcej zamówień**? Wyświetl miasto i liczbę zamówień, tylko **3 pierwsze** miasta.

**➜ Zapisz:** miasto z 3. miejsca i liczbę zamówień.

<details><summary>Podpowiedź</summary>

`klienci` + `zamowienia`, grupowanie po `k.miasto`.

</details>

### Zadanie 68

Ile zamówień zostało złożonych **w dniu rejestracji** klienta (data zamówienia = data rejestracji)?

**➜ Zapisz:** liczbę takich zamówień.

<details><summary>Podpowiedź</summary>

Po połączeniu `klienci` i `zamowienia` w `WHERE` można porównać ze sobą dwie kolumny.

</details>

### Zadanie 69

Ile pozycji zamówień zostało kupionych **taniej niż aktualna cena** produktu (cena jednostkowa w pozycji mniejsza niż `produkty.cena`)?

**➜ Zapisz:** liczbę takich pozycji.

<details><summary>Podpowiedź</summary>

`pozycje_zamowienia` + `produkty`, warunek `pz.cena_jednostkowa < p.cena`.

</details>

### Zadanie 70

Zapisz zapytanie **w stylu egzaminu** (tabele po przecinku, warunki łączenia w `WHERE`): wyświetl imię i nazwisko klienta oraz nazwę produktu dla opinii z oceną **5** wystawionych w **październiku 2026**. Posortuj po nazwisku klienta.

**➜ Zapisz:** liczbę wierszy wyniku.

<details><summary>Podpowiedź</summary>

Trzy tabele po przecinku: `opinie, klienci, produkty`. W `WHERE` potrzebne są **dwa** warunki łączenia i dwa warunki filtrujące, wszystkie połączone `AND`.

</details>

---

## ★★★★ Poziom 4 · Kilka tabel, raporty i LEFT JOIN

### Zadanie 71

Wyświetl wszystko, co kupili klienci z **Opola**: imię, nazwisko, datę zamówienia, nazwę produktu i ilość. Posortuj od najstarszego zamówienia, a w ramach zamówienia — po nazwie produktu.

**➜ Zapisz:** liczbę wierszy wyniku i nazwę produktu w **ostatnim** wierszu.

<details><summary>Podpowiedź</summary>

`klienci` → `zamowienia` → `pozycje_zamowienia` → `produkty` (trzy `JOIN`-y).

</details>

### Zadanie 72

Którzy **3 klienci wydali najwięcej**? Wyświetl imię, nazwisko, miasto i łączną wartość zakupów. Nie licz zamówień anulowanych.

**➜ Zapisz:** klienta z 1. miejsca i kwotę.

<details><summary>Podpowiedź</summary>

`klienci` → `zamowienia` → `pozycje_zamowienia`; `SUM(pz.ilosc * pz.cena_jednostkowa)`; grupuj po `k.id`.

</details>

### Zadanie 73

Jaki przychód przyniosła każda **kategoria**? Wyświetl nazwę kategorii i przychód, od największego. Nie licz zamówień anulowanych.

**➜ Zapisz:** kategorię z największym przychodem i kwotę.

<details><summary>Podpowiedź</summary>

Potrzebne są: `kategorie`, `produkty`, `pozycje_zamowienia` i `zamowienia` (status).

</details>

### Zadanie 74

W bazie są **dwie różne** klientki o imieniu i nazwisku **Anna Nowak**. Dla każdej z nich osobno podaj miasto i łączną wartość zakupów (bez zamówień anulowanych).

**➜ Zapisz:** obie kwoty wraz z miastami.

<details><summary>Podpowiedź</summary>

Grupowanie po `k.imie, k.nazwisko` sklei obie osoby w jeden wiersz. Grupuj po `k.id`.

</details>

### Zadanie 75

Dla **każdego** produktu z kategorii **Smartfony** podaj liczbę opinii — także jeśli wynosi **0**. Posortuj od najmniejszej liczby opinii.

**➜ Zapisz:** ile smartfonów nie ma żadnej opinii.

<details><summary>Podpowiedź</summary>

`produkty` + `kategorie` (zwykły `JOIN`) i `LEFT JOIN opinie`. Licz `COUNT(o.id)`.

</details>

### Zadanie 76

Ilu **różnych** klientów kupiło coś z kategorii **Laptopy**? Nie licz zamówień anulowanych.

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

Pięć tabel: `klienci` (albo samo `zamowienia.id_klienta`), `zamowienia`, `pozycje_zamowienia`, `produkty`, `kategorie`. `COUNT(DISTINCT …)` — ten sam klient mógł kupić kilka laptopów.

</details>

### Zadanie 77

Którzy klienci wydali łącznie **ponad 15 000 zł** (bez zamówień anulowanych)? Wyświetl imię, nazwisko i kwotę, od największej.

**➜ Zapisz:** ilu jest takich klientów.

<details><summary>Podpowiedź</summary>

Jak w zadaniu 72, ale zamiast `LIMIT` — warunek w `HAVING`.

</details>

### Zadanie 78

Dla każdego zamówienia złożonego **24 grudnia 2025** wyświetl: numer zamówienia, wartość towarów, koszt dostawy i kwotę **do zapłaty** (towary + dostawa). Posortuj od najwyższej kwoty do zapłaty.

**➜ Zapisz:** numer zamówienia z najwyższą kwotą do zapłaty i tę kwotę.

<details><summary>Podpowiedź</summary>

Grupuj po `z.id`. Kwota do zapłaty: `SUM(pz.ilosc * pz.cena_jednostkowa) + z.koszt_dostawy` — dostawę dodajemy **raz**, poza `SUM`.

</details>

### Zadanie 79

Które produkty **nigdy nie zostały zamówione**? Wyświetl nazwę i datę dodania do sklepu.

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

`produkty` `LEFT JOIN pozycje_zamowienia` … `IS NULL`.

</details>

### Zadanie 80

Które produkty **nie mają żadnej opinii**? Wyświetl nazwę produktu i nazwę kategorii, posortuj po kategorii i nazwie.

**➜ Zapisz:** ile jest takich produktów.

<details><summary>Podpowiedź</summary>

`produkty` + `kategorie` (`JOIN`) i `LEFT JOIN opinie` z warunkiem `o.id IS NULL`.

</details>

### Zadanie 81

W których miesiącach **2025** roku przychód (bez zamówień anulowanych) przekroczył **70 000 zł**? Wyświetl numer miesiąca i przychód.

**➜ Zapisz:** numery tych miesięcy.

<details><summary>Podpowiedź</summary>

Rok w `WHERE`, grupowanie po `MONTH(…)`, próg w `HAVING`.

</details>

### Zadanie 82

Ile **sztuk** produktów sprzedano dla każdego **kraju pochodzenia producenta**? Posortuj od największej liczby.

**➜ Zapisz:** kraj z 1. miejsca i liczbę sztuk.

<details><summary>Podpowiedź</summary>

`pozycje_zamowienia` → `produkty` → `producenci`, `GROUP BY pr.kraj`.

</details>

### Zadanie 83

Ilu **różnych** klientów kupiło klocki marki **Lego**? Nie licz zamówień anulowanych.

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

`zamowienia` → `pozycje_zamowienia` → `produkty` → `producenci`, `COUNT(DISTINCT z.id_klienta)`.

</details>

### Zadanie 84

Jaki sposób dostawy wybierali **najczęściej** klienci z **Warszawy**? Wyświetl sposób dostawy i liczbę zamówień.

**➜ Zapisz:** sposób dostawy i liczbę zamówień.

<details><summary>Podpowiedź</summary>

`klienci` + `zamowienia`, warunek na miasto, `GROUP BY z.sposob_dostawy`.

</details>

### Zadanie 85

Ile zamówień zawierało **co najmniej 4 różne** produkty? Najpierw wyświetl numery tych zamówień i liczbę produktów, potem odczytaj liczbę wierszy.

**➜ Zapisz:** liczbę takich zamówień.

<details><summary>Podpowiedź</summary>

Jedna tabela: `pozycje_zamowienia`. Każdy wiersz to inny produkt w zamówieniu. `GROUP BY id_zamowienia HAVING …`.

</details>

### Zadanie 86

Jaka jest średnia ocena produktów w każdej **kategorii** (2 miejsca po przecinku)? Posortuj od najwyższej.

**➜ Zapisz:** kategorię z najniższą średnią i tę średnią.

<details><summary>Podpowiedź</summary>

`opinie` → `produkty` → `kategorie`. Najniższa średnia będzie na końcu listy.

</details>

### Zadanie 87

Który produkt przyniósł **największy przychód w 2026** roku (bez zamówień anulowanych)? Wyświetl nazwę i przychód.

**➜ Zapisz:** nazwę produktu i kwotę.

<details><summary>Podpowiedź</summary>

`produkty` + `pozycje_zamowienia` + `zamowienia`, `ORDER BY … DESC LIMIT 1`.

</details>

### Zadanie 88

Ilu klientów zapisanych na **newsletter** nie złożyło **żadnego** zamówienia?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

Jak w zadaniu 62, z dodatkowym warunkiem na kolumnę z tabeli `klienci` (lewej).

</details>

### Zadanie 89

Dla każdego producenta z **Polski** podaj **liczbę produktów** w ofercie i **liczbę sprzedanych sztuk**. Uwzględnij tylko produkty, które sprzedały się chociaż raz.

**➜ Zapisz:** liczbę produktów i liczbę sztuk dla producenta **Helion**.

<details><summary>Podpowiedź</summary>

Po dołączeniu `pozycje_zamowienia` każdy produkt występuje tyle razy, ile razy był kupiony. Produkty policz przez `COUNT(DISTINCT p.id)`.

</details>

---

## ★★★★★ Poziom 5 · Poziom egzaminacyjny

### Zadanie 90

**Raport kategorii.** Dla każdej kategorii, w której coś sprzedano (bez zamówień anulowanych), wyświetl w jednym wierszu: nazwę kategorii, liczbę **różnych** sprzedanych produktów, liczbę sprzedanych sztuk i przychód. Posortuj od największego przychodu.

**➜ Zapisz:** dane z wiersza dla kategorii **Książki**.

<details><summary>Podpowiedź</summary>

Cztery tabele jak w zadaniu 73. Trzy funkcje agregujące w jednym `SELECT`: `COUNT(DISTINCT …)`, `SUM(…)`, `SUM(… * …)`.

</details>

### Zadanie 91

Dla **każdej** z 11 kategorii podaj: liczbę produktów oraz w ilu **pozycjach zamówień** pojawiły się produkty tej kategorii. Kategoria bez produktów ma mieć w obu kolumnach **0**. Posortuj od najmniejszej liczby pozycji.

**➜ Zapisz:** liczbę wierszy wyniku oraz obie liczby dla kategorii **Laptopy**.

<details><summary>Podpowiedź</summary>

`kategorie` `LEFT JOIN produkty` `LEFT JOIN pozycje_zamowienia` — **oba** złączenia muszą być `LEFT`. Po doklejeniu pozycji każdy produkt powtarza się tyle razy, ile razy go kupiono, więc produkty licz przez `COUNT(DISTINCT p.id)`, a pozycje przez `COUNT(pz.id_zamowienia)`.

</details>

### Zadanie 92

**Raport miesięczny 2026.** Dla każdego miesiąca 2026 roku wyświetl: numer miesiąca, liczbę zamówień, liczbę **różnych** klientów i przychód (bez zamówień anulowanych). Pokaż tylko miesiące z przychodem **powyżej 40 000 zł**. Posortuj po numerze miesiąca.

**➜ Zapisz:** ile miesięcy jest w wyniku oraz liczbę zamówień i liczbę klientów we wrześniu (miesiąc 9).

<details><summary>Podpowiedź</summary>

`zamowienia` + `pozycje_zamowienia`. Po złączeniu jedno zamówienie występuje kilka razy — zamówienia i klientów licz przez `COUNT(DISTINCT …)`.

</details>

### Zadanie 93

Wyświetl opinie z oceną **1**, które mają treść: imię i nazwisko klienta, nazwę produktu, treść i datę opinii. Posortuj od najstarszej opinii.

**➜ Zapisz:** liczbę wierszy i nazwisko autora pierwszej opinii.

<details><summary>Podpowiedź</summary>

`opinie` + `klienci` + `produkty`. Dwa warunki: ocena i `tresc IS NOT NULL`.

</details>

### Zadanie 94

Ilu klientów składało zamówienia **zarówno w 2025, jak i w 2026** roku?

**➜ Zapisz:** liczbę klientów.

<details><summary>Podpowiedź</summary>

Dla każdego klienta policz, w ilu **różnych latach** zamawiał: `COUNT(DISTINCT YEAR(data_zamowienia))`. Interesują nas ci, u których wynik = 2. Liczbę klientów odczytasz z liczby wierszy.

</details>

### Zadanie 95

Którzy klienci kupili produkty z **co najmniej 8 różnych kategorii**? Wyświetl imię, nazwisko i liczbę kategorii, od największej.

**➜ Zapisz:** ilu jest takich klientów i ilu z nich kupiło coś ze **wszystkich 10** kategorii, które mają produkty.

<details><summary>Podpowiedź</summary>

`klienci` → `zamowienia` → `pozycje_zamowienia` → `produkty`. Kategorie liczysz przez `COUNT(DISTINCT p.id_kategorii)` — nazwa kategorii nie jest potrzebna.

</details>

### Zadanie 96

Klienci z którego **miasta** wydali najwięcej w **2026** roku (bez zamówień anulowanych)? Wyświetl 3 pierwsze miasta i kwoty.

**➜ Zapisz:** miasto z 1. miejsca i kwotę.

<details><summary>Podpowiedź</summary>

`klienci` → `zamowienia` → `pozycje_zamowienia`, grupowanie po `k.miasto`.

</details>

### Zadanie 97

Które produkty były kupowane w **promocji** (cena jednostkowa niższa niż aktualna cena) w **co najmniej 15 pozycjach** zamówień? Dla każdego podaj liczbę takich pozycji oraz łączną kwotę, jaką klienci **zaoszczędzili** (różnica cen × ilość). Posortuj od największej oszczędności.

**➜ Zapisz:** produkt z największą oszczędnością klientów i tę kwotę.

<details><summary>Podpowiedź</summary>

`pozycje_zamowienia` + `produkty`, warunek porównujący ceny w `WHERE`, oszczędność: `SUM((p.cena - pz.cena_jednostkowa) * pz.ilosc)`.

</details>

### Zadanie 98

Którzy producenci mają **co najmniej 20 opinii** o swoich produktach, a średnia ocena tych opinii jest **niższa niż 3.5**? Wyświetl nazwę producenta, kraj, liczbę opinii i średnią (2 miejsca).

**➜ Zapisz:** nazwy tych producentów.

<details><summary>Podpowiedź</summary>

`opinie` → `produkty` → `producenci`; dwa warunki w `HAVING`.

</details>

### Zadanie 99

Dla klientów, którzy złożyli **co najmniej 20 zamówień**, wyświetl: imię, nazwisko, miasto, **liczbę zamówień** i łączną wartość zakupów (wszystkie zamówienia, także anulowane). Posortuj od największej wartości.

**➜ Zapisz:** ilu jest takich klientów oraz liczbę zamówień i wartość dla osoby z 1. miejsca.

<details><summary>Podpowiedź</summary>

Wartość wymaga dołączenia `pozycje_zamowienia` — a wtedy każde zamówienie występuje tyle razy, ile ma pozycji. Zamówienia policz przez `COUNT(DISTINCT z.id)` (także w `HAVING`).

</details>

### Zadanie 100

Którzy **3 klienci wydali najwięcej na książki** (kategoria **Książki**) w całej historii sklepu, nie licząc zamówień anulowanych? Wyświetl imię, nazwisko, liczbę kupionych książek (sztuk) i wydaną kwotę.

**➜ Zapisz:** klienta z 1. miejsca, liczbę książek i kwotę.

<details><summary>Podpowiedź</summary>

Pięć tabel: `klienci` → `zamowienia` → `pozycje_zamowienia` → `produkty` → `kategorie`. To zadanie łączy wszystko, co ćwiczyliśmy.

</details>
