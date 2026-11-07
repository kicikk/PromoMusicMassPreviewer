# Promo Music Mass Previewer on macOS

[Po polsku niżej](#po-polsku)

> **Beta.** The macOS version is built and checked automatically, but it has not been
> tested on a real Mac yet. If something does not work, please write to
> maciej@proggcast.pl - it helps a lot.
>
> **Beta.** Wersja na macOS jest budowana i sprawdzana automatycznie, ale nie była
> jeszcze testowana na prawdziwym Macu. Jeśli coś nie działa, napisz na
> maciej@proggcast.pl - bardzo pomożesz.

## Which file

- `…_mac_arm64.dmg` - Macs with Apple Silicon (M1, M2, M3, M4…). Apple menu ->
  About This Mac shows "Chip Apple M…".
- `…_mac_x86_64.dmg` - Macs with an Intel processor.

The minimum macOS version is given in the release notes.

## Installing

1. Open the `.dmg` and drag **Promo Music Mass Previewer** to **Applications**.
2. **First launch.** macOS says it cannot verify the app: it is not notarized by Apple,
   which requires a paid developer account. It does not mean the app is harmful.
   - macOS 15 Sequoia and newer: click **Done**, open **System Settings -> Privacy &
     Security**, scroll down and click **Open Anyway** next to Promo Music Mass
     Previewer, then confirm with your password.
   - macOS 14 and older: in Applications, Control-click (right-click) the app ->
     **Open** -> **Open**.

   Needed once for each new version.
3. **Global hotkeys** need permission: **System Settings -> Privacy & Security ->
   Accessibility** and **Input Monitoring** -> turn on Promo Music Mass Previewer
   (macOS usually asks the first time).

## Activation

The same as on Windows: 3-day trial, then send the machine code shown in the window to
maciej@proggcast.pl and paste the free key you get back. A key works on one computer
only, so a Mac needs its own key.

## Updating

Download the new `.dmg`, drag the app to Applications and choose **Replace**.
Settings, ratings and the activation stay.

**After every update, re-enable the hotkey permissions.** The app is not signed with a
paid Apple certificate, so macOS treats each new version as a different program. In
Accessibility and Input Monitoring, remove the old entry with **-** and turn the new
one on, otherwise the hotkeys silently stop working.

## Where the settings are

`~/Library/Application Support/PromoMusicMassPreviewer` - `config.json`, the log, the
Spotify files and the activation. In Finder: **Go -> Go to Folder…** and paste the path.

## Differences from Windows

- No menu bar (tray) icon - the panel is the main window. Closing it (X) quits the
  app; to keep it playing in the background, minimise the window instead.
- The "now playing" overlay stays on top, but clicks do not pass through it.
- The numpad +/- volume hotkeys are not available; set letter keys in `config.json`
  if you need them (e.g. `"vol_up": "ctrl+alt+="`).

Everything else works as described in the [manual](MANUAL.md).

## If the app does not start

Send the start-up log to maciej@proggcast.pl right after the failed attempt (it is
overwritten on every start):

1. In Finder choose **Go -> Go to Folder…** (Shift-Command-G), paste
   `~/Library/Application Support/PromoMusicMassPreviewer` and press Return. (The
   Library folder is hidden in Finder, but Go to Folder opens it anyway.)
2. Attach `startup.log` to the e-mail, and `promo_player.log` too if it is there.

Or copy both logs to the Desktop with one Terminal command:

```bash
cp ~/Library/Application\ Support/PromoMusicMassPreviewer/*.log ~/Desktop/
```

---

## Po polsku

### Który plik

- `…_mac_arm64.dmg` - Maki z procesorem Apple (M1, M2, M3, M4…). Menu Apple ->
  Ten Mac pokazuje „Układ Apple M…”.
- `…_mac_x86_64.dmg` - Maki z procesorem Intel.

Minimalna wersja macOS jest podana w opisie wydania.

### Instalacja

1. Otwórz `.dmg` i przeciągnij **Promo Music Mass Previewer** do **Aplikacji**.
2. **Pierwsze uruchomienie.** macOS napisze, że nie może zweryfikować aplikacji: nie
   jest notaryzowana przez Apple, bo to wymaga płatnego konta deweloperskiego. To nie
   znaczy, że jest szkodliwa.
   - macOS 15 Sequoia i nowsze: kliknij **Gotowe**, otwórz **Ustawienia systemowe ->
     Prywatność i ochrona**, przewiń w dół i kliknij **Otwórz mimo to** przy Promo
     Music Mass Previewer, potwierdź hasłem.
   - macOS 14 i starsze: w Aplikacjach kliknij aplikację z klawiszem Control (prawym
     przyciskiem) -> **Otwórz** -> **Otwórz**.

   Potrzebne raz dla każdej nowej wersji.
3. **Globalne skróty** wymagają zgody: **Ustawienia systemowe -> Prywatność i ochrona
   -> Dostępność** oraz **Monitorowanie wejścia** -> włącz Promo Music Mass Previewer
   (zwykle macOS sam o to zapyta za pierwszym razem).

### Aktywacja

Tak samo jak na Windows: 3 dni próby, potem wyślij kod komputera z okna na
maciej@proggcast.pl i wklej darmowy klucz, który dostaniesz. Klucz działa tylko na
jednym komputerze, więc Mac potrzebuje własnego.

### Aktualizacja

Pobierz nowy `.dmg`, przeciągnij aplikację do Aplikacji i wybierz **Zastąp**.
Ustawienia, oceny i aktywacja zostają.

**Po każdej aktualizacji włącz ponownie zgody dla skrótów.** Aplikacja nie jest
podpisana płatnym certyfikatem Apple, więc macOS traktuje każdą nową wersję jak inny
program. W Dostępności i Monitorowaniu wejścia usuń stary wpis przyciskiem **-** i
włącz nowy - inaczej skróty po cichu przestaną działać.

### Gdzie są ustawienia

`~/Library/Application Support/PromoMusicMassPreviewer` - `config.json`, log, pliki
Spotify i aktywacja. W Finderze: **Idź -> Idź do folderu…** i wklej ścieżkę.

### Różnice względem Windows

- Brak ikony na pasku menu (tray) - głównym oknem jest panel. Zamknięcie go (X) kończy
  program; żeby grał dalej w tle, zminimalizuj okno.
- Nakładka „now playing” jest zawsze na wierzchu, ale kliknięcia nie przechodzą przez
  nią na wylot.
- Brak skrótów głośności z klawiatury numerycznej (+/-); w razie potrzeby ustaw
  literowe w `config.json` (np. `"vol_up": "ctrl+alt+="`).

Cała reszta działa jak w [instrukcji](INSTRUKCJA.md).

### Gdy program nie startuje

Wyślij log startu na maciej@proggcast.pl zaraz po nieudanej próbie (jest nadpisywany
przy każdym uruchomieniu):

1. W Finderze wybierz **Idź -> Idź do folderu…** (Shift-Command-G), wklej
   `~/Library/Application Support/PromoMusicMassPreviewer` i naciśnij Return. (Folder
   Biblioteka jest w Finderze ukryty, ale „Idź do folderu” i tak go otworzy.)
2. Dołącz do maila plik `startup.log`, a jeśli jest, także `promo_player.log`.

Albo skopiuj oba logi na Biurko jedną komendą w Terminalu:

```bash
cp ~/Library/Application\ Support/PromoMusicMassPreviewer/*.log ~/Desktop/
```
