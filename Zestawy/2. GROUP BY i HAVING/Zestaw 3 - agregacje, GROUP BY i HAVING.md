# Zestaw 3 — Agregacje, `GROUP BY` i `HAVING`

**Baza:** `world` (plik `world_pl.sql`) | **Narzędzie:** XAMPP → phpMyAdmin → zakładka **SQL**
**Materiał pomocniczy:** ściąga „GROUP BY + HAVING" (na końcu ściągi jest animacja krok po kroku)
**Zakres:** `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`, `COUNT(DISTINCT …)`, `GROUP BY`, `HAVING`,
pełny schemat zapytania. **Bez `JOIN`** — cały czas pracujemy na jednej tabeli.

**Tabele w bazie:**

| Tabela | Co zawiera | Kolumny przydatne w tym zestawie |
|---|---|---|
| `kraje` | 239 państw | `kod`, `nazwa`, `kontynent`, `region`, `powierzchnia`, `rok_niepodleglosci`, `liczba_mieszkancow`, `srednia_dlugosc_zycia`, `pkb`, `ustroj` |
| `miasta` | 4079 miast | `id`, `nazwa`, `kod_kraju`, `wojewodztwo`, `liczba_mieszkancow` |
| `jezyki` | 984 wpisy | `kod_kraju`, `jezyk`, `oficjalny` (`T`/`F`), `procent` |

**Zasady:**
- każde zapytanie kończymy średnikiem `;`, tekst w apostrofach (`'POL'`), ułamki z **kropką**,
- w każdym zadaniu z `GROUP BY` nadawaj **aliasy** (`AS Ilu`, `AS Ludnosc`) — inaczej nagłówki są nieczytelne,
- po każdym zapytaniu sprawdź **ile wierszy** zwróciło (liczba jest nad wynikiem) i zapisz ją w zeszycie,
- zadania z gwiazdką ⭐ są dla szybszych.

---

## Część I — Jedna liczba z całej tabeli

**Zadanie 1.** Ile jest krajów w tabeli `kraje`?
> Potrzebne: `COUNT(*)`. Nadaj wynikowi nagłówek `IleKrajow`.

**Zadanie 2.** Ile jest miast w tabeli `miasta`, a ile wpisów w tabeli `jezyki`?
(dwa osobne zapytania)

**Zadanie 3.** Wykonaj jedno zapytanie na tabeli `kraje`, które pokaże obok siebie
`COUNT(*)` oraz `COUNT(srednia_dlugosc_zycia)`.
**Dlaczego liczby są różne?** Zapisz wniosek jednym zdaniem.

**Zadanie 4.** Ile krajów ma wpisany `rok_niepodleglosci`, a ile nie ma?
Liczbę braków policz **dwoma sposobami**: przez `COUNT(*) - COUNT(rok_niepodleglosci)`
oraz przez `COUNT(*)` z warunkiem `WHERE rok_niepodleglosci IS NULL`.

**Zadanie 5.** Ilu jest łącznie mieszkańców wszystkich krajów świata?
> Potrzebne: `SUM(liczba_mieszkancow)`

**Zadanie 6.** Jaka jest średnia długość życia na świecie? Zaokrąglij do **2 miejsc** po kropce
i podpisz kolumnę `SredniaZycia`.
> Potrzebne: `ROUND(AVG(...), 2)`

**Zadanie 7.** Podaj powierzchnię najmniejszego i największego kraju — w jednym zapytaniu.
> Potrzebne: `MIN` i `MAX`

**Zadanie 8.** Jaka jest największa liczba mieszkańców miasta w bazie (`MAX`)?
Następnie **drugim zapytaniem** (`ORDER BY … DESC LIMIT 1`) sprawdź, **które to miasto**.
Dlaczego pierwsze zapytanie nie mogło pokazać nazwy?

**Zadanie 9.** Ile jest **różnych** kontynentów, a ile różnych regionów w tabeli `kraje`?
> Potrzebne: `COUNT(DISTINCT kolumna)`

**Zadanie 10.** Ile jest **różnych** języków w tabeli `jezyki`? Porównaj tę liczbę
z wynikiem `COUNT(*)` z zadania 2 i wyjaśnij różnicę.

---

## Część II — Agregat z warunkiem `WHERE`

**Zadanie 11.** Ile miast Polski (`kod_kraju = 'POL'`) jest w bazie?

**Zadanie 12.** Ile krajów leży w Europie?

**Zadanie 13.** Dla polskich miast podaj w jednym zapytaniu: **sumę** mieszkańców
i **średnią** liczbę mieszkańców (średnią zaokrąglij do liczby całkowitej).
> Potrzebne: `SUM`, `ROUND(AVG(...))` oraz `WHERE`

**Zadanie 14.** Jaka jest średnia długość życia w Europie? Zaokrąglij do 1 miejsca.

**Zadanie 15.** Ile mieszkańców ma największe miasto Niemiec (`DEU`)?
Sprawdź drugim zapytaniem, jak się nazywa.

**Zadanie 16.** Ile wpisów w tabeli `jezyki` dotyczy języków **oficjalnych** (`oficjalny = 'T'`)?

**Zadanie 17.** Ile krajów Afryki ma średnią długość życia **poniżej 50 lat**?
> Dwa warunki naraz — `AND`.

---

## Część III — `GROUP BY`, czyli podsumowanie w grupach

**Zadanie 18.** Ile krajów leży na każdym kontynencie? Posortuj malejąco.
> Wzór do zapamiętania:
> ```sql
> SELECT kontynent, COUNT(*) AS Kraje
> FROM kraje
> GROUP BY kontynent
> ORDER BY Kraje DESC;
> ```

**Zadanie 19.** Ilu mieszkańców ma każdy kontynent (`SUM`)? Posortuj od najludniejszego.

**Zadanie 20.** Jaka jest średnia długość życia na każdym kontynencie (`ROUND` do 1 miejsca)?
Jeden kontynent ma w wyniku `NULL` — który i dlaczego?

**Zadanie 21.** Ile miast z bazy należy do poszczególnych krajów (`kod_kraju`)?
Pokaż **10 krajów z największą liczbą miast**.

**Zadanie 22.** Ile polskich miast przypada na każde województwo?
Posortuj malejąco. Które województwo wygrywa i czy to Cię dziwi?

**Zadanie 23.** Dla każdego województwa policz **sumę** mieszkańców polskich miast.
Pokaż 5 najludniejszych województw.

**Zadanie 24.** Ile krajów leży w poszczególnych regionach (`region`)? Pokaż 5 największych regionów.

**Zadanie 25.** W tabeli `jezyki` policz, **w ilu krajach** występuje każdy język.
Pokaż 5 najpopularniejszych języków.

**Zadanie 26.** Dla każdego kontynentu podaj liczbę mieszkańców **najludniejszego** kraju
(`MAX(liczba_mieszkancow)`). Posortuj malejąco.

**Zadanie 27.** Ile krajów ma poszczególne ustroje (`ustroj`)? Pokaż 5 najczęstszych.

**Zadanie 28.** W tabeli `jezyki` pogrupuj wiersze po kolumnie `oficjalny` i podaj dla każdej grupy:
liczbę wpisów oraz średni `procent` (zaokrąglony do 2 miejsc).
Co mówią te dwie liczby?

**Zadanie 29.** Grupowanie po **dwóch** kolumnach: dla krajów Europy pokaż
`kontynent`, `ustroj` i liczbę krajów. Posortuj malejąco.
> `GROUP BY kontynent, ustroj` — pamiętaj, że **obie** kolumny muszą być też w `SELECT`.
> Więcej zadań na grupowanie po dwóch kolumnach znajdziesz w **Części VII**.

**Zadanie 30.** ⭐ Dla każdego województwa Polski podaj liczbę mieszkańców **największego** miasta
i posortuj malejąco. Pokaż 5 pierwszych wierszy.

---

## Część IV — `HAVING`, czyli filtr na grupy

**Zadanie 31.** Które kontynenty mają **więcej niż 40** krajów?
> ```sql
> SELECT kontynent, COUNT(*) AS Kraje
> FROM kraje
> GROUP BY kontynent
> HAVING COUNT(*) > 40
> ORDER BY Kraje DESC;
> ```
> **Pytanie:** dlaczego nie można tu napisać `WHERE COUNT(*) > 40`?

**Zadanie 32.** Które kontynenty mają łączną populację **powyżej 500 milionów**?
Zanim wykonasz zapytanie — obstaw, ile ich będzie. Który kontynent jest najbliżej granicy?

**Zadanie 33.** Które województwa mają w bazie **więcej niż 2** polskie miasta?

**Zadanie 34.** Które kraje mają w bazie **więcej niż 100** miast?

**Zadanie 35.** Które języki występują w **więcej niż 20** krajach?

**Zadanie 36.** Na których kontynentach średnia długość życia przekracza **70 lat**?

**Zadanie 37.** Które regiony mają **co najmniej 15** krajów?

**Zadanie 38.** Które województwa Polski mają łączną populację miast **powyżej 1 000 000**?

**Zadanie 39.** Dwa warunki w `HAVING` naraz: kontynenty, które mają **więcej niż 30 krajów**
**i jednocześnie** średnią długość życia **poniżej 70 lat**.
W wyniku pokaż kontynent, liczbę krajów i średnią długość życia.

---

## Część V — Pełny schemat zapytania

**Zadanie 40.** Złóż wszystko w jedno zapytanie na tabeli `miasta`:
- tylko polskie miasta (`WHERE`),
- grupuj po województwie (`GROUP BY`),
- pokaż liczbę miast i sumę mieszkańców (`COUNT`, `SUM`),
- zostaw tylko województwa z **co najmniej 2** miastami (`HAVING`),
- posortuj malejąco po sumie mieszkańców (`ORDER BY`),
- pokaż **5 pierwszych** wierszy (`LIMIT`).

Następnie **opisz w zeszycie**, w jakiej kolejności serwer wykonał te klauzule.

**Zadanie 41.** Dla krajów Europy pokaż `region`, liczbę krajów w regionie
oraz średnie `pkb` zaokrąglone do liczby całkowitej.
Zostaw tylko regiony mające **co najmniej 5** krajów, posortuj malejąco po średnim `pkb`.

**Zadanie 42.** Które kraje mają **więcej niż jeden język oficjalny**?
Pokaż `kod_kraju` i liczbę języków oficjalnych, posortuj malejąco.
> Uwaga na kolejność: najpierw `WHERE oficjalny = 'T'`, potem `GROUP BY`, na końcu `HAVING`.

**Zadanie 43.** ⭐ Wypisz kody krajów, które mają w bazie **co najmniej 5** języków
(bez względu na to, czy oficjalne). Posortuj malejąco po liczbie języków.
Ile jest takich krajów?

**Zadanie 44.** ⭐ Które kraje mają **co najmniej 2** miasta powyżej 5 000 000 mieszkańców?
> Najpierw odfiltruj duże miasta (`WHERE`), potem policz je w grupach (`GROUP BY` + `HAVING`).

---

## Część VI — Popraw błąd

**Zadanie 45.** To zapytanie **nie działa**. Uruchom je, przeczytaj komunikat błędu,
a potem popraw tak, żeby pokazywało województwa mające więcej niż 2 miasta.
```sql
SELECT wojewodztwo, COUNT(*) AS Miasta
FROM miasta
WHERE COUNT(*) > 2
GROUP BY wojewodztwo;
```
Zapisz: jaki numer błędu pokazał MySQL i dlaczego tak się stało?

**Zadanie 46.** To zapytanie wykonuje się, ale wynik jest **bezsensowny**.
Wyjaśnij, co jest nie tak, i napraw je na dwa sposoby:
a) usuwając niewłaściwą kolumnę, b) zamieniając ją na funkcję agregującą.
```sql
SELECT nazwa, kontynent, COUNT(*) AS Kraje
FROM kraje
GROUP BY kontynent;
```

**Zadanie 47.** Poniższe dwa zapytania różnią się jedną literą w nazwie klauzuli.
Wykonaj oba i wyjaśnij, **czym różnią się wyniki** (ile wierszy, co znaczą liczby).
```sql
SELECT kontynent, COUNT(*) AS Kraje FROM kraje
WHERE liczba_mieszkancow > 50000000
GROUP BY kontynent;
```
```sql
SELECT kontynent, COUNT(*) AS Kraje FROM kraje
GROUP BY kontynent
HAVING SUM(liczba_mieszkancow) > 50000000;
```

---

## Część VII — Grupowanie po **dwóch** kolumnach

W `GROUP BY` można wypisać kilka kolumn po przecinku. Grupa to wtedy **kombinacja wartości**,
więc grup jest **więcej**, a każda jest **mniejsza**. Wszystkie kolumny grupujące powinny
znaleźć się także w `SELECT` — inaczej nie wiadomo, czego dotyczy policzona liczba.
(Animacja: stepper porównawczy na samym końcu ściągi.)

**Zadanie 48.** Dla krajów `POL`, `CHE` i `ZAF` pokaż `kod_kraju`, `oficjalny`
i liczbę wpisów językowych. Posortuj po kodzie kraju.
> ```sql
> SELECT kod_kraju, oficjalny, COUNT(*) AS Wpisy
> FROM jezyki
> WHERE kod_kraju IN ('POL','CHE','ZAF')
> GROUP BY kod_kraju, oficjalny
> ORDER BY kod_kraju, oficjalny;
> ```
> **Pytania:** który z tych krajów ma najwięcej języków **oficjalnych**?
> Dlaczego jeden kraj zajmuje w wyniku tylko **jeden** wiersz, a nie dwa?

**Zadanie 49.** Policz, ile jest grup, gdy grupujesz tabelę `kraje`:
a) tylko po `kontynent`, b) tylko po `ustroj`, c) po `kontynent, ustroj`.
Liczbę grup odczytaj z licznika wierszy nad wynikiem. Ułóż te trzy liczby od najmniejszej
i zapisz wniosek o tym, jak druga kolumna wpływa na liczbę wierszy.

**Zadanie 50.** Pokaż wszystkie pary `kontynent` + `ustroj`, które występują w **co najmniej
5 krajach**. Posortuj malejąco po liczbie krajów.
> `GROUP BY` po dwóch kolumnach + `HAVING` — filtr grup działa dokładnie tak samo.

**Zadanie 51.** Dla krajów Azji pokaż `kontynent`, `region` i liczbę krajów w każdym regionie.
Posortuj malejąco.

**Zadanie 52.** Pogrupuj całą tabelę `kraje` po `kontynent, region` i policz kraje.
Ile wyszło grup? Porównaj tę liczbę z wynikiem `COUNT(DISTINCT region)` z zadania 9
i wyjaśnij, **dlaczego są równe**.

**Zadanie 53.** Na całej tabeli `miasta` znajdź pary `kod_kraju` + `wojewodztwo`,
w których jest **co najmniej 20 miast**. Posortuj malejąco i podaj pierwsze trzy wiersze.
> Tu grupowanie po dwóch kolumnach jest **konieczne**: nazwy regionów mogą się powtarzać
> w różnych krajach, więc samo `GROUP BY wojewodztwo` zlepiłoby je w jedną grupę.

**Zadanie 54.** ⭐ Dla Polski i Czech (`POL`, `CZE`) pokaż pary kraj + województwo/region,
które mają **co najmniej 2** miasta. Posortuj malejąco po liczbie miast.

---

## Część VIII ⭐ — Wyzwania na bazie `world` (dla tych, którzy zrobili wszystko)

Ta część jest trudniejsza i wymaga kilku **nowych narzędzi**. Każde jest opisane w ramce — przeczytaj
ją, zanim zaczniesz zadanie. Zadania idą od łatwiejszych do trudniejszych.

> 🧰 **Narzędzie 1 — grupowanie po wyrażeniu.** `GROUP BY` nie musi dostać gołej kolumny — może
> grupować po **wyniku funkcji albo obliczenia**. Najwygodniej nadać wyrażeniu alias i grupować po aliasie:
> ```sql
> SELECT LEFT(nazwa, 1) AS Litera, COUNT(*) AS Kraje
> FROM kraje
> GROUP BY Litera;
> ```
> `LEFT(tekst, n)` zwraca pierwsze `n` znaków, `FLOOR(x)` zaokrągla w dół do liczby całkowitej.

> 🧰 **Narzędzie 2 — liczenie warunkowe.** W MySQL/MariaDB warunek ma wartość **1** (prawda) albo **0** (fałsz).
> Dlatego `SUM(warunek)` mówi, **ile wierszy w grupie spełnia warunek** — bez osobnego `WHERE`:
> ```sql
> SELECT kontynent,
>        COUNT(*)                         AS Kraje,
>        SUM(liczba_mieszkancow > 1000000) AS PonadMilion
> FROM kraje
> GROUP BY kontynent;
> ```

> 🧰 **Narzędzie 3 — `GROUP_CONCAT`.** Skleja wartości z całej grupy w jeden tekst:
> `GROUP_CONCAT(nazwa ORDER BY nazwa SEPARATOR ', ')`.

**Zadanie 55.** ⭐ *(narzędzie 1)* Na jaką literę zaczyna się najwięcej nazw krajów (kolumna `nazwa`)?
Pokaż 3 najczęstsze litery z liczbą krajów.

**Zadanie 56.** ⭐ *(narzędzie 1)* W którym **stuleciu** niepodległość uzyskało najwięcej państw?
Numer stulecia to `FLOOR(rok_niepodleglosci / 100) + 1` (rok 1918 → XX wiek = 20).
Weź pod uwagę tylko lata od 1500 wzwyż i posortuj rosnąco po stuleciu.
Dlaczego w XX wieku powstało tak dużo państw?
**Dodatkowo:** sprawdź, które kraje mają `rok_niepodleglosci` **ujemny**. Co oznacza taki rok?

**Zadanie 57.** ⭐ *(narzędzie 1)* Podziel kraje na przedziały długości życia co 10 lat
(`FLOOR(srednia_dlugosc_zycia / 10) * 10 AS Od` — wartość 73.2 trafi do przedziału 70).
Ile krajów jest w każdym przedziale? Skąd w wyniku wziął się wiersz z `NULL`?

**Zadanie 58.** ⭐ *(narzędzie 2)* Dla każdego kontynentu pokaż w **jednym** zapytaniu:
liczbę krajów, liczbę krajów powyżej **50 milionów** mieszkańców oraz **jaki to procent**
krajów kontynentu (zaokrąglony do 1 miejsca). Posortuj malejąco po procencie.

**Zadanie 59.** ⭐ *(narzędzie 2)* Dla krajów `POL`, `CHE`, `IND`, `ZAF` pokaż w **jednym wierszu na kraj**:
liczbę języków oficjalnych i liczbę języków nieoficjalnych. Porównaj z zadaniem 48 —
tam ten sam kraj zajmował dwa wiersze. Który zapis jest czytelniejszy?

**Zadanie 60.** ⭐ *(narzędzie 2)* Ile krajów ma w tabeli `jezyki` wpisane języki, ale **żadnego oficjalnego**?
Pokaż kod kraju i liczbę języków nieoficjalnych, posortuj malejąco. Liczbę krajów odczytaj z licznika wierszy.
> Podpowiedź: warunek na `SUM(...)` trafia do `HAVING`.

**Zadanie 61.** ⭐ Na których kontynentach różnica między **najdłuższą** a **najkrótszą** średnią
długością życia przekracza **30 lat**? Pokaż tę różnicę jako kolumnę `Rozpietosc`.

**Zadanie 62.** ⭐ *(narzędzie 2)* W ilu krajach każdego kontynentu PKB **spadł** w porównaniu
z poprzednim rokiem (`pkb < pkb_poprzedni`)? Posortuj malejąco.
Dlaczego Antarktyda ma w wyniku `NULL`, a nie `0`?

**Zadanie 63.** ⭐ *(narzędzie 3)* Dla województw Polski, które mają w bazie **co najmniej 3** miasta,
pokaż liczbę miast i **listę ich nazw** w jednej komórce — od największego miasta do najmniejszego.

**Zadanie 64.** ⭐ **Detektyw.** Ile krajów z tabeli `kraje` **nie ma** w bazie ani jednego miasta?
A ile nie ma wpisanego żadnego języka? Rozwiąż **bez łączenia tabel**: porównaj liczbę krajów
z liczbą **różnych** kodów krajów w tabeli `miasta` (i w `jezyki`).

**Zadanie 65.** ⭐ **Zapytanie w dwóch krokach.**
a) Policz średnią liczbę mieszkańców kraju na świecie.
b) Wpisz tę liczbę do drugiego zapytania i policz, ile krajów ma ludność **większą niż średnia**.
c) Rozbij wynik z b) na kontynenty.
d) Tylko co szósty kraj jest „powyżej średniej”. Jak to możliwe? Co zawyża średnią?

**Zadanie 66.** ⭐ Jaki **procent ludności świata** mieszka na każdym kontynencie?
Liczbę ludności świata masz z zadania 5 — wpisz ją do wzoru `100 * SUM(...) / ludnosc_swiata`.
Zaokrąglij do 1 miejsca. Czy suma procentów wynosi 100?

**Zadanie 67.** ⭐ Policz **gęstość zaludnienia** każdego kontynentu (mieszkańców na km²)
jako `SUM(liczba_mieszkancow) / SUM(powierzchnia)`. Posortuj malejąco.
Europa wypada zaskakująco nisko — który jeden kraj to powoduje?

**Zadanie 68.** ⭐⭐ **Średnia średniej nierówna.** PKB na mieszkańca kontynentu można policzyć na dwa sposoby
(`pkb` jest w milionach dolarów, więc mnożymy przez 1 000 000):
- **ważony:** `SUM(pkb) * 1000000 / SUM(liczba_mieszkancow)` — cały PKB kontynentu przez wszystkich jego mieszkańców,
- **zwykły:** `AVG(pkb * 1000000 / liczba_mieszkancow)` — średnia z „PKB na osobę” każdego kraju.

Policz oba w jednym zapytaniu (zaokrąglone do całości), tylko dla krajów z `pkb > 0` i `liczba_mieszkancow > 0`.
Dlaczego w **Azji** sposób zwykły daje wynik **wyższy**, a w **Ameryce Północnej** — **znacznie niższy**?
Który sposób odpowiada na pytanie „jak bogaty jest przeciętny mieszkaniec kontynentu”?

---

## Część IX ⭐ — Wyzwania na bazie `szkola` (oceny z wagami)

Zaimportuj plik `szkola.sql` (phpMyAdmin → **Import**) i wybierz bazę `szkola`. Struktura jest
na ściądze „budowa bazy danych i SELECT”. Najważniejsza tabela tej części to **`oceny`**:
`id_ucznia`, `id_przedmiotu`, `ocena` (np. `4.5` = „4+”), `waga` (1–3), `data_wystawienia`.

**Zadanie 69.** ⭐ Ile razy wystawiono każdą ocenę? Posortuj od najniższej oceny.
Która ocena jest najczęstsza? Ile jest „plusów” (ocen z `.5`)?

**Zadanie 70.** ⭐ Dla każdego przedmiotu (`id_przedmiotu`) policz liczbę ocen i średnią ocen (2 miejsca).
Z którego przedmiotu średnia jest **najniższa**? Drugim zapytaniem do tabeli `przedmioty`
sprawdź, **jak się ten przedmiot nazywa**.
> Zauważ, ile kombinowania wymaga zamiana numeru na nazwę. Już niedługo poznamy `JOIN`,
> który zrobi to w **jednym** zapytaniu.

**Zadanie 71.** ⭐ Policz **średnią ważoną** każdego ucznia: `SUM(ocena * waga) / SUM(waga)` (2 miejsca).
Pokaż 5 najlepszych `id_ucznia` z liczbą ocen. Potem jednym zapytaniem z `IN (…)` wyświetl
imiona i nazwiska tych pięciu osób.

**Zadanie 72.** ⭐⭐ **Zagrożeni.** Znajdź pary uczeń + przedmiot, w których średnia ważona jest **niższa niż 2.0**.
Pokaż `id_ucznia`, `id_przedmiotu`, średnią i liczbę ocen. Potem ustal, **kto** i **z czego** jest zagrożony.
Czy któryś z tych przypadków jest „niesprawiedliwy” (np. zagrożenie po jednej ocenie)?

**Zadanie 73.** ⭐ Z każdego przedmiotu policz, **ilu różnych uczniów** dostało jedynkę.
Dlaczego trzeba użyć `COUNT(DISTINCT id_ucznia)`, a nie `COUNT(*)`?

**Zadanie 74.** ⭐ *(narzędzie 1)* W który **dzień tygodnia** nauczyciele wystawiają najwięcej ocen?
Funkcja `WEEKDAY(data)` zwraca 0 dla poniedziałku, 1 dla wtorku … 4 dla piątku.

**Zadanie 75.** ⭐ *(narzędzie 2)* Dla każdej klasy (`id_klasy`) z tabeli `uczniowie` pokaż w jednym wierszu:
liczbę uczniów, liczbę uczniów ze średnią **co najmniej 4.5** oraz liczbę uczniów **bez adresu e-mail**.

**Zadanie 76.** ⭐⭐ **Detektyw roczników.** W każdej klasie uczniowie powinni być z tego samego rocznika.
Pogrupuj uczniów po `id_klasy` **i** roczniku (`YEAR(data_urodzenia)`) i znajdź klasę, w której jest
ktoś z innego rocznika. Kto to jest?

**Zadanie 77.** ⭐ Kto ma najwięcej **szóstek**? Podaj imię i nazwisko (dwa zapytania).

---

## Pytania kontrolne

1. Co zwraca funkcja agregująca, gdy w zapytaniu **nie ma** `GROUP BY`?
2. Czym różni się `COUNT(*)` od `COUNT(kolumna)`?
3. Jak funkcje agregujące traktują `NULL`?
4. Co dokładnie robi `GROUP BY` — na co dzieli tabelę i ile wierszy zwraca?
5. Jakie kolumny wolno wpisać w `SELECT`, gdy używamy `GROUP BY`?
6. Czym różni się `WHERE` od `HAVING`? Podaj po jednym przykładzie.
7. Dlaczego `WHERE COUNT(*) > 5` kończy się błędem, a `HAVING COUNT(*) > 5` działa?
8. W jakiej kolejności serwer wykonuje: `SELECT`, `FROM`, `WHERE`, `GROUP BY`, `HAVING`, `ORDER BY`, `LIMIT`?
9. Po ilu kolumnach można grupować? Co się dzieje z liczbą wierszy w wyniku, gdy dopiszemy
   drugą kolumnę do `GROUP BY`?
10. Dlaczego przy `GROUP BY kod_kraju, wojewodztwo` obie kolumny powinny być w `SELECT`?
