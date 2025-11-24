# Robot micro:bit

![Robot micro:bit](../../assets/microbit_robot.jpg)

Projekt polegał na zbudowaniu małego, "inteligentnego" robota-pojazdu, który łączy w sobie dwa tryby działania: zdalne sterowanie oraz autonomiczną nawigację. Wykorzystuje do tego dwie płytki micro:bit, które komunikują się bezprzewodowo za pomocą wbudowanego modułu Bluetooth. Pojazd może być sterowany manualnie przez użytkownika za pomocą kontrolera, a po przełączeniu w tryb autonomiczny, samodzielnie porusza się po otoczeniu, unikając napotykanych przeszkód.

## Komponenty projektu

*   **Pojazd:**
    *   Podwozie robota z silnikami i kołami.
    *   Płytka micro:bit jako jednostka centralna.
    *   Czujnik odległości zamontowany z przodu pojazdu do wykrywania przeszkód.
    *   Zasilanie (baterie AA).

*   **Kontroler:**
    *   Druga płytka micro:bit.
    *   Moduł z joystikiem oraz przyciskami.
    *   Zasilanie.

## Zasada działania

Projekt opiera się na prostym podziale zadań między dwa urządzenia:

*   **Kontroler (Nadajnik):** płytka micro:bit w kontrolerze działa jak pilot. Użytkownik, używając wbudowanego joystika, steruje pojazdem. Program odczytuje dane joystika i na ich podstawie wysyła za pośrednictwem Bluetooth proste komendy do płytki w pojeździe.

*   **Pojazd (Odbiornik):** płytka micro:bit w pojeździe ciągle nasłuchuje na sygnały z kontrolera. Gdy otrzyma komendę, tłumaczy ją na odpowiednie sygnały sterujące dla silników, powodując ruch pojazdu.

*   **Tryb autonomiczny:** po kliknięciu odpowiedniego przycisku na kontrolerze program wchodzi w tryb autonomiczny. Działa on w prostej pętli:
    1.  Jedzie na wprost.
    2.  Co chwilę wysyła impuls do czujnika ultradźwiękowego, aby zmierzyć odległość do najbliższej przeszkody.
    3.  Jeśli odległość jest mniejsza niż ustawiony próg, pojazd zatrzymuje się.
    4.  Wykonuje manewr omijający – cofa się o krótki odcinek, skręca w prawo lub lewo, a następnie ponownie próbuje jechać do przodu.

## Czym jest micro:bit?

**micro:bit** to mała, podręczna płytka komputerowa (mikrokontroler) zaprojektowana z myślą o edukacji. Została stworzona przez BBC we współpracy z partnerami technologicznymi, aby ułatwić dzieciom i młodzieży naukę podstaw programowania i elektroniki.

Kluczowe cechy micro:bita to:

*   **Prostota:** jest bardzo łatwy w użyciu, nawet dla początkujących. Można go programować wizualnie za pomocą bloków (w edytorze MakeCode) lub w językach tekstowych, takich jak Python i JavaScript.
*   **Wbudowane czujniki:** na płytce znajdują się m.in. akcelerometr (czuły na przechylenie i ruch), kompas, czujnik temperatury oraz czujnik światła.
*   **Wyjścia:** posiada 25 programowalnych diod LED, które mogą wyświetlać tekst, proste obrazki i animacje. Ma również dwa przyciski wejściowe oraz gniazda do podłączenia dodatkowych czujników, silników i innych urządzeń.
*   **Łączność:** najważniejszą funkcją w tym projekcie jest wbudowany moduł Bluetooth, który pozwala na bezprzewodową komunikację z innymi urządzeniami, w tym innymi płytkami micro:bit, smartfonami czy komputerami.

Dzięki tym funkcjom micro:bit jest idealnym narzędziem do tworzenia interaktywnych projektów, od prostych gadżetów po zaawansowane roboty, jak w opisanym przypadku.

## Autorzy projektu

- Sebastian Kurpiewski 
- Damian Kurpiewski - [GitHub](https://github.com/blackbat13) - [Strona osobista](https://blackbat13.github.io/)