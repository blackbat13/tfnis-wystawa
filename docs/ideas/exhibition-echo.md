# Echo Wystawy: Twoja osobista opowieść

Otrzymaj swój unikalny chip NFC na wejściu i stań się odkrywcą. Przy każdym projekcie, który Cię zainteresuje, przyłóż chip do czytnika, by zarejestrować swoje "polubienie" lub odpowiedzieć na pytanie: "Co Cię tu zaintrygowało?". Twój chip staje się Twoim cyfrowym notatnikiem, cichym świadkiem Twojej podróży po wystawie. Na końcu, wrzuć go do terminala, a sztuczna inteligencja przeanalizuje Twoje wybory i stworzy dla Ciebie unikalne, spersonalizowane podsumowanie – poetycką refleksję, artystyczny manifest lub zabawną anegdotę opartą na Twojej ścieżce przez wystawę. To nie jest wystawa, którą oglądasz – to wystawa, która ogląda Cię w zamian.

## Pomysły na funkcjonalności

1.  **Głębsza Interakcja z Ekspozycjami:** Zamiast prostego "lajka", każda stacja może oferować bardziej zniuansowane opcje.
    *   **Emocje jako Dane:** Przy ekspozycji można wybrać jedną z kilku emocji, które ona w Tobie wywołała: "Zachwyt", "Zdziwienie", "Zabawę", "Zadumę", "Niesmak". To daje AI o wiele bogatszy materiał do analizy niż sama informacja "byłem tu".
    *   **Pytania Otwarte (z pomocą AI):** Stacja może wyświetlać pytanie: "Jakie słowo przypada Ci na myśl patrząc na ten projekt?". Użytkownik wpisuje słowo. To może być "futurystyczny", "dziwny", "ciepły", "skomplikowany". Małe, lokalne modele AI mogą nawet na bieżąco analizować te słowa, by podpowiadać kolejne projekty.
    *   **Wybory Moralne/Etyczne:** Przy niektórych projektach można zadać dylemat: "Czy wykorzystałbyś tę technologii w swoim życiu? (TAK/NIE/MOŻE)". To buduje profil użytkownika nie tylko jako odbiorcy, ale jako thinkera.

2.  **"Żyjący" Chip NFC i Gamifikacja:**
    *   **Ewolucja Profilu:** Każdy chip może mieć przypisaną awatara lub kształt (np. ameba, krystal, drzewo). Wraz z każdym nowym zeskanowaniem, awatar rośnie, zmienia kolor lub kształt, wizualizując rozwój "doświadczenia" użytkownika. Podsumowanie na końcu to ostateczna, w pełni ukształtowana forma.
    *   **Odblokowywanie Sekretów:** Niektóre, bardziej ukryte stacje mogą wymagać wcześniejszego zebrania określonej liczby "punktów doświadczenia" lub odwiedzenia konkretnych innych projektów, by się aktywować.

3.  **Finalne Podsumowanie jako Dzieło Sztuki:**
    *   **Różne Formy Podsumowania:** AI może wygenerować nie tylko tekst.
        *   **Wizualizacja Danych:** Unikalny "graficzny ślad" – infografika pokazująca mapę emocji, kluczowe słowa i powiązania między wybranymi projektami.
        *   **Spersonalizowana Playlista:** Na podstawie emocji AI generuje playlistę muzyczną idealnie pasującą do nastroju wizyty.
        *   **"Manifest Artystyczny":** AI pisze krótki manifest odzwierciedlający "gust" i wartości użytkownika na podstawie jego wyborów.
    *   **Ways to Take It Home:** Podsumowanie nie musi zniknąć. Użytkownik może je wysłać sobie na e-mail, zeskanować kod QR, aby zapisać obraz, lub nawet wydrukować na specjalnej drukarce termicznej jako pamiątkę.

## Możliwe kierunki realizacji

### Ścieżka 1: "Analogowy Notatnik" (idealna dla początkujących i miłośników DIY)

*   **Cel:** Stworzenie mechanizmu zbierania danych bez skomplikowanego backendu.
*   **Technologia:**
    *   **Chipy NFC:** Zamiast programowalnych, użyj tanich, pasywnych tagów NFC (np. w formie breloków lub kart).
    *   **Stacje:** Każda stacja to tablet lub telefon z aplikacją, która może zapisywać stan (np. w prostym pliku tekstowym lub Google Sheets). Po przyłożeniu tagu, aplikacja zapisuje jego unikalny ID i wybór użytkownika.
    *   **Podsumowanie:** Na końcu wystawy jest jeden komputer z programem, który czyta plik/arkusz i generuje proste podsumowanie typu: "Odwiedziłeś 5 projektów. Najczęściej wybierałeś emocję 'Zdziwienie'. Twoim ulubionym słowem było 'futurystyczny'".
*   **Wyzwania:** Zapewnienie stabilności działania tabletów, synchronizacja danych.

### Ścieżka 2: "Cyfrowy Ślad" (dla średniozaawansowanych)

*   **Cel:** Pełna automatyzacja i dynamiczne generowanie podsumowań.
*   **Technologia:**
    *   **Chipy NFC:** Użycie tagów NTAG215, które można zapisywać.
    *   **Backend:** Prosta aplikacja serwerowa (np. w **Pythonie** z frameworkiem **Flask** lub **Node.js**), która obsługuje bazę danych (np. SQLite lub PostgreSQL). Każda stacja (np. Raspberry Pi z czytnikiem NFC i małym ekranem) komunikuje się z serwerem, wysyłając ID tagu i wybór użytkownika.
    *   **AI:** Podsumowanie generowane przez API dużego modelu językowego (np. OpenAI GPT, Claude) z odpowiednio przygotowanym promptem: "Na podstawie następujących danych o wyborach użytkownika na wystawie, napisz krótką, poetycką refleksję...".
*   **Wyzwania:** Programowanie backendu, obsługa baz danych, integracja z API AI, zarządzanie stanem tagów NFC.

### Ścieżka 3: "Inteligentna Osoba" (dla zaawansowanych)

*   **Cel:** Stworzenie w pełni inteligentnego, kontekstowego systemu.
*   **Technologia:**
    *   **Chipy NFC:** Użycie tagów, które mogą przechowywać więcej danych i być dynamicznie aktualizowane.
    *   **Lokalna AI:** Zamiast zewnętrznego API, użycie lokalnie uruchomionego, mniejszego modelu językowego (np. Llama 3, Mistral) do generowania podsumowań. Daje to pełną kontrolę i prywatność.
    *   **Analiza w Czasie Rzeczywistym:** System nie tylko zbiera dane, ale na bieżąco je analizuje. Jeśli zauważy, że użytkownik wybiera projekty związane z dźwiękiem, może podświetlić mu na mapie wystawy kolejny projekt audio. Podsumowanie jest "uczone" przez całą wizytę.
*   **Wyzwania:** Wymagana moc obliczeniowa (GPU) do lokalnego AI, zaawansowane programowanie, optymalizacja modeli.

## Praktyczne wskazówki i potrzebne zasoby

### Sprzęt

*   **Tagi NFC:** Breloki, karty, naklejki. Kluczowe, by były wytrzymałe i wygodne w użyciu. Potrzebny będzie również czytnik/writer NFC (podłączany przez USB).
*   **Stacje:** Raspberry Pi z ekranem dotykowym i czytnikiem NFC to idealne, tanie i niezawodne rozwiązanie. Alternatywnie, tablety z zewnętrznymi czytnikami NFC (przez USB lub Bluetooth).
*   **Serwer:** Komputer, który będzie działał jako centralny mózg instalacji. W wersji "chmurowej" może to być po prostu serwer VPS.
*   **Terminal Końcowy:** Stacja z większym ekranem, czytnikiem NFC i opcjonalnie drukarką termiczną do wydawania pamiątek.

### Oprogramowanie i umiejętności

*   **Backend:** Python/Flask lub Node.js/Express. Znajomość podstaw baz danych (SQL).
*   **Frontend (dla stacji):** Proste interfejsy webowe (HTML/CSS/JavaScript) działające na Raspberry Pi lub tabletach.
*   **AI/Prompt Engineering:** Umiejętność formułowania promptów dla modeli językowych, by generować pożądane style podsumowań.
*   **Zarządzanie Projektami:** To projekt z wieloma ruchomymi częściami, więc dobra organizacja jest kluczowa.

## Ważne wskazówki do realizacji

*   **Prywatność:** Bądź transparentny. Na początku jasno poinformuj użytkowników, jakie dane są zbierane i jak będą używane. Upewnij się, że dane są anonimowe (tag NFC nie jest powiązany z tożsamością).
*   **Testowanie Przepływu:** Przejdź całą ścieżkę użytkownika od początku do końca. Czy jest intuicyjna? Czy nie ma zbyt długich kolejek przy stacjach? Czy podsumowanie jest warte czekania?
*   **Fallback:** Co się stanie, jeśli ktoś zgubi chip? Miej gotowy plan "awaryjny" – np. możliwość wpisania numeru z tagu ręcznie lub otrzymania podsumowania na podstawie ostatnich 3 zeskanowanych projektów.
