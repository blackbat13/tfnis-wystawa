# Wiatrowe Regaty: Twoja strategia, Twój wiatr

Interaktywna instalacja, która przenosi sztukę żeglowania do miniatury, dając Ci absolutną kontrolę nad siłą natury. W centrum znajduje się niewielki zbiornik, w którym dryfuje elegancka żaglówka. To Ty jesteś wiatrem. Używając panelu z wentylatorami komputerowymi, sterujesz kierunkiem i siłą powiewów, prowadząc statek przez wyznaczone tory lub w otwartym, swobodnym rejsie. To nie jest symulacja – to ty jesteś bosmanem, a żaglówka to wyzwanie dla Twojego wyczucia i precyzji.

## Pomysły na funkcjonalność

1. **Realistyczna fizyka żeglowania:** zamiast prostego popychania łódki, wentylatory generują złożone pola powietrzne. Żaglówka wyposażona w miniaturowy żagiel (z lekkiego materiału) reaguje na zmiany ciśnienia i kierunku wiatru. Ustawienie żagla pod odpowiednim kątem względem "wiatru" generuje siłę nośną, która pcha statek do przodu. Zbyt mocny podmuch w niekorzystnym kierunku może spowodować przechył lub cofnięcie się jednostki. Gracz musi nauczyć się, jak manewrować, wykorzystując siłę wiatru, a nie walcząc z nią.

2. **Tryby gry i wyzwania:**
      * **Tryb Regat:** Na zbiorniku wyznaczone są za pomocą markerów lub projektorów punkty nawigacyjne (boje). Zadaniem gracza jest przepłynięcie całej trasy w jak najkrótszym czasie, omijając przeszkody (np. miniaturowe latarnie morskie) i wykorzystując zmienne warunki wiatrowe.
      * **Tryb "Dockmaster":** W tym trybie celem jest precyzyjne manewrowanie żaglówką, by wpłynąć do bardzo ciasnego "doku" (oznaczonego obszaru) bez dotknięcia jego krawędzi. Wymaga to delikatnych, krótkich podmuchów i idealnego wyczucia.
      * **Tryb Swobodnego Rejsu (Sandbox):** Brak celów, brak ograniczeń. Gracz może swobodnie eksperymentować, tworząc wzorce powietrzne, obserwując, jak żaglówka na nie reaguje i po prostu ciesząc się medytacyjnym aspektem sterowania wiatrem.

3. **Zaawansowane sterowanie i interakcja:**
      * **Manualne sterowanie żaglem:** Żaglówka mogłaby mieć na pokładzie miniaturowy serwomechanizm połączony bezprzewodowo z kontrolerem gracza. Gracz nie tylko steruje wiatrem, ale także w czasie rzeczywistym może obracać żagiel, dodając warstwę strategii.
      * **Dynamiczne warunki pogodowe:** System mógłby wprowadzać losowe zdarzenia. Na przykład, co jakiś czas jeden z wentylatorów mógłby włączać się na krótko w losowym kierunku, symulując nagłą zmianę wiatru lub szkwał, do którego gracz musi zareagować.
      * **Różne typy łódek:** Możliwość wyboru różnych modeli żaglówek – od szybkich, ale niestabilnych jachtów po ciężkie, stabilne, ale powolne szkunery, z których każda wymagałaby innej taktyki.

## Możliwe kierunki realizacji

### Ścieżka 1: "Analogowy Prototyp" (Idealna dla hobbystów elektroniki)

* **Cel:** Stworzenie działającej, w pełni manualnej instalacji.
* **Technologia:**
    * **Sterowanie:** Zestaw przełączników i potencjometrów (suwaków) podłączonych do regulatorów obrotów wentylatorów. Każdy wentylator ma osobny przełącznik włącz/wyłącz i potencjometr do regulacji siły.
    * **Żaglówka:** Model z drewna lub plastiku drukowany w 3D, z prostym, stałym żaglem.
    * **Zbiornik:** Dowolna niecka, np. plastikowe pudełko lub akwarium.
* **Wyzwania:** Dobór odpowiednich wentylatorów (o odpowiednim momencie obrotowym), aby generowały wystarczający ruch powietrza, zbalansowanie żaglówki, aby nie wywracała się przy silniejszych podmuchach.

### Ścieżka 2: "Cyfrowa Kontrola" (Dla średniozaawansowanych)

* **Cel:** Wprowadzenie precyzyjnego, programowalnego sterowania i elementów gry.
* **Technologia:**
    * **Sterowanie:** Mikrokontroler (np. Arduino lub ESP32) podłączony do komputera. Program na komputerze (np. w Pythonie z biblioteką `pyserial`) wysyła komendy do Arduino, które steruje prędkością wentylatorów za pomocą modułów PWM (np. z tranzystorami MOSFET).
    * **Interfejs:** Stworzenie prostego interfejsu graficznego (GUI) na komputerze, gdzie suwaki sterują siłą wiatru z każdego wentylatora.
    * **Wykrywanie pozycji:** Dodanie do zbiornika kamery z góry i użycie prostej biblioteki do przetwarzania obrazu (np. `OpenCV`) do śledzenia pozycji żaglówki (może mieć na sobie kolorowy znacznik).
* **Wyzwania:** Programowanie mikrokontrolera, komunikacja szeregowa między PC a Arduino, implementacja prostej wizji komputerowej do śledzenia obiektu.

### Ścieżka 3: "Inteligentny System" (Dla zaawansowanych)

* **Cel:** Stworzenie w pełni zautomatyzowanego systemu z elementami sztucznej inteligencji.
* **Technologia:**
    * **Sterowanie:** Użycie Raspberry Pi jako głównego mózgu systemu, bezpośrednio sterującego wentylatorami.
    * **Interfejs:** Aplikacja webowa działająca na Raspberry Pi, dostępna przez przeglądarkę na telefonie lub tablecie.
    * **AI i sensory:** Żaglówka wyposażona w miniaturowy czujnik kierunku wiatru (wiatrowskaz) i czujnik przechyłu. Dane z tych sensorów są przesyłane bezprzewodowo (np. przez Bluetooth lub BLE) do Raspberry Pi. System AI może uczyć się, jakiej siły i kierunku wiatru potrzebuje statek, aby wykonać określony manewr, i automatycznie sterować wentylatorami, aby go zrealizować.
* **Wyzwania:** Zasilanie i komunikacja bezprzewodowa z miniaturowej żaglówki, programowanie logiki sterującej w czasie rzeczywistym, implementacja algorytmów uczenia maszynowego.

## Praktyczne wskazówki i potrzebne zasoby

### Sprzęt

* **Podstawowe:** Zbiornik (akwarium, pudełko), model żaglówki (można kupić gotowy model lub wydrukować w 3D), kilka wentylatorów komputerowych (np. 80mm lub 120mm), zasilacz do nich.
* **Zalecane:** Mikrokontroler Arduino, moduły tranzystorów MOSFET do regulacji prędkości wentylatorów, kamera internetowa, kable i przewody.
* **Zaawansowane:** Raspberry Pi, miniaturowe czujniki (akcelerometr, żyroskop, wiatrowskaz), moduły bezprzewodowe (Bluetooth), drukarka 3D do tworzenia customowych części.

### Oprogramowanie i języki programowania

* **Arduino/C++:** Do programowania mikrokontrolera i bezpośredniej obsługi elektroniki.
* **Python:** Doskonały do stworzenia interfejsu graficznego (np. z `Tkinter` lub `PyQt`), obsługi komunikacji szeregowej (`pyserial`) i przetwarzania obrazu z kamery (`OpenCV`).
* **JavaScript/HTML/CSS:** Jeśli interfejs ma być webowy i działać na Raspberry Pi.

### Pierwsze kroki dla zainteresowanych

1. **Zbuduj prosty układ elektroniczny:** Podłącz jeden wentylator do zasilania i sprawdź, jak generuje strumień powietrza. Następnie spróbuj sterować jego prędkością za pomocą potencjometru.
2. **Zrób próbne żeglowanie:** Postaw żaglówkę w zbiorniku i ręcznie (np. dmuchając przez słomkę) spraw, jak reaguje na wiatr z różnych kierunków. Zrozum jej fizykę.
3. **Napisz pierwszy kod dla Arduino:** Napisz program, który włącza i wyłącza wentylator co 2 sekundy, abyś miał pewność, że komunikacja i elektronika działają.
