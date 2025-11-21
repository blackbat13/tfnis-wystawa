# Emo-Symfonia: Twoja Twarz, Twoja Muzyka

Interaktywna instalacja, która w czasie rzeczywistym analizuje Twoją twarz, by rozpoznać emocje, a następnie komponuje unikalny utwór muzyczny idealnie dopasowany do Twojego nastroju. Ale to nie wszystko – system bierze pod uwagę Twoje cechy, takie jak wiek czy dodatkowe atrybuty (okulary, broda), by dodać muzycznemu dziełu unikalny styl i charakter. To Ty jesteś dyrygentem, a Twoja twarz to partytura.

## Pomysły na funkcjonalności

1.  **Dynamiczna ewolucja muzyki:** zamiast odtwarzać gotowy utwór, AI może go komponować w czasie rzeczywistym. Muzyka nie tylko zmienia się w zależności od dominującej emocji, ale także ewoluuje. Na przykład, jeśli użytkownik zaczyna od neutralnego wyrazu, a jego uśmiech staje się coraz szerszy, muzyka może stopniowo przechodzić od spokojnej, ambientowej kompozycji do radosnego, energetycznego utworu. Nagła zmiana emocji (np. z zadowolenia na zaskoczenie) spowodowałaby gwałtowną zmianę rytmu lub instrumentarium.

2.  **Warstwy stylu i "kosmetyki" dźwiękowej:** 
    *   **Wiek jako era muzyczna:** zamiast prostego przypisania, system może tworzyć miks. Dla 50-latka może to być nowoczesny syntpop z elementami retro z lat 80. (np. charakterystyczny pad syntezatorowy). Dla 30-latka może to być rock z lat 90. z nowoczesnym, elektronowym beatem.
    *   **Atrybuty jako efekty specjalne:**
        *   **Okulary:** mogą dodać "chłodny", lekko zdystansowany filtr, np. delikatny chorus lub pogłos, jakby dźwięk docierał przez szkło.
        *   **Broda:** może wzmocnić basy i dodać "gruntowności" dźwięku, sprawiając, że będzie on bardziej pełny i głęboki.
        *   **Kapelusz/Czapka:** może dodać efekt "panorama" – dźwięk będzie się przemieszczał między lewym a prawym kanałem, jakby był szeroki i przestrzenny.
        *   **Długość Włosów:** AI mogłaby analizować "objętość" fryzury i tłumaczyć ją na ilość warstw melodycznych lub harmonicznych.

3.  **Wizualna pętla zwrotna:** ekran nie musi pokazywać tylko kamery. Może na nim pojawiać się wizualizacja generowana jednocześnie z muzyką. Kształty, kolory i ich ruch mogłyby odzwierciedlać zarówno emocje (czerwień dla złości, niebieski dla smutku), jak i wygenerowany styl muzyczny (kanciaste kształty dla rocka, płynne linie dla ambientu).

## Możliwe kierunki realizacji

Projekt ten można zrealizować na wiele sposobów, co czyni go idealnym dla zespołu o zróżnicowanych umiejętnościach.

### Ścieżka 1: "Szybki Prototyp" (Idealna dla początkujących)

*   **Cel:** Stworzenie działającej koncepcji w krótkim czasie.
*   **Technologia:**
    *   **AI:** Gotowe, wstępnie wytrenowane modele dostępne przez proste biblioteki Pythona (np. `face_recognition` do wykrywania twarzy i `deepface` do klasyfikacji emocji).
    *   **Muzyka:** Zamiast generować, można użyć gotowej biblioteki utworów podzielonych na gatunki i nastroje. Program wybiera odpowiedni plik MP3.
    *   **Efekty:** Prosta modyfikacja dźwięku za pomocą biblioteki `pydub` (zmiana tempa, dodanie prostego pogłosu).
*   **Wyzwania:** Integracja kilku bibliotek, obsługa strumienia wideo z kamery.

### Ścieżka 2: "Hybrydowa Generacja" (Dla średniozaawansowanych)

*   **Cel:** Większa kreatywność i unikalność generowanej muzyki.
*   **Technologia:**
    *   **AI:** Użycie bardziej zaawansowanych modeli, np. z `Hugging Face Transformers` do analizy sentymentu.
    *   **Muzyka:** Generowanie muzyki proceduralnej. Zamiast gotowych utworów, program komponuje muzykę od zera na podstawie reguł (np. emocja "radość" = szybkie tempo, tonacja dur, wysokie nuty). Można do tego użyć bibliotek jak `mingus` lub `tone.js` (jeśli część frontendowa będzie w JavaScript).
    *   **Efekty:** Integracja z prostym VST (wirtualnym instrumentem) lub biblioteką do syntezy dźwięku (np. `pyo` w Pythonie), by dynamicznie zmieniać parametry dźwięku.
*   **Wyzwania:** Zrozumienie podstaw teorii muzyki, programowanie logiki generacyjnej, synchronizacja wizji i dźwięku w czasie rzeczywistym.

### Ścieżka 3: "Głęboka Sieć Neuronowa" (Dla zaawansowanych)

*   **Cel:** Projekt ostateczny, w pełni generatywny i zaskakujący.
*   **Technologia:**
    *   **AI:** Trenowanie własnego, mniejszego modelu do rozpoznawania emocji, jeśli chcemy uzyskać unikalne wyniki. Można też użyć dużych, wielomodalnych modeli (np. GPT-4V z API), które opisują scenę i emocje w tekście.
    *   **Muzyka:** Użycie modeli generatywnych do muzyki, jak MusicGen (Meta) czy Riffusion. Promptem dla takiego modelu byłby opis wygenerowany przez moduł wizyjny (np. "upbeat, synth-pop, 80s style, energetic, happy").
    *   **Efekty:** Model muzyczny sam uwzględni styl w promptzie, a dodatkowe efekty można generować za pomocą sieci neuronowej do modyfikacji audio (style transfer dla dźwięku).
*   **Wyzwania:** Wymagana jest mocna karta graficzna (GPU), duże zaplecze obliczeniowe, znajomość frameworków jak PyTorch/TensorFlow, praca z API, optymalizacja wydajności w czasie rzeczywistym.

## Praktyczne wskazówki i potrzebne zasoby

### Sprzęt

*   **Podstawowe:** komputer z kamerą internetową. Do prototypu wystarczy zwykły laptop.
*   **Zalecane:** dedykowana kamera HD (dla lepszego wideo), zewnętrzny mikrofon (choć nie jest konieczny), dobrej jakości słuchawki lub głośniki (aby publiczność mogła docenić niuanse dźwięku).
*   **Zaawansowane:** komputer z wydajną kartą graficzną NVIDIA (z dużą ilością pamięci VRAM) do trenowania lub uruchamiania dużych modeli AI lokalnie.

### Oprogramowanie i języki programowania

*   **Python:** absolutny faworyt. Posiada ogromną liczbę bibliotek do AI (`OpenCV`, `TensorFlow`, `PyTorch`, `Hugging Face`), analizy dźwięku (`librosa`, `pydub`) i obsługi multimediów.
*   **JavaScript (z Node.js):** dobry wybór, jeśli instalacja ma mieć bogaty interfejs webowy. Biblioteki jak `TensorFlow.js` pozwalają na uruchamianie modeli AI bezpośrednio w przeglądarce.
*   **Narzędzia:** `Git` do wersjonowania kodu, `VS Code` jako środowisko programistyczne.

### Pierwsze kroki dla zainteresowanych

1.  **Zainstaluj Pythona i bibliotekę `OpenCV`**. Spróbuj napisać prosty program, który wyświetla obraz z kamery i rysuje na wykrytej twarzy prostokąt.
2.  **Zainstaluj bibliotekę `deepface`**. Połącz ją z poprzednim punktem, aby program wyświetlał na ekranie wykrytą emocję (np. "happy", "sad").
3.  **Zabierz się za `pydub`**. Naucz się, jak załadować plik mp3, zmienić jego tempo lub odtworzyć w pętli.
