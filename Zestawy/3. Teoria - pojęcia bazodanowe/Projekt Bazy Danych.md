# Praca na ocenę — projekt bazy danych

Na lekcjach **samodzielnie projektujesz bazę danych dla klienta**. Korzystasz ze wszystkiego, co było w **kartach pracy 5, 6 i 7** (te z nagłówkiem „Lekcja 5 / 6 / 7 — karta pracy”): encje, atrybuty, typy danych, klucze, związki, cechy relacyjnej bazy i integralność.

Numer tematu dostajesz od nauczyciela. Każdy ma inny temat, ale wszyscy mają **te same wymagania i te same progi ocen**.

---

## Zasady

- Pracujesz **samodzielnie**, na **czystej kartce A4** (jak zabraknie miejsca — weź kolejną). Na górze kartki: **imię i nazwisko, numer tematu, data**.
- Możesz korzystać ze ściągi `Sciaga - pojecia relacyjnej bazy danych.html`, kart pracy 5–7, swoich notatek i struktury bazy `szkola` w phpMyAdmin.
- Masz **rozumieć każdą linijkę, którą napiszesz**. Nie przepisuj z czatu ani od kolegi.
- Nie wiesz, jak ruszyć dalej? Pytaj nauczyciela — nie dostaniesz gotowej odpowiedzi, ale dostaniesz wskazówkę.
- **Telefon schowany.** Kto w trakcie pracy siedzi w telefonie, kończy pracę i oddaje kartkę w takim stanie, w jakim jest.
- Jeśli przez całą lekcję nie pracujesz, nauczyciel może zakończyć Twoją pracę — wtedy ocenia to, co jest na kartce.
- Praca powstaje **tylko na lekcjach**: na koniec każdej lekcji oddajesz kartkę, na następnej dostajesz ją z powrotem. Pracy nie kończy się w domu.
- Ocena jest **cząstkowa**, wystawiana według progów podanych niżej.

---

## Zadanie

Przeczytaj opis swojego tematu (na końcu tej karty) — to słowa klienta, który zamawia bazę danych. Zaprojektuj bazę, w której da się zapisać **wszystko**, o czym mówi klient.

### Część A — Encje, atrybuty, typy danych *(karta pracy 5)*

| Nr | Co zrobić |
|---|---|
| **A1** | Wypisz **encje** z opisu klienta (co najmniej 4). Przy każdej jedno zdanie: co (albo kogo) opisuje. |
| **A2** | Każdą encję zapisz jako **tabelę**: nazwa tabeli i **co najmniej 4 atrybuty** (kolumny, licząc `id`). Nazwy bez polskich znaków i spacji, np. `data_urodzenia`. |
| **A3** | Przy **każdej** kolumnie: **typ danych** z rozmiarem (np. `VARCHAR(30)`, `DECIMAL(6,2)`) oraz **`NULL` / `NOT NULL`**. |
| **A4** | W całym projekcie użyj **co najmniej 6 różnych typów** danych. |
| **A5** | Uzasadnij jednym zdaniem typ **5 kolumn** ze swojego projektu: **a)** kwota pieniędzy, **b)** numer złożony z cyfr (np. PESEL, telefon), **c)** lista dozwolonych wartości, **d)** odpowiedź tak/nie, **e)** kolumna, która może być `NULL` — dlaczego może być pusta? |
| **A6** | Podaj **stopień** każdej tabeli. |

### Część B — Klucze i związki *(karta pracy 6)*

| Nr | Co zrobić |
|---|---|
| **B1** | **Klucz główny** w każdej tabeli (oznacz `PK`). Przy każdym napisz, czy jest **sztuczny**, **naturalny** czy **złożony**. |
| **B2** | **Klucze obce** oznacz w tabelach (`FK → tabela.kolumna`) i wypisz wszystkie w formie `tabela.kolumna → tabela.kolumna`. |
| **B3** | Wskaż **co najmniej 2 klucze kandydujące** — kolumny `UNIQUE`, które mogłyby identyfikować wiersz. Przy jednym z nich wyjaśnij, dlaczego kluczem głównym jest jednak `id`. |
| **B4** | Projekt musi zawierać związki: **co najmniej 2 × 1:N**, **co najmniej 1 × N:M** — przez tabelę łączącą z **kluczem złożonym** i **co najmniej jednym atrybutem związku**, **co najmniej 1 × 1:1**. |
| **B5** | **Tabela związków** dla wszystkich związków w projekcie: Encja A, Encja B, rodzaj (1:1 / 1:N / N:M), gdzie w bazie (kolumna z kluczem obcym albo tabela łącząca). |

### Część C — Dane, integralność, podróż po kluczach *(karty pracy 6 i 7)*

| Nr | Co zrobić |
|---|---|
| **C1** | **Przykładowe dane:** do **każdej** tabeli wpisz co najmniej **3 krotki** (do tabeli łączącej — co najmniej **4**). Dane muszą być **spójne**: każdy klucz obcy wskazuje wiersz, który naprawdę jest w Twoich danych. Podaj **moc** każdej tabeli. |
| **C2** | **Integralność:** napisz **3 polecenia SQL** (`INSERT` albo `DELETE`) do swojej bazy z danymi z C1, które baza **odrzuci**. Każde łamie inną integralność: **encji**, **referencyjną**, **dziedzinową**. Przy każdym napisz, która to integralność i dlaczego baza odrzuci polecenie. |
| **C3** | **Cechy:** wybierz **3 cechy relacyjnej bazy danych** i przy każdej pokaż, gdzie widać ją w Twoim projekcie. |
| **C4** | **Podróż po kluczach:** wymyśl **2 pytania** do swojej bazy, na które odpowiedź wymaga przejścia między tabelami po kluczach. Każde rozwiąż kilkoma zapytaniami `SELECT` po kolei (jak zad. 5 z karty pracy 6) — zapisz każde zapytanie i jego wynik na Twoich danych z C1. **Co najmniej jedno** pytanie musi przechodzić przez **tabelę łączącą**. |

---

## Progi ocen

Dostajesz ocenę za **najwyższy próg**, na którym jest zrobione **wszystko** — razem z wymaganiami z niższych progów. Wymaganie się liczy, jeśli jest zrobione sensownie i w większości poprawnie; pojedyncza drobna pomyłka nie obniża oceny.

| Ocena | Musi być zrobione |
|---|---|
| **dopuszczająca (2)** | A1, A2, A3, B1 |
| **dostateczna (3)** | to, co na 2 **+** A4, A5, A6, B2 |
| **dobra (4)** | to, co na 3 **+** B3, B4, B5 |
| **bardzo dobra (5)** | to, co na 4 **+** C1, C2, C3, C4 |

Najwyższa ocena z tej pracy to **bardzo dobra** — ocenę celującą zdobywa się osobnym projektem indywidualnym (zgodnie z wymaganiami edukacyjnymi).

---

## Przykład rozwiązania krok po kroku — Akademia piłkarska „Orlik”

Tak wygląda kompletna kartka na **bardzo dobry** (A1–C4) — na temacie, którego nikt nie dostał. Zrób to samo, **w tej samej kolejności**, dla swojego tematu. Twój temat ma inne encje i inne związki, więc przepisywanie nic nie da — patrz, **jak** to jest zrobione.

### Opis klienta (przykład)

> Prowadzimy akademię piłkarską dla dzieci i młodzieży. O każdym zawodniku zapisujemy imię, nazwisko, PESEL, pozycję na boisku (bramkarz, obrońca, pomocnik albo napastnik) i telefon do rodzica. Numer na koszulce zawodnik dostaje dopiero po pierwszym meczu.
>
> Zawodnicy są podzieleni na drużyny według rocznika. Drużyna ma nazwę (np. „Orlik 2016” — nazwy się nie powtarzają), rocznik i miesięczną składkę. Zawodnik gra w jednej drużynie, a w drużynie gra wielu zawodników.
>
> Trener ma imię, nazwisko, telefon i numer licencji trenerskiej (każdy ma inny). Każda drużyna ma jednego trenera, a trener prowadzi tylko jedną drużynę.
>
> Latem i zimą organizujemy obozy. Obóz ma nazwę, miejscowość, datę rozpoczęcia, datę zakończenia i cenę. Każdym obozem kieruje jeden trener, a ten sam trener może kierować wieloma obozami. Zawodnik może pojechać na wiele obozów, a na jeden obóz jedzie wielu zawodników — zapisujemy datę zapisu i czy obóz jest już opłacony.

### A1 — Encje

- **Zawodnik** — dziecko lub nastolatek trenujący w akademii.
- **Drużyna** — grupa zawodników z jednego rocznika.
- **Trener** — osoba prowadząca drużynę i kierująca obozami.
- **Obóz** — wyjazd szkoleniowy w konkretnym terminie.

`zapisy_na_obozy` to tabela łącząca zawodnik–obóz — nie liczy się jako encja.

### A2, A3, A6, B1 — Tabele

W nagłówku: stopień tabeli (A6) i rodzaj klucza głównego (B1). Przy każdej kolumnie: typ z rozmiarem, `NULL` / `NOT NULL`, ewentualnie `UNIQUE`, oznaczenie `PK` / `FK`. Na kartce nie musisz wyrównywać kolumn.

```
trenerzy                        stopień: 5          PK: sztuczny
  PK  id                INT           NOT NULL
      imie              VARCHAR(20)   NOT NULL
      nazwisko          VARCHAR(30)   NOT NULL
      telefon           VARCHAR(15)   NOT NULL
      nr_licencji       VARCHAR(12)   NOT NULL   UNIQUE

druzyny                         stopień: 5          PK: sztuczny
  PK  id                INT           NOT NULL
      nazwa             VARCHAR(30)   NOT NULL   UNIQUE
      rocznik           YEAR          NOT NULL
      skladka           DECIMAL(5,2)  NOT NULL
  FK  id_trenera        INT           NOT NULL   UNIQUE   → trenerzy.id

zawodnicy                       stopień: 8          PK: sztuczny
  PK  id                INT           NOT NULL
      imie              VARCHAR(20)   NOT NULL
      nazwisko          VARCHAR(30)   NOT NULL
      pesel             CHAR(11)      NOT NULL   UNIQUE
      pozycja           ENUM('bramkarz','obronca','pomocnik','napastnik')   NOT NULL
      telefon_rodzica   VARCHAR(15)   NOT NULL
      nr_koszulki       TINYINT       NULL
  FK  id_druzyny        INT           NOT NULL   → druzyny.id

obozy                           stopień: 7          PK: sztuczny
  PK  id                INT           NOT NULL
      nazwa             VARCHAR(40)   NOT NULL
      miejscowosc       VARCHAR(40)   NOT NULL
      data_od           DATE          NOT NULL
      data_do           DATE          NOT NULL
      cena              DECIMAL(7,2)  NOT NULL
  FK  id_kierownika     INT           NOT NULL   → trenerzy.id

zapisy_na_obozy  (łącząca)      stopień: 4          PK: złożony
  PK FK  id_zawodnika   INT       NOT NULL   → zawodnicy.id
  PK FK  id_obozu       INT       NOT NULL   → obozy.id
         data_zapisu    DATE      NOT NULL
         oplacony       BOOLEAN   NOT NULL
```

### A4 — Różne typy danych

`INT`, `VARCHAR`, `CHAR`, `DECIMAL`, `YEAR`, `ENUM`, `TINYINT`, `DATE`, `BOOLEAN` — 9 różnych (wymagane co najmniej 6).

### A5 — Uzasadnienia

- **a) kwota pieniędzy — `obozy.cena DECIMAL(7,2)`:** pieniądze muszą być dokładne co do grosza, a `FLOAT` potrafi zgubić grosze; 7 cyfr, w tym 2 po przecinku → max 99 999,99 zł.
- **b) numer z cyfr — `zawodnicy.pesel CHAR(11)`:** PESEL ma zawsze 11 znaków i nic na nim nie liczymy; zawodnik z rocznika 2009 ma PESEL zaczynający się od zera, które w liczbie by zniknęło; 11 cyfr nie mieści się w `INT`.
- **c) lista dozwolonych wartości — `zawodnicy.pozycja ENUM(...)`:** są tylko 4 pozycje; baza nie przyjmie literówki ani wymyślonej pozycji.
- **d) tak/nie — `zapisy_na_obozy.oplacony BOOLEAN`:** są tylko dwie możliwości; tekstem każdy wpisywałby inaczej („tak”, „TAK”, „t”).
- **e) kolumna `NULL` — `zawodnicy.nr_koszulki`:** zawodnik dostaje numer dopiero po pierwszym meczu — do tego czasu numeru nie ma (`NULL` to „brak”, a nie numer 0).

### B2 — Klucze obce

```
druzyny.id_trenera            → trenerzy.id
zawodnicy.id_druzyny          → druzyny.id
obozy.id_kierownika           → trenerzy.id
zapisy_na_obozy.id_zawodnika  → zawodnicy.id
zapisy_na_obozy.id_obozu      → obozy.id
```

### B3 — Klucze kandydujące

`zawodnicy.pesel`, `trenerzy.nr_licencji`, `druzyny.nazwa` — wszystkie są `UNIQUE` i `NOT NULL`.
Dlaczego `druzyny.nazwa` nie jest kluczem głównym: nazwa drużyny może się zmienić (np. nowy sponsor), a klucz główny nie powinien się zmieniać — trzeba by poprawiać wszystkie klucze obce, które go wskazują. Krótkie `id` się nie zmienia.

### B4, B5 — Związki

| Encja A | Encja B | Związek | Gdzie w bazie? |
|---|---|---|---|
| trener | drużyna | 1:1 | `druzyny.id_trenera` (`UNIQUE`) |
| drużyna | zawodnik | 1:N | `zawodnicy.id_druzyny` |
| trener (jako kierownik) | obóz | 1:N | `obozy.id_kierownika` |
| zawodnik | obóz | N:M | tabela łącząca `zapisy_na_obozy` (atrybuty związku: `data_zapisu`, `oplacony`) |

### C1 — Przykładowe dane

`trenerzy` — moc 3

| id | imie | nazwisko | telefon | nr_licencji |
|---|---|---|---|---|
| 1 | Paweł | Nowicki | 601100200 | UEFA-B/0412 |
| 2 | Marta | Lis | 602300400 | UEFA-C/1187 |
| 3 | Jacek | Sowa | 603500600 | UEFA-B/0950 |

`druzyny` — moc 3

| id | nazwa | rocznik | skladka | id_trenera |
|---|---|---|---|---|
| 1 | Orlik 2016 | 2016 | 120.00 | 2 |
| 2 | Młodzik 2013 | 2013 | 150.00 | 1 |
| 3 | Junior 2009 | 2009 | 180.00 | 3 |

`zawodnicy` — moc 3

| id | imie | nazwisko | pesel | pozycja | telefon_rodzica | nr_koszulki | id_druzyny |
|---|---|---|---|---|---|---|---|
| 1 | Kuba | Mazur | 16232104571 | napastnik | 600111222 | 9 | 1 |
| 2 | Filip | Kos | 13250809854 | bramkarz | 600333444 | 1 | 2 |
| 3 | Szymon | Wilk | 09281507653 | obronca | 600555666 | NULL | 3 |

`obozy` — moc 3

| id | nazwa | miejscowosc | data_od | data_do | cena | id_kierownika |
|---|---|---|---|---|---|---|
| 1 | Obóz letni | Zakopane | 2027-07-05 | 2027-07-14 | 1890.00 | 1 |
| 2 | Obóz zimowy | Wisła | 2027-01-25 | 2027-01-31 | 1290.00 | 3 |
| 3 | Obóz bramkarski | Gdańsk | 2027-08-02 | 2027-08-08 | 1490.00 | 1 |

`zapisy_na_obozy` — moc 4

| id_zawodnika | id_obozu | data_zapisu | oplacony |
|---|---|---|---|
| 1 | 1 | 2026-10-05 | 1 |
| 2 | 1 | 2026-10-07 | 0 |
| 2 | 3 | 2026-10-07 | 1 |
| 3 | 2 | 2026-10-12 | 0 |

Sprawdź spójność: każdy `id_trenera`, `id_druzyny`, `id_kierownika`, `id_zawodnika`, `id_obozu` wskazuje wiersz, który naprawdę jest w danych; w `druzyny.id_trenera` żaden trener nie powtarza się (1:1); w tabeli łączącej żadna para się nie powtarza.

### C2 — Integralność

```
INSERT INTO zapisy_na_obozy VALUES (2, 1, '2026-10-20', 1);
→ ❌ integralność encji — para (2, 1) już jest: Filip jest zapisany na obóz letni,
     a klucz główny (id_zawodnika, id_obozu) nie może się powtórzyć; inna data nic nie zmienia

INSERT INTO zawodnicy (imie, nazwisko, pesel, pozycja, telefon_rodzica, id_druzyny)
VALUES ('Adam', 'Bąk', '16210312345', 'pomocnik', '600777888', 9);
→ ❌ integralność referencyjna — nie ma drużyny o id = 9, klucz obcy wskazywałby nieistniejący wiersz

INSERT INTO obozy (nazwa, miejscowosc, data_od, data_do, cena, id_kierownika)
VALUES ('Obóz jesienny', 'Ustka', '2027-10-10', '2027-10-15', 'tysiąc', 2);
→ ❌ integralność dziedzinowa — 'tysiąc' to tekst, a kolumna cena jest typu DECIMAL
```

### C3 — Cechy relacyjnej bazy danych

- **Każdy wiersz jest unikalny** — pilnuje tego klucz główny; w `zapisy_na_obozy` ta sama para zawodnik–obóz nie wystąpi drugi raz.
- **W komórce jedna wartość** — obozy zawodnika to osobne wiersze w `zapisy_na_obozy`, a nie lista „Zakopane, Gdańsk” w jednej komórce.
- **Tabele łączą się przez klucze** — zawodnik wskazuje drużynę przez `id_druzyny`, a nie przez przepisaną nazwę drużyny.

### C4 — Podróż po kluczach

```
Pytanie 1 (przez tabelę łączącą): Na jakie obozy jedzie Filip Kos?
1) SELECT id FROM zawodnicy WHERE nazwisko = 'Kos';                  → 2
2) SELECT id_obozu FROM zapisy_na_obozy WHERE id_zawodnika = 2;      → 1, 3
3) SELECT nazwa FROM obozy WHERE id IN (1, 3);                       → Obóz letni, Obóz bramkarski

Pytanie 2: Kto trenuje drużynę, w której gra Szymon Wilk?
1) SELECT id_druzyny FROM zawodnicy WHERE nazwisko = 'Wilk';         → 3
2) SELECT id_trenera FROM druzyny WHERE id = 3;                      → 3
3) SELECT imie, nazwisko FROM trenerzy WHERE id = 3;                 → Jacek Sowa
```

---

## Tematy

### Temat 1 — Wypożyczalnia samochodów „AutoRent”

> Prowadzę wypożyczalnię samochodów i mam dość zeszytu z wpisami. O każdym aucie muszę wiedzieć: markę, model, numer rejestracyjny, numer VIN (17 znaków — każdy samochód ma inny), rok produkcji, rodzaj paliwa (benzyna, diesel, hybryda albo elektryczny), aktualny przebieg, czy ma klimatyzację i ile kosztuje doba wynajmu.
>
> Klient przy pierwszej wizycie podaje imię, nazwisko, PESEL, numer prawa jazdy i telefon, a e-mail — tylko jeśli chce. Klienci wracają do nas wiele razy, czasem biorą to samo auto co ostatnio.
>
> Przy każdym wypożyczeniu zapisujemy, kto wziął które auto, datę wydania, planowaną datę zwrotu, faktyczną datę zwrotu (dopóki auto nie wróci, nie da się jej wpisać) i kwotę do zapłaty.
>
> Do wypożyczenia można dobrać wyposażenie z naszego cennika: fotelik dziecięcy, nawigację, bagażnik rowerowy, łańcuchy śniegowe. Każda pozycja cennika ma nazwę, cenę za dobę i liczbę sztuk, które mamy na stanie. Klient może wziąć kilka sztuk tej samej rzeczy — np. dwa foteliki — więc przy każdym wypożyczeniu trzeba wiedzieć, ile sztuk czego dobrał.
>
> Stali klienci mogą założyć kartę stałego klienta — najwyżej jedną na osobę. Karta ma 10-cyfrowy numer, datę wydania i liczbę zebranych punktów, i zawsze należy do jednej osoby.

### Temat 2 — Klub fitness „PowerGym”

> Otwieramy siłownię i chcemy prowadzić ewidencję klubowiczów. Od każdego zbieramy imię, nazwisko, datę urodzenia, telefon i e-mail (e-mail jest loginem do aplikacji, więc nie może się powtórzyć). Klubowicz dostaje kartę wejściową z 8-cyfrowym numerem — numery się nie powtarzają i często zaczynają się od zera, np. 00412377. Zapisujemy też rodzaj karnetu (open, poranny albo studencki), do kiedy karnet jest ważny i czy klubowicz zgodził się na newsletter.
>
> Bramka zapisuje każde wejście: kto wszedł oraz datę i godzinę wejścia. Godzinę wyjścia wpisujemy dopiero, gdy klubowicz wychodzi. Większość osób bywa u nas kilka razy w tygodniu.
>
> Zatrudniamy trenerów — zapisujemy imię, nazwisko, telefon, specjalizację (np. crossfit, joga) i stawkę za godzinę. Prowadzimy zajęcia grupowe: każde zajęcia mają nazwę, dzień tygodnia, godzinę rozpoczęcia, limit miejsc i jednego trenera prowadzącego. Jeden trener prowadzi zwykle kilka różnych zajęć.
>
> Klubowicz może zapisać się na dowolnie wiele zajęć grupowych, a na każde zajęcia zapisuje się wiele osób. Chcemy wiedzieć, kiedy kto się zapisał.
>
> W szatni są szafki wynajmowane na stałe. Szafka ma numer, strefę (męska albo damska) i cenę za miesiąc. Klubowicz może wynająć najwyżej jedną szafkę, a szafkę wynajmuje najwyżej jedna osoba — część szafek stoi wolna.

### Temat 3 — Schronisko dla zwierząt „Przytulisko”

> Prowadzimy schronisko i chcemy wiedzieć wszystko o naszych podopiecznych. O każdym zwierzęciu zapisujemy: imię nadane w schronisku, gatunek (pies, kot, królik albo inny), płeć, rasę (często nie wiadomo — wtedy zostaje puste), przybliżoną datę urodzenia (też nie zawsze znana), datę przyjęcia do schroniska, aktualną wagę w kilogramach z dokładnością do 0,1 kg, czy jest wykastrowane i dłuższy opis charakteru do ogłoszenia adopcyjnego. Część zwierząt ma czip z 15-cyfrowym numerem — każdy numer jest inny, ale nie wszystkie zwierzęta są zaczipowane.
>
> Zwierzęta mieszkają w boksach. Boks ma numer, nazwę budynku i maksymalną liczbę zwierząt. W jednym boksie mieszka kilka zwierząt, ale każde zwierzę ma w danej chwili jeden boks.
>
> Pomagają nam wolontariusze — zapisujemy imię, nazwisko, telefon, e-mail i datę dołączenia. Każdy boks ma jednego wolontariusza-opiekuna, a wolontariusz opiekuje się najwyżej jednym boksem.
>
> Regularnie przyjeżdża weterynarz. Przy każdej wizycie zapisujemy, które zwierzę badał, datę, opis zabiegu i koszt. Jedno zwierzę ma w swojej historii wiele wizyt.
>
> Kupujemy kilka rodzajów karmy — każda ma nazwę, producenta i cenę za kilogram. Każde zwierzę je kilka rodzajów karmy, a ta sama karma trafia do wielu zwierząt. Dla każdego zwierzęcia i każdej karmy, którą je, trzeba zapisać dzienną porcję w gramach.

### Temat 4 — Szkoła jazdy „Zielone Światło”

> Prowadzę ośrodek szkolenia kierowców. O każdym kursancie zapisujemy: imię, nazwisko, PESEL, telefon, e-mail (nie każdy podaje), kategorię prawa jazdy, na którą się szkoli (A, B albo C), datę rozpoczęcia kursu, numer PKK — profilu kandydata na kierowcę (20 cyfr, każdy kursant ma inny) — i czy zdał już wewnętrzny egzamin z teorii.
>
> O instruktorze wiemy: imię, nazwisko, telefon, numer legitymacji instruktora i stawkę za godzinę jazdy. Każdy instruktor ma przydzielony na stałe jeden samochód szkoleniowy i tylko on nim jeździ. O samochodzie zapisujemy numer rejestracyjny, markę, model, rok produkcji i rodzaj skrzyni biegów (manualna albo automatyczna).
>
> Najważniejsze są jazdy. Kursant jeździ wiele razy, często z różnymi instruktorami — i wiele razy z tym samym. Przy każdej jeździe zapisujemy datę, godzinę rozpoczęcia, liczbę godzin i uwagi instruktora (nie zawsze je wpisuje).
>
> Zajęcia teoretyczne są podzielone na tematy, np. „Pierwsza pomoc” albo „Znaki ostrzegawcze”. Temat ma numer, tytuł i czas trwania w godzinach. Kursant musi być obecny na każdym temacie, a na jeden temat przychodzi wielu kursantów. Zapisujemy, kiedy kursant był na danym temacie.

### Temat 5 — Przychodnia „Zdrowie+”

> W naszej przychodni przyjmuje kilku lekarzy. O lekarzu zapisujemy: imię, nazwisko, numer prawa wykonywania zawodu (7 cyfr, każdy lekarz ma inny), specjalizację (internista, pediatra, kardiolog albo dermatolog) i telefon. Każdy lekarz ma swój stały gabinet i nie dzieli go z nikim. Gabinet ma numer, piętro i 3-cyfrowy telefon wewnętrzny.
>
> Pacjent podaje imię, nazwisko, PESEL, datę urodzenia, telefon i — jeśli chce — e-mail.
>
> Pacjenci umawiają się na wizyty — wiele razy i do różnych lekarzy. Przy wizycie zapisujemy datę i godzinę, status (zaplanowana, odbyta albo odwołana), czy wizyta jest prywatna, czy na NFZ, oraz opłatę (wizyta na NFZ kosztuje pacjenta 0 zł). Lekarz wpisuje też rozpoznanie — ale dopiero po badaniu, więc przy zaplanowanych wizytach go nie ma.
>
> Mamy bazę leków: nazwa, dawka (np. „500 mg”), cena za opakowanie i czy lek jest na receptę. Na jednej wizycie lekarz może przepisać kilka leków, a ten sam lek jest przepisywany na wielu wizytach. Dla każdego przepisanego leku zapisujemy dawkowanie (np. „2 razy dziennie”) i liczbę opakowań.

### Temat 6 — Hotel „Pod Lipami”

> Mamy hotel z 40 pokojami. Pokój ma numer, piętro, typ (jednoosobowy, dwuosobowy albo apartament), cenę za noc i informację, czy ma balkon.
>
> Gość przy zameldowaniu podaje imię, nazwisko, numer dowodu osobistego albo paszportu (litery i cyfry — każdy dokument ma inny numer), kraj (dwuliterowy kod, np. PL, DE), telefon i — opcjonalnie — e-mail.
>
> Goście robią rezerwacje, a stali goście wracają co roku, często do tego samego pokoju. Rezerwacja dotyczy jednego pokoju. Zapisujemy datę przyjazdu, datę wyjazdu, liczbę osób i uwagi gościa (np. „łóżeczko dla dziecka”) — o ile jakieś ma.
>
> Do rezerwacji można dokupić usługi z cennika: śniadanie, parking, SPA, późne wymeldowanie. Usługa ma nazwę, cenę i sposób naliczania (za dobę albo jednorazowo). Do jednej rezerwacji można dokupić kilka usług, a każda usługa jest dokupowana do wielu rezerwacji. Zapisujemy, ile razy daną usługę dokupiono (np. 4 śniadania).
>
> Po wyjeździe gość może wystawić opinię o pobycie — najwyżej jedną do danej rezerwacji. Opinia ma ocenę od 1 do 10, komentarz (czasem długi, czasem żaden) i datę wystawienia.

### Temat 7 — Sklep internetowy „BitByte” z częściami komputerowymi

> Sprzedajemy przez internet części komputerowe. Każdy produkt ma nazwę, producenta, kod kreskowy EAN (13 cyfr, może zaczynać się od zera; każdy produkt ma inny), cenę, liczbę sztuk w magazynie, okres gwarancji w miesiącach i długi opis techniczny. Produkt należy do jednej kategorii (karty graficzne, procesory, pamięci RAM, dyski…). Kategoria ma nazwę, krótki opis i informację, czy jest widoczna w menu sklepu — i obejmuje wiele produktów.
>
> Klient zakłada konto: imię, nazwisko, e-mail (służy do logowania, więc nie może się powtórzyć), telefon, adres i kod pocztowy. Zapisujemy też, czy kupuje jako firma — wtedy podaje NIP (10 cyfr). Osoby prywatne NIP-u nie mają.
>
> Klienci składają zamówienia — wielu kupuje u nas regularnie. Zamówienie ma datę i godzinę złożenia, status (nowe, opłacone, wysłane, dostarczone albo anulowane) i sposób płatności (BLIK, przelew albo za pobraniem). W jednym zamówieniu może być kilka produktów, a ten sam produkt trafia do wielu zamówień. Dla każdego produktu w zamówieniu zapisujemy liczbę sztuk i cenę z chwili zakupu — ceny w sklepie się zmieniają, a zamówienie musi pamiętać tę, po której klient kupił.
>
> Każde zamówienie wysyłamy jedną paczką, a paczka zawiera tylko jedno zamówienie. Paczka ma numer przesyłki nadany przez kuriera, firmę kurierską (InPost, DPD albo DHL), datę nadania i datę doręczenia — obie daty uzupełniamy dopiero wtedy, gdy to nastąpi.

### Temat 8 — Serwis komputerowy i GSM „FixIT”

> Naprawiamy laptopy, komputery, telefony, tablety i konsole. Klient zostawia nam imię, nazwisko, telefon i — jeśli chce — e-mail.
>
> O każdym urządzeniu zapisujemy: rodzaj (laptop, komputer, telefon, tablet albo konsola), markę, model i numer seryjny (litery i cyfry — każde urządzenie ma inny). Telefony i część tabletów mają też 15-cyfrowy numer IMEI — każdy jest inny, ale laptopy, komputery i konsole go nie mają. Każde urządzenie należy do jednego klienta, a klient często przynosi kilka swoich urządzeń.
>
> Przy każdym przyjęciu do naprawy zakładamy zlecenie: data przyjęcia, opis usterki (czasem bardzo długi), status (przyjęte, w naprawie, gotowe albo odebrane), czy naprawa jest na gwarancji, koszt naprawy i data odbioru. Koszt ustalamy dopiero po diagnozie, a datę odbioru wpisujemy, gdy klient zabierze sprzęt. To samo urządzenie trafia do nas czasem kilka razy.
>
> Zatrudniamy serwisantów — zapisujemy imię, nazwisko, telefon, datę zatrudnienia i stawkę za godzinę pracy. Przy jednym zleceniu może pracować kilku serwisantów, a każdy serwisant pracuje przy wielu zleceniach. Dla każdego serwisanta przy danym zleceniu zapisujemy, ile godzin przepracował (np. 1,5 h).
>
> Każdy serwisant ma swoje stałe stanowisko i nikt inny przy nim nie pracuje. Stanowisko ma numer, strefę (komputery, telefony albo konsole) i informację, czy ma stację lutowniczą.
