# Żywe Płótno: twoje ruchy, nasza sztuka

Wejdź na podłogę, która jest żywym, reagującym na Twoją obecność obrazem. Każdy Twój krok, gest, a nawet sama Twoja obecność, maluje, deformuje i ożywia cyfrową rzeczywistość pod Twoimi stopami. Projektowany obraz nie jest tłem – to płynna, dynamiczna substancja, która wchodzi w interakcję z Tobą. Stoisz sam? Tworzysz indywidualny ślad. Przychodzisz z grupą? Razem tworzycie wspólną, chwilową kompozycję. To Ty jesteś pędzlem, a podłoga – Twoim płótnem.

## Pomysły na funkcjonalności

1.  **Różne "Tryby" Płótna:** Zamiast jednego efektu, instalacja może oferować kilka różnych "światów", które zmieniają się co kilka minut lub mogą być przełączane przez organizatora.
    *   **Świat Wody:** Podłoga wygląda jak tafla wody. Każdy krok wyzwala realistyczne fale i koła, które rozprzestrzeniają się i łączą. Można w niej "chodzić po wodzie".
    *   **Kosmiczna Mgła:** Przestrzeń wypełniona jest ruchomą mgłą lub galaktycznym pyłem. Ludzie, przechodząc, "rozpychają" mgłę, odsłaniając gwiazdy lub nebulę za nią. Po chwili mgła powoli się z powrotem zalewa.
    *   **Magiczny Ogród:** W miejscu, gdzie stanie osoba, zaczynają wyrastać wirtualne kwiaty, pnącza lub trawa. Im dłużej ktoś stoi, tym bujniejsza staje się roślina. Gdy odejdzie, roślina pozostaje jako ślad, ale po chwieniu więdnie i znika.
    *   **Interaktywny Kalidoskop:** Geometryczne wzory i kształty podążają za ludźmi, odbijając się i mnożąc, tworząc hipnotyczne, symetryczne kompozycje, które zmieniają się w zależności od liczby osób i ich wzajemnego położenia.

2.  **Głębsza Interakcja i "Pamięć" Płótna:**
    *   **Światło i Cień:** Obraz może reagować nie tylko na pozycję, ale i na wysokość. Kiedy ktoś podnosi rękę, może "zapalać" światło nad sobą. Instalacja może rzutować cienie ludzi na inne, dynamiczne elementy obrazu.
    *   **Interakcja Międzyludzka:** System może wykrywać, kiedy dwie osoby zbliżają się do siebie. Wtedy między nimi może pojawić się most światła, połączenie energetyczne lub wspólny, bardziej intensywny wzór.
    *   **Pamięć Śladów:** Płótno może "pamiętać" ruchy. Przez kilka sekund po odejściu osoby na podłodze może pozostać jej świetlny zarys lub "duch", który powoli blaknie.

3.  **Warstwa Dźwiękowa:** Dźwięk jest kluczowy dla immersji.
    *   **Generowany Przez Ruch:** Każdy krok może wyzwalać dźwięk – cichy pluszcz w trybie wody, szmer liści w ogrodzie, kosmiczny sygnał w trybie mgławicy.
    *   **Ambientowa Ścieżka:** Każdy tryb obrazu może mieć swoją własną, subtelną ścieżkę dźwiękową, która buduje nastrój i potęguje wrażenie obecności w innym świecie.

## Możliwe kierunki realizacji

### Ścieżka 1: "Kreatywny Patch" (idealna dla początkujących i artystów cyfrowych)

*   **Cel:** Szybkie stworzenie imponującego efektu bez głębokiego programowania.
*   **Technologia:**
    *   **Oprogramowanie:** **TouchDesigner**. To wizualny, węzłowy język programowania, standard w świecie VJ-ingu i instalacji interaktywnych. Ma wbudowane narzędzia do obsługi kamery, śledzenia ruchu (blob tracking) i generowania grafiki 2D/3D. Idealne do szybkiego prototypowania.
    *   **Sprzęt:** Rzutnik, kamera (może być zwykła webcam), komputer z dobrą kartą graficzną.
*   **Wyzwania:** Nauka podstaw logiki węzłowej w TouchDesignerze, kalibracja kamery i projektora.

### Ścieżka 2: "Programistyczna Canva" (dla średniozaawansowanych programistów)

*   **Cel:** Pełna kontrola nad logiką i wyglądem za pomocą kodu.
*   **Technologia:**
    *   **Oprogramowanie:** **Processing** lub **p5.js**. To środowiska programistyczne stworzone z myślą o sztuce i wizualizacjach. Posiadają proste biblioteki do obsługi wideo i kamery. Logikę śledzenia ruchu można zaimplementować samodzielnie (np. przez porównywanie klatek wideo) lub użyć bibliotek zewnętrznych (np. `OpenCV`).
    *   **Alternatywa:** **Unity** z dodatkami do śledzenia ruchu. Daje ogromne możliwości 3D, ale jest bardziej skomplikowane.
*   **Wyzwania:** Pisanie własnego kodu do analizy obrazu, optymalizacja wydajności, by animacja była płynna.

### Ścieżka 3: "AI na Wyzwaniu" (Dla zaawansowanych i pasjonatów AI)

*   **Cel:** Stworzenie instalacji, która nie tylko reaguje na ruch, ale go "rozumie".
*   **Technologia:**
    *   **Oprogramowanie:** **Python** z bibliotekami `OpenCV` do przechwytywania wideo i modelami uczenia maszynowego (np. **MediaPipe** lub **PoseNet**).
    *   **AI:** Zamiast śledzić dowolny ruch, system może identyfikować konkretne części ciała (głowa, dłonie, stopy) i nawet rozpoznawać proste pozy (np. uniesione ręce, skok). Reakcje obrazu mogą być wtedy znacznie bardziej precyzyjne i "inteligentne".
*   **Wyzwania:** Wymagana jest mocna karta graficzna (GPU) do płynnego działania modeli AI w czasie rzeczywistym, zaawansowana znajomość frameworków do machine learningu.

## Praktyczne wskazówki i potrzebne zasoby

### Sprzęt

*   **Rzutnik:** Najważniejszy element. Potrzebujesz rzutnika o **wysokiej jasności (minimum 3000-4000 lumenów)**, ponieważ obraz będzie rzutowany na podłogę i będzie narażony na światło z otoczenia. Krótki rzut (short-throw) jest wielkim plusem – pozwala umieścić rzutnik niedaleko podłogi, unikając cienia rzucanego przez przechodzących.
*   **Kamera:** Kamera umieszczona nad podłogą (np. na statywie lub przymocowana do sufitu) będzie dawać najlepszy obraz. Powinna mieć szerokokątny obiektyw, aby objąć całą aktywną przestrzeń.
*   **Komputer:** Kluczowa jest **dobra karta graficzna**. Nie chodzi o procesor, a o GPU, które będzie odpowiadało za generowanie grafiki i (w ścieżce 3) analizę obrazu z kamery.
*   **Konstrukcja:** Stabilny statyw do rzutnika, uchwyty do kamery.

### Oprogramowanie i umiejętności

*   **TouchDesigner:** Wizualne programowanie, świetne dla artystów i designerów, którzy wolą unikać pisania kodu.
*   **Processing/p5.js:** Programowanie w językach Java/JavaScript, idealne dla studentów informatyki i koderów, którzy chcą połączyć kod ze sztuką.
*   **Python + OpenCV:** Dla entuzjastów AI i danych, którzy chcą wejść na najgłębszy poziom interakcji.

### Kluczowe wskazówki do realizacji

*   **Kalibracja to wszystko:** Największym wyzwaniem jest zeskalowanie obrazu z kamery z obszarem rzutowania rzutnika. Musisz stworzyć mapowanie, które precyzyjnie przypisuje piksele z kamery do pikseli na podłodze.
*   **Oświetlenie:** Instalacja działa najlepiej w zaciemnionym lub półciemnym pomieszczeniu. Im mniej światła z zewnątrz, tym wyraźniejszy i bardziej magiczny będzie obraz.
*   **Testuj na żywo:** Zawsze testuj instalację z prawdziwymi ludźmi. Ich ruchy są często nieprzewidywalne i mogą ujawnić błędy, których nie dało się znaleźć podczas testów.
