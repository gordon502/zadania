# Zestaw 4 — odpowiedzi

**Baza:** `szkola` (zadania 40–41: `world`). Każde zapytanie zostało uruchomione na bazie — wyniki są prawdziwe.

**Jak korzystać:**
- Zaglądaj tu **po** rozwiązaniu zadania (albo gdy podpowiedź nie wystarczyła).
- Twoje zapytanie **nie musi** wyglądać identycznie — ważne, żeby dawało ten sam wynik.
  Inne aliasy, inna kolejność kolumn albo zapis z przecinkami zamiast `JOIN … ON` są w porządku.
- Kolejność wierszy ma znaczenie tylko tam, gdzie zadanie każe sortować.
  Przy remisach (np. dwie klasy z tą samą liczbą) wzorcowe zapytanie ma dodatkowe sortowanie po nazwie — żeby dało się porównać.
- Przy dłuższych wynikach pokazane jest 5 pierwszych wierszy — liczbę wszystkich podaje linijka „Wynik”.

---

## Część I — Dwie tabele

### Zadanie 1

```sql
SELECT uczniowie.imie, uczniowie.nazwisko, klasy.nazwa
FROM uczniowie
JOIN klasy ON uczniowie.id_klasy = klasy.id;
```

Wynik: **39 wierszy**

| imie | nazwisko | nazwa |
|---|---|---|
| Gabriela | Dąbrowska | 1TP |
| Oskar | Czarnecki | 1TP |
| Jan | Kwiatkowski | 1TP |
| Szymon | Kalinowski | 1TP |
| Hanna | Bąk | 1TP |
| … | … | … |

> 💡 **39** wierszy — tyle, ilu jest uczniów. Bez `ORDER BY` kolejność wierszy może być u Ciebie inna — to normalne.

### Zadanie 2

```sql
SELECT u.imie, u.nazwisko, k.nazwa
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
ORDER BY k.nazwa, u.nazwisko;
```

Wynik: **39 wierszy**

| imie | nazwisko | nazwa |
|---|---|---|
| Hanna | Bąk | 1TP |
| Oskar | Czarnecki | 1TP |
| Gabriela | Dąbrowska | 1TP |
| Szymon | Kalinowski | 1TP |
| Jan | Kwiatkowski | 1TP |
| … | … | … |

> 💡 Pierwsza klasa: **1TP**, pierwsza osoba: **Hanna Bąk**.

### Zadanie 3

```sql
SELECT u.imie, u.nazwisko
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
WHERE k.nazwa = '4TI'
ORDER BY u.nazwisko;
```

Wynik: **8 wierszy**

| imie | nazwisko |
|---|---|
| Kamil | Kaczmarczyk |
| Hubert | Kamiński |
| Ewa | Lewandowska |
| Bartosz | Nowak |
| Amelia | Stępień |
| Kacper | Urbański |
| Mateusz | Wojciechowski |
| Hanna | Wójtowicz |

> 💡 **8** uczniów. Typowy błąd: `WHERE id_klasy = 1` — wynik ten sam, ale to numer „z głowy”: przestanie działać, gdy klasy dostaną inne numery. Po to jest `JOIN`, żeby filtrować po nazwie.

### Zadanie 4

```sql
SELECT klasy.nazwa, nauczyciele.imie, nauczyciele.nazwisko
FROM klasy
JOIN nauczyciele ON klasy.id_wychowawcy = nauczyciele.id
ORDER BY klasy.nazwa;
```

Wynik: **5 wierszy**

| nazwa | imie | nazwisko |
|---|---|---|
| 1TP | Monika | Adamczyk |
| 2TI | Marek | Nowicki |
| 4TI | Tomasz | Kaczmarek |
| 4TL | Joanna | Pawlak |
| 5TM | Rafał | Górski |

> 💡 **5** wierszy — każda klasa ma jednego wychowawcę (związek 1:1).

### Zadanie 5

```sql
SELECT ko.nazwa, ko.dzien, n.imie, n.nazwisko
FROM kola ko
JOIN nauczyciele n ON ko.id_opiekuna = n.id;
```

Wynik: **6 wierszy**

| nazwa | dzien | imie | nazwisko |
|---|---|---|---|
| Koło e-sportowe | pt | Marek | Nowicki |
| Koło robotyki | wt | Krzysztof | Michalski |
| Koło fotograficzne | sr | Beata | Król |
| Szkolny klub siatkówki | czw | Paweł | Jabłoński |
| Koło przygotowań do INF.03 | pon | Tomasz | Kaczmarek |
| Koło szachowe | sr | Ewelina | Sikora |

> 💡 **6** wierszy — tyle, ile kół.

### Zadanie 6

```sql
SELECT p.nazwa, o.ocena, o.waga
FROM oceny o
JOIN przedmioty p ON o.id_przedmiotu = p.id
WHERE o.data_wystawienia = '2026-09-30'
ORDER BY p.nazwa;
```

Wynik: **17 wierszy**

| nazwa | ocena | waga |
|---|---|---|
| Bazy danych | 6.0 | 2 |
| Bazy danych | 5.0 | 2 |
| Fizyka | 3.0 | 3 |
| Historia | 3.0 | 2 |
| Historia | 2.0 | 2 |
| … | … | … |

> 💡 **17** ocen.

### Zadanie 7

```sql
SELECT u.imie, u.nazwisko, k.nazwa
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
WHERE k.profil = 'informatyczny'
ORDER BY k.nazwa, u.nazwisko;
```

Wynik: **16 wierszy**

| imie | nazwisko | nazwa |
|---|---|---|
| Natalia | Dudek | 2TI |
| Amelia | Lis | 2TI |
| Amelia | Mazurek | 2TI |
| Łukasz | Ostrowski | 2TI |
| Natalia | Sadowska | 2TI |
| … | … | … |

> 💡 **16** uczniów: po 8 z klas 2TI i 4TI.

### Zadanie 8

Liczba wierszy w tabeli `uczniowie`:

```sql
SELECT COUNT(*) AS Uczniow FROM uczniowie;
```

Wynik: **1 wiersz**

| Uczniow |
|---|
| 39 |

> 💡 Obie liczby to **39**. Każdy uczeń należy do **dokładnie jednej** klasy (`id_klasy` nie może być puste i musi wskazywać istniejącą klasę), więc każdy wiersz `uczniowie` dostaje dokładnie jedną parę. Złączenie „wielu do jednego” (N:1) nie mnoży wierszy.

---

## Część II — Aliasy i kolumny o tych samych nazwach

### Zadanie 9

```sql
SELECT k.nazwa, n.imie, n.nazwisko
FROM klasy k
JOIN nauczyciele n ON k.id_wychowawcy = n.id
ORDER BY k.nazwa;
```

Wynik: **5 wierszy**

| nazwa | imie | nazwisko |
|---|---|---|
| 1TP | Monika | Adamczyk |
| 2TI | Marek | Nowicki |
| 4TI | Tomasz | Kaczmarek |
| 4TL | Joanna | Pawlak |
| 5TM | Rafał | Górski |

> 💡 Wynik taki sam jak w zadaniu 4 — aliasy zmieniają tylko zapis, nie wynik.

### Zadanie 10

Zapytanie z błędem:

```sql
SELECT id, imie, nazwa
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id;
```

Wynik: ❌ `#1052 - Column 'id' in SELECT is ambiguous`

Poprawione:

```sql
SELECT u.id, u.imie, k.nazwa
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id;
```

Wynik: **39 wierszy**

| id | imie | nazwa |
|---|---|---|
| 7 | Gabriela | 1TP |
| 33 | Oskar | 1TP |
| 34 | Jan | 1TP |
| 35 | Szymon | 1TP |
| 36 | Hanna | 1TP |
| … | … | … |

> 💡 Błąd **#1052** — *Column 'id' … is ambiguous* (w XAMPP: „in field list”). Kolumna `id` jest w **obu** tabelach i serwer nie wie, o którą chodzi. Poprawka: dopisz alias — `u.id` (albo `k.id`, zależnie od tego, czyje id chcesz).

### Zadanie 11

```sql
SELECT CONCAT(u.imie, ' ', u.nazwisko) AS Uczen,
       CONCAT(n.imie, ' ', n.nazwisko) AS Wychowawca
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
JOIN nauczyciele n ON k.id_wychowawcy = n.id;
```

Wynik: **39 wierszy**

| Uczen | Wychowawca |
|---|---|
| Amelia Mazurek | Marek Nowicki |
| Karolina Walczak | Marek Nowicki |
| Oliwia Witkowska | Marek Nowicki |
| Michał Sobczak | Marek Nowicki |
| Natalia Sadowska | Marek Nowicki |
| … | … |

> 💡 **39** wierszy. Bez `AS` obie kolumny miałyby nagłówek w stylu `CONCAT(...)` — nie wiadomo, która jest uczniem, a która wychowawcą.

### Zadanie 12

```sql
SELECT uczniowie.imie, uczniowie.nazwisko, klasy.nazwa
FROM uczniowie, klasy
WHERE uczniowie.id_klasy = klasy.id;
```

Wynik: **39 wierszy**

| imie | nazwisko | nazwa |
|---|---|---|
| Gabriela | Dąbrowska | 1TP |
| Oskar | Czarnecki | 1TP |
| Jan | Kwiatkowski | 1TP |
| Szymon | Kalinowski | 1TP |
| Hanna | Bąk | 1TP |
| … | … | … |

> 💡 **39** wierszy — dokładnie ten sam wynik co z `JOIN … ON`. Ten zapis spotkasz w arkuszach egzaminu INF.03.

---

## Część III — Trzy i więcej tabel

### Zadanie 13

```sql
SELECT u.imie, u.nazwisko, k.nazwa, n.nazwisko AS Wychowawca
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
JOIN nauczyciele n ON k.id_wychowawcy = n.id
ORDER BY k.nazwa, u.nazwisko;
```

Wynik: **39 wierszy**

| imie | nazwisko | nazwa | Wychowawca |
|---|---|---|---|
| Hanna | Bąk | 1TP | Adamczyk |
| Oskar | Czarnecki | 1TP | Adamczyk |
| Gabriela | Dąbrowska | 1TP | Adamczyk |
| Szymon | Kalinowski | 1TP | Adamczyk |
| Jan | Kwiatkowski | 1TP | Adamczyk |
| … | … | … | … |

> 💡 **39** wierszy.

### Zadanie 14

```sql
SELECT p.nazwa, o.ocena, o.waga, o.data_wystawienia
FROM oceny o
JOIN przedmioty p ON o.id_przedmiotu = p.id
JOIN uczniowie u ON o.id_ucznia = u.id
WHERE u.imie = 'Anna' AND u.nazwisko = 'Kowalska'
ORDER BY p.nazwa, o.data_wystawienia;
```

Wynik: **9 wierszy**

| nazwa | ocena | waga | data_wystawienia |
|---|---|---|---|
| Fizyka | 3.0 | 1 | 2026-09-04 |
| Historia | 4.5 | 2 | 2026-09-08 |
| Historia | 5.0 | 1 | 2026-09-29 |
| Język angielski | 4.5 | 2 | 2026-09-24 |
| Język polski | 5.0 | 3 | 2026-09-30 |
| Logistyka magazynowa | 5.0 | 1 | 2026-09-14 |
| Logistyka magazynowa | 5.0 | 1 | 2026-09-18 |
| Matematyka | 5.0 | 1 | 2026-09-21 |
| Matematyka | 3.0 | 2 | 2026-09-24 |

> 💡 Anna ma **9** ocen.

### Zadanie 15

```sql
SELECT u.imie, u.nazwisko
FROM uczniowie u
JOIN uczniowie_kola uk ON uk.id_ucznia = u.id
JOIN kola ko ON uk.id_kola = ko.id
WHERE ko.nazwa = 'Koło robotyki'
ORDER BY u.nazwisko;
```

Wynik: **11 wierszy**

| imie | nazwisko |
|---|---|
| Oliwer | Chmielewski |
| Kamil | Grabowski |
| Oliwer | Jankowski |
| Kamil | Kaczmarczyk |
| Natalia | Kubiak |
| Oskar | Leśniak |
| Łukasz | Ostrowski |
| Michał | Sobczak |
| Amelia | Stępień |
| Celina | Wójcik |
| Maja | Zając |

> 💡 **11** osób. Tabela łącząca `uczniowie_kola` stoi w środku — oba warunki `ON` prowadzą do niej.

### Zadanie 16

```sql
SELECT ko.nazwa, ko.dzien, n.nazwisko AS Opiekun
FROM uczniowie u
JOIN uczniowie_kola uk ON uk.id_ucznia = u.id
JOIN kola ko ON uk.id_kola = ko.id
JOIN nauczyciele n ON ko.id_opiekuna = n.id
WHERE u.imie = 'Hubert' AND u.nazwisko = 'Kamiński';
```

Wynik: **3 wiersze**

| nazwa | dzien | Opiekun |
|---|---|---|
| Koło fotograficzne | sr | Król |
| Szkolny klub siatkówki | czw | Jabłoński |
| Koło przygotowań do INF.03 | pon | Kaczmarek |

> 💡 **3** koła: fotograficzne, siatkówka i przygotowania do INF.03.

### Zadanie 17

```sql
SELECT u.imie, u.nazwisko
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
JOIN uczniowie_kola uk ON uk.id_ucznia = u.id
JOIN kola ko ON uk.id_kola = ko.id
WHERE k.nazwa = '4TI' AND ko.nazwa = 'Koło przygotowań do INF.03';
```

Wynik: **4 wiersze**

| imie | nazwisko |
|---|---|
| Bartosz | Nowak |
| Hubert | Kamiński |
| Amelia | Stępień |
| Hanna | Wójtowicz |

> 💡 **4** osoby.

### Zadanie 18

```sql
SELECT u.imie, u.nazwisko, o.ocena, o.data_wystawienia
FROM oceny o
JOIN przedmioty p ON o.id_przedmiotu = p.id
JOIN uczniowie u ON o.id_ucznia = u.id
JOIN klasy k ON u.id_klasy = k.id
WHERE p.nazwa = 'Bazy danych' AND k.nazwa = '2TI'
ORDER BY u.nazwisko, o.data_wystawienia;
```

Wynik: **11 wierszy**

| imie | nazwisko | ocena | data_wystawienia |
|---|---|---|---|
| Natalia | Dudek | 2.0 | 2026-09-21 |
| Natalia | Dudek | 6.0 | 2026-09-23 |
| Natalia | Dudek | 5.0 | 2026-10-02 |
| Amelia | Mazurek | 5.0 | 2026-09-03 |
| Amelia | Mazurek | 4.5 | 2026-09-04 |
| Amelia | Mazurek | 4.5 | 2026-09-25 |
| Natalia | Sadowska | 5.5 | 2026-09-04 |
| Natalia | Sadowska | 6.0 | 2026-09-11 |
| Natalia | Sadowska | 6.0 | 2026-09-30 |
| Michał | Sobczak | 6.0 | 2026-10-02 |
| Oliwia | Witkowska | 6.0 | 2026-09-22 |

> 💡 **11** ocen (5 uczniów).

---

## Część IV — `JOIN` + `GROUP BY` / `HAVING`

### Zadanie 19

```sql
SELECT k.nazwa, COUNT(*) AS Uczniow
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
GROUP BY k.nazwa;
```

Wynik: **5 wierszy**

| nazwa | Uczniow |
|---|---|
| 1TP | 8 |
| 2TI | 8 |
| 4TI | 8 |
| 4TL | 8 |
| 5TM | 7 |

> 💡 **5** wierszy: cztery klasy po 8 osób, 5TM — 7.

### Zadanie 20

```sql
SELECT p.nazwa, COUNT(*) AS Ocen, ROUND(AVG(o.ocena), 2) AS Srednia
FROM oceny o
JOIN przedmioty p ON o.id_przedmiotu = p.id
GROUP BY p.nazwa
ORDER BY Srednia, p.nazwa;
```

Wynik: **10 wierszy**

| nazwa | Ocen | Srednia |
|---|---|---|
| Logistyka magazynowa | 10 | 3.50 |
| Technologia mechaniczna | 12 | 3.50 |
| Historia | 63 | 4.10 |
| Język polski | 46 | 4.10 |
| Programowanie | 48 | 4.11 |
| Fizyka | 52 | 4.15 |
| Matematyka | 55 | 4.32 |
| Wychowanie fizyczne | 60 | 4.34 |
| Język angielski | 68 | 4.48 |
| Bazy danych | 42 | 4.61 |

> 💡 **10** przedmiotów. Najniższa średnia: Logistyka magazynowa i Technologia mechaniczna (**3.50**), najwyższa: Bazy danych (**4.61**).

### Zadanie 21

```sql
SELECT ko.nazwa, COUNT(*) AS Uczniow
FROM kola ko
JOIN uczniowie_kola uk ON uk.id_kola = ko.id
GROUP BY ko.nazwa
ORDER BY Uczniow DESC, ko.nazwa;
```

Wynik: **5 wierszy**

| nazwa | Uczniow |
|---|---|
| Koło fotograficzne | 14 |
| Koło robotyki | 11 |
| Koło przygotowań do INF.03 | 10 |
| Szkolny klub siatkówki | 10 |
| Koło e-sportowe | 7 |

Ile kół jest w tabeli `kola`:

```sql
SELECT COUNT(*) AS Kol FROM kola;
```

Wynik: **1 wiersz**

| Kol |
|---|
| 6 |

> 💡 Wynik ma **5** wierszy, a kół jest **6**. Brakuje **Koła szachowego** — nikt na nie nie chodzi, więc zwykły `JOIN` nie znalazł mu pary i wiersz zniknął. Naprawimy to w zadaniu 26.

### Zadanie 22

```sql
SELECT k.nazwa, ROUND(AVG(o.ocena), 2) AS Srednia
FROM oceny o
JOIN uczniowie u ON o.id_ucznia = u.id
JOIN klasy k ON u.id_klasy = k.id
GROUP BY k.nazwa
ORDER BY Srednia DESC;
```

Wynik: **5 wierszy**

| nazwa | Srednia |
|---|---|
| 2TI | 4.81 |
| 1TP | 4.50 |
| 4TL | 3.98 |
| 5TM | 3.95 |
| 4TI | 3.91 |

> 💡 Najlepsza klasa: **2TI** (4.81).

### Zadanie 23

```sql
SELECT k.nazwa, ROUND(AVG(o.ocena), 2) AS Srednia
FROM oceny o
JOIN przedmioty p ON o.id_przedmiotu = p.id
JOIN uczniowie u ON o.id_ucznia = u.id
JOIN klasy k ON u.id_klasy = k.id
WHERE p.nazwa = 'Matematyka'
GROUP BY k.nazwa
HAVING AVG(o.ocena) > 4.3
ORDER BY Srednia DESC;
```

Wynik: **3 wiersze**

| nazwa | Srednia |
|---|---|
| 1TP | 4.65 |
| 2TI | 4.56 |
| 4TI | 4.31 |

> 💡 **3** klasy: 1TP, 2TI i 4TI. Warunek na matematykę jest w `WHERE` (wybiera oceny **przed** grupowaniem), a warunek na średnią — w `HAVING` (sprawdza gotowe grupy).

### Zadanie 24

```sql
SELECT u.imie, u.nazwisko, COUNT(*) AS Kol
FROM uczniowie u
JOIN uczniowie_kola uk ON uk.id_ucznia = u.id
GROUP BY u.id, u.imie, u.nazwisko
HAVING COUNT(*) >= 2
ORDER BY Kol DESC, u.nazwisko;
```

Wynik: **17 wierszy**

| imie | nazwisko | Kol |
|---|---|---|
| Oskar | Czarnecki | 3 |
| Oliwer | Jankowski | 3 |
| Kamil | Kaczmarczyk | 3 |
| Szymon | Kalinowski | 3 |
| Hubert | Kamiński | 3 |
| … | … | … |

> 💡 **17** uczniów: 9 osób chodzi na 3 koła, 8 osób na 2. Grupujemy po `u.id` — dwie osoby o tym samym nazwisku nie mogą zlać się w jedną grupę.

### Zadanie 25

```sql
SELECT n.imie, n.nazwisko, COUNT(*) AS Uczniow
FROM nauczyciele n
JOIN kola ko ON ko.id_opiekuna = n.id
JOIN uczniowie_kola uk ON uk.id_kola = ko.id
GROUP BY n.id, n.imie, n.nazwisko
ORDER BY Uczniow DESC, n.nazwisko;
```

Wynik: **5 wierszy**

| imie | nazwisko | Uczniow |
|---|---|---|
| Beata | Król | 14 |
| Krzysztof | Michalski | 11 |
| Paweł | Jabłoński | 10 |
| Tomasz | Kaczmarek | 10 |
| Marek | Nowicki | 7 |

> 💡 **5** nauczycieli. Brakuje Eweliny Sikory: prowadzi koło szachowe, na które nikt nie chodzi (zob. zadanie 21).

---

## Część V — `LEFT JOIN`

### Zadanie 26

```sql
SELECT ko.nazwa, COUNT(uk.id_ucznia) AS Uczniow
FROM kola ko
LEFT JOIN uczniowie_kola uk ON uk.id_kola = ko.id
GROUP BY ko.nazwa
ORDER BY Uczniow DESC, ko.nazwa;
```

Wynik: **6 wierszy**

| nazwa | Uczniow |
|---|---|
| Koło fotograficzne | 14 |
| Koło robotyki | 11 |
| Koło przygotowań do INF.03 | 10 |
| Szkolny klub siatkówki | 10 |
| Koło e-sportowe | 7 |
| Koło szachowe | 0 |

Z `COUNT(*)`:

```sql
SELECT ko.nazwa, COUNT(*) AS Uczniow
FROM kola ko
LEFT JOIN uczniowie_kola uk ON uk.id_kola = ko.id
GROUP BY ko.nazwa
ORDER BY Uczniow DESC, ko.nazwa;
```

Wynik: **6 wierszy**

| nazwa | Uczniow |
|---|---|
| Koło fotograficzne | 14 |
| Koło robotyki | 11 |
| Koło przygotowań do INF.03 | 10 |
| Szkolny klub siatkówki | 10 |
| Koło e-sportowe | 7 |
| Koło szachowe | 1 |

> 💡 **6** wierszy, Koło szachowe → **0**. Z `COUNT(*)` szachowe ma **1**: `LEFT JOIN` dał mu jeden wiersz z `NULL`-ami po prawej stronie, a `COUNT(*)` liczy **wiersze**, nie wartości. `COUNT(uk.id_ucznia)` pomija `NULL` — dlatego daje 0.

### Zadanie 27

```sql
SELECT n.imie, n.nazwisko
FROM nauczyciele n
LEFT JOIN klasy k ON k.id_wychowawcy = n.id
WHERE k.id IS NULL
ORDER BY n.nazwisko;
```

Wynik: **5 wierszy**

| imie | nazwisko |
|---|---|
| Paweł | Jabłoński |
| Beata | Król |
| Krzysztof | Michalski |
| Ewelina | Sikora |
| Agnieszka | Wróbel |

> 💡 **5** nauczycieli.

### Zadanie 28

```sql
SELECT u.imie, u.nazwisko, k.nazwa
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
LEFT JOIN uczniowie_kola uk ON uk.id_ucznia = u.id
WHERE uk.id_ucznia IS NULL
ORDER BY k.nazwa, u.nazwisko;
```

Wynik: **13 wierszy**

| imie | nazwisko | nazwa |
|---|---|---|
| Hanna | Bąk | 1TP |
| Gabriela | Dąbrowska | 1TP |
| Amelia | Lis | 2TI |
| Amelia | Mazurek | 2TI |
| Natalia | Sadowska | 2TI |
| Karolina | Walczak | 2TI |
| Oliwia | Witkowska | 2TI |
| Mateusz | Wojciechowski | 4TI |
| Anna | Kowalska | 4TL |
| Maksymilian | Wieczorek | 4TL |
| Łukasz | Głowacki | 5TM |
| Iwona | Mazur | 5TM |
| Damian | Zieliński | 5TM |

> 💡 **13** uczniów. Klasę doklejamy zwykłym `JOIN` (każdy uczeń ma klasę), a koła — `LEFT JOIN` (nie każdy chodzi na koło).

### Zadanie 29

```sql
SELECT n.imie, n.nazwisko
FROM nauczyciele n
LEFT JOIN kola ko ON ko.id_opiekuna = n.id
WHERE ko.id IS NULL
ORDER BY n.nazwisko;
```

Wynik: **4 wiersze**

| imie | nazwisko |
|---|---|
| Monika | Adamczyk |
| Rafał | Górski |
| Joanna | Pawlak |
| Agnieszka | Wróbel |

> 💡 **4** nauczycieli.

### Zadanie 30

```sql
SELECT p.nazwa
FROM przedmioty p
LEFT JOIN oceny o ON o.id_przedmiotu = p.id
WHERE o.id IS NULL;
```

Wynik: **0 wierszy**

> 💡 **0** wierszy — z każdego przedmiotu jest co najmniej jedna ocena. Pusty wynik to też odpowiedź: „nie ma takich przedmiotów”.

### Zadanie 31

```sql
SELECT n.imie, n.nazwisko, k.nazwa
FROM nauczyciele n
LEFT JOIN klasy k ON k.id_wychowawcy = n.id
ORDER BY n.nazwisko;
```

Wynik: **10 wierszy**

| imie | nazwisko | nazwa |
|---|---|---|
| Monika | Adamczyk | 1TP |
| Rafał | Górski | 5TM |
| Paweł | Jabłoński | NULL |
| Tomasz | Kaczmarek | 4TI |
| Beata | Król | NULL |
| Krzysztof | Michalski | NULL |
| Marek | Nowicki | 2TI |
| Joanna | Pawlak | 4TL |
| Ewelina | Sikora | NULL |
| Agnieszka | Wróbel | NULL |

Dla porównania — zwykły `JOIN`:

```sql
SELECT n.imie, n.nazwisko, k.nazwa
FROM nauczyciele n
JOIN klasy k ON k.id_wychowawcy = n.id
ORDER BY n.nazwisko;
```

Wynik: **5 wierszy**

| imie | nazwisko | nazwa |
|---|---|---|
| Monika | Adamczyk | 1TP |
| Rafał | Górski | 5TM |
| Tomasz | Kaczmarek | 4TI |
| Marek | Nowicki | 2TI |
| Joanna | Pawlak | 4TL |

> 💡 `LEFT JOIN`: **10** wierszy (5 osób ma `NULL` zamiast klasy). Zwykły `JOIN`: **5** wierszy — tylko wychowawcy.

---

## Część VI — Popraw błąd

### Zadanie 32

```sql
SELECT u.imie, k.nazwa
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id;
```

Wynik: **39 wierszy**

| imie | nazwa |
|---|---|
| Gabriela | 1TP |
| Oskar | 1TP |
| Jan | 1TP |
| Szymon | 1TP |
| Hanna | 1TP |
| … | … |

> 💡 Warunek `ON u.id = k.id` łączy numer **ucznia** z numerem **klasy** — wychodzi 5 przypadkowych par (np. Anna trafia do 4TI, choć chodzi do 4TL). Łączymy klucz obcy z kluczem głównym: `ON u.id_klasy = k.id` → **39** wierszy.

### Zadanie 33

```sql
SELECT u.imie, u.nazwisko, k.nazwa
FROM uczniowie u, klasy k
WHERE u.id_klasy = k.id;
```

Wynik: **39 wierszy**

| imie | nazwisko | nazwa |
|---|---|---|
| Gabriela | Dąbrowska | 1TP |
| Oskar | Czarnecki | 1TP |
| Jan | Kwiatkowski | 1TP |
| Szymon | Kalinowski | 1TP |
| Hanna | Bąk | 1TP |
| … | … | … |

> 💡 Brak warunku łączenia → **iloczyn kartezjański**: każdy uczeń z każdą klasą, 39 × 5 = 195. Poprawka: warunek w `WHERE` (albo `JOIN … ON`) → **39** wierszy.

### Zadanie 34

Zapytanie z błędem:

```sql
SELECT u.imie, u.nazwisko
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
WHERE uczniowie.id = 1;
```

Wynik: ❌ `#1054 - Unknown column 'uczniowie.id' in 'WHERE'`

Poprawione:

```sql
SELECT u.imie, u.nazwisko
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
WHERE u.id = 1;
```

Wynik: **1 wiersz**

| imie | nazwisko |
|---|---|
| Anna | Kowalska |

> 💡 Błąd **#1054** — *Unknown column 'uczniowie.id'* (w XAMPP: „in 'where clause'”). Tabela ma alias `u`, więc w tym zapytaniu nazwa `uczniowie` „nie istnieje”. Poprawka: `WHERE u.id = 1` → Anna Kowalska.

### Zadanie 35

```sql
SELECT ko.nazwa, COUNT(uk.id_ucznia) AS Zapisy
FROM kola ko
LEFT JOIN uczniowie_kola uk ON uk.id_kola = ko.id AND uk.data_zapisu >= '2026-09-15'
GROUP BY ko.nazwa
ORDER BY ko.nazwa;
```

Wynik: **6 wierszy**

| nazwa | Zapisy |
|---|---|
| Koło e-sportowe | 4 |
| Koło fotograficzne | 11 |
| Koło przygotowań do INF.03 | 6 |
| Koło robotyki | 6 |
| Koło szachowe | 0 |
| Szkolny klub siatkówki | 4 |

> 💡 `WHERE` działa **po** złączeniu. Dla koła szachowego `uk.data_zapisu` to `NULL`, a `NULL >= '2026-09-15'` nie jest prawdą — wiersz wypada i wychodzi 5 wierszy. Warunek dotyczący tabeli z prawej strony `LEFT JOIN` trzeba przenieść do `ON` → **6** wierszy, szachowe **0**.

---

## Część VII ⭐ — Wyzwania

### Zadanie 36

```sql
SELECT k.nazwa, CONCAT(n.imie, ' ', n.nazwisko) AS Wychowawca,
       COUNT(DISTINCT u.id) AS Uczniow, ROUND(AVG(o.ocena), 2) AS Srednia
FROM klasy k
JOIN nauczyciele n ON k.id_wychowawcy = n.id
JOIN uczniowie u ON u.id_klasy = k.id
JOIN oceny o ON o.id_ucznia = u.id
GROUP BY k.nazwa, n.imie, n.nazwisko
ORDER BY Srednia DESC;
```

Wynik: **5 wierszy**

| nazwa | Wychowawca | Uczniow | Srednia |
|---|---|---|---|
| 2TI | Marek Nowicki | 8 | 4.81 |
| 1TP | Monika Adamczyk | 8 | 4.50 |
| 4TL | Joanna Pawlak | 8 | 3.98 |
| 5TM | Rafał Górski | 7 | 3.95 |
| 4TI | Tomasz Kaczmarek | 8 | 3.91 |

> 💡 Po doklejeniu ocen każdy uczeń powtarza się tyle razy, ile ma ocen — dlatego uczniów liczymy `COUNT(DISTINCT u.id)`. Z `COUNT(*)` wyszłyby liczby **ocen** (np. 84 dla 2TI zamiast 8 uczniów).

### Zadanie 37

```sql
SELECT u.imie, u.nazwisko, k.nazwa AS klasa, ko.nazwa AS kolo
FROM uczniowie u
JOIN klasy k ON u.id_klasy = k.id
JOIN uczniowie_kola uk ON uk.id_ucznia = u.id
JOIN kola ko ON uk.id_kola = ko.id
WHERE ko.id_opiekuna = k.id_wychowawcy;
```

Wynik: **5 wierszy**

| imie | nazwisko | klasa | kolo |
|---|---|---|---|
| Łukasz | Ostrowski | 2TI | Koło e-sportowe |
| Bartosz | Nowak | 4TI | Koło przygotowań do INF.03 |
| Hubert | Kamiński | 4TI | Koło przygotowań do INF.03 |
| Amelia | Stępień | 4TI | Koło przygotowań do INF.03 |
| Hanna | Wójtowicz | 4TI | Koło przygotowań do INF.03 |

> 💡 **5** osób: Łukasz Ostrowski (2TI, koło e-sportowe) i czworo uczniów 4TI na kole przygotowań do INF.03.

### Zadanie 38

```sql
SELECT ko.nazwa, ROUND(AVG(o.ocena), 2) AS Srednia
FROM kola ko
JOIN uczniowie_kola uk ON uk.id_kola = ko.id
JOIN oceny o ON o.id_ucznia = uk.id_ucznia
GROUP BY ko.nazwa
ORDER BY Srednia DESC;
```

Wynik: **5 wierszy**

| nazwa | Srednia |
|---|---|
| Koło fotograficzne | 4.34 |
| Koło robotyki | 4.29 |
| Koło przygotowań do INF.03 | 4.25 |
| Koło e-sportowe | 4.08 |
| Szkolny klub siatkówki | 3.85 |

> 💡 Najlepsi uczniowie chodzą na **Koło fotograficzne** (4.34). Tabela `uczniowie` nie jest potrzebna — `uczniowie_kola` i `oceny` mają wspólną kolumnę `id_ucznia`.

### Zadanie 39

```sql
SELECT k.nazwa, COUNT(DISTINCT o.id_ucznia) AS Uczniow
FROM oceny o
JOIN uczniowie u ON o.id_ucznia = u.id
JOIN klasy k ON u.id_klasy = k.id
WHERE o.ocena < 3
GROUP BY k.nazwa
ORDER BY Uczniow DESC, k.nazwa;
```

Wynik: **5 wierszy**

| nazwa | Uczniow |
|---|---|
| 4TI | 4 |
| 5TM | 4 |
| 1TP | 3 |
| 4TL | 3 |
| 2TI | 1 |

> 💡 4TI i 5TM — po **4** uczniów, 1TP i 4TL — po 3, 2TI — 1. Jeden uczeń może mieć kilka ocen poniżej 3, dlatego `COUNT(DISTINCT o.id_ucznia)`, a nie `COUNT(*)`.

### Zadanie 40

a)

```sql
SELECT k.nazwa AS Kraj, m.nazwa AS Stolica
FROM kraje k
JOIN miasta m ON k.stolica = m.id
WHERE k.kontynent = 'Europa'
ORDER BY k.nazwa;
```

Wynik: **46 wierszy**

| Kraj | Stolica |
|---|---|
| Albania | Tirana |
| Andorra | Andorra la Vella |
| Austria | Wien |
| Belarus | Minsk |
| Belgium | Bruxelles [Brussel] |
| … | … |

b)

```sql
SELECT m.nazwa AS Stolica, k.nazwa AS Kraj, m.liczba_mieszkancow
FROM kraje k
JOIN miasta m ON k.stolica = m.id
ORDER BY m.liczba_mieszkancow DESC
LIMIT 3;
```

Wynik: **3 wiersze**

| Stolica | Kraj | liczba_mieszkancow |
|---|---|---|
| Seoul | South Korea | 9981619 |
| Jakarta | Indonesia | 9604900 |
| Ciudad de México | Mexico | 8591309 |

> 💡 a) **46** krajów. b) Największa stolica to **Seoul** (Korea Południowa), potem Jakarta i Ciudad de México.

### Zadanie 41

```sql
SELECT k.nazwa
FROM kraje k
LEFT JOIN miasta m ON m.kod_kraju = k.kod
WHERE m.id IS NULL
ORDER BY k.nazwa;
```

Wynik: **7 wierszy**

| nazwa |
|---|
| Antarktyda |
| Bouvet Island |
| British Indian Ocean Territory |
| French Southern territories |
| Heard Island and McDonald Islands |
| South Georgia and the South Sandwich Islands |
| United States Minor Outlying Islands |

> 💡 **7** krajów (głównie bezludne terytoria i Antarktyda).

---

## Pytania kontrolne — odpowiedzi

1. `JOIN` dokleja do wierszy pierwszej tabeli pasujące wiersze drugiej; `ON` mówi, które wiersze do siebie pasują.
2. Klucz obcy = klucz główny, np. `ON uczniowie.id_klasy = klasy.id`.
3. Skracają zapis i rozróżniają tabele. Po nadaniu aliasu pełna nazwa tabeli daje błąd #1054 (Unknown column).
4. Kolumna o tej nazwie jest w kilku łączonych tabelach — trzeba dopisać przed nią alias (`u.id`).
5. `JOIN` zwraca tylko pary; `LEFT JOIN` — wszystkie wiersze lewej tabeli, a brak pary wypełnia `NULL`.
   `JOIN`: „pokaż powiązane”; `LEFT JOIN`: „pokaż wszystkich, nawet bez pary” albo „znajdź tych bez pary”.
6. `LEFT JOIN … WHERE prawa_tabela.klucz IS NULL`.
7. `COUNT(*)` policzy też wiersz z `NULL`-ami, który `LEFT JOIN` tworzy dla wiersza bez pary (wynik 1 zamiast 0).
8. Trzy: dwie tabele (np. `uczniowie`, `kola`) + tabela łącząca w środku (`uczniowie_kola`), czyli dwa `JOIN`-y —
   bo pary uczeń–koło są zapisane tylko w tabeli łączącej.
9. Iloczyn kartezjański — każdy wiersz z każdym (39 × 5 = 195).
10. `FROM uczniowie JOIN klasy ON uczniowie.id_klasy = klasy.id` ⇔ `FROM uczniowie, klasy WHERE uczniowie.id_klasy = klasy.id`.
