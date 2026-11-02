# Zestaw treningowy 2 — odpowiedzi

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
| 1 | **25** producentów | 51 | **3** producentów |
| 2 | **Oskar Nowakowski** — **2023-02-05** | 52 | **7** klientów |
| 3 | **274** klientów | 53 | **AGD, Gry i konsole, Laptopy, Smartfony, Sport** (5) |
| 4 | **119** produktów | 54 | **22** wierszy; rekord: **12/2025** — 151 zamówień |
| 5 | **9** produktów | 55 | **Monika Grabowska** — **12** opinii |
| 6 | **23** miast, pierwsze: **Białystok** | 56 | **416** zamówień |
| 7 | **Quo vadis** (2025-09-16) | 57 | **461717.84 zł** |
| 8 | **228** klientów | 58 | **40** wierszy; 1. miejsce: **Książki — Helion** (8) |
| 9 | **9** produktów | 59 | **Smartfon Samsung Galaxy Z Flip6** — **4.60** (5 opinii) |
| 10 | **133** zamówień | 60 | **26** produktów |
| 11 | **27** produktów | 61 | **86** klientów |
| 12 | **28** zamówień | 62 | **7** produktów |
| 13 | **364** zamówień | 63 | **Żarówka Philips LED E27** — **29** |
| 14 | **12** klientów | 64 | **10** zamówień, **8630.04 zł** |
| 15 | **Rower Kross Evado 4.0** (0 szt., 2499.50 zł) | 65 | **Polska** — **4.03** (274 opinii) |
| 16 | **2026-10-30** | 66 | **649.00 zł** (Apple) |
| 17 | **Laptop Dell XPS 13** — **6999.00 zł** | 67 | **Wrocław** — **96** |
| 18 | **8286** sztuk | 68 | **10** produktów |
| 19 | **236** opinii | 69 | **174** pozycji |
| 20 | **628** zamówień | 70 | **4** wierszy |
| 21 | **Krzysztof Dąbrowski <krzysztof.dabrowski@wp.pl>** (5 wierszy) | 71 | **2** wierszy, pierwszy: **Grabie Fiskars Solid** |
| 22 | **przelew** — **232** zamówień | 72 | **Weronika Jabłońska** — **16925.97 zł** |
| 23 | **AGD** — **Blender Bosch ErgoMixx** | 73 | **Apple** — **130219.02 zł** |
| 24 | **137** (N: 183) | 74 | **Warszawa: 3 zam., od 2025-01-29**; **Poznań: 6 zam., od 2025-02-21** |
| 25 | **7316.26 zł** (Laptop Apple MacBook Pro 14 M4) | 75 | **Siekiera Fiskars X17** (0 zamówień) |
| 26 | **114** produktów | 76 | **13** klientów |
| 27 | **25** klientów | 77 | **4** produktów |
| 28 | **Paulina Król** | 78 | **74** zamówień |
| 29 | **12** opinii, pierwsza: ocena **2** | 79 | **64** klientów |
| 30 | **5.04 zł** | 80 | **6** klientów |
| 31 | **2024** — **90** klientów | 81 | miesiące: **5, 6, 8, 10, 11, 12** (6) |
| 32 | **9** produktów | 82 | **USA** — **328249.58 zł** |
| 33 | **478.00 zł** (zamówienie ma 5 pozycji) | 83 | **15** klientów |
| 34 | **354** zamówień | 84 | **karta** — **76** zamówień |
| 35 | **21** zamówień | 85 | **158** zamówień |
| 36 | **4521.21 zł** | 86 | **Zielona Góra** — **3.50** |
| 37 | **39.00 zł** i **2499.50 zł** | 87 | **Książki** — **102** szt. |
| 38 | **120** klientów | 88 | **9** klientów |
| 39 | miesiąc **2** — **91** zamówień | 89 | Audio: **147** klientów, **233** zamówień |
| 40 | **Czajnik Bosch TWK3A011** (2026-10-28) | 90 | **9** producentów; 1. miejsce: **Dell** — **38** szt. |
| 41 | **8** dni | 91 | **13** wierszy, **1** z 0 zamówień; 1. wiersz: **Łukasz Bąk** — 4 opinii |
| 42 | **88** klientów | 92 | **Anna Malinowska**: 8 zamówień, 20 szt., **6342.99 zł**, ostatnie 2026-10-05 |
| 43 | **912.39 zł** i **738.60 zł** | 93 | **177** klientów |
| 44 | **7** klientów | 94 | **38** klientów |
| 45 | **69** klientów | 95 | **Gdańsk** — **5804.93 zł** (23 kupujących) |
| 46 | **14** producentów; najwięcej (3): **Apple, Philips** | 96 | **9** producentów; 1. miejsce: **Znak** (107 klientów) |
| 47 | **Książki** — **62.18 zł** | 97 | **Agnieszka Wiśniewska** — **1711.59 zł** |
| 48 | **Ekspres Philips 2200 LatteGo** — **37981.00 zł** | 98 | **9** produktów |
| 49 | **157.96 zł** | 99 | **12** klientów; 1. wiersz: **Monika Grabowska** — 12 opinii, 21 zamówień |
| 50 | **12** wierszy, pierwsza kategoria: **Akcesoria komputerowe** | 100 | **Barbara Tomaszewska** — **8** produktów, **3161.96 zł** |

---

## ★ Poziom 1 · Rozgrzewka — jedna tabela

### Zadanie 1 · SELECT *

**Odpowiedź:** **25** producentów

```sql
SELECT * FROM producenci;
```

Wynik: **25 wierszy**

| id | nazwa | kraj |
|---|---|---|
| 1 | Lenovo | Chiny |
| 2 | Dell | USA |
| 3 | Apple | USA |
| 4 | Asus | Tajwan |
| 5 | Samsung | Korea Południowa |
| … | … | … |

### Zadanie 2 · ORDER BY data

**Odpowiedź:** **Oskar Nowakowski** — **2023-02-05**

```sql
SELECT imie, nazwisko, data_rejestracji FROM klienci ORDER BY data_rejestracji;
```

Wynik: **320 wierszy**

| imie | nazwisko | data_rejestracji |
|---|---|---|
| Oskar | Nowakowski | 2023-02-05 |
| Joanna | Zawadzka | 2023-02-06 |
| Grzegorz | Kowalski | 2023-02-14 |
| Jakub | Zawadzki | 2023-03-07 |
| Justyna | Walczak | 2023-03-07 |
| … | … | … |

### Zadanie 3 · WHERE <>

**Odpowiedź:** **274** klientów

```sql
SELECT imie, nazwisko, miasto FROM klienci WHERE miasto <> 'Warszawa';
```

Wynik: **274 wiersze**

| imie | nazwisko | miasto |
|---|---|---|
| Oskar | Piotrowski | Gdańsk |
| Patrycja | Wójcik | Kraków |
| Kacper | Sadowski | Szczecin |
| Katarzyna | Lewandowska | Kraków |
| Ewelina | Nowakowska | Katowice |
| … | … | … |

### Zadanie 4 · COUNT(*) AS

**Odpowiedź:** **119** produktów

```sql
SELECT COUNT(*) AS LiczbaProduktow FROM produkty;
```

Wynik: **1 wiersz**

| LiczbaProduktow |
|---|
| 119 |

### Zadanie 5 · WHERE >=

**Odpowiedź:** **9** produktów

```sql
SELECT nazwa, stan_magazynowy FROM produkty WHERE stan_magazynowy >= 140;
```

Wynik: **9 wierszy**

| nazwa | stan_magazynowy |
|---|---|
| Laptop Dell Latitude 5440 | 140 |
| Smartfon Xiaomi Redmi Note 13 | 152 |
| Kamera internetowa Logitech C920 | 158 |
| Frytkownica Tefal Easy Fry | 151 |
| Pad Sony DualSense | 155 |
| … | … |

> ⚠️ Dwa produkty mają **dokładnie** 140 sztuk — `> 140` daje o 2 mniej.

### Zadanie 6 · DISTINCT + IS NULL

**Odpowiedź:** **23** miast, pierwsze: **Białystok**

```sql
SELECT DISTINCT miasto FROM klienci WHERE telefon IS NULL ORDER BY miasto;
```

Wynik: **23 wiersze**

| miasto |
|---|
| Białystok |
| Bydgoszcz |
| Częstochowa |
| Gdańsk |
| Gdynia |
| … |

### Zadanie 7 · ORDER BY DESC + LIMIT

**Odpowiedź:** **Quo vadis** (2025-09-16)

```sql
SELECT nazwa, data_dodania FROM produkty ORDER BY data_dodania DESC LIMIT 10;
```

Wynik: **10 wierszy**

| nazwa | data_dodania |
|---|---|
| Monitor Lenovo L24i | 2026-10-29 |
| Gra Spider-Man 2 | 2026-10-27 |
| Algorytmy. Ilustrowany przewodnik | 2026-06-06 |
| Robot sprzątający Xiaomi S10 | 2026-02-20 |
| Ładowarka Xiaomi 67W | 2026-01-07 |
| … | … |

### Zadanie 8 · COUNT(kolumna)

**Odpowiedź:** **228** klientów

```sql
SELECT COUNT(telefon) AS ZTelefonem FROM klienci;
```

Wynik: **1 wiersz**

| ZTelefonem |
|---|
| 228 |

> ⚠️ `COUNT(*)` liczy wszystkie wiersze (320), `COUNT(telefon)` pomija `NULL`-e.

### Zadanie 9 · LIKE '%x%'

**Odpowiedź:** **9** produktów

```sql
SELECT nazwa, cena FROM produkty WHERE nazwa LIKE '%Samsung%';
```

Wynik: **9 wierszy**

| nazwa | cena |
|---|---|
| Smartfon Samsung Galaxy A55 | 1799.00 |
| Smartfon Samsung Galaxy S24 | 3999.00 |
| Smartfon Samsung Galaxy Z Flip6 | 4999.00 |
| Słuchawki Samsung Galaxy Buds3 | 699.00 |
| Soundbar Samsung HW-Q60D | 1299.00 |
| … | … |

> ⚠️ `LIKE 'Samsung%'` daje 0 — nazwy zaczynają się od rodzaju produktu („Smartfon Samsung…”).

### Zadanie 10 · BETWEEN — daty

**Odpowiedź:** **133** zamówień

```sql
SELECT * FROM zamowienia WHERE data_zamowienia BETWEEN '2026-01-01' AND '2026-03-31';
```

Wynik: **133 wiersze**

| id | id_klienta | data_zamowienia | status | sposob_dostawy | sposob_platnosci | koszt_dostawy |
|---|---|---|---|---|---|---|
| 894 | 60 | 2026-01-03 | dostarczone | kurier | pobranie | 0.00 |
| 895 | 102 | 2026-01-03 | anulowane | odbior osobisty | karta | 0.00 |
| 896 | 37 | 2026-01-04 | dostarczone | odbior osobisty | blik | 0.00 |
| 897 | 179 | 2026-01-05 | dostarczone | kurier | karta | 14.99 |
| 898 | 220 | 2026-01-05 | dostarczone | kurier | karta | 0.00 |
| … | … | … | … | … | … | … |

### Zadanie 11 · WHERE < (granica)

**Odpowiedź:** **27** produktów

```sql
SELECT nazwa, cena FROM produkty WHERE cena < 100;
```

Wynik: **27 wierszy**

| nazwa | cena |
|---|---|
| Mysz Logitech M185 | 59.99 |
| Klawiatura Logitech K120 | 49.99 |
| Podkładka SteelSeries QcK Large | 79.00 |
| Pendrive Samsung BAR Plus 64GB | 45.99 |
| Mata do jogi Decathlon | 59.00 |
| … | … |

> ⚠️ Jeden produkt kosztuje **dokładnie** 100.00 zł — `<= 100` daje o 1 więcej.

### Zadanie 12 · NOT IN

**Odpowiedź:** **28** zamówień

```sql
SELECT * FROM zamowienia WHERE status NOT IN ('dostarczone', 'anulowane');
```

Wynik: **28 wierszy**

| id | id_klienta | data_zamowienia | status | sposob_dostawy | sposob_platnosci | koszt_dostawy |
|---|---|---|---|---|---|---|
| 1438 | 74 | 2026-10-17 | wyslane | kurier | blik | 0.00 |
| 1439 | 107 | 2026-10-17 | wyslane | paczkomat | blik | 0.00 |
| 1442 | 297 | 2026-10-17 | wyslane | paczkomat | karta | 0.00 |
| 1444 | 309 | 2026-10-18 | wyslane | paczkomat | karta | 9.99 |
| 1448 | 88 | 2026-10-19 | wyslane | kurier | przelew | 14.99 |
| … | … | … | … | … | … | … |

### Zadanie 13 · AND + OR z nawiasami

**Odpowiedź:** **364** zamówień

```sql
SELECT * FROM zamowienia
WHERE sposob_dostawy = 'kurier' AND (sposob_platnosci = 'karta' OR sposob_platnosci = 'blik');
```

Wynik: **364 wiersze**

| id | id_klienta | data_zamowienia | status | sposob_dostawy | sposob_platnosci | koszt_dostawy |
|---|---|---|---|---|---|---|
| 3 | 84 | 2025-01-04 | dostarczone | kurier | blik | 0.00 |
| 5 | 296 | 2025-01-04 | dostarczone | kurier | karta | 14.99 |
| 6 | 76 | 2025-01-05 | dostarczone | kurier | karta | 0.00 |
| 10 | 235 | 2025-01-07 | dostarczone | kurier | blik | 14.99 |
| 13 | 186 | 2025-01-09 | dostarczone | kurier | blik | 0.00 |
| … | … | … | … | … | … | … |

> ⚠️ Bez nawiasów `… = 'kurier' AND … = 'karta' OR … = 'blik'` dolicza **wszystkie** zamówienia BLIK-iem, także paczkomatem — wychodzi 712. Zamiast `OR` można napisać `sposob_platnosci IN ('karta', 'blik')`.

### Zadanie 14 · LIKE z _

**Odpowiedź:** **12** klientów

```sql
SELECT imie, nazwisko FROM klienci WHERE imie LIKE '___';
```

Wynik: **12 wierszy**

| imie | nazwisko |
|---|---|
| Jan | Krawczyk |
| Jan | Jankowski |
| Jan | Baran |
| Jan | Marciniak |
| Ewa | Piotrowska |
| … | … |

### Zadanie 15 · ORDER BY 2 kolumny

**Odpowiedź:** **Rower Kross Evado 4.0** (0 szt., 2499.50 zł)

```sql
SELECT nazwa, stan_magazynowy, cena FROM produkty ORDER BY stan_magazynowy, cena DESC;
```

Wynik: **119 wierszy**

| nazwa | stan_magazynowy | cena |
|---|---|---|
| Rower Kross Evado 4.0 | 0 | 2499.50 |
| Konsola Sony PlayStation 5 Slim | 0 | 2399.00 |
| Kosiarka Bosch ARM 37 | 0 | 799.00 |
| Gra Zelda Tears of the Kingdom | 0 | 289.00 |
| Gra Mario Kart 8 Deluxe | 0 | 239.00 |
| … | … | … |

> ⚠️ `ORDER BY stan_magazynowy, cena` (cena rosnąco) daje na górze najtańszy produkt z zerowym stanem.

### Zadanie 16 · MAX na dacie

**Odpowiedź:** **2026-10-30**

```sql
SELECT MAX(data_rejestracji) AS OstatniaRejestracja FROM klienci;
```

Wynik: **1 wiersz**

| OstatniaRejestracja |
|---|
| 2026-10-30 |

### Zadanie 17 · LIMIT + OFFSET

**Odpowiedź:** **Laptop Dell XPS 13** — **6999.00 zł**

```sql
SELECT nazwa, cena FROM produkty ORDER BY cena DESC LIMIT 1 OFFSET 1;
```

Wynik: **1 wiersz**

| nazwa | cena |
|---|---|
| Laptop Dell XPS 13 | 6999.00 |

### Zadanie 18 · SUM

**Odpowiedź:** **8286** sztuk

```sql
SELECT SUM(stan_magazynowy) AS Sztuk FROM produkty;
```

Wynik: **1 wiersz**

| Sztuk |
|---|
| 8286 |

### Zadanie 19 · WHERE >= + BETWEEN

**Odpowiedź:** **236** opinii

```sql
SELECT COUNT(*) AS Ile FROM opinie WHERE ocena >= 4 AND data_opinii BETWEEN '2026-01-01' AND '2026-12-31';
```

Wynik: **1 wiersz**

| Ile |
|---|
| 236 |

### Zadanie 20 · COUNT + WHERE

**Odpowiedź:** **628** zamówień

```sql
SELECT COUNT(*) AS PlatnaDostawa FROM zamowienia WHERE koszt_dostawy > 0;
```

Wynik: **1 wiersz**

| PlatnaDostawa |
|---|
| 628 |

---

## ★★ Poziom 2 · Funkcje, grupowanie i pierwsze złączenia

### Zadanie 21 · CONCAT kilku kolumn

**Odpowiedź:** **Krzysztof Dąbrowski <krzysztof.dabrowski@wp.pl>** (5 wierszy)

```sql
SELECT CONCAT(imie, ' ', nazwisko, ' <', email, '>') AS Adresat
FROM klienci
WHERE miasto = 'Gdynia' AND newsletter = 'T'
ORDER BY nazwisko, imie;
```

Wynik: **5 wierszy**

| Adresat |
|---|
| Krzysztof Dąbrowski <krzysztof.dabrowski@wp.pl> |
| Marek Dąbrowski <marek.dabrowski@outlook.com> |
| Weronika Nowicka <weronika.nowicka@interia.pl> |
| Jakub Szewczyk <jakub.szewczyk@wp.pl> |
| Ewa Walczak <ewa.walczak@interia.pl> |

### Zadanie 22 · GROUP BY + ORDER BY ASC

**Odpowiedź:** **przelew** — **232** zamówień

```sql
SELECT sposob_platnosci, COUNT(*) AS Zamowienia
FROM zamowienia
GROUP BY sposob_platnosci
ORDER BY Zamowienia;
```

Wynik: **4 wiersze**

| sposob_platnosci | Zamowienia |
|---|---|
| przelew | 232 |
| pobranie | 241 |
| karta | 470 |
| blik | 549 |

### Zadanie 23 · JOIN 2 tabele + ORDER BY 2 kolumny

**Odpowiedź:** **AGD** — **Blender Bosch ErgoMixx**

```sql
SELECT kat.nazwa AS kategoria, p.nazwa, p.cena_promocyjna
FROM produkty p
JOIN kategorie kat ON p.id_kategorii = kat.id
WHERE p.cena_promocyjna IS NOT NULL
ORDER BY kat.nazwa, p.nazwa;
```

Wynik: **24 wiersze**

| kategoria | nazwa | cena_promocyjna |
|---|---|---|
| AGD | Blender Bosch ErgoMixx | 237.14 |
| AGD | Czajnik Bosch TWK3A011 | 110.48 |
| AGD | Frytkownica Philips Airfryer XL | 539.98 |
| AGD | Frytkownica Tefal Easy Fry | 404.98 |
| AGD | Patelnia Tefal Ingenio 28 cm | 126.74 |
| … | … | … |

### Zadanie 24 · GROUP BY

**Odpowiedź:** **137** (N: 183)

```sql
SELECT newsletter, COUNT(*) AS Klienci FROM klienci GROUP BY newsletter;
```

Wynik: **2 wiersze**

| newsletter | Klienci |
|---|---|
| N | 183 |
| T | 137 |

### Zadanie 25 · obliczenia + ROUND

**Odpowiedź:** **7316.26 zł** (Laptop Apple MacBook Pro 14 M4)

```sql
SELECT nazwa, cena, ROUND(cena / 1.23, 2) AS Netto
FROM produkty
WHERE cena > 5000
ORDER BY cena DESC;
```

Wynik: **6 wierszy**

| nazwa | cena | Netto |
|---|---|---|
| Laptop Apple MacBook Pro 14 M4 | 8999.00 | 7316.26 |
| Laptop Dell XPS 13 | 6999.00 | 5690.24 |
| Laptop Asus ROG Strix G16 | 6499.00 | 5283.74 |
| Laptop Lenovo Legion 5 | 5999.00 | 4877.24 |
| Smartfon Apple iPhone 16 Pro | 5799.00 | 4714.63 |
| Laptop Apple MacBook Air 13 M3 | 5299.00 | 4308.13 |

### Zadanie 26 · COUNT(DISTINCT)

**Odpowiedź:** **114** produktów

```sql
SELECT COUNT(DISTINCT id_produktu) AS Produkty FROM pozycje_zamowienia;
```

Wynik: **1 wiersz**

| Produkty |
|---|
| 114 |

> ⚠️ Porównaj z liczbą produktów w sklepie (119) — różnica to produkty, których nikt nie zamówił.

### Zadanie 27 · MONTH()

**Odpowiedź:** **25** klientów

```sql
SELECT COUNT(*) AS Ile FROM klienci WHERE MONTH(data_urodzenia) = 11;
```

Wynik: **1 wiersz**

| Ile |
|---|
| 25 |

### Zadanie 28 · LIMIT + OFFSET

**Odpowiedź:** **Paulina Król**

```sql
SELECT imie, nazwisko FROM klienci ORDER BY nazwisko, imie LIMIT 25 OFFSET 100;
```

Wynik: **25 wierszy**

| imie | nazwisko |
|---|---|
| Paulina | Król |
| Szymon | Król |
| Barbara | Kwiatkowska |
| Magdalena | Kwiatkowska |
| Jakub | Kwiatkowski |
| … | … |

### Zadanie 29 · JOIN + WHERE

**Odpowiedź:** **12** opinii, pierwsza: ocena **2**

```sql
SELECT k.imie, k.nazwisko, o.ocena, o.data_opinii
FROM opinie o
JOIN klienci k ON o.id_klienta = k.id
WHERE k.miasto = 'Toruń'
ORDER BY o.data_opinii;
```

Wynik: **12 wierszy**

| imie | nazwisko | ocena | data_opinii |
|---|---|---|---|
| Szymon | Adamczyk | 2 | 2025-04-04 |
| Szymon | Adamczyk | 4 | 2025-04-11 |
| Ewa | Jabłońska | 4 | 2025-11-07 |
| Andrzej | Stępień | 5 | 2025-11-13 |
| Andrzej | Stępień | 5 | 2025-11-23 |
| … | … | … | … |

### Zadanie 30 · GROUP BY + AVG + MAX

**Odpowiedź:** **5.04 zł**

```sql
SELECT status, ROUND(AVG(koszt_dostawy), 2) AS SredniKoszt, MAX(koszt_dostawy) AS MaxKoszt
FROM zamowienia
GROUP BY status;
```

Wynik: **5 wierszy**

| status | SredniKoszt | MaxKoszt |
|---|---|---|
| nowe | 7.50 | 14.99 |
| oplacone | 5.00 | 9.99 |
| wyslane | 5.25 | 14.99 |
| dostarczone | 5.02 | 14.99 |
| anulowane | 5.04 | 14.99 |

### Zadanie 31 · YEAR() + GROUP BY + ORDER BY

**Odpowiedź:** **2024** — **90** klientów

```sql
SELECT YEAR(data_rejestracji) AS Rok, COUNT(*) AS Rejestracji
FROM klienci
GROUP BY YEAR(data_rejestracji)
ORDER BY Rejestracji DESC;
```

Wynik: **4 wiersze**

| Rok | Rejestracji |
|---|---|
| 2024 | 90 |
| 2025 | 85 |
| 2026 | 73 |
| 2023 | 72 |

### Zadanie 32 · GROUP BY + HAVING SUM

**Odpowiedź:** **9** produktów

```sql
SELECT id_produktu, SUM(ilosc) AS Sztuk
FROM pozycje_zamowienia
GROUP BY id_produktu
HAVING SUM(ilosc) >= 100;
```

Wynik: **9 wierszy**

| id_produktu | Sztuk |
|---|---|
| 34 | 108 |
| 38 | 117 |
| 88 | 187 |
| 96 | 129 |
| 99 | 105 |
| … | … |

### Zadanie 33 · kolumna obliczana

**Odpowiedź:** **478.00 zł** (zamówienie ma 5 pozycji)

```sql
SELECT id_produktu, ilosc, cena_jednostkowa, ilosc * cena_jednostkowa AS Wartosc
FROM pozycje_zamowienia
WHERE id_zamowienia = 700
ORDER BY Wartosc DESC;
```

Wynik: **5 wierszy**

| id_produktu | ilosc | cena_jednostkowa | Wartosc |
|---|---|---|---|
| 72 | 2 | 239.00 | 478.00 |
| 60 | 1 | 399.00 | 399.00 |
| 28 | 1 | 269.00 | 269.00 |
| 59 | 1 | 237.14 | 237.14 |
| 119 | 1 | 13.48 | 13.48 |

### Zadanie 34 · DAY()

**Odpowiedź:** **354** zamówień

```sql
SELECT COUNT(*) AS Ile FROM zamowienia WHERE DAY(data_zamowienia) <= 7;
```

Wynik: **1 wiersz**

| Ile |
|---|
| 354 |

### Zadanie 35 · JOIN + WHERE 2 warunki

**Odpowiedź:** **21** zamówień

```sql
SELECT k.imie, k.nazwisko, z.data_zamowienia, z.koszt_dostawy
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
WHERE k.miasto = 'Łódź' AND z.sposob_platnosci = 'pobranie';
```

Wynik: **21 wierszy**

| imie | nazwisko | data_zamowienia | koszt_dostawy |
|---|---|---|---|
| Julia | Dąbrowska | 2026-01-08 | 9.99 |
| Kacper | Michalak | 2025-01-14 | 0.00 |
| Andrzej | Tomaszewski | 2025-11-23 | 9.99 |
| Bartosz | Pawłowski | 2026-04-08 | 0.00 |
| Paweł | Witkowski | 2025-03-26 | 0.00 |
| … | … | … | … |

### Zadanie 36 · SUM + WHERE YEAR

**Odpowiedź:** **4521.21 zł**

```sql
SELECT SUM(koszt_dostawy) AS ZaDostawe FROM zamowienia WHERE YEAR(data_zamowienia) = 2025;
```

Wynik: **1 wiersz**

| ZaDostawe |
|---|
| 4521.21 |

### Zadanie 37 · MIN, MAX + WHERE

**Odpowiedź:** **39.00 zł** i **2499.50 zł**

```sql
SELECT MIN(cena) AS Najtanszy, MAX(cena) AS Najdrozszy FROM produkty WHERE stan_magazynowy = 0;
```

Wynik: **1 wiersz**

| Najtanszy | Najdrozszy |
|---|---|
| 39.00 | 2499.50 |

> ⚠️ Bez `WHERE` wychodzą ceny całego sklepu: 14.99 i 8999.00 zł.

### Zadanie 38 · NOT LIKE

**Odpowiedź:** **120** klientów

```sql
SELECT COUNT(*) AS Ile FROM klienci WHERE email NOT LIKE '%@gmail.com' AND email NOT LIKE '%@wp.pl';
```

Wynik: **1 wiersz**

| Ile |
|---|
| 120 |

> ⚠️ Z `OR` zamiast `AND` warunek jest prawdziwy dla **każdego** adresu (żaden nie jest naraz w obu domenach) — wychodzi 320.

### Zadanie 39 · MONTH() + GROUP BY

**Odpowiedź:** miesiąc **2** — **91** zamówień

```sql
SELECT MONTH(data_zamowienia) AS Miesiac, COUNT(*) AS Zamowienia
FROM zamowienia
GROUP BY MONTH(data_zamowienia)
ORDER BY Zamowienia;
```

Wynik: **12 wierszy**

| Miesiac | Zamowienia |
|---|---|
| 2 | 91 |
| 1 | 102 |
| 3 | 104 |
| 11 | 117 |
| 4 | 118 |
| … | … |

### Zadanie 40 · JOIN + ORDER BY + LIMIT

**Odpowiedź:** **Czajnik Bosch TWK3A011** (2026-10-28)

```sql
SELECT o.data_opinii, p.nazwa, o.ocena
FROM opinie o
JOIN produkty p ON o.id_produktu = p.id
ORDER BY o.data_opinii DESC, p.nazwa
LIMIT 5;
```

Wynik: **5 wierszy**

| data_opinii | nazwa | ocena |
|---|---|---|
| 2026-10-30 | Piłka nożna Decathlon F500 | 4 |
| 2026-10-30 | Python. Wprowadzenie | 5 |
| 2026-10-29 | Gra planszowa Trefl Rodzina Treflików | 2 |
| 2026-10-29 | Żarówka Philips LED E27 | 5 |
| 2026-10-28 | Czajnik Bosch TWK3A011 | 3 |

> ⚠️ Kilka opinii ma tę samą datę — bez drugiej kolumny sortowania 5. wiersz byłby przypadkowy.

### Zadanie 41 · GROUP BY data + HAVING

**Odpowiedź:** **8** dni

```sql
SELECT data_zamowienia, COUNT(*) AS Zamowienia
FROM zamowienia
GROUP BY data_zamowienia
HAVING COUNT(*) >= 8;
```

Wynik: **8 wierszy**

| data_zamowienia | Zamowienia |
|---|---|
| 2025-11-12 | 8 |
| 2025-11-19 | 10 |
| 2025-12-06 | 11 |
| 2025-12-17 | 8 |
| 2025-12-18 | 11 |
| 2025-12-22 | 8 |
| 2026-10-20 | 8 |
| 2026-10-22 | 9 |

### Zadanie 42 · COUNT(DISTINCT) + WHERE

**Odpowiedź:** **88** klientów

```sql
SELECT COUNT(DISTINCT id_klienta) AS Klienci FROM zamowienia WHERE data_zamowienia BETWEEN '2026-10-01' AND '2026-10-31';
```

Wynik: **1 wiersz**

| Klienci |
|---|
| 88 |

### Zadanie 43 · AVG + ROUND + WHERE

**Odpowiedź:** **912.39 zł** i **738.60 zł**

```sql
SELECT ROUND(AVG(cena), 2) AS SredniaRegularna, ROUND(AVG(cena_promocyjna), 2) AS SredniaPromocyjna
FROM produkty
WHERE cena_promocyjna IS NOT NULL;
```

Wynik: **1 wiersz**

| SredniaRegularna | SredniaPromocyjna |
|---|---|
| 912.39 | 738.60 |

> ⚠️ Bez `WHERE` średnia regularna obejmie wszystkie produkty, a `AVG(cena_promocyjna)` i tak pominie `NULL`-e — wyniki nie będą porównywalne.

### Zadanie 44 · JOIN + WHERE + DISTINCT

**Odpowiedź:** **7** klientów

```sql
SELECT DISTINCT k.imie, k.nazwisko
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
WHERE k.miasto = 'Kraków' AND z.sposob_dostawy = 'odbior osobisty';
```

Wynik: **7 wierszy**

| imie | nazwisko |
|---|---|
| Oliwia | Wiśniewska |
| Łukasz | Kowalczyk |
| Ewa | Ostrowska |
| Karolina | Nowicka |
| Małgorzata | Pawlak |
| Weronika | Rutkowska |
| Hanna | Kozłowska |

### Zadanie 45 · obliczenia na dacie

**Odpowiedź:** **69** klientów

```sql
SELECT COUNT(*) AS Ile FROM klienci WHERE 2026 - YEAR(data_urodzenia) > 60;
```

Wynik: **1 wiersz**

| Ile |
|---|
| 69 |

---

## ★★★ Poziom 3 · Złączenia z grupowaniem

### Zadanie 46 · JOIN + WHERE + GROUP BY

**Odpowiedź:** **14** producentów; najwięcej (3): **Apple, Philips**

```sql
SELECT pr.nazwa, COUNT(*) AS WPromocji
FROM produkty p
JOIN producenci pr ON p.id_producenta = pr.id
WHERE p.cena_promocyjna IS NOT NULL
GROUP BY pr.nazwa
ORDER BY WPromocji DESC;
```

Wynik: **14 wierszy**

| nazwa | WPromocji |
|---|---|
| Apple | 3 |
| Philips | 3 |
| Tefal | 2 |
| Bosch | 2 |
| Logitech | 2 |
| … | … |

> ⚠️ Na pierwszym miejscu jest remis — przy pytaniu „kto ma najwięcej” zawsze sprawdź, czy kolejny wiersz nie ma tej samej wartości.

### Zadanie 47 · JOIN + GROUP BY + AVG

**Odpowiedź:** **Książki** — **62.18 zł**

```sql
SELECT kat.nazwa, ROUND(AVG(p.cena), 2) AS SredniaCena
FROM produkty p
JOIN kategorie kat ON p.id_kategorii = kat.id
GROUP BY kat.nazwa
ORDER BY SredniaCena;
```

Wynik: **10 wierszy**

| nazwa | SredniaCena |
|---|---|
| Książki | 62.18 |
| Dom i ogród | 254.04 |
| Zabawki | 373.49 |
| Akcesoria komputerowe | 373.89 |
| Audio | 625.15 |
| … | … |

### Zadanie 48 · JOIN 3 tabel + SUM(a*b) + LIMIT

**Odpowiedź:** **Ekspres Philips 2200 LatteGo** — **37981.00 zł**

```sql
SELECT p.nazwa, SUM(pz.ilosc * pz.cena_jednostkowa) AS Przychod
FROM produkty p
JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
JOIN zamowienia z ON pz.id_zamowienia = z.id
WHERE z.status <> 'anulowane'
GROUP BY p.nazwa
ORDER BY Przychod DESC
LIMIT 5;
```

Wynik: **5 wierszy**

| nazwa | Przychod |
|---|---|
| Laptop Dell XPS 13 | 90987.00 |
| Laptop Apple MacBook Pro 14 M4 | 62993.00 |
| Smartfon Samsung Galaxy Z Flip6 | 44991.00 |
| Laptop Lenovo ThinkPad E14 | 42889.00 |
| Ekspres Philips 2200 LatteGo | 37981.00 |

### Zadanie 49 · JOIN + SUM + dostawa

**Odpowiedź:** **157.96 zł**

```sql
SELECT z.id, SUM(pz.ilosc * pz.cena_jednostkowa) + z.koszt_dostawy AS DoZaplaty
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE z.id = 1103
GROUP BY z.id, z.koszt_dostawy;
```

Wynik: **1 wiersz**

| id | DoZaplaty |
|---|---|
| 1103 | 157.96 |

> ⚠️ `SUM(pz.ilosc * pz.cena_jednostkowa + z.koszt_dostawy)` doliczy dostawę 3 razy (zamówienie ma 3 pozycje).

### Zadanie 50 · JOIN w zapisie egzaminacyjnym

**Odpowiedź:** **12** wierszy, pierwsza kategoria: **Akcesoria komputerowe**

```sql
SELECT kategorie.nazwa, produkty.nazwa
FROM produkty, kategorie
WHERE produkty.id_kategorii = kategorie.id AND produkty.stan_magazynowy = 0
ORDER BY kategorie.nazwa, produkty.nazwa;
```

Wynik: **12 wierszy**

| nazwa | nazwa |
|---|---|
| Akcesoria komputerowe | Hub USB-C Lenovo |
| Akcesoria komputerowe | Klawiatura Logitech K120 |
| Dom i ogród | Kosiarka Bosch ARM 37 |
| Dom i ogród | Wąż ogrodowy Gardena 20 m |
| Gry i konsole | Gra Mario Kart 8 Deluxe |
| … | … |

### Zadanie 51 · LEFT JOIN + HAVING COUNT(kolumna)

**Odpowiedź:** **3** producentów

```sql
SELECT pr.nazwa, COUNT(p.id) AS Produkty
FROM producenci pr
LEFT JOIN produkty p ON p.id_producenta = pr.id
GROUP BY pr.nazwa
HAVING COUNT(p.id) < 3;
```

Wynik: **3 wiersze**

| nazwa | Produkty |
|---|---|
| Gardena | 2 |
| Microsoft | 2 |
| Nokia | 0 |

> ⚠️ Ze zwykłym `JOIN` znika producent bez produktów; z `COUNT(*)` miałby 1 zamiast 0.

### Zadanie 52 · JOIN 3 tabel + DISTINCT

**Odpowiedź:** **7** klientów

```sql
SELECT DISTINCT k.imie, k.nazwisko
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
WHERE p.nazwa = 'Konsola Sony PlayStation 5 Slim';
```

Wynik: **7 wierszy**

| imie | nazwisko |
|---|---|
| Marta | Piotrowska |
| Anna | Malinowska |
| Magdalena | Walczak |
| Filip | Sikora |
| Paulina | Król |
| Natalia | Pawlak |
| Aleksandra | Kowalczyk |

### Zadanie 53 · JOIN + GROUP BY + HAVING AVG

**Odpowiedź:** **AGD, Gry i konsole, Laptopy, Smartfony, Sport** (5)

```sql
SELECT kat.nazwa, ROUND(AVG(p.cena), 2) AS SredniaCena
FROM produkty p
JOIN kategorie kat ON p.id_kategorii = kat.id
GROUP BY kat.nazwa
HAVING AVG(p.cena) > 800
ORDER BY kat.nazwa;
```

Wynik: **5 wierszy**

| nazwa | SredniaCena |
|---|---|
| AGD | 826.73 |
| Gry i konsole | 885.50 |
| Laptopy | 4917.18 |
| Smartfony | 2937.89 |
| Sport | 831.36 |

### Zadanie 54 · GROUP BY 2 kolumny (rok, miesiąc)

**Odpowiedź:** **22** wierszy; rekord: **12/2025** — 151 zamówień

```sql
SELECT YEAR(data_zamowienia) AS Rok, MONTH(data_zamowienia) AS Miesiac, COUNT(*) AS Zamowienia
FROM zamowienia
GROUP BY YEAR(data_zamowienia), MONTH(data_zamowienia)
ORDER BY Zamowienia DESC;
```

Wynik: **22 wiersze**

| Rok | Miesiac | Zamowienia |
|---|---|---|
| 2025 | 12 | 151 |
| 2025 | 11 | 117 |
| 2026 | 10 | 102 |
| 2025 | 8 | 78 |
| 2026 | 9 | 74 |
| … | … | … |

### Zadanie 55 · JOIN + GROUP BY po id

**Odpowiedź:** **Monika Grabowska** — **12** opinii

```sql
SELECT k.imie, k.nazwisko, COUNT(*) AS Opinii
FROM opinie o
JOIN klienci k ON o.id_klienta = k.id
WHERE k.miasto = 'Gdańsk'
GROUP BY k.id, k.imie, k.nazwisko
ORDER BY Opinii DESC;
```

Wynik: **18 wierszy**

| imie | nazwisko | Opinii |
|---|---|---|
| Monika | Grabowska | 12 |
| Oskar | Piotrowski | 11 |
| Oskar | Kowalczyk | 9 |
| Aleksandra | Walczak | 8 |
| Filip | Grabowski | 7 |
| … | … | … |

### Zadanie 56 · AND + OR z nawiasami + YEAR

**Odpowiedź:** **416** zamówień

```sql
SELECT COUNT(*) AS Ile
FROM zamowienia
WHERE YEAR(data_zamowienia) = 2025
  AND (sposob_dostawy = 'paczkomat' OR sposob_dostawy = 'kurier')
  AND koszt_dostawy = 0;
```

Wynik: **1 wiersz**

| Ile |
|---|
| 416 |

### Zadanie 57 · JOIN + SUM(a*b) + GROUP BY

**Odpowiedź:** **461717.84 zł**

```sql
SELECT z.sposob_platnosci, SUM(pz.ilosc * pz.cena_jednostkowa) AS Przychod
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE z.status <> 'anulowane'
GROUP BY z.sposob_platnosci;
```

Wynik: **4 wiersze**

| sposob_platnosci | Przychod |
|---|---|
| blik | 461717.84 |
| karta | 382278.29 |
| przelew | 211388.60 |
| pobranie | 208005.37 |

### Zadanie 58 · JOIN 3 tabel + GROUP BY 2 kolumny

**Odpowiedź:** **40** wierszy; 1. miejsce: **Książki — Helion** (8)

```sql
SELECT kat.nazwa AS kategoria, pr.nazwa AS producent, COUNT(*) AS Produkty
FROM produkty p
JOIN kategorie kat ON p.id_kategorii = kat.id
JOIN producenci pr ON p.id_producenta = pr.id
GROUP BY kat.nazwa, pr.nazwa
ORDER BY Produkty DESC;
```

Wynik: **40 wierszy**

| kategoria | producent | Produkty |
|---|---|---|
| Książki | Helion | 8 |
| Akcesoria komputerowe | Logitech | 6 |
| Sport | Decathlon | 6 |
| AGD | Philips | 5 |
| Zabawki | Lego | 5 |
| … | … | … |

### Zadanie 59 · JOIN 3 tabel + AVG + ORDER BY 2 kolumny

**Odpowiedź:** **Smartfon Samsung Galaxy Z Flip6** — **4.60** (5 opinii)

```sql
SELECT p.nazwa, ROUND(AVG(o.ocena), 2) AS Srednia, COUNT(*) AS Opinii
FROM opinie o
JOIN produkty p ON o.id_produktu = p.id
JOIN producenci pr ON p.id_producenta = pr.id
WHERE pr.nazwa = 'Samsung'
GROUP BY p.nazwa
ORDER BY Srednia DESC, Opinii DESC;
```

Wynik: **9 wierszy**

| nazwa | Srednia | Opinii |
|---|---|---|
| Smartfon Samsung Galaxy Z Flip6 | 4.60 | 5 |
| Słuchawki Samsung Galaxy Buds3 | 4.50 | 4 |
| Pendrive Samsung BAR Plus 64GB | 4.32 | 19 |
| Smartfon Samsung Galaxy S24 | 4.00 | 2 |
| Dysk SSD Samsung 990 EVO 1TB | 3.70 | 10 |
| … | … | … |

### Zadanie 60 · HAVING z dwoma warunkami

**Odpowiedź:** **26** produktów

```sql
SELECT p.nazwa, SUM(pz.ilosc) AS Sztuk, COUNT(*) AS Zamowien
FROM pozycje_zamowienia pz
JOIN produkty p ON pz.id_produktu = p.id
GROUP BY p.nazwa
HAVING SUM(pz.ilosc) >= 50 AND COUNT(*) >= 40;
```

Wynik: **26 wierszy**

| nazwa | Sztuk | Zamowien |
|---|---|---|
| Bidon Decathlon 0,75 l | 187 | 122 |
| Ferdydurke | 161 | 108 |
| Gra planszowa Trefl Rodzina Treflików | 129 | 77 |
| Hantle Decathlon 2 x 5 kg | 94 | 56 |
| HTML5 i CSS3. Praktyczne projekty | 99 | 65 |
| … | … | … |

### Zadanie 61 · LEFT JOIN … IS NULL

**Odpowiedź:** **86** klientów

```sql
SELECT k.imie, k.nazwisko
FROM klienci k
LEFT JOIN opinie o ON o.id_klienta = k.id
WHERE o.id IS NULL;
```

Wynik: **86 wierszy**

| imie | nazwisko |
|---|---|
| Katarzyna | Lewandowska |
| Tomasz | Wiśniewski |
| Zofia | Dudek |
| Grzegorz | Jasiński |
| Weronika | Nowak |
| … | … |

### Zadanie 62 · LEFT JOIN … IS NULL + WHERE

**Odpowiedź:** **7** produktów

```sql
SELECT p.nazwa, p.data_dodania
FROM produkty p
LEFT JOIN opinie o ON o.id_produktu = p.id
WHERE o.id IS NULL AND p.data_dodania < '2025-01-01';
```

Wynik: **7 wierszy**

| nazwa | data_dodania |
|---|---|
| Laptop Lenovo Legion 5 | 2024-08-26 |
| Laptop Apple MacBook Pro 14 M4 | 2024-12-20 |
| Laptop Asus ROG Strix G16 | 2024-05-29 |
| Smartfon Apple iPhone 16 Pro | 2024-05-16 |
| Smartfon Xiaomi 14T | 2024-12-21 |
| Smartfon Sony Xperia 10 VI | 2024-10-28 |
| Siekiera Fiskars X17 | 2024-12-09 |

### Zadanie 63 · JOIN + IS NOT NULL + GROUP BY + LIMIT

**Odpowiedź:** **Żarówka Philips LED E27** — **29**

```sql
SELECT p.nazwa, COUNT(*) AS ZKomentarzem
FROM opinie o
JOIN produkty p ON o.id_produktu = p.id
WHERE o.tresc IS NOT NULL
GROUP BY p.nazwa
ORDER BY ZKomentarzem DESC
LIMIT 1;
```

Wynik: **1 wiersz**

| nazwa | ZKomentarzem |
|---|---|
| Żarówka Philips LED E27 | 29 |

### Zadanie 64 · JOIN 3 tabel + COUNT(DISTINCT) + SUM

**Odpowiedź:** **10** zamówień, **8630.04 zł**

```sql
SELECT COUNT(DISTINCT z.id) AS Zamowien, SUM(pz.ilosc * pz.cena_jednostkowa) AS Wydatki
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE k.email = 'monika.sadowska@gmail.com' AND z.status <> 'anulowane';
```

Wynik: **1 wiersz**

| Zamowien | Wydatki |
|---|---|
| 10 | 8630.04 |

> ⚠️ `COUNT(*)` w tym zapytaniu daje liczbę **pozycji**, a nie zamówień.

### Zadanie 65 · JOIN 3 tabel + GROUP BY + HAVING

**Odpowiedź:** **Polska** — **4.03** (274 opinii)

```sql
SELECT pr.kraj, COUNT(*) AS Opinii, ROUND(AVG(o.ocena), 2) AS Srednia
FROM opinie o
JOIN produkty p ON o.id_produktu = p.id
JOIN producenci pr ON p.id_producenta = pr.id
GROUP BY pr.kraj
HAVING COUNT(*) >= 50
ORDER BY Srednia DESC;
```

Wynik: **7 wierszy**

| kraj | Opinii | Srednia |
|---|---|---|
| Polska | 274 | 4.03 |
| Korea Południowa | 54 | 3.96 |
| Holandia | 78 | 3.90 |
| Francja | 98 | 3.80 |
| Dania | 55 | 3.58 |
| Szwajcaria | 65 | 3.49 |
| Niemcy | 62 | 3.48 |

### Zadanie 66 · JOIN + MIN + GROUP BY

**Odpowiedź:** **649.00 zł** (Apple)

```sql
SELECT pr.nazwa, MIN(p.cena) AS Najtanszy
FROM produkty p
JOIN producenci pr ON p.id_producenta = pr.id
WHERE pr.kraj = 'USA'
GROUP BY pr.nazwa;
```

Wynik: **4 wiersze**

| nazwa | Najtanszy |
|---|---|
| Apple | 649.00 |
| Dell | 649.99 |
| JBL | 179.00 |
| Microsoft | 259.00 |

### Zadanie 67 · JOIN + GROUP BY + LIMIT

**Odpowiedź:** **Wrocław** — **96**

```sql
SELECT k.miasto, COUNT(*) AS Opinii
FROM opinie o
JOIN klienci k ON o.id_klienta = k.id
GROUP BY k.miasto
ORDER BY Opinii DESC
LIMIT 3;
```

Wynik: **3 wiersze**

| miasto | Opinii |
|---|---|
| Warszawa | 115 |
| Poznań | 110 |
| Wrocław | 96 |

### Zadanie 68 · porównanie z wyrażeniem

**Odpowiedź:** **10** produktów

```sql
SELECT COUNT(*) AS Ile FROM produkty WHERE cena_promocyjna < 0.8 * cena;
```

Wynik: **1 wiersz**

| Ile |
|---|
| 10 |

> ⚠️ Produkty bez promocji (`NULL`) same odpadają — porównanie z `NULL` nie jest prawdziwe.

### Zadanie 69 · JOIN 3 tabel + YEAR() po obu stronach

**Odpowiedź:** **174** pozycji

```sql
SELECT COUNT(*) AS Ile
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
WHERE YEAR(z.data_zamowienia) = YEAR(p.data_dodania);
```

Wynik: **1 wiersz**

| Ile |
|---|
| 174 |

### Zadanie 70 · JOIN 3 tabel w zapisie egzaminacyjnym

**Odpowiedź:** **4** wierszy

```sql
SELECT klienci.imie, klienci.nazwisko, produkty.nazwa, pozycje_zamowienia.ilosc
FROM klienci, zamowienia, pozycje_zamowienia, produkty
WHERE zamowienia.id_klienta = klienci.id
  AND pozycje_zamowienia.id_zamowienia = zamowienia.id
  AND pozycje_zamowienia.id_produktu = produkty.id
  AND zamowienia.data_zamowienia = '2026-05-01'
ORDER BY klienci.nazwisko;
```

Wynik: **4 wiersze**

| imie | nazwisko | nazwa | ilosc |
|---|---|---|---|
| Bartosz | Dąbrowski | Sieci komputerowe. Kompendium | 1 |
| Zofia | Piotrowska | Mysz Logitech M185 | 1 |
| Zofia | Piotrowska | Linux. Komendy i polecenia | 1 |
| Zofia | Piotrowska | Gra planszowa Trefl Rodzina Treflików | 1 |

---

## ★★★★ Poziom 4 · Kilka tabel, raporty i LEFT JOIN

### Zadanie 71 · pułapka: dwie osoby o tym samym nazwisku

**Odpowiedź:** **2** wierszy, pierwszy: **Grabie Fiskars Solid**

```sql
SELECT z.data_zamowienia, p.nazwa, pz.ilosc, pz.cena_jednostkowa
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
WHERE k.imie = 'Anna' AND k.nazwisko = 'Nowak' AND k.miasto = 'Gdańsk'
ORDER BY z.data_zamowienia, p.nazwa;
```

Wynik: **2 wiersze**

| data_zamowienia | nazwa | ilosc | cena_jednostkowa |
|---|---|---|---|
| 2026-10-13 | Grabie Fiskars Solid | 2 | 79.99 |
| 2026-10-13 | Ładowarka Xiaomi 67W | 2 | 84.99 |

### Zadanie 72 · JOIN 3 tabel + SUM + WHERE YEAR + LIMIT

**Odpowiedź:** **Weronika Jabłońska** — **16925.97 zł**

```sql
SELECT k.imie, k.nazwisko, SUM(pz.ilosc * pz.cena_jednostkowa) AS Wydatki
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE YEAR(z.data_zamowienia) = 2025 AND z.status <> 'anulowane'
GROUP BY k.id, k.imie, k.nazwisko
ORDER BY Wydatki DESC
LIMIT 5;
```

Wynik: **5 wierszy**

| imie | nazwisko | Wydatki |
|---|---|---|
| Zofia | Jankowska | 24271.53 |
| Grzegorz | Nowak | 21988.03 |
| Marta | Piotrowska | 18690.31 |
| Piotr | Wójcik | 17195.76 |
| Weronika | Jabłońska | 16925.97 |

### Zadanie 73 · JOIN 4 tabel + SUM + GROUP BY + LIMIT

**Odpowiedź:** **Apple** — **130219.02 zł**

```sql
SELECT pr.nazwa, SUM(pz.ilosc * pz.cena_jednostkowa) AS Przychod
FROM producenci pr
JOIN produkty p ON p.id_producenta = pr.id
JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
JOIN zamowienia z ON pz.id_zamowienia = z.id
WHERE z.status <> 'anulowane'
GROUP BY pr.nazwa
ORDER BY Przychod DESC
LIMIT 3;
```

Wynik: **3 wiersze**

| nazwa | Przychod |
|---|---|
| Dell | 139774.63 |
| Samsung | 139126.11 |
| Apple | 130219.02 |

### Zadanie 74 · pułapka: GROUP BY po id + MIN

**Odpowiedź:** **Warszawa: 3 zam., od 2025-01-29**; **Poznań: 6 zam., od 2025-02-21**

```sql
SELECT k.id, k.miasto, COUNT(*) AS Zamowien, MIN(z.data_zamowienia) AS Pierwsze
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
WHERE k.imie = 'Piotr' AND k.nazwisko = 'Wiśniewski'
GROUP BY k.id, k.miasto;
```

Wynik: **2 wiersze**

| id | miasto | Zamowien | Pierwsze |
|---|---|---|---|
| 95 | Warszawa | 3 | 2025-01-29 |
| 247 | Poznań | 6 | 2025-02-21 |

> ⚠️ `GROUP BY k.imie, k.nazwisko` skleja obie osoby — wychodzi jeden wiersz z sumą zamówień.

### Zadanie 75 · LEFT JOIN + COUNT(kolumna) + JOIN

**Odpowiedź:** **Siekiera Fiskars X17** (0 zamówień)

```sql
SELECT p.nazwa, COUNT(pz.id_zamowienia) AS Zamowien
FROM produkty p
JOIN producenci pr ON p.id_producenta = pr.id
LEFT JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
WHERE pr.nazwa = 'Fiskars'
GROUP BY p.nazwa
ORDER BY Zamowien;
```

Wynik: **3 wiersze**

| nazwa | Zamowien |
|---|---|
| Siekiera Fiskars X17 | 0 |
| Sekator Fiskars PowerGear | 33 |
| Grabie Fiskars Solid | 37 |

### Zadanie 76 · JOIN 5 tabel + COUNT(DISTINCT)

**Odpowiedź:** **13** klientów

```sql
SELECT COUNT(DISTINCT k.id) AS Klienci
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
JOIN kategorie kat ON p.id_kategorii = kat.id
WHERE k.miasto = 'Warszawa' AND kat.nazwa = 'AGD' AND z.status <> 'anulowane';
```

Wynik: **1 wiersz**

| Klienci |
|---|
| 13 |

### Zadanie 77 · JOIN 3 tabel + WHERE YEAR + HAVING SUM

**Odpowiedź:** **4** produktów

```sql
SELECT p.nazwa, SUM(pz.ilosc * pz.cena_jednostkowa) AS Przychod
FROM produkty p
JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
JOIN zamowienia z ON pz.id_zamowienia = z.id
WHERE YEAR(z.data_zamowienia) = 2026 AND z.status <> 'anulowane'
GROUP BY p.nazwa
HAVING SUM(pz.ilosc * pz.cena_jednostkowa) > 15000
ORDER BY Przychod DESC;
```

Wynik: **4 wiersze**

| nazwa | Przychod |
|---|---|
| Laptop Dell XPS 13 | 41994.00 |
| Laptop Apple MacBook Air 13 M3 | 21196.00 |
| Ekspres Philips 2200 LatteGo | 19990.00 |
| Laptop Lenovo ThinkPad E14 | 15596.00 |

### Zadanie 78 · JOIN + WHERE + HAVING SUM

**Odpowiedź:** **74** zamówień

```sql
SELECT z.id, SUM(pz.ilosc * pz.cena_jednostkowa) AS Towary, z.koszt_dostawy
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE z.koszt_dostawy > 0
GROUP BY z.id, z.koszt_dostawy
HAVING SUM(pz.ilosc * pz.cena_jednostkowa) > 250;
```

Wynik: **74 wiersze**

| id | Towary | koszt_dostawy |
|---|---|---|
| 25 | 299.00 | 9.99 |
| 86 | 265.74 | 14.99 |
| 139 | 295.97 | 14.99 |
| 169 | 259.00 | 9.99 |
| 184 | 299.00 | 14.99 |
| … | … | … |

> ⚠️ Wszystkie mają wartość poniżej 300 zł — od 300 zł dostawa jest darmowa.

### Zadanie 79 · JOIN + LEFT JOIN … IS NULL + COUNT(DISTINCT)

**Odpowiedź:** **64** klientów

```sql
SELECT COUNT(DISTINCT k.id) AS Klienci
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
LEFT JOIN opinie o ON o.id_klienta = k.id
WHERE o.id IS NULL;
```

Wynik: **1 wiersz**

| Klienci |
|---|
| 64 |

> ⚠️ Porównaj z zadaniem 61: różnica to klienci bez zamówień (oni też nie mają opinii).

### Zadanie 80 · LEFT JOIN … IS NULL + WHERE

**Odpowiedź:** **6** klientów

```sql
SELECT k.imie, k.nazwisko
FROM klienci k
LEFT JOIN opinie o ON o.id_klienta = k.id
WHERE o.id IS NULL AND k.miasto = 'Poznań';
```

Wynik: **6 wierszy**

| imie | nazwisko |
|---|---|
| Monika | Stępień |
| Julia | Ostrowska |
| Justyna | Dudek |
| Paweł | Grabowski |
| Oskar | Wróbel |
| Dominika | Witkowska |

### Zadanie 81 · MONTH() + HAVING COUNT(DISTINCT)

**Odpowiedź:** miesiące: **5, 6, 8, 10, 11, 12** (6)

```sql
SELECT MONTH(data_zamowienia) AS Miesiac, COUNT(DISTINCT id_klienta) AS Klientow
FROM zamowienia
WHERE YEAR(data_zamowienia) = 2025
GROUP BY MONTH(data_zamowienia)
HAVING COUNT(DISTINCT id_klienta) > 55
ORDER BY Miesiac;
```

Wynik: **6 wierszy**

| Miesiac | Klientow |
|---|---|
| 5 | 59 |
| 6 | 56 |
| 8 | 63 |
| 10 | 57 |
| 11 | 84 |
| 12 | 95 |

### Zadanie 82 · JOIN 4 tabel + SUM + GROUP BY

**Odpowiedź:** **USA** — **328249.58 zł**

```sql
SELECT pr.kraj, SUM(pz.ilosc * pz.cena_jednostkowa) AS Przychod
FROM producenci pr
JOIN produkty p ON p.id_producenta = pr.id
JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
JOIN zamowienia z ON pz.id_zamowienia = z.id
WHERE z.status <> 'anulowane'
GROUP BY pr.kraj
ORDER BY Przychod DESC;
```

Wynik: **12 wierszy**

| kraj | Przychod |
|---|---|
| USA | 328249.58 |
| Chiny | 189087.81 |
| Polska | 167467.06 |
| Korea Południowa | 139126.11 |
| Holandia | 93787.10 |
| … | … |

### Zadanie 83 · JOIN 4 tabel + COUNT(DISTINCT) + YEAR

**Odpowiedź:** **15** klientów

```sql
SELECT COUNT(DISTINCT z.id_klienta) AS Klienci
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
JOIN producenci pr ON p.id_producenta = pr.id
WHERE pr.nazwa = 'Apple' AND YEAR(z.data_zamowienia) = 2026 AND z.status <> 'anulowane';
```

Wynik: **1 wiersz**

| Klienci |
|---|
| 15 |

### Zadanie 84 · JOIN + YEAR + GROUP BY + LIMIT

**Odpowiedź:** **karta** — **76** zamówień

```sql
SELECT z.sposob_platnosci, COUNT(*) AS Zamowien
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
WHERE YEAR(k.data_urodzenia) >= 2000
GROUP BY z.sposob_platnosci
ORDER BY Zamowien DESC
LIMIT 1;
```

Wynik: **1 wiersz**

| sposob_platnosci | Zamowien |
|---|---|
| karta | 76 |

### Zadanie 85 · GROUP BY + HAVING SUM (pozycje)

**Odpowiedź:** **158** zamówień

```sql
SELECT id_zamowienia, SUM(ilosc) AS Sztuk
FROM pozycje_zamowienia
GROUP BY id_zamowienia
HAVING SUM(ilosc) >= 6;
```

Wynik: **158 wierszy**

| id_zamowienia | Sztuk |
|---|---|
| 2 | 9 |
| 13 | 7 |
| 41 | 9 |
| 47 | 6 |
| 57 | 8 |
| … | … |

### Zadanie 86 · JOIN + AVG + HAVING + ORDER BY

**Odpowiedź:** **Zielona Góra** — **3.50**

```sql
SELECT k.miasto, COUNT(*) AS Opinii, ROUND(AVG(o.ocena), 2) AS Srednia
FROM opinie o
JOIN klienci k ON o.id_klienta = k.id
GROUP BY k.miasto
HAVING COUNT(*) >= 30
ORDER BY Srednia;
```

Wynik: **8 wierszy**

| miasto | Opinii | Srednia |
|---|---|---|
| Zielona Góra | 30 | 3.50 |
| Kraków | 84 | 3.77 |
| Gdańsk | 82 | 3.80 |
| Warszawa | 115 | 3.83 |
| Poznań | 110 | 3.85 |
| Rzeszów | 38 | 3.87 |
| Łódź | 61 | 3.87 |
| Wrocław | 96 | 3.91 |

### Zadanie 87 · JOIN 4 tabel + daty + SUM + LIMIT

**Odpowiedź:** **Książki** — **102** szt.

```sql
SELECT kat.nazwa, SUM(pz.ilosc) AS Sztuk
FROM kategorie kat
JOIN produkty p ON p.id_kategorii = kat.id
JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
JOIN zamowienia z ON pz.id_zamowienia = z.id
WHERE z.data_zamowienia BETWEEN '2025-12-01' AND '2025-12-31' AND z.status <> 'anulowane'
GROUP BY kat.nazwa
ORDER BY Sztuk DESC
LIMIT 1;
```

Wynik: **1 wiersz**

| nazwa | Sztuk |
|---|---|
| Książki | 102 |

### Zadanie 88 · LEFT JOIN … IS NULL + YEAR

**Odpowiedź:** **9** klientów

```sql
SELECT k.imie, k.nazwisko, k.data_rejestracji
FROM klienci k
LEFT JOIN zamowienia z ON z.id_klienta = k.id
WHERE z.id IS NULL AND YEAR(k.data_rejestracji) = 2026;
```

Wynik: **9 wierszy**

| imie | nazwisko | data_rejestracji |
|---|---|---|
| Weronika | Nowak | 2026-10-16 |
| Julia | Ostrowska | 2026-10-28 |
| Kamil | Walczak | 2026-02-09 |
| Maria | Jankowska | 2026-05-06 |
| Szymon | Król | 2026-10-27 |
| … | … | … |

### Zadanie 89 · pułapka: COUNT(DISTINCT) po JOIN

**Odpowiedź:** Audio: **147** klientów, **233** zamówień

```sql
SELECT kat.nazwa, COUNT(DISTINCT z.id_klienta) AS Klientow, COUNT(DISTINCT z.id) AS Zamowien
FROM kategorie kat
JOIN produkty p ON p.id_kategorii = kat.id
JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
JOIN zamowienia z ON pz.id_zamowienia = z.id
GROUP BY kat.nazwa
ORDER BY kat.nazwa;
```

Wynik: **10 wierszy**

| nazwa | Klientow | Zamowien |
|---|---|---|
| AGD | 136 | 246 |
| Akcesoria komputerowe | 197 | 461 |
| Audio | 147 | 233 |
| Dom i ogród | 184 | 363 |
| Gry i konsole | 104 | 146 |
| … | … | … |

> ⚠️ Jedno zamówienie może zawierać dwa produkty z tej samej kategorii — dlatego `COUNT(*)` daje więcej niż `COUNT(DISTINCT z.id)`.

---

## ★★★★★ Poziom 5 · Poziom egzaminacyjny

### Zadanie 90 · raport: JOIN 4 tabel + kilka agregatów + HAVING

**Odpowiedź:** **9** producentów; 1. miejsce: **Dell** — **38** szt.

```sql
SELECT pr.nazwa, pr.kraj, COUNT(DISTINCT p.id) AS Produktow, SUM(pz.ilosc) AS Sztuk,
       SUM(pz.ilosc * pz.cena_jednostkowa) AS Przychod
FROM producenci pr
JOIN produkty p ON p.id_producenta = pr.id
JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
JOIN zamowienia z ON pz.id_zamowienia = z.id
WHERE z.status <> 'anulowane'
GROUP BY pr.nazwa, pr.kraj
HAVING SUM(pz.ilosc * pz.cena_jednostkowa) > 50000
ORDER BY Przychod DESC;
```

Wynik: **9 wierszy**

| nazwa | kraj | Produktow | Sztuk | Przychod |
|---|---|---|---|---|
| Dell | USA | 4 | 38 | 139774.63 |
| Samsung | Korea Południowa | 9 | 186 | 139126.11 |
| Apple | USA | 6 | 36 | 130219.02 |
| Xiaomi | Chiny | 8 | 212 | 102469.81 |
| Philips | Holandia | 7 | 436 | 93787.10 |
| … | … | … | … | … |

### Zadanie 91 · pułapka: dwa LEFT JOIN-y + COUNT(DISTINCT)

**Odpowiedź:** **13** wierszy, **1** z 0 zamówień; 1. wiersz: **Łukasz Bąk** — 4 opinii

```sql
SELECT k.imie, k.nazwisko, COUNT(DISTINCT z.id) AS Zamowien, COUNT(DISTINCT o.id) AS Opinii
FROM klienci k
LEFT JOIN zamowienia z ON z.id_klienta = k.id
LEFT JOIN opinie o ON o.id_klienta = k.id
WHERE k.miasto = 'Katowice'
GROUP BY k.id, k.imie, k.nazwisko
ORDER BY Zamowien DESC, Opinii DESC, k.nazwisko;
```

Wynik: **13 wierszy**

| imie | nazwisko | Zamowien | Opinii |
|---|---|---|---|
| Łukasz | Bąk | 8 | 4 |
| Natalia | Michalska | 6 | 1 |
| Rafał | Kowalczyk | 4 | 6 |
| Kamil | Górski | 4 | 5 |
| Justyna | Wiśniewska | 4 | 4 |
| … | … | … | … |

> ⚠️ Zwykły `JOIN` gubi klientów bez zamówień albo bez opinii. `COUNT(*)` (albo `COUNT(z.id)` bez `DISTINCT`) daje iloczyn zamówień i opinii.

### Zadanie 92 · raport klienta: COUNT(DISTINCT) + SUM + MAX

**Odpowiedź:** **Anna Malinowska**: 8 zamówień, 20 szt., **6342.99 zł**, ostatnie 2026-10-05

```sql
SELECT k.imie, k.nazwisko, COUNT(DISTINCT z.id) AS Zamowien, SUM(pz.ilosc) AS Sztuk,
       SUM(pz.ilosc * pz.cena_jednostkowa) AS Wydatki, MAX(z.data_zamowienia) AS Ostatnie
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE k.miasto = 'Gdynia'
GROUP BY k.id, k.imie, k.nazwisko
ORDER BY Wydatki DESC;
```

Wynik: **10 wierszy**

| imie | nazwisko | Zamowien | Sztuk | Wydatki | Ostatnie |
|---|---|---|---|---|---|
| Anna | Malinowska | 8 | 20 | 6342.99 | 2026-10-05 |
| Weronika | Nowicka | 7 | 22 | 6128.51 | 2026-10-21 |
| Michał | Jasiński | 5 | 18 | 3956.62 | 2026-03-04 |
| Oliwia | Marciniak | 4 | 13 | 2123.36 | 2026-07-29 |
| Marek | Sadowski | 3 | 8 | 1361.86 | 2026-09-02 |
| … | … | … | … | … | … |

### Zadanie 93 · HAVING COUNT(DISTINCT) = 2

**Odpowiedź:** **177** klientów

```sql
SELECT id_klienta, COUNT(DISTINCT sposob_dostawy) AS Sposobow
FROM zamowienia
WHERE sposob_dostawy IN ('kurier', 'paczkomat')
GROUP BY id_klienta
HAVING COUNT(DISTINCT sposob_dostawy) = 2;
```

Wynik: **177 wierszy**

| id_klienta | Sposobow |
|---|---|
| 1 | 2 |
| 2 | 2 |
| 3 | 2 |
| 5 | 2 |
| 8 | 2 |
| … | … |

> ⚠️ Bez `WHERE … IN` warunek `= 2` złapie też np. parę „kurier + odbiór osobisty”, a pominie osoby z wszystkimi trzema sposobami.

### Zadanie 94 · JOIN + HAVING COUNT(DISTINCT)

**Odpowiedź:** **38** klientów

```sql
SELECT k.imie, k.nazwisko, COUNT(DISTINCT p.id_kategorii) AS Kategorii, COUNT(*) AS Opinii
FROM opinie o
JOIN klienci k ON o.id_klienta = k.id
JOIN produkty p ON o.id_produktu = p.id
GROUP BY k.id, k.imie, k.nazwisko
HAVING COUNT(DISTINCT p.id_kategorii) >= 5
ORDER BY Kategorii DESC;
```

Wynik: **38 wierszy**

| imie | nazwisko | Kategorii | Opinii |
|---|---|---|---|
| Barbara | Tomaszewska | 9 | 14 |
| Natalia | Jaworska | 9 | 11 |
| Monika | Grabowska | 9 | 12 |
| Oskar | Piotrowski | 8 | 11 |
| Krzysztof | Majewski | 8 | 10 |
| … | … | … | … |

### Zadanie 95 · SUM / COUNT(DISTINCT) + HAVING

**Odpowiedź:** **Gdańsk** — **5804.93 zł** (23 kupujących)

```sql
SELECT k.miasto, COUNT(DISTINCT k.id) AS Kupujacych,
       ROUND(SUM(pz.ilosc * pz.cena_jednostkowa) / COUNT(DISTINCT k.id), 2) AS NaKlienta
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
WHERE z.status <> 'anulowane'
GROUP BY k.miasto
HAVING COUNT(DISTINCT k.id) >= 10
ORDER BY NaKlienta DESC;
```

Wynik: **7 wierszy**

| miasto | Kupujacych | NaKlienta |
|---|---|---|
| Gdańsk | 23 | 5804.93 |
| Poznań | 28 | 5433.21 |
| Łódź | 22 | 4733.71 |
| Warszawa | 40 | 4539.47 |
| Wrocław | 34 | 3855.88 |
| Kraków | 31 | 2871.68 |
| Katowice | 12 | 2454.57 |

> ⚠️ `AVG(pz.ilosc * pz.cena_jednostkowa)` to średnia wartość **pozycji**, a nie wydatki na klienta.

### Zadanie 96 · JOIN 4 tabel + HAVING COUNT(DISTINCT) + YEAR

**Odpowiedź:** **9** producentów; 1. miejsce: **Znak** (107 klientów)

```sql
SELECT pr.nazwa, COUNT(DISTINCT z.id_klienta) AS Klientow
FROM producenci pr
JOIN produkty p ON p.id_producenta = pr.id
JOIN pozycje_zamowienia pz ON pz.id_produktu = p.id
JOIN zamowienia z ON pz.id_zamowienia = z.id
WHERE YEAR(z.data_zamowienia) = 2026 AND z.status <> 'anulowane'
GROUP BY pr.nazwa
HAVING COUNT(DISTINCT z.id_klienta) >= 40
ORDER BY Klientow DESC;
```

Wynik: **9 wierszy**

| nazwa | Klientow |
|---|---|
| Znak | 107 |
| Helion | 97 |
| Philips | 92 |
| Decathlon | 84 |
| Logitech | 56 |
| … | … |

### Zadanie 97 · JOIN + obliczenia w SUM + LIMIT

**Odpowiedź:** **Agnieszka Wiśniewska** — **1711.59 zł**

```sql
SELECT k.imie, k.nazwisko, SUM((p.cena - pz.cena_jednostkowa) * pz.ilosc) AS Oszczednosc
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
WHERE pz.cena_jednostkowa < p.cena
GROUP BY k.id, k.imie, k.nazwisko
ORDER BY Oszczednosc DESC
LIMIT 3;
```

Wynik: **3 wiersze**

| imie | nazwisko | Oszczednosc |
|---|---|---|
| Agnieszka | Wiśniewska | 1711.59 |
| Dominika | Woźniak | 1632.13 |
| Paweł | Jankowski | 1119.62 |

### Zadanie 98 · HAVING z COUNT(DISTINCT) i AVG

**Odpowiedź:** **9** produktów

```sql
SELECT p.nazwa, COUNT(DISTINCT z.id_klienta) AS Klientow,
       ROUND(AVG(pz.cena_jednostkowa), 2) AS SredniaCenaZakupu, p.cena
FROM zamowienia z
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
GROUP BY p.id, p.nazwa, p.cena
HAVING COUNT(DISTINCT z.id_klienta) >= 30 AND AVG(pz.cena_jednostkowa) < p.cena;
```

Wynik: **9 wierszy**

| nazwa | Klientow | SredniaCenaZakupu | cena |
|---|---|---|---|
| Klawiatura Logitech K120 | 60 | 44.43 | 49.99 |
| Blender Bosch ErgoMixx | 39 | 265.37 | 279.00 |
| Piłka nożna Decathlon F500 | 44 | 81.79 | 89.00 |
| Bidon Decathlon 0,75 l | 95 | 19.03 | 19.99 |
| SQL. Praktyczny kurs | 50 | 64.80 | 69.00 |
| … | … | … | … |

> ⚠️ Średnia cena zakupu jest niższa tylko wtedy, gdy część sztuk kupiono w promocji.

### Zadanie 99 · pułapka: dwie tabele „wiele” naraz

**Odpowiedź:** **12** klientów; 1. wiersz: **Monika Grabowska** — 12 opinii, 21 zamówień

```sql
SELECT k.imie, k.nazwisko, COUNT(DISTINCT o.id) AS Opinii, COUNT(DISTINCT z.id) AS Zamowien
FROM klienci k
JOIN opinie o ON o.id_klienta = k.id
JOIN zamowienia z ON z.id_klienta = k.id
WHERE k.miasto = 'Gdańsk'
GROUP BY k.id, k.imie, k.nazwisko
HAVING COUNT(DISTINCT o.id) >= 3
ORDER BY Opinii DESC, k.nazwisko;
```

Wynik: **12 wierszy**

| imie | nazwisko | Opinii | Zamowien |
|---|---|---|---|
| Monika | Grabowska | 12 | 21 |
| Oskar | Piotrowski | 11 | 19 |
| Oskar | Kowalczyk | 9 | 15 |
| Aleksandra | Walczak | 8 | 15 |
| Filip | Grabowski | 7 | 6 |
| … | … | … | … |

> ⚠️ `COUNT(*)` daje tu iloczyn opinii i zamówień (np. 5 opinii × 8 zamówień = 40).

### Zadanie 100 · pełne zapytanie: JOIN 5 tabel + COUNT(DISTINCT) + LIMIT

**Odpowiedź:** **Barbara Tomaszewska** — **8** produktów, **3161.96 zł**

```sql
SELECT k.imie, k.nazwisko, COUNT(DISTINCT p.id) AS Produktow, SUM(pz.ilosc * pz.cena_jednostkowa) AS Wydatki
FROM klienci k
JOIN zamowienia z ON z.id_klienta = k.id
JOIN pozycje_zamowienia pz ON pz.id_zamowienia = z.id
JOIN produkty p ON pz.id_produktu = p.id
JOIN kategorie kat ON p.id_kategorii = kat.id
WHERE kat.nazwa = 'Akcesoria komputerowe' AND z.status <> 'anulowane'
GROUP BY k.id, k.imie, k.nazwisko
ORDER BY Produktow DESC, Wydatki DESC
LIMIT 3;
```

Wynik: **3 wiersze**

| imie | nazwisko | Produktow | Wydatki |
|---|---|---|---|
| Barbara | Tomaszewska | 8 | 3161.96 |
| Andrzej | Ostrowski | 7 | 2883.97 |
| Oskar | Piotrowski | 7 | 2801.95 |
