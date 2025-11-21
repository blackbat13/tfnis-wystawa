# Przestrzeń Transformacji: kamera jako płótno

Wyobraź sobie, że świat widziany przez obiektyw kamery to nie tylko pasywny obraz, ale dynamiczna, płynna substancja, którą można kształtować, wyginać i malować w czasie rzeczywistym. Nasz projekt to cyfrowa pracownia, gdzie zwykły strumień wideo staje się polem do eksperymentów wizualnych, a Ty jesteś artystą, który jednym kliknięciem zmienia rzeczywistość.

To nie jest zwykła aplikacja do nakładania filtrów. To interaktywne lustro, które odbija nie tylko to, co jest przed nim, ale także to, co może być. Zamiast statycznych nakładek, oferujemy żywe, pulsujące efekty, które reagują na ruch, geometrię i Twoją kreatywność. Zanurz się w świecie, gdzie Twoja twarz może stać się częścią kalejdoskopu, a otoczenie – płótnem dla abstrakcyjnych fal i zniekształceń.

**Doświadczenie:**

- **Zabawa formą:** Zmień swój wizerunek za pomocą efektu "Rybie Oko", który rozszerza perspektywę, albo "Duża Głowa", która nadaje karykaturalny, humorystyczny wygląd.
- **Abstrakcja w ruchu:** Przekształć swoje otoczenie w falującą materię ("Fale") lub w siatkę kropkową ("Kropki"), która dekonstruuje obraz do jego fundamentalnych elementów.
- **Magia symetrii:** Efekt "Symetria" tworzy hipnotyzujące, lustrzane odbicia, idealne do medytacyjnych wizualizacji.
- **Sztuka detekcji:** Nasza aplikacja potrafi nie tylko modyfikować obraz, ale też go rozumieć. Zaawansowane algorytmy wykrywają twarze, pozwalając na zabawną funkcję "Swap Faces", która płynnie zamienia rysunki dwóch osób w kadrze.
- **Nostalgia za pikselami:** Przenieś się do ery 8-bitowych gier wideo z efektem "Gra retro", który upraszcza kolory i rozdzielczość, tworząc unikalny, stylizowany wygląd.

Interfejs jest prosty i intuicyjny – panel przycisków pozwala natychmiast przełączać się między efektami, a dyskretny suwak daje Ci kontrolę nad intensywnością wybranych modyfikacji. To Ty dyktujesz warunki, a technologia jest tylko narzędziem w Twoich rękach.

## Szczegóły techniczne

Projekt jest zrealizowany w języku Python i opiera się na synergii kilku potężnych bibliotek, co pozwala na przetwarzanie wideo w czasie rzeczywistym z minimalnym opóźnieniem.

### Główne komponenty technologiczne

1. **Przechwytywanie i wyświetlanie wideo:**
    - **OpenCV (`cv2`):** Serce aplikacji. Odpowiada za komunikację z kamerą (`cv2.VideoCapture`), przechwytywanie kolejnych klatek i fundamentalne operacje na obrazie, takie jak zmiana rozmiaru, konwersja przestrzeni kolorów (BGR na RGB dla wyświetlenia w interfejsie) oraz kluczowa funkcja `cv2.remap`, która jest wykorzystywana do większości efektów geometrycznych.
    - **Tkinter i Pillow (`tkinter`, `PIL`):** Odpowiadają za stworzenie graficznego interfejsu użytkownika (GUI). Tkinter tworzy okno, przyciski i suwak, a Pillow (PIL) konwertuje obrazy z formatu NumPy (używanego przez OpenCV) na format, który można wyświetlić w widżecie `Label` w Tkinterze.

2. **Realizacja Efektów Wizualnych:**
    - **Efekty oparte na mapowaniu (`cv2.remap`):** To najbardziej wydajna grupa efektów. Zamiast modyfikować każdy piksel indywidualnie w pętli, co jest powolne, pre-generujemy dwie mapy (`map_x`, `map_y`) dla całego obrazu. Każda mapa mówi, skąd w obrazie źródłowym wziąć piksel dla danej pozycji w obrazie docelowym. Tak działają: "Rybie Oko", "Fale" oraz wszystkie zniekształcenia ("Krzywe zwierciadło", "Duża głowa", "Klepsydra").
    - **Wirtualna Kamera (`vcam`, `meshGen`):** Efekty zniekształcające wykorzystują genialną bibliotekę `vcam`. Pozwala ona zdefiniować wirtualną siatkę 3D (mesh) i nadać jej kształt za pomocą funkcji matematycznych (np. funkcji Gaussa dla efektu "bubla"). Następnie ta wypukła/wklęsła siatka jest rzutowana na płaszczyznę 2D, a wynikowe mapy pikseli są używane przez `cv2.remap`. To podejście pozwala na tworzenie płynnych, organicznych zniekształceń.
    - **Efekty oparte na pętlach i manipulacji pikselami:** Efekty takie jak "Kropki" czy "Piksele" działają poprzez iterację po obrazie. "Kropki" najpierw pomniejsza obraz, a następnie rysuje kropki w kolorach z pomniejszonej wersji. "Piksele" działa na podobnej zasadzie, ale zamiast kropel wstawia powiększone kwadraty pikseli.
    - **Detekcja i manipulacja twarzy:**
        - **Dlib:** To najnowocześniejsza biblioteka do rozpoznawania twarzy i jej 68 kluczowych punktów (landmarków). Jest wykorzystywana w funkcji `swap_faces_effect` do precyzyjnego zlokalizowania oczu, nosa i ust, co pozwala na inteligentne wyrównanie i wymianę twarzy za pomocą zaawansowanej techniki `cv2.seamlessClone`, która zapewnia naturalne przejścia na krawędziach.
        - **OpenCV Haar Cascades:** Dostępna jest również prostsza, szybsza, ale mniej precyzyjna metoda detekcji twarzy za pomocą klasyfikatorów Haar, zaimplementowana w funkcji `simple_face_swap`.

3. **Architektura i Wydajność:**
    - **Pre-kalkulacja:** Mapy dla efektów geometrycznych (`distortion1`, `fish_eye`, `waves` itp.) są generowane tylko raz podczas uruchamiania programu. To kluczowe dla utrzymania płynności, ponieważ w głównej pętli (`update_frame`) wykonywana jest już tylko szybka operacja `remap`.
    - **Główna pętla (`update_frame`):** Funkcja ta, wywoływana co 10 milisekund, stanowi pętlę aplikacji. Przechwytuje klatkę, stosuje wybrany efekt, konwertuje format i wyświetla wynik w oknie Tkinter. Taka struktura zapewnia niemal płynne wideo, które jest postrzegane jako ruchome w czasie rzeczywistym.
    - **Interaktywność:** Suwak jest dynamicznie powiązany z parametrami wybranych efektów. Na przykład, w przypadku "Rybiego Oka", zmiana suwaka natychmiast przelicza wartość `strength` i generuje nowe mapy zniekształcenia, dając użytkownikowi natychmiastową informację zwrotną.

### Link do źródeł

[Zobacz kod źródłowy na GitHub](https://github.com/blackbat13/py-camera-exp/blob/main/exp2.py)

## Autor projektu

Damian Kurpiewski - [GitHub](https://github.com/blackbat13) - [Strona osobista](https://blackbat13.github.io/)
