# Pixel Pilot: Twój własnoręcznie zbudowany kontroler

Dlaczego grać na standardowym padzie, skoro możesz zbudować własny? W tym projekcie zaprojektujesz, wydrukujesz w 3D i złożysz unikalny kontroler do gier, w sercu którego znajduje się micro:bit – mały komputer z żyroskopem, akcelerometrem i przyciskami. Pochylaj go, by sterować postacią, potrząśnij, by aktywować specjalną moc, naciskaj przyciski, by skakać i strzelać. Możesz połączyć go z grą stworzoną od podstaw lub zhakować ulubioną grę internetową. To nie jest tylko projekt – to tworzenie własnego, osobistego narzędzia do cyfrowej zabawy.

## Pomysły na funkcjonalności

1.  **Różne typy kontrolerów dla różnych gier:** zamiast jednego, uniwersalnego padu, stwórzmy kilka specjalizowanych kontrolerów.
    *   **Kontroler wyścigowy:** obudowa w kształcie małej kierownicy. Pochylenie do przodu/tyłu to gaz/hamulec, a obrót w lewo/prawo to skręt. Przycisk A na micro:bicie to klakson.
    *   **Kontroler lotniczy (joystick):** pionowa obudowa trzymana w dłoni. Pochylenie w osi X i Y steruje samolotem lub statkiem kosmicznym. Potrząśnięcie uruchamia barrel roll.
    *   **Kontroler "magiczna dżdżownica":** kontroler w kształcie kostki lub pudełka leżącego na stole. Gracz manipuluje nim, obracając i przekręcając, by sterować postacią w labiryncie lub rozwiązywać zagadki logiczne. Idealne do gier z góry.
    *   **Kontroler fitnessowy:** Obudowa w formie opaski na nadgarstek. Gracze wykonują fizyczne ruchy (np. przysiady, skoki, machanie ramionami), a żyroskop w micro:bicie rozpoznaje akcje i przenosi je do prostej gry sportowej.

2.  **Rozbudowa o dodatkowe czujniki (DIY):** micro:bit można łatwo rozbudować.
    *   **Dodatkowy przycisk:** podłączony do pinów GPIO micro:bita, może służyć jako drugi przycisk akcji.
    *   **Fotorezystor:** można go zamontować w obudowie. Przykrycie go palcem może aktywować tryb "niewidzialności" w grze.
    *   **Buzzer:** mały głośniczek podłączony do micro:bita może generować dźwięki efektowe bezpośrednio z kontrolera (np. dźwięk wystrzału, sygnał niskiego poziomu baterii).

3.  **Wizualna informacja zwrotna z kontrolera:**
    *   **Wyświetlacz LED:** wykorzystaj wbudowaną w micro:bit matrycę LED do wyświetlania informacji. Może pokazywać poziom życia, liczbę amunicji, aktualny tryb fire lub po prostu "żywą" animację, gdy kontroler jest w użyciu.
    *   **Diody RGB:** podłącz zewnętrzne diody LED do obudowy, które mogą zmieniać kolor w zależności od sytuacji w grze (czerwony przy obrażeniach, niebieski przy tarczy).

## Możliwe kierunki realizacji

### Ścieżka 1: "Gotowiec z Sieci" (idealna dla początkujących i szybkiego efektu)

*   **Cel:** stworzenie działającego kontrolera w jak najkrótszym czasie.
*   **Technologia:**
    *   **Gra:** użycie gotowej gry, która wspiera kontrolery, np. prosta gra HTML5 z obsługą joysticku.
    *   **Komunikacja:** skrypt w Pythonie na komputerze, który odczytuje dnae z micro:bita (przez Bluetooth lub USB) i symuluje naciśnięcia klawiszy (np. strzałek, spacji) za pomocą biblioteki `pyautogui`.
    *   **Obudowa:** znalezienie gotowego projektu na Thingiverse i po prostu wydrukowanie go.
*   **Wyzwania:** konfiguracja Bluetooth między micro:bitem a komputerem, kalibracja odczytów z żyroskopu.

### Ścieżka 2: "Własna Gra, Własne Zasady" (dla średniozaawansowanych)

*   **Cel:** stworzenie spójnego ekosystemu: kontroler + gra stworzona specjalnie dla niego.
*   **Technologia:**
    *   **Gra:** napisanie prostej gry 2D w silniku **Godot** lub **Unity**. Silnik ten ma wbudowane wsparcie dla odbierania danych niestandardowych z kontrolerów.
    *   **Komunikacja:** napisanie własnego prostego serwera (np. w Pythonie z `flask-socketio`), który odbiera dane z micro:bita (przez Bluetooth) i przekazuje je w czasie rzeczywistym do gry.
    *   **Obudowa:** zaprojektowanie własnej obudowy w prostym programie do modelowania 3D (np. **Tinkercad**).
*   **Wyzwania:** podstawy programowania gier, tworzenie prostej komunikacji sieciowej, nauka podstaw modelowania 3D.

### Ścieżka 3: "Zaawansowany Prototyp" (dla zaawansowanych)

*   **Cel:** stworzenie w pełni funkcjonalnego, bezprzewodowego kontrolera z rozbudowanymi funkcjami.
*   **Technologia:**
    *   **Hardware:** dodanie do micro:bita modułu Bluetooth (np. HC-05) dla większego zasięgu i stabilności, podłączenie dodatkowych czujników (przycisków, diod) przez pinout GPIO.
    *   **Komunikacja:** implementacja bezpośredniej komunikacji między kontrolerem a grą przez protokół Bluetooth Low Energy (BLE), bez potrzeby korzystania z komputerowego "pośrednika".
    *   **Obudowa:** zaprojektowanie zaawansowanej obudowy w **Blenderze** lub **Fusion 360**, z uwzględnieniem montażu elektroniki, przycisków i swobodnego przepływu powietrza.
*   **Wyzwania:** zaawansowana elektronika, programowanie na niskim poziomie (obsługa BLE), precyzyjne modelowanie 3D z uwzględnieniem tolerancji.

## Praktyczne wskazówki i potrzebne zasoby

### Sprzęt

*   **Micro:bit:** serce projektu. Warto kupić zestaw z kabelkiem USB i baterią.
*   **Drukarka 3D:** kluczowy element. Jeśli nie macie własnej, można skorzystać z usług lokalnej fablabki lub zamówić druk online.
*   **Materiał do druku:** najczęściej PLA – łatwy w druku, wystarczająco wytrzymały na obudowę.
*   **Narzędzia:** komputer, kabel micro USB, ewentualnie lutownica (do podłączania dodatkowych elementów).

### Oprogramowanie i umiejętności

*   **Programowanie micro:bit:** Można używać blokowego **MakeCode** (idealne dla początkujących) lub **MicroPython** (dla zaawansowanych).
*   **Modelowanie 3D:** **Tinkercad** (dla początkujących), **Blender** (dla średniozaawansowanych) lub **Fusion 360** (dla zaawansowanych).
*   **Tworzenie Gier:** **Scratch** (dla absolutnie początkujących), **Godot** (świetny, darmowy silnik 2D/3D), **Unity** (standard branżowy).
*   **Python:** język, który świetnie nadaje się do "sklejania" wszystkiego w całość (komunikacja z micro:bitem, symulacja klawiszy).

### Ważne wskazówki do realizacji

*   **Zacznij od kodu, potem obudowa:** zanim wydrukujesz cokolwiek, upewnij się, że elektronika działa i komunikacja z grą działa. Możesz trzymać micro:bit na kabelku i testować.
*   **Kalibracja to klucz:** odczyty z żyroskopu mogą być "głośne". W kodzie musisz dodać kalibrację i progi, aby małe, mimowolne drżenia ręki nie były interpretowane jako ruch.
*   **Ergonomia:** testuj wirtualny model obudowy, trzymając w dłoni "kartonowy prototyp". Czy przyciski są w łatwo dostępnym miejscu? Czy nie jest za ciężki? Wygoda użytkowania jest równie ważna, co funkcjonalność.
