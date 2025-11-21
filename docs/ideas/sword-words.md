
# Słowa Mieczem: opowieść pisana w biegu

Wcielasz się w rolę Strażnika Słów, a Twoim orężem jest klawiatura. Na ekranie pojawiają się wrogowie – nie potwory, lecz słowa. Szybko i poprawnie wpisz je, by zniszczyć przeciwnika przed dotarciem do Ciebie. To nie jest jednak zwykła gra. Sztuczna inteligencja na żywo generuje słowa, które tworzą spójną, rozwijającą się historię. Im lepiej piszesz, tym bardziej epicka staje się opowieść. Jeśli masz problem, AI dostosowuje słowa, by pomóc Ci odnaleźć rytm. Każda rozgrywka to unikalna, pisana na Twoich oczach opowieść o zwycięstwie, walce i sile słów.

## Pomysły na funkcjonalności

1.  **Dynamiczna narracja i świat:**
    *   **Żyjąca opowieść:** AI nie tylko generuje losowe słowa. Generuje **zdania** lub fragmenty zdań. Gracz, pokonując wrogów, "odkrywa" historię. Na przykład, fala wrogów to słowa: "*kruk* *wzleciał* *nad* *stary* *zamek*". Kolejna fala może kontynuować: "*gdzie* *czekał* *na* *niego* *przeklęty* *rycerz*".
    *   **Typy wrogów:** słowa mogą mieć przypisane "typy" w zależności od ich znaczenia w historii. Słowa kluczowe (np. imiona, miejsca, magiczne przedmioty) mogą być "bossami" – mają więcej "życia" (trzeba wpisać je bezbłędnie) lub pojawiają się rzadziej, ale ich pokonanie daje duży bonus.
    *   **Zmieniające się otoczenie:** tło gry może się zmieniać w zależności od tego, co dzieje się w historii. Jeśli opowieść przenosi się do lasu, tło staje się leśne. Jeśli walka staje się intensywna, na ekranie pojawiają się płomienie lub błyskawice.

2.  **Głębsza adaptacja AI:**
    *   **Analiza stylu pisania:** AI może analizować nie tylko prędkość, ale też rodzaj błędów. Np. jeśli gracz często myli litki `a` i `s`, AI może chwilowo generować słowa bez tych liter, by dać mu "odpocząć", po czym powoli wprowadzać je z powrotem.
    *   **Generowanie tematyczne:** jeśli gracz radzi sobie bardzo dobrze, AI może zacząć generować dłuższe, bardziej skomplikowane słowa lub słowa z obcej, fantastyjnej mowy. Jeśli gracz ma trudności, AI generuje krótsze, bardziej fonetyczne słowa.
    *   **"Pętla" fabularna:** jeśli gracz przegrywa, AI może rozpocząć następną grę od słów: "*lecz* *Strażnik* *powrócił* *by* *dokonać* *rewanżu*", tworząc poczucie ciągłości.

3.  **Rozbudowana mechanika gry:**
    *   **Specjalne umiejętności:** za pokonanie kilku słów z rzędu (combo) gracz może aktywować specjalne umiejętności, np. "Zamień" (zamienia trudne słowo na łatwiejsze), "Spowolnienie Czasu" (słowa poruszają się wolniej) lub "Eksplozja" (niszczy wszystkich słów krótszych niż 4 litery).
    *   **Rodzaje wrogów:** niektóre słowa mogą mieć specjalne właściwości. Słowo na "e" może się rozpadać na dwie mniejsze słowa po trafieniu. Słowo-pytanie może wymagać wpisania go z znakiem zapytania.
    *   **Tryby gry:**
        *   **Tryb historii:** przechodzenie przez spójną, generowaną przez AI opowieść.
        *   **Tryb przetrwania:** niekończąca się fala wrogów o rosnącym poziomie trudności.
        *   **Tryb wyzwania:** AI generuje słowa z określonej kategorii (np. "najdłuższe słowa", "słowa z polskiej literaty").

## Możliwe kierunki realizacji

### Ścieżka 1: "Prosty Trener" (idealna dla początkujących)

*   **Cel:** stworzenie działającej gry z podstawową mechaniką i prostym generatorem słów.
*   **Technologia:**
    *   **Silnik gry:** **Pygame** w Pythonie. Jest prosty i idealny do gier 2D.
    *   **Generowanie słów:** użycie prostego API do dużych modeli językowych (np. Groq, OpenAI) z promptem: "Wygeneruj 20 losowych, prostych słów w języku polskim". Gra pobiera listę i wyświetla je jako wrogów.
    *   **Logika:** prosta detekcja kolizji i sprawdzanie, czy wpisany przez użytkownika tekst pasuje do słowa-wroga.
*   **Wyzwania:** podstawy programowania gier (pętle, zdarzenia), obsługa API, projektowanie prostego interfejsu.

### Ścieżka 2: "Opowieść na Żywo" (dla średniozaawansowanych)

*   **Cel:** stworzenie gry z adaptacyjnym AI i spójną narracją.
*   **Technologia:**
    *   **Silnik gry:** **Godot** lub **Unity**. Dają lepsze narzędzia do zarządzania stanem gry, animacjami i UI.
    *   **Generowanie słów:** bardziej zaawansowane promptowanie. Program wysyła do AI kontekst: "Historia dzieje się w lesie. Gracz radzi sobie dobrze. Wygeneruj kolejne zdanie historii, podzielone na słowa. Słowa powinny być średnio trudne."
    *   **Logika:** implementacja systemu "pamięci" AI, który śledzi wyniki gracza i na tej podstawie modyfikuje kolejne prompty.
*   **Wyzwania:** projektowanie zaawansowanych promptów, zarządzanie stanem gry (punkty, zdrowie, combo), tworzenie płynnych animacji i efektów wizualnych.

### Ścieżka 3: "Żyjący Świat" (dla zaawansowanych)

*   **Cel:** stworzenie w pełni dynamicznej gry, która jest niemal grą narracyjną.
*   **Technologia:**
    *   **Silnik gry:** **Unity** z zaawansowanym systemem UI i animacji.
    *   **AI:** użycie lokalnie działającego modelu językowego (np. przez `Ollama`), co pozwala na bardzo szybką i niemal natychmiastową generację treści. Można też eksperymentować z fine-tuningiem mniejszego modelu do specyficznej stylistyki gier.
    *   **Logika:** system, w którym AI ma dostęp do funkcji gry (np. `zmien_tlo('las')`, `stwórz_bossa('Smok')`). AI nie tylko generuje tekst, ale podejmuje decyzje o przebiegu rozgrywki.
*   **Wyzwania:** bardzo zaawansowane programowanie, integracja z lokalnym AI, projektowanie systemu, który jest zarówno grą, jak i interaktywnym opowiadaczem.

## Praktyczne wskazówki i potrzebne zasoby

### Sprzęt

*   **Komputer:** wystarczy praktycznie dowolny komputer capable of running Pythona lub Godot/Unity. W ścieżce 3 mocna karta graficzna (GPU) będzie potrzebna do lokalnego AI.

### Oprogramowanie i umiejętności

*   **Python:** podstawa w ścieżce 1.
*   **Godot/Unity:** standard w ścieżkach 2 i 3.
*   **Obsługa API:** kluczowa umiejętność do komunikacji z modelami językowymi.
*   **Prompt engineering:** najważniejsza umiejętność w tym projekcie. To sztuka pisania instrukcji dla AI, by generowała pożądaną treść.
*   **Podstawy projektowania gier:** zrozumienie pętli gry, stanów, logiki kolizji i projektowania UI.

### Ważne wskazówki do realizacji

*   **Poczucie płynności jest kluczowe:** najważniejsze jest to, by pisanie na klawiaturze czuło się dobrze. Opóźnienia między wpisaniem litowy a jej pojawieniem się na ekranie (tzw. input lag) muszą być minimalne.
*   **Zacznij od statycznej listy słów:** zanim połączysz grę z AI, stwórz wersję, która używa statycznej listy słów z pliku tekstowego. Dzięki temu przetestujesz i dopracujesz samą mechanikę gry.
*   **Daj graczowi czas:** nie zalewaj gracza słowami od razu. Daj mu chwilę na przeczytanie słowa, zanim zacznie się zbliżać. Dobre tempo to podstawa udanej gry tego typu.
