# Chromo-keyboard: Twoje dźwięki, Twoje kolory

Interaktywna instalacja, która zamienia każdy klawisz w pędzel malujący dźwiękiem na ekranie. Zamiast tradycyjnych nut, naciśnięcie klawisza na podłączonym keyboardzie generuje unikalny kolor, kształt i animację, tworząc w czasie rzeczywistym płótno wizualnej symfonii. To Ty jesteś malarzem, a klawiatura to paleta barwnych dźwięków. Każdy akord to eksplozja kolorów, a melodia staje się żywym, pulsującym obrazem.

## Pomysły na funkcjonalności

1. **Dynamiczne mapowanie dźwięk-kolor:** zamiast statycznego przypisania, system może interpretować charakter dźwięku. Wysokie, szybkie nuty (np. z sekcji instrumentów perkusyjnych) mogą generować małe, szybko migoczące punkty w odcieniach żółci i bieli. Niskie, długie nuty (np. z basu) mogą tworzyć duże, powoli pulsujące plamy w kolorach granatu, fioletu lub zieleni. Nagły, gwałtowny akord forte spowodowałby rozbłysk wielu odcieni jednocześnie, podczas gdy legato zamieniłoby się w płynne, łączące się ze sobą smugi kolorów.

2. **Warstwy stylistyczne i "malarskie" efekty:**
    * **Instrument jako technika malarska:** każdy instrument ma swój unikalny "pędzel".
      * **Pianino:** tworzy wyraźne, okrągłe plamy koloru, które powoli blakną.
      * **Skrzypce:** generują cienkie, falujące linie, niczym pociągnięcia pędzla.
      * **Syntezator analogowy:** może tworzyć geometryczne, jaskrawe kształty z wyraźnymi krawędziami.
      * **Gitara elektryczna:** przy zniekształceniu (distortion) powoduje "rozpryski" koloru i "grube", chaotyczne ślady.
    * **Atrybuty muzyczne jako efekty specjalne:**
        * **Głośność (Velocity):** im mocniej uderzysz w klawisz, tym większy i bardziej nasycony kolor zostanie wygenerowany.
        * **Sustaining (Pedał):** przytrzymanie pedału sprawia, że kolory nie znikają, lecz zaczynają się ze sobą mieszać, tworząc nowe, mieszane odcienie na ekranie.
        * **Arpeggio:** automatyczna sekwencja nut tworzy powtarzający się, geometryczny wzór, np. spiralę lub falę.

3. **Ewolucja kompozycji wizualnej:** ekran nie jest tylko płótnem, ale żywym ekosystemem. Kolory i kształty nie pojawiają się i znikają, oddzielnie od siebie. Mogą wchodzić w interakcje – dwa przeciwległe kolory mogą się odpychać, a podobne – łączyć w większe struktury. Długa, spokojna melodia sprawi, że obraz będzie powoli oddychać, a szybka, rytmiczna kompozycja zamieni go w pulsujący, hipnotyczny kalejdoskop.

## Możliwe kierunki realizacji

### Ścieżka 1: "Szybki Prototyp" (Idealna dla początkujących)

* **Cel:** Stworzenie działającej koncepcji w krótkim czasie.
* **Technologia:**
  * **Wejście MIDI:** Użycie prostej biblioteki do obsługi MIDI, np. `mido` w Pythonie, do przechwytywania naciśniętych klawiszy.
  * **Wizualizacja:** Użycie gotowej biblioteki do grafiki 2D, jak `pygame` lub `processing`. Każdy klawisz może po prostu rysować na ekranie kształt (np. kółko) w z góry zdefiniowanym kolorze i pozycji.
  * **Logika:** Prosty słownik mapujący numer nuty MIDI na kolor (np. 60 -> czerwony, 61 -> pomarańczowy, 62 -> żółty).
* **Wyzwania:** Konfiguracja sterowników MIDI, podstawowa grafika i obsługa pętli renderującej.

### Ścieżka 2: "Generatywna Abstrakcja" (Dla średniozaawansowanych)

* **Cel:** Większa kreatywność i organiczność wizualizacji.
* **Technologia:**
  * **Wejście MIDI:** Użycie biblioteki `rtmidi` lub `portmidi` dla niższego poziomu kontroli nad sygnałami, w tym velocity (siłę uderzenia).
  * **Wizualizacja:** Użycie silnika graficznego 2D z możliwościami cieniowania i shaderów, jak `Godot` lub `Unity` (w trybie 2D). Alternatywnie, `p5.js` w JavaScript dla łatwego publikowania w sieci.
  * **Logika:** Implementacja systemu cząstek. Każda nuta to emisja cząstek, których żywotność, rozmiar, prędkość i kolor zależą od parametrów MIDI (wysokość dźwięku, głośność, czas trwania).
* **Wyzwania:** Zrozumienie podstaw grafiki komputerowej (cząstki, shadery), projektowanie estetycznych i płynnych animacji, optymalizacja wydajności przy dużej liczbie obiektów na ekranie.

### Ścieżka 3: "Głęboka Sieć Neuronowa" (Dla zaawansowanych)

* **Cel:** Projekt ostateczny, w pełni generatywny i zaskakujący, gdzie AI sama decyduje o wyglądzie.
* **Technologia:**
  * **Wejście MIDI:** Przechwytywanie pełnego strumienia danych MIDI, w tym zmian w kontrolerach (pitch bend, modulation wheel).
  * **AI:** Trenowanie modelu generatywnego (np. GAN lub Diffusion Model, jak StyleGAN) na zbiorze danych obrazów abstrakcyjnych. Sygnał MIDI byłby wejściem do modelu, który generowałby unikalne, spójne stylistycznie obrazy w czasie rzeczywistym. Alternatywnie, użycie modelu `Stable Diffusion` z `ControlNet`, gdzie dane MIDI kontrolują np. pozycję, kolor i kształt generowanego obrazu.
  * **Wizualizacja:** Wynik z modelu AI renderowany na ekranie w czasie rzeczywistym.
* **Wyzwania:** Wymagana jest bardzo mocna karta graficzna (GPU) z dużą ilością pamięci VRAM, znajomość frameworków AI (PyTorch/TensorFlow), praca z dużymi zbiorami danych, optymalizacja generowania obrazu w czasie rzeczywistym (co jest ekstremalnie trudne).

## Praktyczne wskazówki i potrzebne zasoby

### Sprzęt

* **Podstawowe:** komputer oraz dowolny keyboard MIDI lub klawiatura cyfrowa z portem USB. Do prototypu wystarczy zwykły laptop.
* **Zalecane:** dedykowany interfejs audio/MIDI dla niższych opóźnień, większy monitor lub projektor, aby w pełni docenić wizualne efekty.
* **Zaawansowane:** komputer z wydajną kartą graficzną NVIDIA (z dużą ilością pamięci VRAM) do trenowania lub uruchamiania dużych modeli AI lokalnie.

### Oprogramowanie i języki programowania

* **Python:** absolutny faworyt. Posiada świetne biblioteki do obsługi MIDI (`mido`), grafiki (`pygame`, `pyglet`) i AI (`PyTorch`, `TensorFlow`).
* **JavaScript (z Node.js):** doskonały wybór, jeśli instalacja ma działać w przeglądarce. `WebMIDI API` pozwala na bezpośrednią komunikację z urządzeniami MIDI, a biblioteki jak `p5.js` lub `Three.js` ułatwiają tworzenie grafiki 2D/3D.
* **Narzędzia:** `Git` do wersjonowania kodu, `VS Code` jako środowisko programistyczne, opcjonalnie DAW (np. Ableton Live) do testowania połączeń MIDI.

### Pierwsze kroki dla zainteresowanych

1. **Podłącz keyboard do komputera** i upewnij się, że jest widoczny jako urządzenie MIDI.
2. **Zainstaluj Pythona i bibliotekę `mido`**. Spróbuj napisać prosty program, który nasłuchuje na portach MIDI i drukuje w konsoli informację o każdym naciśniętym klawiszu (np. "Note ON: C4, Velocity: 80").
3. **Zainstaluj bibliotekę `pygame`**. Połącz ją z poprzednim punktem, aby program, zamiast drukować tekst, rysował na ekranie w losowym miejscu kółko za każdym razem, gdy naciśniesz klawisz.
