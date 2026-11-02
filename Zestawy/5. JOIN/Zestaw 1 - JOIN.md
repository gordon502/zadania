# Zestaw 4 — Łączenie tabel: `JOIN` i `LEFT JOIN`

**Baza:** `szkola` (plik `szkola.sql`) | **Narzędzie:** XAMPP → phpMyAdmin → zakładka **SQL**
**Materiał pomocniczy:** ściąga „JOIN — łączenie tabel” (część 2 to ściąga do warunków `ON`, na końcu dwie animacje)
**Odpowiedzi:** plik `Zestaw 4 - odpowiedzi.md` — zaglądaj dopiero **po** rozwiązaniu zadania.
**Zakres:** `JOIN … ON`, aliasy tabel, kolumny o tych samych nazwach, łączenie 3–4 tabel, związek N:M,
`JOIN` + `GROUP BY` / `HAVING`, `LEFT JOIN`, szukanie wierszy bez pary (`IS NULL`).

**Tabele w bazie:**

| Tabela | Co zawiera | Klucze obce (do `ON`) |
|---|---|---|
| `uczniowie` | 39 uczniów: `id`, `pesel`, `imie`, `nazwisko`, `id_klasy`, `data_urodzenia`, `email`, `srednia` | `id_klasy` → `klasy.id` |
| `klasy` | 5 klas: `id`, `nazwa` (np. `4TI`), `profil`, `sala`, `id_wychowawcy` | `id_wychowawcy` → `nauczyciele.id` |
| `nauczyciele` | 10 nauczycieli: `id`, `imie`, `nazwisko`, `email` | — |
| `przedmioty` | 10 przedmiotów: `id`, `nazwa`, `godziny_tyg`, `rozszerzony` | — |
| `oceny` | 456 ocen: `id`, `id_ucznia`, `id_przedmiotu`, `ocena`, `waga`, `data_wystawienia` | `id_ucznia` → `uczniowie.id`, `id_przedmiotu` → `przedmioty.id` |
| `kola` | 6 kół zainteresowań: `id`, `nazwa`, `dzien`, `id_opiekuna` | `id_opiekuna` → `nauczyciele.id` |
| `uczniowie_kola` | 52 zapisy (tabela łącząca): `id_ucznia`, `id_kola`, `data_zapisu` | `id_ucznia` → `uczniowie.id`, `id_kola` → `kola.id` |

**Zasady:**
- **nie wpisuj numerów „z głowy”** — jeśli zadanie mówi o klasie 4TI, filtruj po `k.nazwa = '4TI'`, a nie po `id_klasy = 1`. Właśnie po to jest `JOIN`,
- przy łączeniu tabel **zawsze** pisz, z której tabeli jest kolumna (`u.imie`, `k.nazwa`),
- po każdym zapytaniu zapisz w zeszycie **ile wierszy** zwróciło,
- pod każdym zadaniem jest schowana **podpowiedź** — rozwiń ją dopiero wtedy, gdy utkniesz,
- zadania z gwiazdką ⭐ są dla szybszych.

---

## Część I — Dwie tabele

**Zadanie 1.** Wyświetl imię i nazwisko każdego ucznia oraz **nazwę** jego klasy.
> Wzór do zapamiętania:
> ```sql
> SELECT uczniowie.imie, uczniowie.nazwisko, klasy.nazwa
> FROM uczniowie
> JOIN klasy ON uczniowie.id_klasy = klasy.id;
> ```

<details><summary>Podpowiedź</summary>

Przepisz wzór i uruchom. W `ON` łączymy **klucz obcy** (`uczniowie.id_klasy`) z **kluczem głównym** (`klasy.id`).

</details>

**Zadanie 2.** To samo co w zadaniu 1, ale posortowane po nazwie klasy, a w obrębie klasy — po nazwisku.
Która klasa jest pierwsza i kto jest pierwszy na liście?

<details><summary>Podpowiedź</summary>

Dopisz na końcu `ORDER BY` z **dwiema** kolumnami: najpierw nazwa klasy, potem nazwisko.

</details>

**Zadanie 3.** Wyświetl uczniów klasy **4TI** (imię, nazwisko), alfabetycznie. Nie sprawdzaj wcześniej, jaki numer ma 4TI!

<details><summary>Podpowiedź</summary>

Połącz `uczniowie` z `klasy` jak w zadaniu 1 i dopisz `WHERE k.nazwa = '4TI'`. Na końcu `ORDER BY` po nazwisku.

</details>

**Zadanie 4.** Dla każdej klasy wyświetl jej nazwę oraz imię i nazwisko **wychowawcy**. Posortuj po nazwie klasy.

<details><summary>Podpowiedź</summary>

Tabele `klasy` i `nauczyciele`. Warunek `ON` znajdziesz w ściądze (część 2): `klasy.id_wychowawcy = nauczyciele.id`.

</details>

**Zadanie 5.** Wyświetl wszystkie koła zainteresowań: nazwę, dzień tygodnia oraz imię i nazwisko **opiekuna**.

<details><summary>Podpowiedź</summary>

Tabele `kola` i `nauczyciele`, warunek `ON kola.id_opiekuna = nauczyciele.id`.

</details>

**Zadanie 6.** Wyświetl oceny wystawione **30 września 2026**: nazwę przedmiotu, ocenę i wagę.
Posortuj po nazwie przedmiotu.

<details><summary>Podpowiedź</summary>

`oceny` + `przedmioty` (`ON oceny.id_przedmiotu = przedmioty.id`). Datę piszemy w apostrofach: `'2026-09-30'`.

</details>

**Zadanie 7.** Wyświetl uczniów wszystkich klas o profilu **informatycznym** (imię, nazwisko, nazwa klasy).
Posortuj po klasie i nazwisku.

<details><summary>Podpowiedź</summary>

`uczniowie` + `klasy`. Kolumna `profil` jest w tabeli `klasy`. Sortowanie po dwóch kolumnach.

</details>

**Zadanie 8.** Ile wierszy zwraca zapytanie z zadania 1? Porównaj z liczbą wierszy w tabeli `uczniowie`.
Dlaczego te liczby są równe?

<details><summary>Podpowiedź</summary>

Liczbę wierszy w tabeli sprawdzisz przez `SELECT COUNT(*) FROM uczniowie;`. Pomyśl: do ilu klas może należeć jeden uczeń?

</details>

---

## Część II — Aliasy i kolumny o tych samych nazwach

**Zadanie 9.** Przepisz zadanie 4, nadając tabelom aliasy `k` i `n`.

<details><summary>Podpowiedź</summary>

Alias piszesz zaraz po nazwie tabeli: `FROM klasy k`. Potem wszędzie zamiast `klasy.` piszesz `k.` (i tak samo `n.`).

</details>

**Zadanie 10.** Uruchom poniższe zapytanie. Zapisz numer błędu i jego treść, a potem popraw zapytanie.
```sql
SELECT id, imie, nazwa
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id;
```

<details><summary>Podpowiedź</summary>

Przeczytaj komunikat — mówi, która kolumna jest *ambiguous* (niejednoznaczna). W których tabelach jest kolumna `id`? Dopisz przed nią alias.

</details>

**Zadanie 11.** Wyświetl dwie kolumny: `Uczen` (imię i nazwisko ucznia sklejone `CONCAT`)
i `Wychowawca` (imię i nazwisko jego wychowawcy). Potrzebne są **trzy** tabele.
Dlaczego bez `AS` wynik byłby mylący?

<details><summary>Podpowiedź</summary>

`uczniowie` → `klasy` → `nauczyciele` (dwa `JOIN`-y). Kolumna: `CONCAT(u.imie, ' ', u.nazwisko) AS Uczen` — tak samo dla wychowawcy.

</details>

**Zadanie 12.** Zapisz zadanie 1 „po egzaminacyjnemu”: tabele po przecinku w `FROM`, warunek łączenia w `WHERE`.
Sprawdź, czy liczba wierszy jest taka sama.

<details><summary>Podpowiedź</summary>

`FROM uczniowie, klasy` — a warunek, który stał w `ON`, przenosisz do `WHERE`.

</details>

---

## Część III — Trzy i więcej tabel

**Zadanie 13.** Dla każdego ucznia wyświetl: imię, nazwisko, nazwę klasy i nazwisko wychowawcy. Posortuj po klasie i nazwisku ucznia.

<details><summary>Podpowiedź</summary>

Połączenie zadań 1 i 4: `uczniowie` → `klasy` → `nauczyciele`. Nazwisko wychowawcy podpisz aliasem, np. `AS Wychowawca`.

</details>

**Zadanie 14.** Wyświetl wszystkie oceny **Anny Kowalskiej**: nazwę przedmiotu, ocenę, wagę i datę.
Posortuj po przedmiocie i dacie. Ile ocen ma Anna?

<details><summary>Podpowiedź</summary>

`oceny` + `przedmioty` + `uczniowie`. Imię i nazwisko ucznia w `WHERE`. Liczbę ocen odczytasz z liczby wierszy.

</details>

**Zadanie 15.** *(N:M)* Kto chodzi na **Koło robotyki**? Wyświetl imiona i nazwiska, alfabetycznie.
> Tabela łącząca `uczniowie_kola` stoi **w środku** — potrzebne są dwa `JOIN`-y.

<details><summary>Podpowiedź</summary>

`uczniowie` → `uczniowie_kola` (`ON uk.id_ucznia = u.id`) → `kola` (`ON uk.id_kola = ko.id`), a w `WHERE` nazwa koła.

</details>

**Zadanie 16.** Na jakie koła chodzi **Hubert Kamiński**? Pokaż nazwę koła, dzień i nazwisko opiekuna (4 tabele).

<details><summary>Podpowiedź</summary>

Jak w zadaniu 15, tylko filtrujesz po uczniu, a na końcu doklejasz `nauczyciele` (`ON ko.id_opiekuna = n.id`).

</details>

**Zadanie 17.** Którzy uczniowie klasy **4TI** chodzą na **Koło przygotowań do INF.03**?

<details><summary>Podpowiedź</summary>

Potrzebne są: `uczniowie`, `klasy`, `uczniowie_kola`, `kola`. W `WHERE` dwa warunki połączone `AND`.

</details>

**Zadanie 18.** Wyświetl oceny z przedmiotu **Bazy danych** uczniów klasy **2TI**: imię, nazwisko, ocenę i datę.
Posortuj po nazwisku i dacie. *(4 tabele: oceny, przedmioty, uczniowie, klasy)*

<details><summary>Podpowiedź</summary>

Zacznij od `oceny` i doklejaj po kolei `przedmioty`, `uczniowie`, `klasy`. W `WHERE`: nazwa przedmiotu `AND` nazwa klasy.

</details>

---

## Część IV — `JOIN` + `GROUP BY` / `HAVING`

**Zadanie 19.** Ilu uczniów jest w każdej klasie? W wyniku ma być **nazwa** klasy, nie numer.

<details><summary>Podpowiedź</summary>

`uczniowie` + `klasy`, potem `GROUP BY k.nazwa` i `COUNT(*)`.

</details>

**Zadanie 20.** Dla każdego przedmiotu (nazwa) podaj liczbę ocen i średnią ocen (2 miejsca). Posortuj od najniższej średniej.

<details><summary>Podpowiedź</summary>

`oceny` + `przedmioty`, `GROUP BY p.nazwa`. Średnia: `ROUND(AVG(o.ocena), 2)`, sortowanie rosnąco po średniej.

</details>

**Zadanie 21.** Ilu uczniów chodzi na każde koło (nazwa koła)? Posortuj malejąco.
Ile wierszy dostałeś? Ile jest kół w tabeli `kola`? Zapisz, którego koła brakuje — wrócimy do tego w Części V.

<details><summary>Podpowiedź</summary>

`kola` + `uczniowie_kola`, `GROUP BY ko.nazwa`, `COUNT(*)`. Liczbę kół sprawdź osobno: `SELECT COUNT(*) FROM kola;`.

</details>

**Zadanie 22.** Jaka jest średnia ocen w każdej klasie (nazwa klasy)? Która klasa jest najlepsza?

<details><summary>Podpowiedź</summary>

Ocena → uczeń → klasa: `oceny`, `uczniowie`, `klasy`. `GROUP BY k.nazwa`, średnia malejąco.

</details>

**Zadanie 23.** Które klasy mają średnią ocen z **matematyki** wyższą niż **4.3**? Pokaż nazwę klasy i średnią.

<details><summary>Podpowiedź</summary>

Jak w zadaniu 22 + tabela `przedmioty`. Warunek na matematykę idzie do `WHERE` (przed grupowaniem), warunek na średnią — do `HAVING`.

</details>

**Zadanie 24.** Którzy uczniowie chodzą na **co najmniej 2** koła? Pokaż imię, nazwisko i liczbę kół.
> Grupuj po `u.id` (i dopisz `u.imie, u.nazwisko`) — nie po samym nazwisku!

<details><summary>Podpowiedź</summary>

`uczniowie` + `uczniowie_kola`. Każdy wiersz `uczniowie_kola` to jeden zapis na koło, więc `COUNT(*)` w grupie ucznia = liczba jego kół. Warunek „co najmniej 2” — w `HAVING`.

</details>

**Zadanie 25.** Dla każdego nauczyciela, który prowadzi koło, podaj, ilu uczniów łącznie ma na swoich zajęciach.

<details><summary>Podpowiedź</summary>

`nauczyciele` → `kola` (`ON ko.id_opiekuna = n.id`) → `uczniowie_kola`. Grupuj po nauczycielu: `n.id, n.imie, n.nazwisko`.

</details>

---

## Część V — `LEFT JOIN`

**Zadanie 26.** Popraw zadanie 21 tak, żeby w wyniku były **wszystkie 6 kół**, a koło bez uczniów miało **0**.
Potem zamień `COUNT(uk.id_ucznia)` na `COUNT(*)`. Co się zmieniło i dlaczego?

<details><summary>Podpowiedź</summary>

Zacznij od tabeli `kola` i zamień `JOIN` na `LEFT JOIN`. Licz kolumnę z **prawej** tabeli: `COUNT(uk.id_ucznia)` (ściąga, część 4).

</details>

**Zadanie 27.** Którzy nauczyciele **nie są** wychowawcami żadnej klasy?
> Wzór: `LEFT JOIN … WHERE prawa_tabela.id IS NULL`

<details><summary>Podpowiedź</summary>

Lewa tabela: `nauczyciele`. Prawa: `klasy` (`ON k.id_wychowawcy = n.id`). Szukasz wierszy, w których `k.id IS NULL`.

</details>

**Zadanie 28.** Którzy uczniowie **nie chodzą** na żadne koło? Pokaż imię, nazwisko i nazwę klasy. Ilu ich jest?

<details><summary>Podpowiedź</summary>

`uczniowie LEFT JOIN uczniowie_kola … WHERE uk.id_ucznia IS NULL`. Nazwę klasy doklejasz zwykłym `JOIN klasy` — każdy uczeń ma klasę.

</details>

**Zadanie 29.** Którzy nauczyciele **nie prowadzą** żadnego koła?

<details><summary>Podpowiedź</summary>

Jak w zadaniu 27, ale prawa tabela to `kola` (`ON ko.id_opiekuna = n.id`).

</details>

**Zadanie 30.** Czy jest przedmiot, z którego **nie wystawiono** ani jednej oceny? Napisz zapytanie, które to sprawdza.
Co oznacza pusty wynik?

<details><summary>Podpowiedź</summary>

`przedmioty LEFT JOIN oceny … WHERE o.id IS NULL`. Pusty wynik to też odpowiedź.

</details>

**Zadanie 31.** Wyświetl **wszystkich** nauczycieli z nazwą klasy, której są wychowawcami (u kogo jej nie ma — `NULL`).
Ile wierszy? A ile wierszy dałby zwykły `JOIN`?

<details><summary>Podpowiedź</summary>

`nauczyciele LEFT JOIN klasy` — tym razem **bez** `WHERE`. Potem zamień `LEFT JOIN` na `JOIN` i porównaj liczbę wierszy.

</details>

---

## Część VI — Popraw błąd

**Zadanie 32.** Zapytanie działa i zwraca 5 wierszy — ale bez sensu. Co jest nie tak? Popraw.
```sql
SELECT u.imie, k.nazwa
FROM uczniowie u
JOIN klasy k ON u.id = k.id;
```

<details><summary>Podpowiedź</summary>

Spójrz na `ON`: czy łączy klucz obcy z kluczem głównym? Która kolumna tabeli `uczniowie` wskazuje na klasę?

</details>

**Zadanie 33.** Zapytanie zwraca **195** wierszy, choć uczniów jest 39. Dlaczego? Popraw.
```sql
SELECT u.imie, u.nazwisko, k.nazwa
FROM uczniowie u, klasy k;
```

<details><summary>Podpowiedź</summary>

195 = 39 × 5. Czego brakuje między tabelami wypisanymi po przecinku? (ściąga: „bez `ON` dostaniesz każdy z każdym”)

</details>

**Zadanie 34.** Zapytanie kończy się błędem. Odczytaj numer i popraw.
```sql
SELECT u.imie, u.nazwisko
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
WHERE uczniowie.id = 1;
```

<details><summary>Podpowiedź</summary>

Przeczytaj błąd #1054. Tabela `uczniowie` dostała alias `u` — czy po nadaniu aliasu wolno jeszcze używać pełnej nazwy?

</details>

**Zadanie 35.** ⭐ Autor chciał policzyć zapisy na koła **od 15 września** dla **wszystkich** kół (także z zerem),
ale koło szachowe znowu znika. Dlaczego? Popraw tak, żeby było 6 wierszy.
```sql
SELECT ko.nazwa, COUNT(uk.id_ucznia) AS Zapisy
FROM kola ko
LEFT JOIN uczniowie_kola uk ON uk.id_kola = ko.id
WHERE uk.data_zapisu >= '2026-09-15'
GROUP BY ko.nazwa;
```

<details><summary>Podpowiedź</summary>

Dla koła szachowego `uk.data_zapisu` to `NULL`. Czy `NULL >= '2026-09-15'` jest prawdą? Warunek na prawą tabelę przenieś do `ON`: `ON uk.id_kola = ko.id AND …`.

</details>

---

## Część VII ⭐ — Wyzwania

**Zadanie 36.** ⭐ **Raport klas.** Dla każdej klasy w jednym wierszu: nazwa klasy, wychowawca (imię i nazwisko),
**liczba uczniów** i **średnia ocen** klasy. Posortuj po średniej malejąco.
> Uwaga: po doklejeniu ocen każdy uczeń występuje tyle razy, ile ma ocen. Jak policzyć **uczniów**, a nie oceny?

<details><summary>Podpowiedź</summary>

Cztery tabele: `klasy`, `nauczyciele`, `uczniowie`, `oceny`. Uczniów policz przez `COUNT(DISTINCT u.id)` (ściąga: „puchnące liczby”).

</details>

**Zadanie 37.** ⭐⭐ Którzy uczniowie chodzą na koło prowadzone przez **własnego wychowawcę**?
Pokaż ucznia, jego klasę i nazwę koła.

<details><summary>Podpowiedź</summary>

Dołącz do ucznia **i** klasę, **i** koło (przez `uczniowie_kola`) — a potem w `WHERE` porównaj `k.id_wychowawcy` z `ko.id_opiekuna`.

</details>

**Zadanie 38.** ⭐ Dla każdego koła policz średnią **wszystkich ocen** jego uczestników. Na którym kole są „najlepsi uczniowie”?

<details><summary>Podpowiedź</summary>

`kola` → `uczniowie_kola` → `oceny`. Tabela `uczniowie` nie jest potrzebna: `oceny` łączysz z `uczniowie_kola` po `id_ucznia`.

</details>

**Zadanie 39.** ⭐ W każdej klasie policz, ilu **różnych** uczniów dostało co najmniej jedną ocenę **poniżej 3**.

<details><summary>Podpowiedź</summary>

`oceny` → `uczniowie` → `klasy`, `WHERE o.ocena < 3`. Jeden uczeń może mieć kilka takich ocen — `COUNT(DISTINCT o.id_ucznia)`.

</details>

**Zadanie 40.** ⭐ **Powrót do bazy `world`.** Na lekcji 3 szukaliśmy stolic „ręcznie” (`kraje.stolica` → `miasta.id`).
a) Wyświetl wszystkie kraje Europy z nazwą **stolicy**, alfabetycznie.
b) Która stolica świata ma najwięcej mieszkańców? Pokaż 3 największe stolice z nazwą kraju.

<details><summary>Podpowiedź</summary>

a) `kraje JOIN miasta ON kraje.stolica = miasta.id`, `WHERE kontynent = 'Europa'`. b) To samo bez filtra kontynentu, `ORDER BY liczba_mieszkancow DESC LIMIT 3`.

</details>

**Zadanie 41.** ⭐ *(baza `world`)* W zestawie 3 (zad. 64) policzyliśmy, że **7** krajów nie ma w bazie żadnego miasta —
ale nie wiedzieliśmy **których**. Teraz to sprawdź (`LEFT JOIN … IS NULL`).

<details><summary>Podpowiedź</summary>

`kraje LEFT JOIN miasta ON miasta.kod_kraju = kraje.kod … WHERE miasta.id IS NULL`.

</details>

---

## Pytania kontrolne

1. Co robi `JOIN` i co oznacza warunek `ON`?
2. Jaki warunek `ON` piszemy prawie zawsze? Podaj przykład z bazy `szkola`.
3. Po co są aliasy tabel? Co się stanie, jeśli po nadaniu aliasu użyjesz pełnej nazwy tabeli?
4. Co oznacza błąd #1052 i jak go naprawić?
5. Czym różni się `JOIN` (INNER) od `LEFT JOIN`? Kiedy użyjesz którego?
6. Jak znaleźć wiersze, które **nie mają** pary w drugiej tabeli?
7. Dlaczego przy `LEFT JOIN` liczymy `COUNT(kolumna_z_prawej)`, a nie `COUNT(*)`?
8. Ile tabel trzeba połączyć, żeby zapisać związek N:M (np. uczniowie — koła)? Dlaczego?
9. Co się stanie, gdy zapomnisz o warunku łączenia?
10. Napisz to samo połączenie dwoma zapisami: `JOIN … ON` i „po przecinku” z `WHERE`.
