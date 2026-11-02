# Zestaw treningowy 1 — odpowiedzi

Wszystkie wyniki zostały sprawdzone na bazie `sklep` (plik `sklep.sql`, MariaDB 11).

**Jak korzystać:**
- Twoje zapytanie **nie musi** wyglądać identycznie jak wzorcowe — ważne, żeby dawało ten sam wynik.
  Inna kolejność kolumn, inne aliasy albo `JOIN` zamiast zapisu z przecinkami są w porządku.
- Kolejność wierszy ma znaczenie tylko wtedy, gdy zadanie każe sortować.
- Przy dłuższych wynikach pokazane jest tylko 5 pierwszych wierszy — liczbę wszystkich podaje nagłówek.
- Kwoty i średnie z bazy mają kilka miejsc po przecinku (np. `3.8510`) — to normalne, `AVG` tak zwraca.

## Szybkie sprawdzanie

| Nr | Odpowiedź | Nr | Odpowiedź |
|---|---|---|---|
| 1 | **11** kategorii | 51 | **Karty podarunkowe** — 0 produktów; wynik ma **11** wierszy |
| 2 | **Laptop Apple MacBook Pro 14 M4** — **8999.00 zł** | 52 | **9** produktów |
| 3 | **36** klientów | 53 | **Helion, Samsung, Sony, Xiaomi** (4 producentów) |
| 4 | **1492** zamówień | 54 | miesiąc **10** — **102** zamówień |
| 5 | **12** produktów | 55 | **Maria Jabłońska** — **18** zamówień |
| 6 | **12** krajów, pierwszy: **Chiny** | 56 | **92** zamówień |
| 7 | **Ferdydurke** — **32.99 zł** | 57 | **780275.95 zł** w 2025 (i 483114.15 zł w 2026) |
| 8 | **92** klientów | 58 | **paczkomat + blik** — **285** zamówień (wynik ma 11 wierszy) |
| 9 | **11** produktów | 59 | **Laptop Dell Latitude 5440** — **5.00** (2 opinii) |
| 10 | **117** zamówień | 60 | **9** produktów |
| 11 | **43** produktów | 61 | **Nokia** (1 producent) |
| 12 | **38** klientów | 62 | **22** klientów |
| 13 | **42** zamówień | 63 | **Marta Zalewska** (Poznań) — **16** opinii |
| 14 | **143** klientów | 64 | **159** zamówień, **244** sztuk |
| 15 | **24** produktów, pierwszy: **Bidon Decathlon 0,75 l** | 65 | **Znak** — **4.13** (105 opinii) |
| 16 | **Krzysztof Dąbrowski**, ur. **1955-07-16** | 66 | **2899.00 zł** (Sport) |
| 17 | **26** miast, pierwsze: **Zielona Góra** | 67 | **Poznań** — **167** zamówień |
| 18 | **3.8300** (≈ 3.83) | 68 | **5** zamówień |
| 19 | **5** produktów | 69 | **432** pozycji |
| 20 | **348** opinii | 70 | **8** wierszy |
| 21 | **Dawid Kamiński**, łącznie **8** wierszy | 71 | **25** wierszy, ostatni: **Soundbar Sony HT-S100F** |
| 22 | **Wrocław** — **38** klientów | 72 | **Zofia Jankowska** (Białystok) — **24769.30 zł** |
| 23 | **6** produktów, najdroższy jest w kategorii **Laptopy** | 73 | **Laptopy** — **336532.75 zł** |
| 24 | **112** anulowanych (wynik ma 5 wierszy) | 74 | **Kraków: 209.78 zł**, **Gdańsk: 329.96 zł** |
| 25 | **Smartfon Apple iPhone 16 Pro** — **1449.76 zł** | 75 | bez opinii: **3** — Smartfon Apple iPhone 16 Pro, Smartfon Xiaomi 14T, Smartfon Sony Xperia 10 VI |
| 26 | **298** klientów | 76 | **55** klientów |
| 27 | **44** klientów | 77 | **16** klientów |
| 28 | **Kosiarka Bosch ARM 37** | 78 | zamówienie **867** — **514.96 zł** |
| 29 | **6** produktów, najtańszy: **Słuchawki Apple AirPods 4** | 79 | **5** produktów |
| 30 | **7.08 zł** (kurier, 521 zamówień) | 80 | **12** produktów |
| 31 | **262** opinii z oceną 5 | 81 | miesiące: **3, 5, 11, 12** (4) |
| 32 | **7** klientów | 82 | **Polska** — **1457** szt. |
| 33 | **Laptop Dell XPS 13** — **902871.00 zł** | 83 | **64** klientów |
| 34 | **151** zamówień | 84 | **paczkomat** — **118** zamówień |
| 35 | **7** zamówień, najnowsze: **nowe** (2026-10-29) | 85 | **212** zamówień |
| 36 | **4295** sztuk | 86 | **Dom i ogród** — **3.53** |
| 37 | **2025-01-03** i **2026-10-31** | 87 | **Laptop Dell XPS 13** — **41994.00 zł** |
| 38 | **88** | 88 | **6** klientów |
| 39 | **893** zamówień w 2025 (i 599 w 2026) | 89 | Helion: **8** produktów, **507** sztuk |
| 40 | **15** opinii, najnowsza: **Lalka** | 90 | Książki: **13** produktów, **1049** sztuk, **54404.83 zł** |
| 41 | **9** miast | 91 | **11** wierszy; Laptopy: **11** produktów, **64** pozycji |
| 42 | **25** miast | 92 | **6** miesięcy; wrzesień: **67** zamówień, **57** klientów |
| 43 | **1113.43 zł** (min 14.99, max 8999.00) | 93 | **11** opinii, pierwsza: **Ewelina Krawczyk** |
| 44 | **6** książek, najtańsza: **Pan Tadeusz** (24.99 zł) | 94 | **175** klientów |
| 45 | **90** klientów | 95 | **58** klientów, w tym **6** ze wszystkich 10 kategorii |
| 46 | **Akcesoria komputerowe** — **19** produktów; wynik ma **10** wierszy (o 1 mniej niż kategorii!) | 96 | **Warszawa** — **71156.95 zł** |
| 47 | **Kross** — **1622.00 zł** | 97 | **Klawiatura Logitech K120** — **630.63 zł** (40 pozycji) |
| 48 | **Ferdydurke** — **161** szt. | 98 | **Gardena, Fiskars, Logitech** (3) |
| 49 | **45.99 zł** | 99 | **7** klientów; 1. miejsce: **Marta Piotrowska** — **23** zamówień, **26178.47 zł** |
| 50 | **12** produktów, pierwszy: **Gra Gran Turismo 7** | 100 | **Natalia Pawlak** — **25** książek, **1332.84 zł** |

---

## ★ Poziom 1 · Rozgrzewka — jedna tabela

### Zadanie 1 · SELECT *

**Odpowiedź:** **11** kategorii

```sql
SELECT * FROM kategorie;
```

Wynik: **11 wierszy**

| id | nazwa |
|---|---|
| 5 | AGD |
| 4 | Akcesoria komputerowe |
| 3 | Audio |
| 10 | Dom i ogród |
| 6 | Gry i konsole |
| … | … |

### Zadanie 2 · ORDER BY DESC

**Odpowiedź:** **Laptop Apple MacBook Pro 14 M4** — **8999.00 zł**

```sql
SELECT nazwa, cena FROM produkty ORDER BY cena DESC;
```

Wynik: **119 wierszy**

| nazwa | cena |
|---|---|
| Laptop Apple MacBook Pro 14 M4 | 8999.00 |
| Laptop Dell XPS 13 | 6999.00 |
| Laptop Asus ROG Strix G16 | 6499.00 |
| Laptop Lenovo Legion 5 | 5999.00 |
| Smartfon Apple iPhone 16 Pro | 5799.00 |
| … | … |

### Zadanie 3 · WHERE =

**Odpowiedź:** **36** klientów

```sql
SELECT imie, nazwisko FROM klienci WHERE miasto = 'Kraków';
```

Wynik: **36 wierszy**

| imie | nazwisko |
|---|---|
| Patrycja | Wójcik |
| Katarzyna | Lewandowska |
| Weronika | Nowak |
| Magdalena | Kowalska |
| Monika | Mazur |
| … | … |

### Zadanie 4 · COUNT(*)

**Odpowiedź:** **1492** zamówień

```sql
SELECT COUNT(*) AS LiczbaZamowien FROM zamowienia;
```

Wynik: **1 wiersz**

| LiczbaZamowien |
|---|
| 1492 |

### Zadanie 5 · WHERE liczba

**Odpowiedź:** **12** produktów

```sql
SELECT nazwa FROM produkty WHERE stan_magazynowy = 0;
```

Wynik: **12 wierszy**

| nazwa |
|---|
| Klawiatura Logitech K120 |
| Hub USB-C Lenovo |
| Konsola Sony PlayStation 5 Slim |
| Gra Mario Kart 8 Deluxe |
| Gra Zelda Tears of the Kingdom |
| … |

### Zadanie 6 · DISTINCT, ORDER BY

**Odpowiedź:** **12** krajów, pierwszy: **Chiny**

```sql
SELECT DISTINCT kraj FROM producenci ORDER BY kraj;
```

Wynik: **12 wierszy**

| kraj |
|---|
| Chiny |
| Dania |
| Finlandia |
| Francja |
| Holandia |
| … |

> ⚠️ Bez `DISTINCT` wychodzi 25 wierszy — po jednym na każdego producenta.

### Zadanie 7 · ORDER BY, LIMIT

**Odpowiedź:** **Ferdydurke** — **32.99 zł**

```sql
SELECT nazwa, cena FROM produkty ORDER BY cena LIMIT 5;
```

Wynik: **5 wierszy**

| nazwa | cena |
|---|---|
| Żarówka Philips LED E27 | 14.99 |
| Bidon Decathlon 0,75 l | 19.99 |
| Pan Tadeusz | 24.99 |
| Puzzle Trefl 500 el. Tatry | 29.99 |
| Ferdydurke | 32.99 |

### Zadanie 8 · IS NULL

**Odpowiedź:** **92** klientów

```sql
SELECT imie, nazwisko, email FROM klienci WHERE telefon IS NULL;
```

Wynik: **92 wiersze**

| imie | nazwisko | email |
|---|---|---|
| Kacper | Sadowski | kacper.sadowski@gmail.com |
| Kamil | Stępień | kamil.stepien@gmail.com |
| Grzegorz | Jasiński | grzegorz.jasinski@o2.pl |
| Magdalena | Kowalska | magdalena.kowalska@gmail.com |
| Katarzyna | Górska | katarzyna.gorska@o2.pl |
| … | … | … |

> ⚠️ `WHERE telefon = NULL` zwraca **0** wierszy — porównanie z `NULL` nigdy nie jest prawdziwe.

### Zadanie 9 · LIKE 'x%'

**Odpowiedź:** **11** produktów

```sql
SELECT * FROM produkty WHERE nazwa LIKE 'Laptop%';
```

Wynik: **11 wierszy**

| id | nazwa | id_kategorii | id_producenta | cena | cena_promocyjna | stan_magazynowy | data_dodania |
|---|---|---|---|---|---|---|---|
| 7 | Laptop Apple MacBook Air 13 M3 | 1 | 3 | 5299.00 | NULL | 32 | 2025-09-28 |
| 8 | Laptop Apple MacBook Pro 14 M4 | 1 | 3 | 8999.00 | NULL | 31 | 2024-12-20 |
| 10 | Laptop Asus ROG Strix G16 | 1 | 4 | 6499.00 | NULL | 70 | 2024-05-29 |
| 9 | Laptop Asus VivoBook 15 | 1 | 4 | 2199.00 | NULL | 88 | 2023-11-23 |
| 11 | Laptop Asus ZenBook 14 | 1 | 4 | 4299.00 | NULL | 66 | 2024-11-24 |
| … | … | … | … | … | … | … | … |

### Zadanie 10 · BETWEEN — daty

**Odpowiedź:** **117** zamówień

```sql
SELECT * FROM zamowienia WHERE data_zamowienia BETWEEN '2025-11-01' AND '2025-11-30';
```

Wynik: **117 wierszy**

| id | id_klienta | data_zamowienia | status | sposob_dostawy | sposob_platnosci | koszt_dostawy |
|---|---|---|---|---|---|---|
| 626 | 25 | 2025-11-01 | dostarczone | paczkomat | pobranie | 0.00 |
| 627 | 84 | 2025-11-01 | dostarczone | kurier | pobranie | 0.00 |
| 628 | 175 | 2025-11-01 | anulowane | paczkomat | przelew | 0.00 |
| 629 | 303 | 2025-11-01 | dostarczone | paczkomat | pobranie | 9.99 |
| 630 | 44 | 2025-11-02 | dostarczone | paczkomat | karta | 9.99 |
| … | … | … | … | … | … | … |

### Zadanie 11 · BETWEEN — liczby

**Odpowiedź:** **43** produktów

```sql
SELECT nazwa, cena FROM produkty WHERE cena BETWEEN 100 AND 500;
```

Wynik: **43 wiersze**

| nazwa | cena |
|---|---|
| Słuchawki Sony WH-CH520 | 199.00 |
| Słuchawki JBL Tune 520BT | 229.00 |
| Słuchawki Xiaomi Redmi Buds 6 | 129.00 |
| Słuchawki SteelSeries Arctis Nova 1 | 269.00 |
| Głośnik JBL Flip 6 | 499.00 |
| … | … |

> ⚠️ W bazie są produkty kosztujące **dokładnie** 100.00 i 500.00 zł. `cena > 100 AND cena < 500` daje 41 zamiast 43.

### Zadanie 12 · IN

**Odpowiedź:** **38** klientów

```sql
SELECT imie, nazwisko, miasto FROM klienci WHERE miasto IN ('Gdańsk', 'Gdynia', 'Sopot');
```

Wynik: **38 wierszy**

| imie | nazwisko | miasto |
|---|---|---|
| Oskar | Piotrowski | Gdańsk |
| Natalia | Pawłowska | Gdynia |
| Grzegorz | Jasiński | Gdańsk |
| Paweł | Michalak | Gdańsk |
| Marek | Sadowski | Gdynia |
| … | … | … |

### Zadanie 13 · WHERE AND

**Odpowiedź:** **42** zamówień

```sql
SELECT * FROM zamowienia WHERE status = 'anulowane' AND sposob_platnosci = 'blik';
```

Wynik: **42 wiersze**

| id | id_klienta | data_zamowienia | status | sposob_dostawy | sposob_platnosci | koszt_dostawy |
|---|---|---|---|---|---|---|
| 9 | 40 | 2025-01-07 | anulowane | paczkomat | blik | 9.99 |
| 14 | 11 | 2025-01-11 | anulowane | kurier | blik | 14.99 |
| 24 | 148 | 2025-01-17 | anulowane | paczkomat | blik | 9.99 |
| 77 | 84 | 2025-02-17 | anulowane | odbior osobisty | blik | 0.00 |
| 114 | 39 | 2025-03-06 | anulowane | paczkomat | blik | 0.00 |
| … | … | … | … | … | … | … |

### Zadanie 14 · LIKE '%x'

**Odpowiedź:** **143** klientów

```sql
SELECT imie, nazwisko, email FROM klienci WHERE email LIKE '%@gmail.com';
```

Wynik: **143 wiersze**

| imie | nazwisko | email |
|---|---|---|
| Kacper | Sadowski | kacper.sadowski@gmail.com |
| Tomasz | Adamczyk | tomasz.adamczyk@gmail.com |
| Kamil | Stępień | kamil.stepien@gmail.com |
| Kacper | Dąbrowski | kacper.dabrowski@gmail.com |
| Katarzyna | Ostrowska | katarzyna.ostrowska@gmail.com |
| … | … | … |

### Zadanie 15 · IS NOT NULL, ORDER BY

**Odpowiedź:** **24** produktów, pierwszy: **Bidon Decathlon 0,75 l**

```sql
SELECT nazwa, cena, cena_promocyjna FROM produkty WHERE cena_promocyjna IS NOT NULL ORDER BY nazwa;
```

Wynik: **24 wiersze**

| nazwa | cena | cena_promocyjna |
|---|---|---|
| Bidon Decathlon 0,75 l | 19.99 | 17.98 |
| Blender Bosch ErgoMixx | 279.00 | 237.14 |
| Czajnik Bosch TWK3A011 | 129.99 | 110.48 |
| Frytkownica Philips Airfryer XL | 599.99 | 539.98 |
| Frytkownica Tefal Easy Fry | 449.99 | 404.98 |
| … | … | … |

### Zadanie 16 · ORDER BY, LIMIT 1

**Odpowiedź:** **Krzysztof Dąbrowski**, ur. **1955-07-16**

```sql
SELECT imie, nazwisko, data_urodzenia FROM klienci ORDER BY data_urodzenia LIMIT 1;
```

Wynik: **1 wiersz**

| imie | nazwisko | data_urodzenia |
|---|---|---|
| Krzysztof | Dąbrowski | 1955-07-16 |

> ⚠️ Częsty błąd: `ORDER BY data_urodzenia DESC` — to daje **najmłodszego** klienta.

### Zadanie 17 · DISTINCT, ORDER BY DESC

**Odpowiedź:** **26** miast, pierwsze: **Zielona Góra**

```sql
SELECT DISTINCT miasto FROM klienci ORDER BY miasto DESC;
```

Wynik: **26 wierszy**

| miasto |
|---|
| Zielona Góra |
| Zakopane |
| Wrocław |
| Warszawa |
| Toruń |
| … |

> ⚠️ Baza używa polskiego porządku alfabetycznego: „Ł” to osobna litera po „L”, więc przy sortowaniu malejącym „Łódź” stoi tuż przed „Lublin”.

### Zadanie 18 · AVG

**Odpowiedź:** **3.8300** (≈ 3.83)

```sql
SELECT AVG(ocena) AS SredniaOcena FROM opinie;
```

Wynik: **1 wiersz**

| SredniaOcena |
|---|
| 3.8300 |

### Zadanie 19 · WHERE AND, porównania

**Odpowiedź:** **5** produktów

```sql
SELECT nazwa, cena, stan_magazynowy FROM produkty WHERE cena > 1000 AND stan_magazynowy < 20;
```

Wynik: **5 wierszy**

| nazwa | cena | stan_magazynowy |
|---|---|---|
| Laptop Dell Inspiron 15 | 2799.00 | 19 |
| Monitor Asus TUF VG27AQ | 1249.00 | 6 |
| Konsola Sony PlayStation 5 Slim | 2399.00 | 0 |
| Konsola Microsoft Xbox Series X | 2499.99 | 12 |
| Rower Kross Evado 4.0 | 2499.50 | 0 |

### Zadanie 20 · COUNT + IS NULL

**Odpowiedź:** **348** opinii

```sql
SELECT COUNT(*) AS BezKomentarza FROM opinie WHERE tresc IS NULL;
```

Wynik: **1 wiersz**

| BezKomentarza |
|---|
| 348 |

> ⚠️ Inny sposób: `SELECT COUNT(*) - COUNT(tresc) FROM opinie;` — `COUNT(kolumna)` nie liczy wartości `NULL`.

---

## ★★ Poziom 2 · Funkcje, grupowanie i pierwsze złączenia

### Zadanie 21 · CONCAT, AS, ORDER BY 2 kolumny

**Odpowiedź:** **Dawid Kamiński**, łącznie **8** wierszy

```sql
SELECT CONCAT(imie, ' ', nazwisko) AS Klient FROM klienci WHERE miasto = 'Lublin' ORDER BY nazwisko, imie;
```

Wynik: **8 wierszy**

| Klient |
|---|
| Dawid Kamiński |
| Grzegorz Kowalski |
| Justyna Lewandowska |
| Maria Majewska |
| Natalia Nowicka |
| Wojciech Sikora |
| Marek Wiśniewski |
| Andrzej Wróblewski |

### Zadanie 22 · GROUP BY, COUNT, ORDER BY

**Odpowiedź:** **Wrocław** — **38** klientów

```sql
SELECT miasto, COUNT(*) AS LiczbaKlientow FROM klienci GROUP BY miasto ORDER BY LiczbaKlientow DESC;
```

Wynik: **26 wierszy**

| miasto | LiczbaKlientow |
|---|---|
| Warszawa | 46 |
| Wrocław | 38 |
| Kraków | 36 |
| Poznań | 30 |
| Gdańsk | 26 |
| … | … |

### Zadanie 23 · JOIN 2 tabele

**Odpowiedź:** **6** produktów, najdroższy jest w kategorii **Laptopy**

```sql
SELECT p.nazwa, p.cena, kat.nazwa AS kategoria
FROM produkty p
JOIN kategorie kat ON p.id_kategorii = kat.id
WHERE p.cena > 5000
ORDER BY p.cena DESC;
```

Wynik: **6 wierszy**

| nazwa | cena | kategoria |
|---|---|---|
| Laptop Apple MacBook Pro 14 M4 | 8999.00 | Laptopy |
| Laptop Dell XPS 13 | 6999.00 | Laptopy |
| Laptop Asus ROG Strix G16 | 6499.00 | Laptopy |
| Laptop Lenovo Legion 5 | 5999.00 | Laptopy |
| Smartfon Apple iPhone 16 Pro | 5799.00 | Smartfony |
| Laptop Apple MacBook Air 13 M3 | 5299.00 | Laptopy |

### Zadanie 24 · GROUP BY

**Odpowiedź:** **112** anulowanych (wynik ma 5 wierszy)

```sql
SELECT status, COUNT(*) AS Ile FROM zamowienia GROUP BY status;
```

Wynik: **5 wierszy**

| status | Ile |
|---|---|
| nowe | 4 |
| oplacone | 4 |
| wyslane | 20 |
| dostarczone | 1352 |
| anulowane | 112 |

### Zadanie 25 · kolumna obliczana

**Odpowiedź:** **Smartfon Apple iPhone 16 Pro** — **1449.76 zł**

```sql
SELECT nazwa, cena - cena_promocyjna AS Obnizka
FROM produkty
WHERE cena_promocyjna IS NOT NULL
ORDER BY Obnizka DESC;
```

Wynik: **24 wiersze**

| nazwa | Obnizka |
|---|---|
| Smartfon Apple iPhone 16 Pro | 1449.76 |
| Konsola Sony PlayStation 5 Slim | 599.76 |
| Laptop Dell Inspiron 15 | 559.81 |
| Laptop Dell Latitude 5440 | 459.91 |
| Konsola Nintendo Switch OLED | 300.01 |
| … | … |

> ⚠️ Bez `WHERE … IS NOT NULL` w wyniku będą też wiersze z `NULL` (odejmowanie od `NULL` daje `NULL`).

### Zadanie 26 · COUNT(DISTINCT)

**Odpowiedź:** **298** klientów

```sql
SELECT COUNT(DISTINCT id_klienta) AS Klienci FROM zamowienia;
```

Wynik: **1 wiersz**

| Klienci |
|---|
| 298 |

> ⚠️ `COUNT(id_klienta)` daje liczbę **zamówień** (1492), a nie klientów.

### Zadanie 27 · YEAR()

**Odpowiedź:** **44** klientów

```sql
SELECT COUNT(*) AS Ile FROM klienci WHERE YEAR(data_urodzenia) >= 2000;
```

Wynik: **1 wiersz**

| Ile |
|---|
| 44 |

### Zadanie 28 · LIMIT + OFFSET

**Odpowiedź:** **Kosiarka Bosch ARM 37**

```sql
SELECT nazwa FROM produkty ORDER BY nazwa LIMIT 20 OFFSET 40;
```

Wynik: **20 wierszy**

| nazwa |
|---|
| Kosiarka Bosch ARM 37 |
| Lalka |
| Lampa Philips Hue White |
| Laptop Apple MacBook Air 13 M3 |
| Laptop Apple MacBook Pro 14 M4 |
| … |

> ⚠️ Częsty błąd: `OFFSET 60` (to już 4. strona) albo `OFFSET 3`.

### Zadanie 29 · JOIN + WHERE po nazwie

**Odpowiedź:** **6** produktów, najtańszy: **Słuchawki Apple AirPods 4**

```sql
SELECT p.nazwa, p.cena
FROM produkty p
JOIN producenci pr ON p.id_producenta = pr.id
WHERE pr.nazwa = 'Apple'
ORDER BY p.cena;
```

Wynik: **6 wierszy**

| nazwa | cena |
|---|---|
| Słuchawki Apple AirPods 4 | 649.00 |
| Słuchawki Apple AirPods Pro 2 | 1149.00 |
| Smartfon Apple iPhone 15 | 3799.00 |
| Laptop Apple MacBook Air 13 M3 | 5299.00 |
| Smartfon Apple iPhone 16 Pro | 5799.00 |
| Laptop Apple MacBook Pro 14 M4 | 8999.00 |

### Zadanie 30 · GROUP BY, AVG, ROUND

**Odpowiedź:** **7.08 zł** (kurier, 521 zamówień)

```sql
SELECT sposob_dostawy, COUNT(*) AS Zamowienia, ROUND(AVG(koszt_dostawy), 2) AS SredniKoszt
FROM zamowienia
GROUP BY sposob_dostawy;
```

Wynik: **3 wiersze**

| sposob_dostawy | Zamowienia | SredniKoszt |
|---|---|---|
| kurier | 521 | 7.08 |
| paczkomat | 816 | 4.68 |
| odbior osobisty | 155 | 0.00 |

> ⚠️ Średni koszt jest niższy niż 14,99 zł, bo zamówienia od 300 zł mają darmową dostawę (koszt 0.00).

### Zadanie 31 · GROUP BY, ORDER BY

**Odpowiedź:** **262** opinii z oceną 5

```sql
SELECT ocena, COUNT(*) AS Ile FROM opinie GROUP BY ocena ORDER BY ocena;
```

Wynik: **5 wierszy**

| ocena | Ile |
|---|---|
| 1 | 15 |
| 2 | 71 |
| 3 | 221 |
| 4 | 290 |
| 5 | 262 |

### Zadanie 32 · GROUP BY + HAVING

**Odpowiedź:** **7** klientów

```sql
SELECT id_klienta, COUNT(*) AS Zamowienia FROM zamowienia GROUP BY id_klienta HAVING COUNT(*) >= 20;
```

Wynik: **7 wierszy**

| id_klienta | Zamowienia |
|---|---|
| 33 | 23 |
| 78 | 23 |
| 84 | 21 |
| 141 | 23 |
| 157 | 23 |
| 216 | 24 |
| 303 | 21 |

> ⚠️ `WHERE COUNT(*) >= 20` kończy się błędem #1111 (Invalid use of group function).

### Zadanie 33 · kolumna obliczana, ORDER BY alias

**Odpowiedź:** **Laptop Dell XPS 13** — **902871.00 zł**

```sql
SELECT nazwa, cena * stan_magazynowy AS WartoscMagazynu FROM produkty ORDER BY WartoscMagazynu DESC;
```

Wynik: **119 wierszy**

| nazwa | WartoscMagazynu |
|---|---|
| Laptop Dell XPS 13 | 902871.00 |
| Laptop Lenovo Legion 5 | 683886.00 |
| Laptop Dell Latitude 5440 | 643860.00 |
| Smartfon Samsung Galaxy S24 | 455886.00 |
| Laptop Asus ROG Strix G16 | 454930.00 |
| … | … |

### Zadanie 34 · MONTH()

**Odpowiedź:** **151** zamówień

```sql
SELECT COUNT(*) AS Grudzien FROM zamowienia WHERE MONTH(data_zamowienia) = 12;
```

Wynik: **1 wiersz**

| Grudzien |
|---|
| 151 |

### Zadanie 35 · JOIN + WHERE

**Odpowiedź:** **7** zamówień, najnowsze: **nowe** (2026-10-29)

```sql
SELECT k.imie, k.nazwisko, z.data_zamowienia, z.status
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
WHERE k.miasto = 'Zakopane'
ORDER BY z.data_zamowienia;
```

Wynik: **7 wierszy**

| imie | nazwisko | data_zamowienia | status |
|---|---|---|---|
| Maria | Pawłowska | 2025-09-03 | dostarczone |
| Maria | Pawłowska | 2025-11-19 | dostarczone |
| Maria | Pawłowska | 2025-11-29 | dostarczone |
| Maria | Pawłowska | 2026-01-27 | dostarczone |
| Maria | Pawłowska | 2026-03-12 | dostarczone |
| Anna | Wróbel | 2026-09-18 | anulowane |
| Magdalena | Michalak | 2026-10-29 | nowe |

### Zadanie 36 · SUM

**Odpowiedź:** **4295** sztuk

```sql
SELECT SUM(ilosc) AS Sztuk FROM pozycje_zamowienia;
```

Wynik: **1 wiersz**

| Sztuk |
|---|
| 4295 |

> ⚠️ `COUNT(*)` daje 3087 — to liczba **pozycji**, a nie sztuk (w jednej pozycji może być kilka sztuk).

### Zadanie 37 · MIN, MAX

**Odpowiedź:** **2025-01-03** i **2026-10-31**

```sql
SELECT MIN(data_zamowienia) AS Pierwsze, MAX(data_zamowienia) AS Ostatnie FROM zamowienia;
```

Wynik: **1 wiersz**

| Pierwsze | Ostatnie |
|---|---|
| 2025-01-03 | 2026-10-31 |

### Zadanie 38 · LIKE + COUNT

**Odpowiedź:** **88**

```sql
SELECT COUNT(*) AS Ile FROM klienci WHERE nazwisko LIKE '%ska';
```

Wynik: **1 wiersz**

| Ile |
|---|
| 88 |

> ⚠️ `'%ska%'` daje ten sam wynik w tej bazie, ale to przypadek — wzorzec jest nieprecyzyjny.

### Zadanie 39 · YEAR() + GROUP BY

**Odpowiedź:** **893** zamówień w 2025 (i 599 w 2026)

```sql
SELECT YEAR(data_zamowienia) AS Rok, COUNT(*) AS Zamowienia FROM zamowienia GROUP BY YEAR(data_zamowienia);
```

Wynik: **2 wiersze**

| Rok | Zamowienia |
|---|---|
| 2025 | 893 |
| 2026 | 599 |

### Zadanie 40 · JOIN + WHERE + ORDER BY

**Odpowiedź:** **15** opinii, najnowsza: **Lalka**

```sql
SELECT p.nazwa, o.tresc, o.data_opinii
FROM opinie o
JOIN produkty p ON o.id_produktu = p.id
WHERE o.ocena = 1
ORDER BY o.data_opinii DESC;
```

Wynik: **15 wierszy**

| nazwa | tresc | data_opinii |
|---|---|---|
| Lalka | Produkt niezgodny z opisem! | 2026-09-16 |
| Bidon Decathlon 0,75 l | Zwróciłem po tygodniu. | 2026-09-15 |
| Pan Tadeusz | NULL | 2026-02-15 |
| Podkładka SteelSeries QcK Large | Totalna porażka. | 2026-01-14 |
| Bidon Decathlon 0,75 l | Totalna porażka. | 2026-01-01 |
| … | … | … |

### Zadanie 41 · GROUP BY + HAVING

**Odpowiedź:** **9** miast

```sql
SELECT miasto, COUNT(*) AS Klienci FROM klienci GROUP BY miasto HAVING COUNT(*) >= 10;
```

Wynik: **9 wierszy**

| miasto | Klienci |
|---|---|
| Bydgoszcz | 11 |
| Gdańsk | 26 |
| Gdynia | 11 |
| Katowice | 13 |
| Kraków | 36 |
| … | … |

### Zadanie 42 · COUNT(DISTINCT) + WHERE

**Odpowiedź:** **25** miast

```sql
SELECT COUNT(DISTINCT miasto) AS Miasta FROM klienci WHERE newsletter = 'T';
```

Wynik: **1 wiersz**

| Miasta |
|---|
| 25 |

### Zadanie 43 · MIN, MAX, AVG, ROUND

**Odpowiedź:** **1113.43 zł** (min 14.99, max 8999.00)

```sql
SELECT MIN(cena) AS Najtanszy, MAX(cena) AS Najdrozszy, ROUND(AVG(cena), 2) AS Srednia FROM produkty;
```

Wynik: **1 wiersz**

| Najtanszy | Najdrozszy | Srednia |
|---|---|---|
| 14.99 | 8999.00 | 1113.43 |

### Zadanie 44 · JOIN + 2 warunki

**Odpowiedź:** **6** książek, najtańsza: **Pan Tadeusz** (24.99 zł)

```sql
SELECT p.nazwa, p.cena
FROM produkty p
JOIN kategorie kat ON p.id_kategorii = kat.id
WHERE kat.nazwa = 'Książki' AND p.cena < 50
ORDER BY p.cena;
```

Wynik: **6 wierszy**

| nazwa | cena |
|---|---|
| Pan Tadeusz | 24.99 |
| Ferdydurke | 32.99 |
| Lalka | 34.99 |
| Quo vadis | 37.99 |
| Solaris | 44.99 |
| Linux. Komendy i polecenia | 49.90 |

### Zadanie 45 · YEAR() / BETWEEN

**Odpowiedź:** **90** klientów

```sql
SELECT COUNT(*) AS Ile FROM klienci WHERE YEAR(data_rejestracji) = 2024;
```

Wynik: **1 wiersz**

| Ile |
|---|
| 90 |

---

## ★★★ Poziom 3 · Złączenia z grupowaniem

### Zadanie 46 · JOIN + GROUP BY

**Odpowiedź:** **Akcesoria komputerowe** — **19** produktów; wynik ma **10** wierszy (o 1 mniej niż kategorii!)

```sql
SELECT kat.nazwa, COUNT(*) AS Produkty
FROM produkty p
JOIN kategorie kat ON p.id_kategorii = kat.id
GROUP BY kat.nazwa
ORDER BY Produkty DESC;
```

Wynik: **10 wierszy**

| nazwa | Produkty |
|---|---|
| Akcesoria komputerowe | 19 |
| AGD | 15 |
| Audio | 13 |
| Książki | 13 |
| Laptopy | 11 |
| … | … |

> ⚠️ Kategoria „Karty podarunkowe” nie ma produktów, więc zwykły `JOIN` jej nie pokazuje. Wrócimy do tego w zadaniu 51.

### Zadanie 47 · JOIN + WHERE + GROUP BY + ROUND

**Odpowiedź:** **Kross** — **1622.00 zł**

```sql
SELECT pr.nazwa, ROUND(AVG(p.cena), 2) AS SredniaCena
FROM produkty p
JOIN producenci pr ON p.id_producenta = pr.id
WHERE pr.kraj = 'Polska'
GROUP BY pr.nazwa
ORDER BY SredniaCena DESC;
```

Wynik: **5 wierszy**

| nazwa | SredniaCena |
|---|---|
| Kross | 1622.00 |
| Amica | 1316.00 |
| Helion | 79.05 |
| Trefl | 46.33 |
| Znak | 35.19 |

### Zadanie 48 · JOIN + GROUP BY + SUM + LIMIT

**Odpowiedź:** **Ferdydurke** — **161** szt.

```sql
SELECT p.nazwa, SUM(pz.ilosc) AS Sztuk
FROM pozycje_zamowienia pz
JOIN produkty p ON pz.id_produktu = p.id
GROUP BY p.nazwa
ORDER BY Sztuk DESC
LIMIT 3;
```

Wynik: **3 wiersze**

| nazwa | Sztuk |
|---|---|
| Żarówka Philips LED E27 | 244 |
| Bidon Decathlon 0,75 l | 187 |
| Ferdydurke | 161 |

> ⚠️ `COUNT(*)` zamiast `SUM(pz.ilosc)` liczy, w ilu zamówieniach był produkt, a nie ile sztuk sprzedano.

### Zadanie 49 · SUM(a*b)

**Odpowiedź:** **45.99 zł**

```sql
SELECT SUM(ilosc * cena_jednostkowa) AS Wartosc FROM pozycje_zamowienia WHERE id_zamowienia = 1000;
```

Wynik: **1 wiersz**

| Wartosc |
|---|
| 45.99 |

### Zadanie 50 · JOIN w zapisie egzaminacyjnym

**Odpowiedź:** **12** produktów, pierwszy: **Gra Gran Turismo 7**

```sql
SELECT produkty.nazwa, producenci.nazwa
FROM produkty, producenci
WHERE produkty.id_producenta = producenci.id AND producenci.kraj = 'Japonia'
ORDER BY produkty.nazwa;
```

Wynik: **12 wierszy**

| nazwa | nazwa |
|---|---|
| Gra Gran Turismo 7 | Sony |
| Gra Mario Kart 8 Deluxe | Nintendo |
| Gra Spider-Man 2 | Sony |
| Gra Zelda Tears of the Kingdom | Nintendo |
| Konsola Nintendo Switch Lite | Nintendo |
| … | … |

> ⚠️ Bez warunku łączenia w `WHERE` wychodzi iloczyn kartezjański — każdy produkt z każdym producentem.

### Zadanie 51 · LEFT JOIN + COUNT(kolumna)

**Odpowiedź:** **Karty podarunkowe** — 0 produktów; wynik ma **11** wierszy

```sql
SELECT kat.nazwa, COUNT(p.id) AS Produkty
FROM kategorie kat
LEFT JOIN produkty p ON p.id_kategorii = kat.id
GROUP BY kat.nazwa
ORDER BY Produkty;
```

Wynik: **11 wierszy**

| nazwa | Produkty |
|---|---|
| Karty podarunkowe | 0 |
| Zabawki | 8 |
| Smartfony | 9 |
| Gry i konsole | 10 |
| Dom i ogród | 10 |
| … | … |

> ⚠️ `COUNT(*)` liczy wiersze, a `LEFT JOIN` tworzy dla pustej kategorii jeden wiersz z `NULL`-ami — wyszłoby 1 zamiast 0.

### Zadanie 52 · JOIN 3 tabel + DISTINCT

**Odpowiedź:** **9** produktów

```sql
SELECT DISTINCT p.nazwa
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
WHERE z.data_zamowienia = '2025-12-24'
ORDER BY p.nazwa;
```

Wynik: **9 wierszy**

| nazwa |
|---|
| Czajnik Philips HD9350 |
| Klawiatura Logitech K120 |
| Lalka |
| Linux. Komendy i polecenia |
| Mysz Logitech M185 |
| … |

### Zadanie 53 · JOIN + GROUP BY + HAVING

**Odpowiedź:** **Helion, Samsung, Sony, Xiaomi** (4 producentów)

```sql
SELECT pr.nazwa, COUNT(*) AS Produkty
FROM produkty p
JOIN producenci pr ON p.id_producenta = pr.id
GROUP BY pr.nazwa
HAVING COUNT(*) >= 8
ORDER BY pr.nazwa;
```

Wynik: **4 wiersze**

| nazwa | Produkty |
|---|---|
| Helion | 8 |
| Samsung | 9 |
| Sony | 8 |
| Xiaomi | 8 |

### Zadanie 54 · MONTH() + GROUP BY + WHERE YEAR()

**Odpowiedź:** miesiąc **10** — **102** zamówień

```sql
SELECT MONTH(data_zamowienia) AS Miesiac, COUNT(*) AS Zamowienia
FROM zamowienia
WHERE YEAR(data_zamowienia) = 2026
GROUP BY MONTH(data_zamowienia)
ORDER BY Zamowienia DESC;
```

Wynik: **10 wierszy**

| Miesiac | Zamowienia |
|---|---|
| 10 | 102 |
| 9 | 74 |
| 6 | 64 |
| 7 | 59 |
| 4 | 58 |
| … | … |

### Zadanie 55 · JOIN + GROUP BY po id

**Odpowiedź:** **Maria Jabłońska** — **18** zamówień

```sql
SELECT k.imie, k.nazwisko, COUNT(*) AS Zamowienia
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
WHERE k.miasto = 'Bydgoszcz'
GROUP BY k.id, k.imie, k.nazwisko
ORDER BY Zamowienia DESC;
```

Wynik: **10 wierszy**

| imie | nazwisko | Zamowienia |
|---|---|---|
| Maria | Jabłońska | 18 |
| Barbara | Bąk | 8 |
| Hanna | Nowicka | 6 |
| Joanna | Kowalska | 5 |
| Łukasz | Ostrowski | 5 |
| … | … | … |

### Zadanie 56 · WHERE — 3 warunki

**Odpowiedź:** **92** zamówień

```sql
SELECT COUNT(*) AS Ile FROM zamowienia WHERE sposob_dostawy = 'kurier' AND sposob_platnosci = 'karta' AND koszt_dostawy = 0;
```

Wynik: **1 wiersz**

| Ile |
|---|
| 92 |

### Zadanie 57 · JOIN + SUM(a*b) + GROUP BY YEAR

**Odpowiedź:** **780275.95 zł** w 2025 (i 483114.15 zł w 2026)

```sql
SELECT YEAR(z.data_zamowienia) AS Rok, SUM(pz.ilosc * pz.cena_jednostkowa) AS Przychod
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE z.status <> 'anulowane'
GROUP BY YEAR(z.data_zamowienia);
```

Wynik: **2 wiersze**

| Rok | Przychod |
|---|---|
| 2025 | 780275.95 |
| 2026 | 483114.15 |

> ⚠️ Liczymy z `cena_jednostkowa` (cena w chwili zakupu), a nie z `produkty.cena` — część towarów kupiono w promocji.

### Zadanie 58 · GROUP BY 2 kolumny

**Odpowiedź:** **paczkomat + blik** — **285** zamówień (wynik ma 11 wierszy)

```sql
SELECT sposob_dostawy, sposob_platnosci, COUNT(*) AS Ile
FROM zamowienia
GROUP BY sposob_dostawy, sposob_platnosci
ORDER BY Ile DESC;
```

Wynik: **11 wierszy**

| sposob_dostawy | sposob_platnosci | Ile |
|---|---|---|
| paczkomat | blik | 285 |
| paczkomat | karta | 239 |
| kurier | blik | 201 |
| kurier | karta | 163 |
| paczkomat | pobranie | 157 |
| … | … | … |

### Zadanie 59 · JOIN 3 tabel + GROUP BY + AVG

**Odpowiedź:** **Laptop Dell Latitude 5440** — **5.00** (2 opinii)

```sql
SELECT p.nazwa, ROUND(AVG(o.ocena), 2) AS Srednia, COUNT(*) AS Opinii
FROM opinie o
JOIN produkty p ON o.id_produktu = p.id
JOIN kategorie kat ON p.id_kategorii = kat.id
WHERE kat.nazwa = 'Laptopy'
GROUP BY p.nazwa
ORDER BY Srednia DESC, Opinii DESC;
```

Wynik: **7 wierszy**

| nazwa | Srednia | Opinii |
|---|---|---|
| Laptop Dell Latitude 5440 | 5.00 | 2 |
| Laptop Apple MacBook Air 13 M3 | 5.00 | 1 |
| Laptop Dell XPS 13 | 4.20 | 5 |
| Laptop Lenovo IdeaPad 3 | 4.00 | 2 |
| Laptop Dell Inspiron 15 | 3.33 | 3 |
| Laptop Asus VivoBook 15 | 3.00 | 1 |
| Laptop Asus ZenBook 14 | 3.00 | 1 |

> ⚠️ Dwa laptopy mają średnią 5.00 — bez drugiej kolumny sortowania ich kolejność byłaby przypadkowa.

### Zadanie 60 · JOIN + HAVING z dwoma warunkami

**Odpowiedź:** **9** produktów

```sql
SELECT p.nazwa, COUNT(*) AS Opinii, ROUND(AVG(o.ocena), 2) AS Srednia
FROM opinie o
JOIN produkty p ON o.id_produktu = p.id
GROUP BY p.nazwa
HAVING COUNT(*) >= 15 AND AVG(o.ocena) >= 4.0;
```

Wynik: **9 wierszy**

| nazwa | Opinii | Srednia |
|---|---|---|
| Blender Bosch ErgoMixx | 16 | 4.19 |
| Ferdydurke | 29 | 4.62 |
| Hantle Decathlon 2 x 5 kg | 16 | 4.50 |
| HTML5 i CSS3. Praktyczne projekty | 25 | 4.32 |
| Pan Tadeusz | 25 | 4.08 |
| … | … | … |

### Zadanie 61 · LEFT JOIN … IS NULL

**Odpowiedź:** **Nokia** (1 producent)

```sql
SELECT pr.nazwa
FROM producenci pr
LEFT JOIN produkty p ON p.id_producenta = pr.id
WHERE p.id IS NULL;
```

Wynik: **1 wiersz**

| nazwa |
|---|
| Nokia |

### Zadanie 62 · LEFT JOIN … IS NULL

**Odpowiedź:** **22** klientów

```sql
SELECT k.imie, k.nazwisko, k.data_rejestracji
FROM klienci k
LEFT JOIN zamowienia z ON z.id_klienta = k.id
WHERE z.id IS NULL;
```

Wynik: **22 wiersze**

| imie | nazwisko | data_rejestracji |
|---|---|---|
| Katarzyna | Lewandowska | 2023-03-22 |
| Weronika | Nowak | 2026-10-16 |
| Julia | Ostrowska | 2026-10-28 |
| Marta | Wieczorek | 2025-10-23 |
| Kamil | Walczak | 2026-02-09 |
| … | … | … |

> ⚠️ Sprawdzenie: 320 klientów − 298 kupujących (zadanie 26) = 22.

### Zadanie 63 · JOIN + GROUP BY po id + LIMIT

**Odpowiedź:** **Marta Zalewska** (Poznań) — **16** opinii

```sql
SELECT k.imie, k.nazwisko, k.miasto, COUNT(*) AS Opinii
FROM opinie o
JOIN klienci k ON o.id_klienta = k.id
GROUP BY k.id, k.imie, k.nazwisko, k.miasto
ORDER BY Opinii DESC
LIMIT 1;
```

Wynik: **1 wiersz**

| imie | nazwisko | miasto | Opinii |
|---|---|---|---|
| Marta | Zalewska | Poznań | 16 |

### Zadanie 64 · JOIN + COUNT + SUM

**Odpowiedź:** **159** zamówień, **244** sztuk

```sql
SELECT COUNT(*) AS Zamowien, SUM(pz.ilosc) AS Sztuk
FROM pozycje_zamowienia pz
JOIN produkty p ON pz.id_produktu = p.id
WHERE p.nazwa = 'Żarówka Philips LED E27';
```

Wynik: **1 wiersz**

| Zamowien | Sztuk |
|---|---|
| 159 | 244 |

### Zadanie 65 · JOIN 3 tabel + GROUP BY + HAVING

**Odpowiedź:** **Znak** — **4.13** (105 opinii)

```sql
SELECT pr.nazwa, COUNT(*) AS Opinii, ROUND(AVG(o.ocena), 2) AS Srednia
FROM opinie o
JOIN produkty p ON o.id_produktu = p.id
JOIN producenci pr ON p.id_producenta = pr.id
GROUP BY pr.nazwa
HAVING COUNT(*) >= 30
ORDER BY Srednia DESC;
```

Wynik: **9 wierszy**

| nazwa | Opinii | Srednia |
|---|---|---|
| Znak | 105 | 4.13 |
| Helion | 100 | 4.10 |
| Samsung | 54 | 3.96 |
| Philips | 78 | 3.90 |
| Bosch | 36 | 3.81 |
| … | … | … |

### Zadanie 66 · JOIN + MAX + GROUP BY

**Odpowiedź:** **2899.00 zł** (Sport)

```sql
SELECT kat.nazwa, MAX(p.cena) AS Najdrozszy
FROM produkty p
JOIN kategorie kat ON p.id_kategorii = kat.id
GROUP BY kat.nazwa
ORDER BY kat.nazwa;
```

Wynik: **10 wierszy**

| nazwa | Najdrozszy |
|---|---|
| AGD | 2299.00 |
| Akcesoria komputerowe | 1249.00 |
| Audio | 1499.00 |
| Dom i ogród | 799.00 |
| Gry i konsole | 2499.99 |
| … | … |

> ⚠️ Z samym `GROUP BY` nie da się poprawnie pokazać **nazwy** najdroższego produktu obok `MAX(cena)` — to wymaga podzapytania (poza zakresem). Dopisanie `p.nazwa` do `SELECT` da przypadkowy produkt z grupy.

### Zadanie 67 · JOIN + GROUP BY + LIMIT

**Odpowiedź:** **Poznań** — **167** zamówień

```sql
SELECT k.miasto, COUNT(*) AS Zamowienia
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
GROUP BY k.miasto
ORDER BY Zamowienia DESC
LIMIT 3;
```

Wynik: **3 wiersze**

| miasto | Zamowienia |
|---|---|
| Warszawa | 207 |
| Wrocław | 190 |
| Poznań | 167 |

### Zadanie 68 · JOIN — porównanie dwóch kolumn

**Odpowiedź:** **5** zamówień

```sql
SELECT COUNT(*) AS Ile
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
WHERE z.data_zamowienia = k.data_rejestracji;
```

Wynik: **1 wiersz**

| Ile |
|---|
| 5 |

### Zadanie 69 · JOIN — porównanie kolumn z dwóch tabel

**Odpowiedź:** **432** pozycji

```sql
SELECT COUNT(*) AS Ile
FROM pozycje_zamowienia pz
JOIN produkty p ON pz.id_produktu = p.id
WHERE pz.cena_jednostkowa < p.cena;
```

Wynik: **1 wiersz**

| Ile |
|---|
| 432 |

> ⚠️ To właśnie dlatego wartość zamówień liczymy z `cena_jednostkowa`, a nie z `produkty.cena`.

### Zadanie 70 · JOIN 3 tabel w zapisie egzaminacyjnym

**Odpowiedź:** **8** wierszy

```sql
SELECT klienci.imie, klienci.nazwisko, produkty.nazwa
FROM opinie, klienci, produkty
WHERE opinie.id_klienta = klienci.id AND opinie.id_produktu = produkty.id
  AND opinie.ocena = 5 AND opinie.data_opinii BETWEEN '2026-10-01' AND '2026-10-31'
ORDER BY klienci.nazwisko;
```

Wynik: **8 wierszy**

| imie | nazwisko | nazwa |
|---|---|---|
| Zofia | Chmielewska | Python. Wprowadzenie |
| Julia | Jankowska | Linux. Komendy i polecenia |
| Jakub | Kowalczyk | Lodówka Amica FK2995 |
| Paulina | Król | Żarówka Philips LED E27 |
| Filip | Sikora | Kask rowerowy Kross Ventego |
| Dawid | Szymański | Klocki Lego Classic 1500 el. |
| Agnieszka | Wiśniewska | Solaris |
| Kacper | Wiśniewski | Ładowarka Xiaomi 67W |

> ⚠️ Brak jednego z warunków łączenia daje ogromny wynik (iloczyn kartezjański z jedną z tabel).

---

## ★★★★ Poziom 4 · Kilka tabel, raporty i LEFT JOIN

### Zadanie 71 · JOIN 4 tabel

**Odpowiedź:** **25** wierszy, ostatni: **Soundbar Sony HT-S100F**

```sql
SELECT k.imie, k.nazwisko, z.data_zamowienia, p.nazwa, pz.ilosc
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
WHERE k.miasto = 'Opole'
ORDER BY z.data_zamowienia, p.nazwa;
```

Wynik: **25 wierszy**

| imie | nazwisko | data_zamowienia | nazwa | ilosc |
|---|---|---|---|---|
| Karolina | Jaworska | 2025-01-09 | Dysk SSD Samsung 990 EVO 1TB | 1 |
| Karolina | Jaworska | 2025-01-09 | Ferdydurke | 2 |
| Karolina | Jaworska | 2025-01-09 | Głośnik JBL Flip 6 | 1 |
| Karolina | Jaworska | 2025-01-09 | Kask rowerowy Kross Ventego | 2 |
| Karolina | Jaworska | 2025-01-09 | Solaris | 1 |
| … | … | … | … | … |

### Zadanie 72 · JOIN 3 tabel + SUM + GROUP BY + LIMIT

**Odpowiedź:** **Zofia Jankowska** (Białystok) — **24769.30 zł**

```sql
SELECT k.imie, k.nazwisko, k.miasto, SUM(pz.ilosc * pz.cena_jednostkowa) AS Wydatki
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE z.status <> 'anulowane'
GROUP BY k.id, k.imie, k.nazwisko, k.miasto
ORDER BY Wydatki DESC
LIMIT 3;
```

Wynik: **3 wiersze**

| imie | nazwisko | miasto | Wydatki |
|---|---|---|---|
| Zofia | Jankowska | Białystok | 24769.30 |
| Marta | Piotrowska | Rzeszów | 24302.48 |
| Grzegorz | Nowak | Wrocław | 22455.91 |

### Zadanie 73 · JOIN 4 tabel + SUM + GROUP BY

**Odpowiedź:** **Laptopy** — **336532.75 zł**

```sql
SELECT kat.nazwa, SUM(pz.ilosc * pz.cena_jednostkowa) AS Przychod
FROM kategorie kat
JOIN produkty p ON p.id_kategorii = kat.id
JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
JOIN zamowienia z ON pz.id_zamowienia = z.id
WHERE z.status <> 'anulowane'
GROUP BY kat.nazwa
ORDER BY Przychod DESC;
```

Wynik: **10 wierszy**

| nazwa | Przychod |
|---|---|
| Laptopy | 336532.75 |
| Smartfony | 168026.48 |
| AGD | 162975.13 |
| Akcesoria komputerowe | 130854.44 |
| Audio | 116524.54 |
| … | … |

### Zadanie 74 · pułapka: GROUP BY po id

**Odpowiedź:** **Kraków: 209.78 zł**, **Gdańsk: 329.96 zł**

```sql
SELECT k.id, k.imie, k.nazwisko, k.miasto, SUM(pz.ilosc * pz.cena_jednostkowa) AS Wydatki
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE k.imie = 'Anna' AND k.nazwisko = 'Nowak' AND z.status <> 'anulowane'
GROUP BY k.id, k.imie, k.nazwisko, k.miasto;
```

Wynik: **2 wiersze**

| id | imie | nazwisko | miasto | Wydatki |
|---|---|---|---|---|
| 61 | Anna | Nowak | Kraków | 209.78 |
| 208 | Anna | Nowak | Gdańsk | 329.96 |

> ⚠️ `GROUP BY k.imie, k.nazwisko` daje jeden wiersz z sumą obu klientek — wynik formalnie „działa”, ale jest błędny.

### Zadanie 75 · LEFT JOIN + COUNT(kolumna) + WHERE

**Odpowiedź:** bez opinii: **3** — Smartfon Apple iPhone 16 Pro, Smartfon Xiaomi 14T, Smartfon Sony Xperia 10 VI

```sql
SELECT p.nazwa, COUNT(o.id) AS Opinii
FROM produkty p
JOIN kategorie kat ON p.id_kategorii = kat.id
LEFT JOIN opinie o ON o.id_produktu = p.id
WHERE kat.nazwa = 'Smartfony'
GROUP BY p.nazwa
ORDER BY Opinii;
```

Wynik: **9 wierszy**

| nazwa | Opinii |
|---|---|
| Smartfon Apple iPhone 16 Pro | 0 |
| Smartfon Xiaomi 14T | 0 |
| Smartfon Sony Xperia 10 VI | 0 |
| Smartfon Samsung Galaxy S24 | 2 |
| Smartfon Apple iPhone 15 | 2 |
| … | … |

> ⚠️ Warunek `kat.nazwa = 'Smartfony'` może stać w `WHERE`, bo dotyczy tabeli połączonej zwykłym `JOIN`. Warunek na kolumnę z tabeli dołączonej `LEFT JOIN` (np. `o.ocena = 5`) wyrzuciłby smartfony bez opinii — wiersze z `NULL`-ami nie spełniają żadnego porównania.

### Zadanie 76 · JOIN 5 tabel + COUNT(DISTINCT)

**Odpowiedź:** **55** klientów

```sql
SELECT COUNT(DISTINCT z.id_klienta) AS Klienci
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
JOIN kategorie kat ON p.id_kategorii = kat.id
WHERE kat.nazwa = 'Laptopy' AND z.status <> 'anulowane';
```

Wynik: **1 wiersz**

| Klienci |
|---|
| 55 |

### Zadanie 77 · JOIN + GROUP BY + HAVING SUM

**Odpowiedź:** **16** klientów

```sql
SELECT k.imie, k.nazwisko, SUM(pz.ilosc * pz.cena_jednostkowa) AS Wydatki
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE z.status <> 'anulowane'
GROUP BY k.id, k.imie, k.nazwisko
HAVING SUM(pz.ilosc * pz.cena_jednostkowa) > 15000
ORDER BY Wydatki DESC;
```

Wynik: **16 wierszy**

| imie | nazwisko | Wydatki |
|---|---|---|
| Zofia | Jankowska | 24769.30 |
| Marta | Piotrowska | 24302.48 |
| Grzegorz | Nowak | 22455.91 |
| Filip | Sikora | 22218.59 |
| Monika | Grabowska | 19874.76 |
| … | … | … |

### Zadanie 78 · JOIN + SUM + kolumna obliczana

**Odpowiedź:** zamówienie **867** — **514.96 zł**

```sql
SELECT z.id, SUM(pz.ilosc * pz.cena_jednostkowa) AS Towary, z.koszt_dostawy,
       SUM(pz.ilosc * pz.cena_jednostkowa) + z.koszt_dostawy AS DoZaplaty
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE z.data_zamowienia = '2025-12-24'
GROUP BY z.id, z.koszt_dostawy
ORDER BY DoZaplaty DESC;
```

Wynik: **5 wierszy**

| id | Towary | koszt_dostawy | DoZaplaty |
|---|---|---|---|
| 867 | 514.96 | 0.00 | 514.96 |
| 863 | 304.96 | 0.00 | 304.96 |
| 864 | 159.00 | 14.99 | 173.99 |
| 866 | 119.98 | 9.99 | 129.97 |
| 865 | 49.90 | 14.99 | 64.89 |

> ⚠️ `SUM(pz.ilosc * pz.cena_jednostkowa + z.koszt_dostawy)` doliczy dostawę tyle razy, ile pozycji ma zamówienie.

### Zadanie 79 · LEFT JOIN … IS NULL

**Odpowiedź:** **5** produktów

```sql
SELECT p.nazwa, p.data_dodania
FROM produkty p
LEFT JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
WHERE pz.id_produktu IS NULL;
```

Wynik: **5 wierszy**

| nazwa | data_dodania |
|---|---|
| Laptop Asus ROG Strix G16 | 2024-05-29 |
| Smartfon Sony Xperia 10 VI | 2024-10-28 |
| Monitor Lenovo L24i | 2026-10-29 |
| Puzzle Trefl 500 el. Tatry | 2025-02-04 |
| Siekiera Fiskars X17 | 2024-12-09 |

### Zadanie 80 · LEFT JOIN … IS NULL + JOIN

**Odpowiedź:** **12** produktów

```sql
SELECT p.nazwa, kat.nazwa AS kategoria
FROM produkty p
JOIN kategorie kat ON p.id_kategorii = kat.id
LEFT JOIN opinie o ON o.id_produktu = p.id
WHERE o.id IS NULL
ORDER BY kat.nazwa, p.nazwa;
```

Wynik: **12 wierszy**

| nazwa | kategoria |
|---|---|
| Pralka Amica WA1S610 | AGD |
| Monitor Lenovo L24i | Akcesoria komputerowe |
| Siekiera Fiskars X17 | Dom i ogród |
| Gra Spider-Man 2 | Gry i konsole |
| Laptop Apple MacBook Pro 14 M4 | Laptopy |
| … | … |

### Zadanie 81 · JOIN + MONTH() + GROUP BY + HAVING

**Odpowiedź:** miesiące: **3, 5, 11, 12** (4)

```sql
SELECT MONTH(z.data_zamowienia) AS Miesiac, SUM(pz.ilosc * pz.cena_jednostkowa) AS Przychod
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE YEAR(z.data_zamowienia) = 2025 AND z.status <> 'anulowane'
GROUP BY MONTH(z.data_zamowienia)
HAVING SUM(pz.ilosc * pz.cena_jednostkowa) > 70000
ORDER BY Miesiac;
```

Wynik: **4 wiersze**

| Miesiac | Przychod |
|---|---|
| 3 | 76471.33 |
| 5 | 70717.39 |
| 11 | 95309.06 |
| 12 | 124774.50 |

### Zadanie 82 · JOIN 3 tabel + GROUP BY

**Odpowiedź:** **Polska** — **1457** szt.

```sql
SELECT pr.kraj, SUM(pz.ilosc) AS Sztuk
FROM pozycje_zamowienia pz
JOIN produkty p ON pz.id_produktu = p.id
JOIN producenci pr ON p.id_producenta = pr.id
GROUP BY pr.kraj
ORDER BY Sztuk DESC;
```

Wynik: **12 wierszy**

| kraj | Sztuk |
|---|---|
| Polska | 1457 |
| Francja | 561 |
| Holandia | 470 |
| Szwajcaria | 303 |
| Chiny | 290 |
| … | … |

### Zadanie 83 · JOIN 4 tabel + COUNT(DISTINCT)

**Odpowiedź:** **64** klientów

```sql
SELECT COUNT(DISTINCT z.id_klienta) AS Klienci
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
JOIN producenci pr ON p.id_producenta = pr.id
WHERE pr.nazwa = 'Lego' AND z.status <> 'anulowane';
```

Wynik: **1 wiersz**

| Klienci |
|---|
| 64 |

### Zadanie 84 · JOIN + GROUP BY + LIMIT

**Odpowiedź:** **paczkomat** — **118** zamówień

```sql
SELECT z.sposob_dostawy, COUNT(*) AS Zamowienia
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
WHERE k.miasto = 'Warszawa'
GROUP BY z.sposob_dostawy
ORDER BY Zamowienia DESC
LIMIT 1;
```

Wynik: **1 wiersz**

| sposob_dostawy | Zamowienia |
|---|---|
| paczkomat | 118 |

### Zadanie 85 · GROUP BY + HAVING (pozycje)

**Odpowiedź:** **212** zamówień

```sql
SELECT id_zamowienia, COUNT(*) AS Produktow
FROM pozycje_zamowienia
GROUP BY id_zamowienia
HAVING COUNT(*) >= 4;
```

Wynik: **212 wierszy**

| id_zamowienia | Produktow |
|---|---|
| 2 | 5 |
| 12 | 4 |
| 13 | 5 |
| 34 | 5 |
| 41 | 5 |
| … | … |

### Zadanie 86 · JOIN 3 tabel + AVG + GROUP BY

**Odpowiedź:** **Dom i ogród** — **3.53**

```sql
SELECT kat.nazwa, ROUND(AVG(o.ocena), 2) AS Srednia
FROM opinie o
JOIN produkty p ON o.id_produktu = p.id
JOIN kategorie kat ON p.id_kategorii = kat.id
GROUP BY kat.nazwa
ORDER BY Srednia DESC;
```

Wynik: **10 wierszy**

| nazwa | Srednia |
|---|---|
| Książki | 4.12 |
| Audio | 4.09 |
| AGD | 4.04 |
| Gry i konsole | 4.00 |
| Laptopy | 4.00 |
| … | … |

### Zadanie 87 · JOIN 3 tabel + WHERE YEAR + SUM + LIMIT

**Odpowiedź:** **Laptop Dell XPS 13** — **41994.00 zł**

```sql
SELECT p.nazwa, SUM(pz.ilosc * pz.cena_jednostkowa) AS Przychod
FROM produkty p
JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
JOIN zamowienia z ON pz.id_zamowienia = z.id
WHERE YEAR(z.data_zamowienia) = 2026 AND z.status <> 'anulowane'
GROUP BY p.nazwa
ORDER BY Przychod DESC
LIMIT 1;
```

Wynik: **1 wiersz**

| nazwa | Przychod |
|---|---|
| Laptop Dell XPS 13 | 41994.00 |

### Zadanie 88 · LEFT JOIN … IS NULL + WHERE

**Odpowiedź:** **6** klientów

```sql
SELECT k.imie, k.nazwisko, k.email
FROM klienci k
LEFT JOIN zamowienia z ON z.id_klienta = k.id
WHERE z.id IS NULL AND k.newsletter = 'T';
```

Wynik: **6 wierszy**

| imie | nazwisko | email |
|---|---|---|
| Kamil | Walczak | kamil.walczak@o2.pl |
| Joanna | Grabowska | joanna.grabowska@onet.pl |
| Jakub | Kamiński | jakub.kaminski@wp.pl |
| Marek | Dąbrowski | marek.dabrowski@outlook.com |
| Piotr | Dudek | piotr.dudek@gmail.com |
| Marek | Wiśniewski | marek.wisniewski@wp.pl |

### Zadanie 89 · pułapka: COUNT(DISTINCT) po JOIN

**Odpowiedź:** Helion: **8** produktów, **507** sztuk

```sql
SELECT pr.nazwa, COUNT(DISTINCT p.id) AS Produktow, SUM(pz.ilosc) AS Sztuk
FROM producenci pr
JOIN produkty p ON p.id_producenta = pr.id
JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
WHERE pr.kraj = 'Polska'
GROUP BY pr.nazwa
ORDER BY pr.nazwa;
```

Wynik: **5 wierszy**

| nazwa | Produktow | Sztuk |
|---|---|---|
| Amica | 3 | 35 |
| Helion | 8 | 507 |
| Kross | 4 | 85 |
| Trefl | 2 | 208 |
| Znak | 5 | 622 |

> ⚠️ `COUNT(*)` albo `COUNT(p.id)` daje liczbę **pozycji zamówień** (setki), a nie liczbę produktów.

---

## ★★★★★ Poziom 5 · Poziom egzaminacyjny

### Zadanie 90 · raport: JOIN 4 tabel + kilka agregatów

**Odpowiedź:** Książki: **13** produktów, **1049** sztuk, **54404.83 zł**

```sql
SELECT kat.nazwa, COUNT(DISTINCT p.id) AS Produktow, SUM(pz.ilosc) AS Sztuk,
       SUM(pz.ilosc * pz.cena_jednostkowa) AS Przychod
FROM kategorie kat
JOIN produkty p ON p.id_kategorii = kat.id
JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
JOIN zamowienia z ON pz.id_zamowienia = z.id
WHERE z.status <> 'anulowane'
GROUP BY kat.nazwa
ORDER BY Przychod DESC;
```

Wynik: **10 wierszy**

| nazwa | Produktow | Sztuk | Przychod |
|---|---|---|---|
| Laptopy | 10 | 68 | 336532.75 |
| Smartfony | 8 | 74 | 168026.48 |
| AGD | 15 | 304 | 162975.13 |
| Akcesoria komputerowe | 18 | 672 | 130854.44 |
| Audio | 13 | 260 | 116524.54 |
| … | … | … | … |

### Zadanie 91 · pułapka: łańcuch LEFT JOIN + COUNT(kolumna) / COUNT(DISTINCT)

**Odpowiedź:** **11** wierszy; Laptopy: **11** produktów, **64** pozycji

```sql
SELECT kat.nazwa, COUNT(DISTINCT p.id) AS Produktow, COUNT(pz.id_zamowienia) AS Pozycji
FROM kategorie kat
LEFT JOIN produkty p ON p.id_kategorii = kat.id
LEFT JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
GROUP BY kat.nazwa
ORDER BY Pozycji;
```

Wynik: **11 wierszy**

| nazwa | Produktow | Pozycji |
|---|---|---|
| Karty podarunkowe | 0 | 0 |
| Laptopy | 11 | 64 |
| Smartfony | 9 | 74 |
| Gry i konsole | 10 | 150 |
| Zabawki | 8 | 225 |
| … | … | … |

> ⚠️ Drugie złączenie jako zwykły `JOIN` gubi „Karty podarunkowe” (10 wierszy). `COUNT(*)` dałby tej kategorii 1, a `COUNT(p.id)` bez `DISTINCT` liczyłby produkty tyle razy, ile razy je kupiono.

### Zadanie 92 · raport: JOIN + MONTH() + COUNT(DISTINCT) + HAVING

**Odpowiedź:** **6** miesięcy; wrzesień: **67** zamówień, **57** klientów

```sql
SELECT MONTH(z.data_zamowienia) AS Miesiac, COUNT(DISTINCT z.id) AS Zamowien,
       COUNT(DISTINCT z.id_klienta) AS Klientow, SUM(pz.ilosc * pz.cena_jednostkowa) AS Przychod
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE YEAR(z.data_zamowienia) = 2026 AND z.status <> 'anulowane'
GROUP BY MONTH(z.data_zamowienia)
HAVING SUM(pz.ilosc * pz.cena_jednostkowa) > 40000
ORDER BY Miesiac;
```

Wynik: **6 wierszy**

| Miesiac | Zamowien | Klientow | Przychod |
|---|---|---|---|
| 1 | 47 | 41 | 44158.62 |
| 4 | 53 | 45 | 46878.63 |
| 6 | 57 | 44 | 54215.56 |
| 8 | 51 | 41 | 47363.93 |
| 9 | 67 | 57 | 80625.02 |
| 10 | 96 | 82 | 101797.13 |

> ⚠️ `COUNT(*)` liczy pozycje zamówień, a nie zamówienia.

### Zadanie 93 · JOIN 3 tabel + WHERE

**Odpowiedź:** **11** opinii, pierwsza: **Ewelina Krawczyk**

```sql
SELECT k.imie, k.nazwisko, p.nazwa, o.tresc, o.data_opinii
FROM opinie o
JOIN klienci k ON o.id_klienta = k.id
JOIN produkty p ON o.id_produktu = p.id
WHERE o.ocena = 1 AND o.tresc IS NOT NULL
ORDER BY o.data_opinii;
```

Wynik: **11 wierszy**

| imie | nazwisko | nazwa | tresc | data_opinii |
|---|---|---|---|---|
| Ewelina | Krawczyk | Wąż ogrodowy Gardena 20 m | Totalna porażka. | 2025-02-16 |
| Monika | Grabowska | PHP i MySQL. Od podstaw | Produkt niezgodny z opisem! | 2025-04-24 |
| Marek | Nowakowski | Dysk przenośny Samsung T7 1TB | Zwróciłem po tygodniu. | 2025-05-01 |
| Marek | Wieczorek | Powerbank Xiaomi 20000mAh | Zwróciłem po tygodniu. | 2025-06-10 |
| Aleksandra | Walczak | Hub USB-C Lenovo | Totalna porażka. | 2025-09-01 |
| … | … | … | … | … |

### Zadanie 94 · GROUP BY + HAVING COUNT(DISTINCT YEAR())

**Odpowiedź:** **175** klientów

```sql
SELECT id_klienta, COUNT(DISTINCT YEAR(data_zamowienia)) AS Lat
FROM zamowienia
GROUP BY id_klienta
HAVING COUNT(DISTINCT YEAR(data_zamowienia)) = 2;
```

Wynik: **175 wierszy**

| id_klienta | Lat |
|---|---|
| 1 | 2 |
| 2 | 2 |
| 3 | 2 |
| 5 | 2 |
| 8 | 2 |
| … | … |

### Zadanie 95 · JOIN 4 tabel + HAVING COUNT(DISTINCT)

**Odpowiedź:** **58** klientów, w tym **6** ze wszystkich 10 kategorii

```sql
SELECT k.imie, k.nazwisko, COUNT(DISTINCT p.id_kategorii) AS Kategorii
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
GROUP BY k.id, k.imie, k.nazwisko
HAVING COUNT(DISTINCT p.id_kategorii) >= 8
ORDER BY Kategorii DESC;
```

Wynik: **58 wierszy**

| imie | nazwisko | Kategorii |
|---|---|---|
| Krzysztof | Majewski | 10 |
| Weronika | Jabłońska | 10 |
| Michał | Pawłowski | 10 |
| Zofia | Jankowska | 10 |
| Monika | Grabowska | 10 |
| … | … | … |

### Zadanie 96 · JOIN 4 tabel + WHERE YEAR + GROUP BY

**Odpowiedź:** **Warszawa** — **71156.95 zł**

```sql
SELECT k.miasto, SUM(pz.ilosc * pz.cena_jednostkowa) AS Wydatki
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE YEAR(z.data_zamowienia) = 2026 AND z.status <> 'anulowane'
GROUP BY k.miasto
ORDER BY Wydatki DESC
LIMIT 3;
```

Wynik: **3 wiersze**

| miasto | Wydatki |
|---|---|
| Warszawa | 71156.95 |
| Wrocław | 54512.20 |
| Poznań | 53064.63 |

### Zadanie 97 · JOIN + obliczenia w SUM + HAVING

**Odpowiedź:** **Klawiatura Logitech K120** — **630.63 zł** (40 pozycji)

```sql
SELECT p.nazwa, COUNT(*) AS Pozycji, SUM((p.cena - pz.cena_jednostkowa) * pz.ilosc) AS Oszczednosc
FROM pozycje_zamowienia pz
JOIN produkty p ON pz.id_produktu = p.id
WHERE pz.cena_jednostkowa < p.cena
GROUP BY p.nazwa
HAVING COUNT(*) >= 15
ORDER BY Oszczednosc DESC;
```

Wynik: **8 wierszy**

| nazwa | Pozycji | Oszczednosc |
|---|---|---|
| Klawiatura Logitech K120 | 40 | 630.63 |
| Piłka nożna Decathlon F500 | 27 | 534.40 |
| Sekator Fiskars PowerGear | 15 | 446.89 |
| SQL. Praktyczny kurs | 34 | 359.32 |
| Pan Tadeusz | 49 | 355.71 |
| Lampa Philips Hue White | 22 | 224.00 |
| Bidon Decathlon 0,75 l | 58 | 192.96 |
| Żarówka Philips LED E27 | 76 | 170.63 |

### Zadanie 98 · JOIN 3 tabel + HAVING z dwoma warunkami

**Odpowiedź:** **Gardena, Fiskars, Logitech** (3)

```sql
SELECT pr.nazwa, pr.kraj, COUNT(*) AS Opinii, ROUND(AVG(o.ocena), 2) AS Srednia
FROM opinie o
JOIN produkty p ON o.id_produktu = p.id
JOIN producenci pr ON p.id_producenta = pr.id
GROUP BY pr.nazwa, pr.kraj
HAVING COUNT(*) >= 20 AND AVG(o.ocena) < 3.5
ORDER BY Srednia;
```

Wynik: **3 wiersze**

| nazwa | kraj | Opinii | Srednia |
|---|---|---|---|
| Gardena | Niemcy | 26 | 3.04 |
| Fiskars | Finlandia | 29 | 3.34 |
| Logitech | Szwajcaria | 65 | 3.49 |

### Zadanie 99 · pułapka: COUNT(DISTINCT) zamówień po JOIN

**Odpowiedź:** **7** klientów; 1. miejsce: **Marta Piotrowska** — **23** zamówień, **26178.47 zł**

```sql
SELECT k.imie, k.nazwisko, k.miasto, COUNT(DISTINCT z.id) AS Zamowien,
       SUM(pz.ilosc * pz.cena_jednostkowa) AS Wartosc
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
GROUP BY k.id, k.imie, k.nazwisko, k.miasto
HAVING COUNT(DISTINCT z.id) >= 20
ORDER BY Wartosc DESC;
```

Wynik: **7 wierszy**

| imie | nazwisko | miasto | Zamowien | Wartosc |
|---|---|---|---|---|
| Marta | Piotrowska | Rzeszów | 23 | 26178.47 |
| Monika | Grabowska | Gdańsk | 21 | 20933.72 |
| Barbara | Tomaszewska | Rzeszów | 23 | 18962.83 |
| Andrzej | Ostrowski | Wrocław | 23 | 18355.66 |
| Michał | Pawłowski | Zielona Góra | 23 | 16092.45 |
| Natalia | Jaworska | Poznań | 21 | 9443.07 |
| Natalia | Pawlak | Wrocław | 24 | 9227.22 |

> ⚠️ Z `COUNT(*)` „zamówień” wychodzi kilkadziesiąt (to liczba pozycji), a `HAVING COUNT(*) >= 20` przepuszcza dużo więcej klientów.

### Zadanie 100 · pełne zapytanie: JOIN 5 tabel + WHERE + GROUP BY + ORDER BY + LIMIT

**Odpowiedź:** **Natalia Pawlak** — **25** książek, **1332.84 zł**

```sql
SELECT k.imie, k.nazwisko, SUM(pz.ilosc) AS Ksiazek, SUM(pz.ilosc * pz.cena_jednostkowa) AS Wydatki
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
JOIN kategorie kat ON p.id_kategorii = kat.id
WHERE kat.nazwa = 'Książki' AND z.status <> 'anulowane'
GROUP BY k.id, k.imie, k.nazwisko
ORDER BY Wydatki DESC
LIMIT 3;
```

Wynik: **3 wiersze**

| imie | nazwisko | Ksiazek | Wydatki |
|---|---|---|---|
| Natalia | Pawlak | 25 | 1332.84 |
| Oskar | Piotrowski | 19 | 1046.48 |
| Natalia | Jaworska | 14 | 869.49 |
