# Magiczne Oko: AI, które przepisuje rzeczywistość

Spójrz na świat przez magiczne oko AI. Na dużym ekranie widzisz obraz z kamery w czasie rzeczywistym, ale to nie jest zwykłe odbicie. Sztuczna inteligencja analizuje to, co widzi, i na bieżąco "przekształca" obiekty. Ludzie zamieniają się w proste ludziki z patyków, zwykłe krzesła stają się majestatycznymi tronami, a kubek z kawą zamienia się w eliksir w świecącej fiolce. To Ty i Twoje otoczenie stajecie się częścią żywego, surrealistycznego obrazu, który nieustannie się zmienia i zaskakuje. To zabawa z tożsamością obiektów i pokazanie, jak AI "widzi" i "interpretuje" świat.

## Pomysły na funkcjonalności

1.  **Różne "filtry" lub "stylistyczne" AI:** zamiast jednego, stałego stylu transformacji, AI może mieć kilka różnych "humorów" artystycznych.
    *   **Styl "zabawki LEGO":** wszystkie obiekty (ludzie, meble, przedmioty) są zamieniane na budowane z klocków modele, proste i geometryczne.
    *   **Styl "akwarelowy szkic":** AI nie zmienia kształtów, ale "przemalowuje" cały obraz na akwarelową, malarską stylizację, jakby był szkicem artysty.
    *   **Styl "kreskówkowy":** ludzie i przedmioty są zamieniane na postacie i obiekty z kreskówki, z grubymi konturami i płaskim kolorem.
    *   **Styl "steampunk":** nowoczesne obiekty (laptop, telefon) są przekształcane w swoje wiktoriańskie, mechaniczne odpowiedniki pełne kół zębatych, rur i mosiądzu.

2.  **Interaktywna i kontekstowa transformacja:** AI może reagować nie tylko na to, *co* widzi, ale też *jak* się to zachowuje.
    *   **Reakcja na tuch:** gdy ktoś zacznie machać ręką, jego "patykowy" awatar może zacząć trząść się i rozpadać, a po zatrzymaniu się składać z powrotem. Gdy ktoś siada na krzeło, jego "tron" może rozbłysnąć złotym światłem.
    *   **Interakcja między obiektami:** jeśli AI wykryje, że osoba podnosi kubek, może to zinterpretować jako "czarodziej bierze do ręki magiczny artefakt", a kubek zacznie świecić.
    *   **"Zjadanie" obiektów:** AI może mieć "głód". Jeśli wykryje określony kolor lub kształt, może "zjadać" go z obrazu, zamieniając w piksele lub unoszące się cząsteczki.

3.  **Wymagania specjalne i zagadki:** instalacja może stać się interaktywną grą.
    *   **"Znajdź obiekt":** na ekranie pojawia się napis: "Znajdź tron!". Ludzie muszą zrozumieć, że muszą usiąść na krzeło, by AI je zamieniło i "zaliczyło" zadanie.
    *   **"Odtwórz pozę":** ekran pokazuje sylwetkę ludzika z patyków w konkretnej pozie. Gracz musi stanąć przed kamerą i przybrać tę samą pozę, by AI uznało wyzwanie za wykonane.

## Możliwe kierunki realizacji

### Ścieżka 1: "Prosta Zamiana" (idealna dla początkujących)

*   **Cel:** stworzenie działającego prototypu z kilkoma prostymi transformacjami.
*   **Technologia:**
    *   **AI do wykrywania obiektów:** użycie gotowych, wstępnie wytrenowanych modeli dostępnych przez biblioteki Pythona, np. **YOLO** (przez `ultralytics`) lub **Detectron2** (Facebook). Są w stanie wykrywać dziesiątki klas obiektów (osoba, krzesło, kubek, laptop itp.).
    *   **Modyfikacja obrazu:** gdy model wykryje obiekt (np. "osoba") i zwróci jego współrzędne (bounding box), prosty skrypt w **OpenCV** nakłada na ten obszar inny obraz (np. grafikę ludzika z patyków).
*   **Wyzwania:** instalacja bibliotek AI, zrozumienie, jak działać na współrzędnych bounding boxów, zapewnienie płynnego działania w czasie rzeczywistym.

### Ścieżka 2: "Inteligentny Montaż" (dla średniozaawansowanych)

*   **Cel:** stworzenie bardziej zaawansowanych i płynnych transformacji.
*   **Technologia:**
    *   **AI do segmantacji obrazu:** zamiast prostych ramek (bounding box), użycie modeli do **segmentacji semantycznej** (np. **Mask R-CNN** lub **U-Net**). Te modele nie tylko znajdują obiekt, ale tworzą jego dokładną "maskę" piksel po pikselu.
    *   **Modyfikacja obrazu:** użycie technik **inpaintingu** lub **blendingu**. Skrypt w OpenCV lub GIMP (przez skrypty) "wycina" obiekt po jego masce i "wkleja" na jego miejsce nową grafikę, dbając o płynne przejścia krawędzi.
*   **Wyzwania:** modele segmentacji są bardziej wymagające obliczeniowo, blending obrazów bez efektu "wycięcia nożem" jest trudny.

### Ścieżka 3: "Generatywna Transformacja" (dla zaawansowanych)

*   **Cel:** stworzenie instalacji, która nie "nakłada" obrazów, a "przemalowuje" rzeczywistość.
*   **Technologia:**
    *   **AI do generowania obrazu:** użycie zaawansowanych modeli **Image-to-Image**, takich jak **ControlNet** z **Stable Diffusion**. Model taki bierze obraz z kamery i na podstawie "mapy głębi" lub "mapy krawędzi" (wygenerowanej z tego samego obrazu) oraz promptu tekstowego ("stick figure person, throne chair, cartoon style") generuje od zera nowy obraz, który zachowuje kompozycję oryginału, ale jest w całości przerysowany.
*   **Wyzwania:** wymagana jest bardzo mocna karta graficzna (GPU) z dużą ilością VRAM, obsługa zaawansowanych frameworków (np. `diffusers` w Pythonie) i optymalizacja, by uzyskać sensowną liczbę klatek na sekundę.

## Praktyczne wskazówki i potrzebne zasoby

### Sprzęt

*   **Kamera:** dobra jakość kamerki internetowej. Ważne jest stabilne oświetlenie, aby AI miało czysty obraz do analizy.
*   **Komputer:** to projekt wymagający mocy obliczeniowej. **Karta graficzna (GPU) NVIDIA** jest praktycznie niezbędna, zwłaszcza w ścieżkach 2 i 3.
*   **Ekran/Rzutnik:** duży ekran lub projektor, aby efekt był dobrze widoczny dla publiczności.

### Oprogramowanie i umiejętności

*   **Python:** język dominujący w świecie AI i wizji komputerowej.
*   **Biblioteki AI:** `OpenCV` (podstawy przetwarzania obrazu), `PyTorch`/`TensorFlow` (frameworki do uruchamiania modeli), `ultralytics` (łatwy dostęp do YOLO), `diffusers` (dla Stable Diffusion).
*   **Wiedza o modelach:** zrozumienie różnicy między detekcją obiektów (bounding box), a segmentacją (maska pikseli).

### Ważne wskazówki do realizacji

*   **Wydajność to priorytet:** przetwarzanie wideo w czasie rzeczywistym jest kosztowne. Zacznij od mniejszej rozdzielczości obrazu i prostszych modeli. Płynność jest ważniejsza niż idealna jakość detekcji.
*   **Testuj na różnych danych:** Twój model musi działać na różnorodnych danych. Testuj go na różnych ludziach, w różnych ubraniach, przy różnym oświetleniu i z różnymi meblami.
*   **Stwórz "Fallback":** co się stanie, gdy AI nie rozpozna obiektu? System powinien mieć domyślne zachowanie, np. pozostawić obiekt bez zmiany lub zamienić go w "mgłę", co wygląda celowo.
