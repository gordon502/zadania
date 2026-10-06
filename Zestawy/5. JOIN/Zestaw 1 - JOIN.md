# Zestaw 4 — Łączenie tabel: `JOIN` i `LEFT JOIN`

**Baza:** `szkola` (plik `szkola.sql`) | **Narzędzie:** XAMPP → phpMyAdmin → zakładka **SQL**
**Materiał pomocniczy:** ściąga „JOIN — łączenie tabel” (część 2 to ściąga do warunków `ON`, na końcu dwie animacje)
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

**Zadanie 2.** To samo co w zadaniu 1, ale posortowane po nazwie klasy, a w obrębie klasy — po nazwisku.
Która klasa jest pierwsza i kto jest pierwszy na liście?

**Zadanie 3.** Wyświetl uczniów klasy **4TI** (imię, nazwisko), alfabetycznie. Nie sprawdzaj wcześniej, jaki numer ma 4TI!

**Zadanie 4.** Dla każdej klasy wyświetl jej nazwę oraz imię i nazwisko **wychowawcy**. Posortuj po nazwie klasy.

**Zadanie 5.** Wyświetl wszystkie koła zainteresowań: nazwę, dzień tygodnia oraz imię i nazwisko **opiekuna**.

**Zadanie 6.** Wyświetl oceny wystawione **30 września 2026**: nazwę przedmiotu, ocenę i wagę.
Posortuj po nazwie przedmiotu.

**Zadanie 7.** Wyświetl uczniów wszystkich klas o profilu **informatycznym** (imię, nazwisko, nazwa klasy).
Posortuj po klasie i nazwisku.

**Zadanie 8.** Ile wierszy zwraca zapytanie z zadania 1? Porównaj z liczbą wierszy w tabeli `uczniowie`.
Dlaczego te liczby są równe?

---

## Część II — Aliasy i kolumny o tych samych nazwach

**Zadanie 9.** Przepisz zadanie 4, nadając tabelom aliasy `k` i `n`.

**Zadanie 10.** Uruchom poniższe zapytanie. Zapisz numer błędu i jego treść, a potem popraw zapytanie.
```sql
SELECT id, imie, nazwa
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id;
```

**Zadanie 11.** Wyświetl dwie kolumny: `Uczen` (imię i nazwisko ucznia sklejone `CONCAT`)
i `Wychowawca` (imię i nazwisko jego wychowawcy). Potrzebne są **trzy** tabele.
Dlaczego bez `AS` wynik byłby mylący?

**Zadanie 12.** Zapisz zadanie 1 „po egzaminacyjnemu”: tabele po przecinku w `FROM`, warunek łączenia w `WHERE`.
Sprawdź, czy liczba wierszy jest taka sama.

---

## Część III — Trzy i więcej tabel

**Zadanie 13.** Dla każdego ucznia wyświetl: imię, nazwisko, nazwę klasy i nazwisko wychowawcy. Posortuj po klasie i nazwisku ucznia.

**Zadanie 14.** Wyświetl wszystkie oceny **Anny Kowalskiej**: nazwę przedmiotu, ocenę, wagę i datę.
Posortuj po przedmiocie i dacie. Ile ocen ma Anna?

**Zadanie 15.** *(N:M)* Kto chodzi na **Koło robotyki**? Wyświetl imiona i nazwiska, alfabetycznie.
> Tabela łącząca `uczniowie_kola` stoi **w środku** — potrzebne są dwa `JOIN`-y.

**Zadanie 16.** Na jakie koła chodzi **Hubert Kamiński**? Pokaż nazwę koła, dzień i nazwisko opiekuna (4 tabele).

**Zadanie 17.** Którzy uczniowie klasy **4TI** chodzą na **Koło przygotowań do INF.03**?

**Zadanie 18.** Wyświetl oceny z przedmiotu **Bazy danych** uczniów klasy **2TI**: imię, nazwisko, ocenę i datę.
Posortuj po nazwisku i dacie. *(4 tabele: oceny, przedmioty, uczniowie, klasy)*

---

## Część IV — `JOIN` + `GROUP BY` / `HAVING`

**Zadanie 19.** Ilu uczniów jest w każdej klasie? W wyniku ma być **nazwa** klasy, nie numer.

**Zadanie 20.** Dla każdego przedmiotu (nazwa) podaj liczbę ocen i średnią ocen (2 miejsca). Posortuj od najniższej średniej.

**Zadanie 21.** Ilu uczniów chodzi na każde koło (nazwa koła)? Posortuj malejąco.
Ile wierszy dostałeś? Ile jest kół w tabeli `kola`? Zapisz, którego koła brakuje — wrócimy do tego w Części V.

**Zadanie 22.** Jaka jest średnia ocen w każdej klasie (nazwa klasy)? Która klasa jest najlepsza?

**Zadanie 23.** Które klasy mają średnią ocen z **matematyki** wyższą niż **4.3**? Pokaż nazwę klasy i średnią.

**Zadanie 24.** Którzy uczniowie chodzą na **co najmniej 2** koła? Pokaż imię, nazwisko i liczbę kół.
> Grupuj po `u.id` (i dopisz `u.imie, u.nazwisko`) — nie po samym nazwisku!

**Zadanie 25.** Dla każdego nauczyciela, który prowadzi koło, podaj, ilu uczniów łącznie ma na swoich zajęciach.

---

## Część V — `LEFT JOIN`

**Zadanie 26.** Popraw zadanie 21 tak, żeby w wyniku były **wszystkie 6 kół**, a koło bez uczniów miało **0**.
Potem zamień `COUNT(uk.id_ucznia)` na `COUNT(*)`. Co się zmieniło i dlaczego?

**Zadanie 27.** Którzy nauczyciele **nie są** wychowawcami żadnej klasy?
> Wzór: `LEFT JOIN … WHERE prawa_tabela.id IS NULL`

**Zadanie 28.** Którzy uczniowie **nie chodzą** na żadne koło? Pokaż imię, nazwisko i nazwę klasy. Ilu ich jest?

**Zadanie 29.** Którzy nauczyciele **nie prowadzą** żadnego koła?

**Zadanie 30.** Czy jest przedmiot, z którego **nie wystawiono** ani jednej oceny? Napisz zapytanie, które to sprawdza.
Co oznacza pusty wynik?

**Zadanie 31.** Wyświetl **wszystkich** nauczycieli z nazwą klasy, której są wychowawcami (u kogo jej nie ma — `NULL`).
Ile wierszy? A ile wierszy dałby zwykły `JOIN`?

---

## Część VI — Popraw błąd

**Zadanie 32.** Zapytanie działa i zwraca 5 wierszy — ale bez sensu. Co jest nie tak? Popraw.
```sql
SELECT u.imie, k.nazwa
FROM uczniowie u
JOIN klasy k ON u.id = k.id;
```

**Zadanie 33.** Zapytanie zwraca **195** wierszy, choć uczniów jest 39. Dlaczego? Popraw.
```sql
SELECT u.imie, u.nazwisko, k.nazwa
FROM uczniowie u, klasy k;
```

**Zadanie 34.** Zapytanie kończy się błędem. Odczytaj numer i popraw.
```sql
SELECT u.imie, u.nazwisko
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
WHERE uczniowie.id = 1;
```

**Zadanie 35.** ⭐ Autor chciał policzyć zapisy na koła **od 15 września** dla **wszystkich** kół (także z zerem),
ale koło szachowe znowu znika. Dlaczego? Popraw tak, żeby było 6 wierszy.
```sql
SELECT ko.nazwa, COUNT(uk.id_ucznia) AS Zapisy
FROM kola ko
LEFT JOIN uczniowie_kola uk ON uk.id_kola = ko.id
WHERE uk.data_zapisu >= '2026-09-15'
GROUP BY ko.nazwa;
```

---

## Część VII ⭐ — Wyzwania

**Zadanie 36.** ⭐ **Raport klas.** Dla każdej klasy w jednym wierszu: nazwa klasy, wychowawca (imię i nazwisko),
**liczba uczniów** i **średnia ocen** klasy. Posortuj po średniej malejąco.
> Uwaga: po doklejeniu ocen każdy uczeń występuje tyle razy, ile ma ocen. Jak policzyć **uczniów**, a nie oceny?

**Zadanie 37.** ⭐⭐ Którzy uczniowie chodzą na koło prowadzone przez **własnego wychowawcę**?
Pokaż ucznia, jego klasę i nazwę koła.
> Podpowiedź: dołącz do ucznia i klasę, i koło — a potem porównaj `id_wychowawcy` z `id_opiekuna`.

**Zadanie 38.** ⭐ Dla każdego koła policz średnią **wszystkich ocen** jego uczestników. Na którym kole są „najlepsi uczniowie”?

**Zadanie 39.** ⭐ W każdej klasie policz, ilu **różnych** uczniów dostało co najmniej jedną ocenę **poniżej 3**.

**Zadanie 40.** ⭐ **Powrót do bazy `world`.** Na lekcji 3 szukaliśmy stolic „ręcznie” (`kraje.stolica` → `miasta.id`).
a) Wyświetl wszystkie kraje Europy z nazwą **stolicy**, alfabetycznie.
b) Która stolica świata ma najwięcej mieszkańców? Pokaż 3 największe stolice z nazwą kraju.

**Zadanie 41.** ⭐ *(baza `world`)* W zestawie 3 (zad. 64) policzyliśmy, że **7** krajów nie ma w bazie żadnego miasta —
ale nie wiedzieliśmy **których**. Teraz to sprawdź (`LEFT JOIN … IS NULL`).

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
