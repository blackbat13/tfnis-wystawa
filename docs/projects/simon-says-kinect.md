# Simon Says Kinect

> **Gra ruchowa z sensorami ruchu Kinect v2**

---

## O Projekcie

**Simon Says Kinect** to innowacyjna, interaktywna gra ruchowa, która łączy tradycyjną grę "Simon Says" z zaawansowaną technologią rozpoznawania ruchów. Gracz musi wykonywać różne pozycje i gesty ciała w czasie rzeczywistym, reagując na polecenia wydawane przez komputer. To doskonała zabawa dla całej rodziny, która jednocześnie aktywizuje fizycznie!

Gra wykorzystuje sensor Kinect dla Windows v2, który śledzi całe ciało gracza i analizuje jego pozy. Komputer wydaje polecenia (np. "podnieś prawą rękę"), a Ty musisz je wykonać w przewidzianym czasie. Im więcej poprawnych odpowiedzi, tym więcej punktów!

### Idealne do:

- Zabawy rodzinnej i z przyjaciółmi
- Imprez i eventów
- Edukacji i nauki o technologii
- Aktywności fizycznej

---

## Główne Cechy

### Interaktywna Rozgrywka

- **Rozpoznawanie pozycji ciała w czasie rzeczywistym** za pomocą sensora Kinect
- Gra automatycznie rozpoznaje 7 różnych pozycji: stanie, klęczenie, ręce do góry, ramiona rozłożone, nogi rozsunięte, ręce za głową, postawa spoczynkowa
- **10 rund** z rosnącym poziomem trudności
- Odliczanie 3 sekund przed grą i 5 sekund na rundę

### Podchwytliwe Polecenia

- 80% poleceń zaczyna się od "Simon says" (Simon mówi) - wtedy musisz wykonać ruch
- W 20% przypadków pojawią się **fałszywe polecenia** bez hasła "Simon says"
- Gracz musi zauważyć podstęp i **nie wykonać** danego ruchu
- To dodaje napięcia i sprawia, że gra staje się większym wyzwaniem

### Skalowana Trudność

- Na początek gra jest łaskawa
- Po każdym błędzie poziom trudności wzrasta
- Polecenie "ręce za głową" pojawia się dopiero po pierwszym błędzie
- Polecenia klęczenia stają się coraz częstsze w miarę postępu
- Idealne wykonanie ruchu utrzymuje grę w łatwym trybie

### Udźwiękowienie

- Głos komputera wydaje polecenia po angielsku (np. "raise your left hand", "kneel on one knee")
- Dźwięk "Simon says" na początek każdej rundy
- Dźwięki potwierdzenia/porażki

### Atrakcyjna Wizualizacja

- Duży tekst polecenia u góry ekranu (złoty dla "Simon says", pomarańczowy dla podchwytliwych poleceń)
- Gigantyczne odliczanie w centrum ekranu (niebieski kolor)
- Duży tekst wyniku na dole ekranu (zielony dla poprawnej odpowiedzi, czerwony dla błędu)
- Wizualizacja szkieletu gracza z pozycjami wszystkich stawów
- Podsumowanie gry z finalnym wynikiem

---

## Minimalne Wymagania Systemowe

### Sprzęt

| Komponent | Wymaganie |
|-----------|-----------|
| **Sensor** | Kinect dla Windows v2 (obowiązkowy) |
| **Procesor** | Intel Core i5 lub równoważny AMD (2.4 GHz) |
| **RAM** | Minimum 4 GB (rekomendowane 8 GB) |
| **Dysk** | 1 GB wolnego miejsca |
| **Ekran** | 1080p lub wyższa rozdzielczość, szeroki format |
| **Oświetlenie** | Wystarczające do pracy sensora (najlepiej 300+ lux) |

### Oprogramowanie

- **System operacyjny**: Windows 10 lub Windows 11 (64-bit)
- **Kinect SDK**: Microsoft Kinect Runtime v2 (ze strony Microsoftu)

### Zalecane Warunki do Gry

- Dystans od sensora: **2-3 metry**
- Jasne oświetlenie pomieszczenia
- Wolna przestrzeń przed sensorem (minimum 2m x 2m)
- Jedna osoba w zasięgu sensora w danym momencie
- Pełna widoczność całego ciała na ekranie sensora

---

## Szybki Start

### Proste Uruchomienie (Wersja .EXE)

1. Pobierz plik **SimonSaysKinect.exe** z sekcji releases na stronie projektu: [https://github.com/blackbat13/simon_says_kinect](https://github.com/blackbat13/simon_says_kinect)
2. Uruchom dwukrotnie klikając
3. Gotowe! Gra automatycznie wykryje sensor Kinect i zacznie działać. Upewnij się, że masz zainstalowany Kinect Runtime SDK.

---

## Jak Grać?

### Przygotowanie

1. Postaw się prosto przed sensorem Kinect
2. Upewnij się, że całe Twoje ciało jest widoczne na ekranie
3. Sprawdź oświetlenie - powinno być jasne i równomiernie rozłożone

### Startowanie Gry

- Podnies jedną rękę i przytrzymaj pozycję przez kilka sekund
- Gdy zobaczysz że rysunek gracza zmieni kolor, gra się rozpocznie
- Odbędzie się 3-sekundowe odliczanie

### Wykonywanie Ruchów

1. Słuchaj polecenia wydawanego przez głos komputera
2. Zwróć uwagę na tekst na ekranie:
   - **Złoty tekst** = Prawidłowy rozkaz ("Simon mówi")
   - **Pomarańczowy tekst** = Podstęp! ("Simon nie mówi")
3. Wykonaj ruch zgodnie z poleceniem (lub zostań nieruchomy w przypadku podstępu)
4. Masz 5 sekund na wykonanie każdego ruchu
5. Gra poda Ci wynik (zielony = dobrze, czerwony = źle)

### Cel Gry

Przejdź wszystkie 10 rund z jak największą liczbą poprawnych odpowiedzi. Im mniej błędów, tym lepiej grasz!

---

## Technologia

Projekt wykorzystuje:

- **Python 3.7+** - język programowania
- **Kinect SDK v2** - biblioteka do obsługi sensora
- **Pygame** - silnik grafiki
- **OpenCV** - przetwarzanie obrazu
- **NumPy** - obliczenia liczbowe
- **Comtypes** - interfejs COM do Windows

---

## Link do projektu

- **Projekt na GitHub**: [https://github.com/blackbat13/simon_says_kinect](https://github.com/blackbat13/simon_says_kinect)

---

*Simon Says Kinect - gra, która zmienia sposób zabawy i uczenia się technologii!*
