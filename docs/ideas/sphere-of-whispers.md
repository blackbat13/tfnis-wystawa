# Sfera Szeptów: architektura dźwięku i przestrzeni

Wejdź do środka instalacji złożonej z kilku głośników i stań się częścią żywej kompozycji dźwiękowej. Każdy głośnik emituje inną rozmowę, fragment historii, szept lub melodię. Dzięki precyzyjnemu rozmieszczeniu i kontrolowanemu zasięgowi dźwięku, w zależności od tego, gdzie się znajdujesz, słyszysz inną kombinację głosów. Krok w lewo, a zgiełk miasta zamienia się w cichą rozmowę. Krok w prawo, a szept staje się krzykiem. To Ty odkrywasz ukryte narracje, poruszając się w fizycznej przestrzeni dźwięku.

## Pomysły na funkcjonalności

1.  **Warstwy narracji i kontekstu:** zamiast losowych rozmów, stwórz spójny świat.
    *   **Opowiadana historia:** każdy głośnik może reprezentować innego narratora lub perspektywę na to samo wydarzenie. Użytkownik, poruszając się, składa sobie obraz całej historii jak puzzle. Jeden głośnik to relacja świadka, drugi to myśli głównej postaci, trzeci to odgłosy otoczenia, czwarty to komentarz narratora.
    *   **Abstrakcyjne emocje:** każdy głośnik emituje dźwięk kojarzący się z inną emocją: radość (śmiech, muzyka), smutek (płacz, deszcz), złość (krzyk, zgiełk), spokój (szepty szumu, oddech). Użytkownik, przechodząc, doświadcza zmiany emocjonalnego krajobrazu.
    *   **Dźwiękowa mapa miasta:** głośniki mogą odtwarzać dźwięki charakterystyczne dla różnych miejsc – kawiarni, parku, ruchliwej ulicy, cichej biblioteki. Poruszając się, użytkownik "zwiedza" dźwiękową mapę.

2.  **Interaktywność i dynamika:** instalacja może reagować na publiczność.
    *   **Reakcja na ruch:** proste czujniki ruchu lub nawet kamera z analizą pozycji mogą włączać lub wyłączać poszczególne głośniki, gdy ktoś zbliża się do ich "strefy". Dźwięk może podążać za użytkownikiem.
    *   **Reakcja na głośność:** mikrofon w centralnym punkcie może analizować poziom hałasu. Jeśli jest głośno, rozmowy stają się cichsze i bardziej szeptane, aby zachęcić do wyciszenia. Jeśli jest cicho, dźwięki mogą stawać się wyraźniejsze i głośniejsze.
    *   **Zmiana czasowa:** dźwięki mogą zmieniać się w zależności od pory dnia podczas wystawy. Rano – delikatne, budzące się dźwięki. W południe – gwar i energia. Wieczorem – ciche, refleksyjne szepty.

3.  **Wizualny komponent:** dźwięk jest niewidzialny, ale możemy go zobrazować.
    *   **Światło:** każdy głośnik może być połączony ze źródłem światła (np. pasek LED), które pulsuje lub zmienia kolor w rytm emitowanego dźwięku. To stworzy wizualną mapę aktywności dźwiękowej.
    *   **Projekcje:** na podłodze lub ścianach można projekować abstrakcyjne wizualizacje generowane na podstawie analizy dźwięku w czasie rzeczywistym. Gdzieś, gdzie dźwięki się nakładają, projekcje mogą tworzyć bardziej złożone wzory.

## Możliwe kierunki realizacji

### Ścieżka 1: "Analogowa Strefa" (idealna dla początkujących i miłośników DIY)

*   **Cel:** stworzenie działającego prototypu bez skomplikowanego kodowania.
*   **Technologia:**
    *   **Głośniki:** zwykłe, pasywne głośniki komputerowe lub małe głośniki przenośne z własnym zasilaniem.
    *   **Sterowanie:** kilka odtwarzaczy MP3 (np. tanie odtwarzacze z aliexpress) lub smartfony, każdy z własną playlistą. Sterowanie ręczne – włączasz i ustawiasz głośność na każdym urządzeniu.
    *   **Kierunkowość:** uzyskana przez fizyczne osłonięcie głośnika (np. kartonowy tuba, rura) lub ustawienie go pod odpowiednim kąlem w kierunku ściany, by dźwięk się odbijał.
*   **Wyzwania:** zdobycie odpowiednich materiałów, precyzyjne ustawienie głośników, synchronizacja startu odtwarzania.

### Ścieżka 2: "Cyfrowy Dyrygent" (dla średniozaawansowanych)

*   **Cel:** pełna kontrola nad dźwiękiem i jego dynamicznym sterowaniem.
*   **Technologia:**
    *   **Głośniki:** aktywne głośniki studyjne lub głośniki podłączone do wzmacniacza.
    *   **Sterowanie:** jeden komputer z kartą dźwiękową wielokanałową (np. 4.1, 5.1, 7.1) lub kilkoma kartami dźwiękowymi USB. Program napisany w **Pythonie** (z biblioteką `pyo` lub `sounddevice`) lub **Max/MSP**/**Pure Data** (wizualne języki programowania dla dźwięku) do sterowania każdym kanałem (głośnikiem) niezależnie.
    *   **Kierunkowość:** użycie dedykowanych głośnikach kierunkowych (tzw. "sound showers" lub "dźwiękowy prysznic") lub głośników tubowych (horn speakers). Można też eksperymentować z ultradźwiękowym przetwornikiem (podobnym do tego w "dźwiękowej laserce"), ale to już wyższa półka.
*   **Wyzwania:** nauka podstaw programowania dźwięku w czasie rzeczywistym, konfiguracja sprzętu audio, zrozumienie akustyki przestrzeni.

### Ścieżka 3: "Immersyjna Rzeczywistość" (dla zaawansowanych)

*   **Cel:** stworzenie w pełni interaktywnej, reagującej na użytkownika instalacji.
*   **Technologia:**
    *   **Sterowanie:** integracja z systemami **Ambisonics** lub **Wave Field Synthesis**, które pozwalają na precyzyjne modelowanie pól dźwiękowych w 3D.
    *   **Interaktywność:** użycie kamery i bibliotek do wizji komputerowej (`OpenCV`, `MediaPipe`) do śledzenia pozycji i ruchu użytkownika. System dynamicznie modyfikuje panoramę dźwięku, głośność i treść w zależności od tego, gdzie stoi i co robi widz.
    *   **Dźwięk:** generowanie dźwięku proceduralnego w czasie rzeczywistym, a nie tylko odtwarzanie plików.
*   **Wyzwania:** bardzo zaawansowana wiedza z zakresu psychoakustyki i programowania dźwięku 3D, wymagany mocny sprzęt, skomplikowana kalibracja systemu.

## Praktyczne wskazówki i potrzebne zasoby

### Sprzęt

*   **Głośniki:** kluczowy element. Najlepiej sprawdzają się małe głośniki kierunkowe ("sound shower") lub głośniki tubowe. Są droższe, ale dają najlepszy efekt. Alternatywą są głośniki studyjne, które mają dobre kierowanie wysokich tonów.
*   **Źródło dźwięku:** komputer z odpowiednią kartą dźwiękową. Wersja "budżetowa" to kilka Raspberry Pi, każde sterujące jednym głośnikiem i synchronizowane przez sieć.

### Oprogramowanie

*   **Max/MSP lub Pure Data:** wizualne języki programowania, standard w świecie instalacji artystycznych. Intuicyjne, świetne do prototypowania.
*   **Python + `pyo`:** `pyo` to potężna biblioteka do syntezy i przetwarzania dźwięku w czasie rzeczywistym. Daje ogromne możliwości.
*   **Ableton Live lub Reaper:** można użyć DAW (Digital Audio Workstation) do przygotowania ścieżek dźwiękowych i sterowania nimi za pomocą zewnętrznych kontrolerów lub skryptów.

### Wskazówki do realizacji

*   **Lokalizacja to Klucz:** to projekt, który wymaga cichego, ciemnego pomieszczenia. Im mniej hałasu z zewnątrz i odbić, tym lepszy efekt.
*   **Testuj, Testuj, Testuj:** zanim zamontujesz wszystko finalnie, przetestuj ustawienie głośników w różnych miejscach. Nagraj dźwięk w różnych punktach przestrzeni, by upewnić się, że efekt jest taki, jakiego oczekujesz.
*   **Bezpieczeństwo:** upewnij się, że żadne kable nie leżą na drodze ludzi, a konstrukcja jest stabilna. Publiczność będzie rozglądać się w głąb i na boki, a nie tylko przed siebie.
