# Serce Chaosu: jak Twój ruch kreuje Losowość

Zobacz na własne oczy, jak komputer "uczy się" być losowy. Na ekranie widzisz abstrakcyjną, pulsującą animację, która początkowo jest powolna, przewidywalna i schematyczna. To wizualizacja pracy prostego generatora liczb pseudolosowych. Ale gdy zaczniesz poruszać myszą, pisać na klawiaturze, a nawet machać ręką przed kamerą, animacja ożywa. Staje się chaotyczna, nieprzewidywalna, pełna niespodziewanych wzorów i eksplozji kolorów. Każdy Twój ruch, każde kliknięcie, każde zakłócenie jest "kropką oleju" w maszynce do generowania losowości – źródłem entropii, które zamienia porządek w piękny, cyfrowy chaos. To Ty jesteś sercem tego systemu.

## Pomysły na funkcjonalności

1.  **Wizualizacja różnych źródeł entropii:** zamiast jednej animacji, stwórzmy kilka "warstw", które pokazują, jak różne źródła entropii wpływają na system.
    *   **"Cichy" tryb:** na początku instalacja działa w trybie "cichym", używając tylko wewnętrznego, przewidywalnego generatora pseudolosowego (PRNG). Animacja jest płynna, ale powtarzalna.
    *   **"Mysz" jako źródło:** gdy użytkownik porusza myszą, jej pozycja i prędkość są pobierane i mieszane z PRNG. Na ekranie pojawia się nowa, bardziej dynamiczna warstwa animacji, która "tańczy" w rytm ruchów myszy.
    *   **"Klawiatura" jako źródło:** każde naciśnięcie klawisza generuje "dźwiękowy" impuls losowości, który może powodować nagłe zmiany koloru lub geometryczne "przeskoki" w animacji.
    *   **"Kamera" jako źródło:** ruch wykryty przez kamerę jest najbardziej chaotycznym źródłem. Może on generować "cząsteczki" lub "plamy" na ekranie, które wprowadzają najwięcej nieprzewidywalności.

2.  **Edukacyjna warstwa informacyjna:** instalacja może być nie tylko piękna, ale i pouczająca.
    *   **Wskaźniki entropii:** w rogu ekranu mogą pojawiać się proste wskaźniki pokazujące, ile "entropii" jest aktualnie generowane przez każde źródło (mysz, klawiatura, kamera). Użytkownik widzi, jak jego działania bezpośrednio wpływają na "jakość" losowości.
    *   **Przykłady zastosowania:** obok animacji mogą pojawiać się krótkie napisy: "Ta losowość jest teraz wystarczająco silna, by zaszyfrować Twoją wiadomość" lub "Potrzebujemy więcej entropii, by wygenerować bezpieczny klucz!". To pokazuje praktyczne znaczenie tego, co dzieje się na ekranie.

3.  **Różne "silniki" losowości:** instalacja może pozwolić użytkownikowi "przełączać" różne algorytmy generowania liczb losowych i wizualizować różnice.
    *   **PRNG:** prosty, ale łatwy do złamania generator.
    *   **XORShift:** szybszy i lepszy generator.
    *   **Kryptograficzny RNG:** użycie kryptograficznie bezpiecznego generatora (np. `/dev/urandom` na Linuksie), który już na wejściu jest karmiony entropią z systemu. Animacja w tym trybie może być od początku chaotyczna, ale w inny, bardziej "zorganizowany" sposób.

## Możliwe kierunki realizacji

### Ścieżka 1: "Prosty Chaos" (idealna dla początkujących)

*   **Cel:** stworzenie działającej koncepcji z jedną animacją i jednym źródłem entropii.
*   **Technologia:**
    *   **Silnik graficzny:** **Processing** lub **p5.js**. Te środowiska są stworzone do prostych, interaktywnych animacji i mają wbudowane funkcje do obsługi myszy i klawiatury.
    *   **Logika:** program używa wbudowanej funkcji `random()` do animacji. Gdy użytkownik porusza myszą, wartość jej pozycji (np. `mouseX`) jest używana do zmiany parametru animacji (np. koloru, rozmiaru).
*   **Wyzwania:** zrozumienie podstaw pętli animacji i obsługi zdarzeń wejściowych.

### Ścieżka 2: "Prawdziwa Entropia" (dla średniozaawansowanych)

*   **Cel:** stworzenie bardziej zaawansowanej symulacji z wieloma źródłami i lepszą wizualizacją.
*   **Technologia:**
    *   **Silnik graficzny:** **Unity** lub **Godot**. Dają większe możliwości w tworzeniu skomplikowanych systemów cząsteczkowych i shaderów.
    *   **Logika:** napisanie własnego, prostego generatora PRNG (np. LCG - Linear Congruential Generator). Następnie stworzenie funkcji `mix_entropy(source)`, która pobiera surowe dane z wejścia (pozycja myszy, czas od ostatniego naciśnięcia klawisza, dane o ruchu z kamery) i używa ich do "przemieszania" stanu wewnętrznego PRNG.
*   **Wyzwania:** zrozumienie matematyki generatorów PRNG, obsługa strumienia wideo z kamery, programowanie bardziej złożonych systemów wizualnych.

### Ścieżka 3: "Kryptograficzne Laboratorium" (dla zaawansowanych)

*   **Cel:** stworzenie w pełni funkcjonalnej, edukacyjnej instalacji pokazującej realne mechanizmy.
*   **Technologia:**
    *   **Silnik graficzny:** **Unity** z zaawansowanymi shaderami lub **TouchDesigner** do tworzenia skomplikowanych wizualizacji w czasie rzeczywistym.
    *   **Logika:** implementacja kilku różnych algorytmów PRNG i kryptograficznych RNG. Integracja z systemowym źródłem entropii (`/dev/urandom` na Linuxie, `CryptGenRandom` na Windowsie). Wizualizacja może pokazywać nawet stan bitów wewnętrznego stanu generatora.
*   **Wyzwania:** głęboka wiedza z zakresu kryptografii i generatorów liczb losowych, zaawansowane programowanie grafiki (shadery), optymalizacja wydajności.

## Praktyczne wskazówki i potrzebne zasoby

### Sprzęt

*   **Komputer:** wystarczy standardowy komputer. W ścieżce 3 karta graficzna przyda się do zaawansowanych efektów.
*   **Mysz i klawiatura:** standardowe urządzenia wejściowe.
*   **Kamera (opcjonalnie):** zwykła kamerka internetowa.

### Oprogramowanie i umiejętności

*   **Processing/p5.js:** idealne do nauki i szybkiego prototypowania. Wymagają podstaw JavaScriptu lub Javy.
*   **Python z `Pygame` lub `Tkinter`:** dobra alternatywa dla osób, które wolą Pythona.
*   **Unity/Godot:** do bardziej zaawansowanych projektów, wymagają nauki C# lub GDScript.
*   **Podstawowa Wiedza Matematyczna:** zrozumienie, czym jest modulo, operacje bitowe (XOR) i pojęcie entropii będzie bardzo pomocne.

### Ważne wskazówki do realizacji

*   **Wizualizuj stan, a nie tylko wynik:** zamiast tylko pokazywać finalną, losową animację, spróbuj wizualizować "stan wewnętrzny" generatora. Może to być pasek, kolor, wzór – coś, co zmienia się, gdy dodajesz entropię.
*   **Daj natychmiastową informację zwrotną:** kluczem jest to, by użytkownik *odczuł* swoją kontrolę nad chaosem. Reakcja animacji na ruch musi być natychmiastowa i wyraźna.
*   **Zacznij od prostego PRNG:** nie używaj od razu wbudowanego, "magicznego" `random()`. Zaimplementuj sam najprostszy generator (np. LCG). Dzięki temu będziesz miał pełną kontrolę i będziesz mógł wizualizować każdy krok jego działania.
