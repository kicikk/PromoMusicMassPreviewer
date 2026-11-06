# Promo Music Mass Previewer - instrukcja

Aplikacja do szybkiego przesłuchiwania (i odsiewania) dużej ilości muzyki promo.
Zamiast słuchać każdego utworu od początku do końca, player sam pomija intro/outro
i gra krótkie próbki przez najważniejsze fragmenty (z naciskiem na drop), a Ty
decydujesz: zachować czy odrzucić. Działa w tle - możesz robić swoje, a reagować
globalnymi skrótami albo z panelu.

---

## 1. Instalacja i pierwsze uruchomienie

Windows 10/11, 64-bit.

1. Pobierz `Promo_Music_Mass_Previewer.exe` z
   [Releases](https://github.com/kicikk/promo-music-mass-previewer-releases/releases/latest).
2. Włóż go do osobnego folderu, np. `Dokumenty\Promo Music Mass Previewer`. Program
   trzyma ustawienia (`config.json`) i plik logu obok `.exe`, więc folder musi być
   zapisywalny (nie `Program Files`).
3. Uruchom `.exe` dwuklikiem.

Przy starcie wskazujesz folder z muzyką. Aplikacja skanuje go (rekurencyjnie) i
zaczyna grać. Obsługiwane formaty: mp3, wav, flac, ogg, aiff, m4a.

### Aktywacja

Program działa za darmo przez 3 dni. Przy każdym starcie pokazuje okno aktywacji z
kodem Twojego komputera (`XXXX-XXXX-XXXX-XXXX`):

1. Kliknij **Wyślij e-mail** - otworzy się program pocztowy z gotową wiadomością na
   maciej@proggcast.pl z kodem w środku. Albo kliknij **Kopiuj kod** i wyślij go
   dowolnie.
2. Dostajesz z powrotem darmowy klucz aktywacyjny (zaczyna się od `PMMP1-`).
3. Wklej go w pole i kliknij **Aktywuj**. Okno już się nie pokaże.

W trakcie próby **Kontynuuj próbę** uruchamia program bez klucza. Po 3 dniach zostaje
tylko aktywacja.

- Klucz działa tylko na komputerze, dla którego został wydany.
- Aktywacja odbywa się offline - program nie łączy się z żadnym serwerem.
- Przeniesienie `.exe` albo aktualizacja do nowej wersji zachowują aktywację.
- Po reinstalacji Windowsa kod komputera się zmienia - wystarczy wysłać nowy.

Okno aktywacji jest w języku ustawionym w `config.json` (`"language": "pl"`;
domyślnie angielski).

### Aktualizacja

Pobierz nowy `.exe` z
[Releases](https://github.com/kicikk/promo-music-mass-previewer-releases/releases/latest)
i podmień nim stary w tym samym folderze. Ustawienia, oceny i aktywacja zostają.
Numer Twojej wersji widać na dole panelu (np. `v20261106_b5.8`), a listę zmian w
[CHANGELOG.md](CHANGELOG.md).

### Windows ostrzega przed .exe albo go blokuje

`.exe` nie jest podpisany cyfrowo - certyfikat do podpisywania kodu kosztuje kilkaset
dolarów rocznie i ta aplikacja go nie ma. To nie znaczy, że plik jest zarażony.

- **SmartScreen** („System Windows ochronił ten komputer"): kliknij **Więcej
  informacji** -> **Uruchom mimo to**. Tylko za pierwszym razem.
- **Inteligentna kontrola aplikacji** (Smart App Control, Windows 11: komunikat, że nie
  udało się zweryfikować wydawcy, bez opcji uruchomienia): ta funkcja blokuje każdy
  program bez podpisu od zaufanego wystawcy i w odróżnieniu od SmartScreena nie ma
  opcji „uruchom mimo to" dla pojedynczego pliku. Jedyne wyjście to ją wyłączyć:
  Zabezpieczenia Windows -> Kontrola aplikacji i przeglądarki -> Inteligentna kontrola
  aplikacji -> Wyłączone. Wyłącza to ochronę całego systemu.

---

## 2. Panel - główne okno

![Panel](docs/panel.png)

Od góry:

- **Nazwa utworu** (na niebiesko).
- **Linijka stanu**: tryb (np. `smart 5x`), pozycja `0:50 / 3:48`, numer w kolejce
  `1/1` oraz `saves 61%` - czyli ile czasu oszczędzasz w tym trybie w stosunku do
  pełnego odsłuchu.
- **Waveform** (wykres głośności całego utworu) - patrz punkt 4.
- **Pasek postępu** pod waveformem - klikalny (przewijanie myszką).
- **Transport**: `|< Prev` (poprzedni), `-10s`, `Pause/Play`, `+10s`, `Next >|`
  (następny).
- `Jump to drop` - skok do najbliższego dropu względem aktualnej pozycji.
- `Listen in full` - wyłącza skip dla tego jednego utworu (słuchasz w całości).
- **Tryb skanowania**: `Standard / Shorter / Longer / Middle` - patrz punkt 3.
- **Oceny**: `YES` (zachowaj), `MAYBE`, `NO -> Trash` (do Kosza) + liczniki.
- **Auto-cull** (przełącznik po prawej) - patrz punkt 6.
- **Volume** - głośność.
- **Queue** - lista utworów. Podwójny klik = przeskok do danego utworu. Pole filtra
  nad listą zawęża ją do wpisów, których nazwa zawiera wpisany tekst (na żywo, bez
  rozróżniania wielkości liter). „x" wewnątrz pola (lub Esc) czyści filtr. Filtr
  zmienia tylko widok - kolejność grania i oceny bez zmian.
- Dół: `Folder...` (zmiana folderu), `Purge deleted` (opróżnienie folderu to_delete).
  (Zbiorcze `Sort` i `Delete NO` są w menu zasobnika - patrz punkt 5.)

Zamknięcie okna (X) zamyka całą aplikację. Żeby tylko schować panel (a grać dalej
w tle), użyj menu w zasobniku albo lewego kliknięcia na ikonie obok zegara.

---

## 3. Tryby skanowania

Wybierasz, jak gęsto i jak długo player próbkuje utwór:

- **Standard** - próbka 18 s, przeskok 35 s (domyślny).
- **Shorter** - krótsze, częstsze próbki (więcej skoków).
- **Longer** - dłuższe, rzadsze próbki.
- **Middle** - bez próbkowania, gra ciągle sam środek utworu (od końca intro do
  początku outro).

Wskaźnik `saves X%` pokazuje, ile czasu zaoszczędzisz danym trybem.

Najedź myszką na dany tryb, żeby zobaczyć krótki dymek z opisem (długość próbki /
przeskok albo „ciągły środek").

---

## 4. Waveform - co oznaczają markery

Na wykresie głośności:

- **Cyjanowe trójkąty u góry** - miejsca, do których player przeskoczy (początki
  próbek). To jest plan odsłuchu.
- **Żółte linie** - wykryte dropy/narosty energii. Główny drop to wejście po
  najdłuższym breakdownie. Są chronione - player ich nie utnie.
- **Szare przerywane** - koniec intra i początek outra.
- **Biały pionowy kursor** - aktualna pozycja odtwarzania.

Markery skipów celują kilka sekund PRZED każdym dropem, żebyś słyszał jego wejście,
a nie wpadał w środek.

Klik w waveform = przewinięcie tam. Po ręcznym przewinięciu player gra dalej od
tego miejsca i normalnie skipuje do przodu (nie cofa się).

---

## 5. Ocenianie i segregacja

- **YES** - zachowujesz. Jeśli włączone `move_on_yes`, plik od razu trafia do
  podfolderu `selected`.
- **MAYBE** - oznaczenie pośrednie (też liczone jako zachowane).
- **NO** - odrzucasz. Jeśli włączone `delete_on_no`, plik jest od razu usuwany
  (patrz „Jak działa kasowanie" niżej).

Oceny zapisują się na bieżąco do pliku `promo_player_marks.csv` w folderze z muzyką.

Uwaga: przy domyślnych ustawieniach YES od razu idzie do `selected`, a NO / auto-cull
do `to_delete` - więc większość segregacji dzieje się w trakcie oceniania. Poniższe
akcje zbiorcze są tylko dla resztek (np. MAYBE) albo gdy wyłączysz natychmiastowe
akcje. Są w menu zasobnika (prawy klik na ikonie):
- `Sort` / Segregacja - przenosi wciąż leżące ocenione pliki do `_YES`, `_MAYBE`, `_NO`.
- `Delete NO` - usuwa oznaczone NO, które nie zostały jeszcze usunięte.

Na dole panelu:
- `Purge deleted` - opróżnia folder `to_delete` (patrz niżej).
- Eksport playlist M3U (z menu zasobnika).

### Jak działa kasowanie (dwa tryby)

Ustawiane przez `delete_mode` w konfiguracji:

- `folder` (domyślny, najbezpieczniejszy) - nic nie ginie od razu. NO, `Delete NO`
  i auto-cull PRZENOSZĄ plik do podfolderu `to_delete` (tworzony, jeśli brak). Pliki
  po prostu tam czekają. Żeby je naprawdę skasować, klikasz `Purge deleted`
  (przycisk pokazuje licznik, np. `Purge deleted (12)`) albo kasujesz folder ręcznie
  w Eksploratorze. `Purge deleted` prosi o potwierdzenie i wysyła zawartość
  do Kosza (odwracalne).
- `recycle` - stare zachowanie: NO / Delete NO / auto-cull lecą od razu do Kosza
  (albo trwale, jeśli `delete_to_recycle_bin` jest false).

Sens trybu `folder`: jeśli podczas auto-cull odejdziesz od komputera i zapomnisz
zapauzować, nic nie przepada - utwory tylko zbierają się w `to_delete` i możesz je
przywrócić, przenosząc z powrotem.

W każdym przypadku wpis na playliście zostaje (czerwony = skasowany), nie znika.

---

## 6. Auto-cull - tryb agresywnego odsiewania (UWAGA)

![Auto-cull](docs/panel_autocull.png)

Do masowego czyszczenia. Po włączeniu: utwór, którego NIE zachowasz (YES albo
MAYBE), jest usuwany przy przejściu dalej (Next albo gdy player sam przejdzie do
następnego). Założenie: brak akcji = nie podoba się. Żeby coś zostawić, musisz
świadomie kliknąć YES.

Przy domyślnym `delete_mode: folder` „usuwany" znaczy przeniesiony do folderu
`to_delete` - więc nawet jeśli zostawisz włączony auto-cull bez nadzoru, nic nie
przepada, dopóki nie klikniesz `Purge deleted`. Baner pokazuje rzeczywisty cel.

Tryb jest WYRAŹNIE oznaczony:
- czerwony baner na górze panelu,
- nakładka w rogu robi się czerwona z dopiskiem `[AUTO-CULL]`.

Włączenie (przełącznik w panelu) wymaga potwierdzenia. Domyślnie wyłączone.

Ważne: auto-cull kasuje tylko od aktualnej pozycji w przód. Wszystko, co było w
playliście PRZED momentem włączenia, jest chronione i nie zostanie skasowane -
nawet jeśli się do tego cofniesz.

Bezpiecznik: kasowanie idzie do Kosza, więc pomyłki odzyskasz.

---

## 7. Nakładka „now playing"

![Nakładka](docs/overlay.png)

Mały napis w rogu ekranu, zawsze na wierzchu, klikalny na wylot (kliknięcia
przechodzą pod spód) i nie przejmuje fokusu - nie przeszkadza w pracy. Pokazuje:
stan (gra/pauza), numer w kolejce, tryb, pozycję/długość, oszczędność czasu i
ewentualną ocenę. Pozycję i wygląd ustawisz w konfiguracji.

---

## 8. Globalne skróty (działają, gdy okno jest schowane)

| Skrót | Akcja |
|---|---|
| Ctrl+Alt+Right | następny utwór |
| Ctrl+Alt+Left | poprzedni utwór |
| Ctrl+Alt+Space | pauza / wznów |
| Ctrl+Alt+Up | oznacz YES (zachowaj) |
| Ctrl+Alt+Down | oznacz NO |
| Ctrl+Alt+M | oznacz MAYBE |
| Ctrl+Alt+L | posłuchaj w całości |
| Ctrl+Alt+D | skok do najbliższego dropu |
| Ctrl+Alt+R | od początku tego utworu |
| Ctrl+Alt+S | skip wł./wył. |
| Ctrl+Alt+Shift+Right / Left | przewiń o 10 s w przód / w tył |
| Ctrl+Alt+plus / minus (numpad) | głośniej / ciszej |

Skróty zmienisz w `config.json` w sekcji `hotkeys`. Można przypisać kilka kombinacji
do jednej akcji (np. strzałka dla klawiatury + litera dla Stream Decka).

Uwaga: jeśli skróty nie reagują, spróbuj uruchomić aplikację jako administrator.

---

## 9. Stream Deck

Emulacja klawiszy ze Stream Decka bywa zawodna, dlatego aplikacja ma własny kanał
poleceń: mały serwer HTTP nasłuchujący tylko na Twoim komputerze (`127.0.0.1`, port
48757). Przycisk po prostu wywołuje adres, bez emulacji klawiszy.

W Stream Decku zainstaluj darmowy plugin do zapytań HTTP (np. BarRaider „API Ninja"
albo „Web Requests") i ustaw przycisk na:

GET `http://127.0.0.1:48757/<akcja>`

Akcje: `next`, `prev`, `play_pause`, `mark_yes`, `mark_no`, `mark_maybe`,
`listen_full`, `jump_drop`, `replay`, `toggle_skip`, `vol_up`, `vol_down`, `seek_fwd`,
`seek_back`, `panel_toggle`, `auto_cull` (każde wciśnięcie przełącza tryb),
`purge_deleted`.

Pokazanie stanu przełącznika na przycisku (opcjonalnie): ustaw tytuł pluginu na
tylko-odczytowy endpoint stanu:

- przełączenie na wciśnięcie: GET `http://127.0.0.1:48757/auto_cull`
- tytuł (odpytywany co 1-2 s): GET `http://127.0.0.1:48757/state/auto_cull`
  - zwraca czysty tekst `ON` albo `OFF`

`http://127.0.0.1:48757/state` (bez klucza) zwraca JSON ze wszystkimi stanami
(`auto_cull`, `skip`, `paused`). Użyj portu z `config.json` (`command_port`,
domyślnie 48757).

---

## 10. Ustawienia (config.json)

Plik `config.json` leży obok `.exe` (menu zasobnika -> Otwórz config.json).
Najważniejsze:

| Klucz | Znaczenie |
|---|---|
| language | "en" (domyślnie) lub "pl" - język interfejsu |
| snippet_sec / gap_sec | długość próbki / przeskok (tryb Standard) |
| drop_lead_sec | ile sekund przed dropem ustawia się marker (domyślnie 4) |
| move_on_yes / yes_dir | YES przenosi plik do podfolderu (domyślnie "selected") |
| delete_on_no | NO usuwa bieżący plik od razu (wg delete_mode) |
| delete_mode | "folder" (przenieś do to_delete, domyślnie) lub "recycle" (od razu) |
| to_delete_dir | nazwa folderu miękkiego kasowania (domyślnie "to_delete") |
| delete_to_recycle_bin | true = Kosz (odwracalne), false = trwale |
| auto_cull | tryb agresywnego odsiewania (domyślnie false) |
| skip_marked | pomijaj utwory już ocenione w poprzednich sesjach |
| overlay_corner / overlay_margin | pozycja nakładki |
| notifications | powiadomienia Windows przy ocenie (domyślnie false) |

Po zmianie konfiguracji zrestartuj aplikację.

---

## 11. Tryb Spotify (wymaga Premium)

Przesłuchiwanie katalogu Spotify dokładnie tak samo jak plików: appka skacze po
utworze, oceniasz tymi samymi skrótami, leci dalej. Dźwięk gra w Twoim kliencie
Spotify - previewer steruje nim przez Spotify Connect.

**Co dostajesz:** całą dyskografię artysty albo dowolny album czy playlistę, bez
zakładania czegokolwiek. Kolejkę trzyma appka.

**Czego nie dostajesz:** detekcji dropu i waveformu. Spotify nie udostępnia próbek
audio (DRM), więc nie ma czego analizować. Skip na sekundach i wszystkie tryby
skanowania działają normalnie.

### Konfiguracja (raz)

1. Wejdź na **developer.spotify.com** -> Dashboard -> **Create app**.
2. Wpisz dowolną nazwę i opis. W polu **Redirect URIs** wklej dokładnie:
   `http://127.0.0.1:48758/callback` i kliknij **Add**. Uwaga: `localhost` nie
   zadziała - Spotify przyjmuje tylko jawny adres pętli zwrotnej.
3. Zaznacz **Web API**, zaakceptuj regulamin, **Save**.
4. Skopiuj **Client ID** ze strony aplikacji.
5. W previewerze naciśnij **Spotify...** (przycisk w panelu albo pozycja w menu
   zasobnika), wklej Client ID, naciśnij **Połącz** i zatwierdź w przeglądarce.

Każdy, kto używa appki, zakłada sobie własną aplikację Spotify - w programie nie ma
zaszytych żadnych cudzych dostępów. Twój token siedzi w `spotify_auth.json` obok
configu.

### Codzienne użycie

- Uruchom klienta Spotify i zagraj cokolwiek raz, żeby previewer zobaczył urządzenie.
  Wybierz je pod **Urządzenie odtwarzające**.
- W polu **Co przesłuchać** wpisz nazwę artysty albo wklej link/URI do artysty, albumu
  lub playlisty. Wybierz sortowanie (data wydania, tytuł, długość...) i naciśnij
  **Wczytaj**.
- Albo kliknij dwukrotnie jedną ze swoich playlist na liście poniżej.
- Oceniaj normalnymi skrótami. Oceny idą do `spotify_marks.csv` obok configu. Przy
  kolejnym wejściu na to samo źródło już ocenione są pomijane.

### Duże dyskografie, cache i dzienny limit Spotify

Twoja aplikacja deweloperska ma **dzienny limit zapytań do API**. Po jego
przekroczeniu Spotify odmawia wszystkiego na kilkanaście-dwadzieścia godzin
(niezależnie od źródła), a appka powie wprost, za ile wrócić.

Dlatego dyskografia jest pobierana **raz**. Pierwsze wejście na artystę kosztuje
mniej więcej jedno zapytanie na wydawnictwo - u płodnego producenta (np. Gai
Barone: 240 wydawnictw) to około 260 zapytań i kilka minut. Wynik zapisuje się
w cache i **każde następne wczytanie, także po restarcie aplikacji, jest
natychmiastowe i nie kosztuje ani jednego zapytania**.

- **Wczytaj** - bierze z cache, jeśli dyskografia była już pobrana.
- **Sprawdź nowe** - odczytuje listę wydawnictw na nowo i dociąga tylko te,
  których jeszcze nie masz. Dla artysty bez nowości to około 25 zapytań zamiast
  260, bo zawartość znanych wydawnictw brana jest z cache.

Status po wczytaniu pokazuje, ile zapytań poszło - warto na to patrzeć, bo to
Twój dzienny budżet.

Jeśli wolisz oszczędniej kosztem kompletności, w `config.json` w sekcji `spotify`
ustaw `"discography_mode": "search"`. Wtedy dyskografia leci przez wyszukiwarkę:
około 15 zapytań zamiast 260, ale bez gwarancji kompletności i z limitem 1000
utworów na artystę.

### Ograniczenia

- **Cudzych playlist nie da się odczytać** - Spotify odmawia nawet przy publicznych.
  Dostępne są tylko własne. Obejście: otwórz playlistę w kliencie Spotify, zaznacz
  utwory, „Dodaj do playlisty" i wskaż previewerowi swoją kopię.
- Operacje na plikach (segregacja do podfolderów, kasowanie, auto-cull, eksport M3U)
  są w trybie Spotify wyłączone - nie ma pliku do ruszenia. Oceny i tak zapisują się
  w CSV.
- Pierwsze wczytanie dużej dyskografii trwa ~20 sekund, potem jest brane z cache
  (patrz wyżej).

---

Wersja widoczna jest na dole panelu (np. `v20261106_b5.8`), lista zmian w
[CHANGELOG.md](CHANGELOG.md).

Developed by Maciej Kiciński (kicikk), powered by [proggcast.pl](https://www.proggcast.pl)
· [Proggcast na YouTube](https://www.youtube.com/@proggcastpl)
(c) proggcast.pl
