# EmoSymphony - muzyka, która czuje to, co Ty

> **Aplikacja, która patrzy na Twoje oblicze i komponuje dla Ciebie muzykę w czasie rzeczywistym.**

---

## Czym jest EmoSymphony?

Wyobraź sobie, że siadasz przed komputerem, a on - zamiast pytać, czego chcesz posłuchać - po prostu **patrzy na Ciebie i wie**. Widzi radość w Twoich oczach, zmęczenie po ciężkim dniu, skupienie podczas pracy. I odpowiada muzyką.

Właśnie tym jest **EmoSymphony**: aplikacją, która w czasie rzeczywistym **rozpoznaje Twoją emocję** poprzez kamerę internetową, a następnie dobiera i odtwarza muzykę idealnie dopasowaną do Twojego nastroju - i do Twojego wieku.

Nie musisz niczego klikać. Nie musisz niczego wybierać. Muzyka pojawia się sama.

---

## Jak to działa?

1. **Kamera patrzy na Ciebie** - aplikacja co chwilę „zagląda" w Twój wyraz twarzy przez kamerę.
2. **Sztuczna inteligencja rozpoznaje emocję** - system analizuje mimikę i określa, czy jesteś szczęśliwy, smutny, zły, zaskoczony, czy może po prostu spokojny.
3. **Dobierana jest muzyka** - na podstawie emocji *i* szacowanego wieku dobierany jest odpowiedni utwór z wcześniej wygenerowanej biblioteki.
4. **Muzyka płynnie się zmienia** - co 15 sekund (nawet jeśli emocja się nie zmieniła) pojawia się nowy utwór z płynnym przejściem, by nie było nudy.

Wszystko dzieje się **lokalnie na Twoim komputerze** - żadne zdjęcia ani dane o Twojej twarzy nie są nigdzie wysyłane.

---

## Co wyróżnia EmoSymphony?

- **Reaguje na emocje** - rozpoznaje radość, smutek, złość, zaskoczenie i neutralny spokój.
- **Dopasowuje muzykę do wieku** - muzyka dla 15-latka brzmi inaczej niż dla 40-latka.
- **Generuje muzykę AI** - biblioteka ścieżek jest tworzona przez model AI (MusicGen od Meta), więc każdy utwór jest unikalny.
- **Działa offline** - po pierwszym uruchomieniu nie potrzebuje internetu; Twoja prywatność jest chroniona.
- **Podgląd na żywo** - w oknie aplikacji widzisz obraz z kamery z nakładkami pokazującymi wykrytą emocję i szacowany wiek.
- **Płynne przejścia** - zmiana ścieżki następuje z 500 ms crossfade, bez żadnych zgrzytów.

---

## Kod źródłowy i pobieranie

Projekt jest open-source. Zapraszamy do zapoznania się z kodem, zgłaszania pomysłów i współtworzenia!

> **Repozytorium GitHub:** [github.com/blackbat13/EmoSymphony](https://github.com/blackbat13/EmoSymphony)

---

## Minimalne wymagania sprzętowe

Aby uruchomić EmoSymphony, Twój komputer powinien spełniać poniższe wymagania:

| Komponent | Minimum |
|---|---|
| **System operacyjny** | Windows 10 / Ubuntu 20.04 / macOS 11+ |
| **Procesor (CPU)** | 4-rdzeniowy, 2.5 GHz (Intel Core i5 / AMD Ryzen 5 lub nowszy) |
| **Pamięć RAM** | 8 GB |
| **Karta graficzna (GPU)** | Opcjonalna, ale zalecana (CUDA) - bez GPU generowanie muzyki trwa dłużej |
| **Miejsce na dysku** | ~5 GB (modele AI ważą ok. 3–4 GB i są pobierane przy pierwszym uruchomieniu) |
| **Kamera internetowa** | Dowolna kamera (wbudowana lub zewnętrzna USB) |
| **Python** | 3.10 lub nowszy |
| **Internet** | Potrzebny tylko przy pierwszym uruchomieniu (pobieranie modeli AI) |

> **Uwaga:** Pierwsze uruchomienie może trwać od kilku do kilkunastu minut - aplikacja pobiera modele AI (~3–4 GB). Kolejne starty są natychmiastowe, bo modele są zapisane lokalnie.

---

## Technologie użyte w projekcie

- **Python** - główny język aplikacji
- **DeepFace** - rozpoznawanie emocji i szacowanie wieku z obrazu twarzy
- **MusicGen (Meta AI)** - generatywny model AI do tworzenia muzyki
- **OpenCV** - przechwytywanie obrazu z kamery i detekcja twarzy
- **Pygame** - odtwarzanie dźwieku z płynnymi przejściami

---

## Chcesz spróbować?

Szczegółowa instrukcja instalacji i uruchomienia dostępna jest w repozytorium GitHub. Projekt działa na Windows, Linux i macOS.

> **[Przejdź do repozytorium →](https://github.com/blackbat13/EmoSymphony)**

---

*EmoSymphony - bo muzyka powinna rozumieć Cię, nie odwrotnie.*
