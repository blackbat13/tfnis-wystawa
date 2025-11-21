# Nieskończona opowieść: gra, która pisze się na Twoich oczach

Wejdź do świata, który nie istniał przed Twoim przybyciem. To klasyczna gra tekstowa, gdzie sterujesz postacią za pomocą prostych poleceń (`idź na północ`, `weź miecz`, `porozmawiaj z czarodziejem`). Ale tu każda komnata, każdy napotkany nieznajomy i każdy przedmiot jest generowany na żywo przez sztuczną inteligencję. Nie ma dwóch takich samych przygód. Świat jest płynny, nieprzewidywalny i nieograniczony, a Ty jesteś jedyną stałą w tej dynamicznej, cyfrowej opowieści. Każda decyzja prowadzi do zupełnie nowego, unikalnego rozdziału.

## Pomysły na funkcjonalności

1.  **Pamięć i spójność świata:** to największe wyzwanie i jednocześnie największa szansa.
    *   **"Pamięć" AI:** zamiast każde polecenie wysyłać do AI w oderwaniu od kontekstu, twój program musi budować i przekazywać AI "pamięć" stanu gry. Prompt do AI mógłby wyglądać tak: "Jesteś w lochu. Gracz jest w [opis aktualnej lokalizacji]. Ma przy sobie [przedmioty w ekwipunku]. Ostatnio rozmawiał z [postać], która mu powiedziała [kluczowa informacja]. Gracz właśnie napisał '[polecenie]'. Opisz, co się stało, biorąc pod uwagę cały ten kontekst."
    *   **Dynamiczne zmiany w świecie:** AI może nie tylko opisywać, ale też zmieniać stan świata. Jeśli gracz podłoży ogień w bibliotece, AI może zdecydować, że "dym utrudnia widoczność" i przy kolejnym wejściu do pomieszczenia dodać do opisu elementy związane z pożarem. Świat staje się żywy.

2.  **Głębsza interakcja z postaciami:**
    *   **Unikalne osobowości:** każda postać NPC może mieć swój unikalny "prompt systemowy" dla AI. Na przykład: "Jesteś krasnoludem-kowalem. Jesteś zrzędliwy, ale uczciwy. Nie lubisz magów. Odpowiadaj krótko i zbywczo, chyba że gracz mówi o broni. Jeśli gracz zaoferuje ci złoto, staniesz się bardziej rozmowny."
    *   **Dialogi generowane na żywo:** zamiast predefiniowanych drzewek dialogowych, gracz może rozmawiać z postaciami używając własnych słów (`powiedz czarodziejowi, że szukam magicznego miecza`), a AI, wcielając się w postać, wygeneruje unikalną odpowiedź.

3.  **Proceduralne zadania i zagadki:**
    *   **Dynamiczne Questy:** AI może generować zadania w locie. Na przykład, gdy gracz wejdzie do wioski, AI może zdecydować: "Wioska jest nękana przez gobliny. Wieśniak prosi o pomoc. Zadanie: zabij 5 goblinów i przynieś ich głowy". To sprawia, że świat jest pełen celów.
    *   **Zagadki logiczne:** AI może tworzyć zagadki, których rozwiązanie nie jest stałe. Na przykład: "Na drzwiach jest napis: 'Odpowiedź na moje pytanie to pierwsza litera imienia króla, który zbudował ten zamek'". Informację o królu gracz musi znaleźć gdzieś indziej w świecie, a AI będzie "pamiętać", jaką odpowiedź uznał za poprawną.

## Możliwe kierunki realizacji

### Ścieżka 1: "Prosta Eksploracja" (idealna dla początkujących)

*   **Cel:** stworzenie działającej gry z dynamicznie generowanymi opisami lokacji.
*   **Technologia:**
    *   **Silnik gry:** **`adventurelib`** w Pythonie. Jest prosty i idealny do nauki.
    *   **AI:** wykorzystanie prostego API do dużych modeli językowych (np. OpenAI, Groq, Anthropic).
    *   **Logika:** program wysyła do AI krótki prompt: "Opisz mroczną jaskinię w stylu fantasy". AI zwraca opis, który jest wyświetlany graczowi. Polecenia gracza (`idź na północ`) zmieniają tylko "aktualną lokację", a nowy prompt jest generowany dla nowej lokacji.
*   **Wyzwania:** obsługa API, nauka podstaw `adventurelib`, projektowanie prostych poleceń.

### Ścieżka 2: "Spójna Opowieść" (dla średniozaawansowanych)

*   **Cel:** stworzenie gry, w której AI "pamięta" stan świata i postaci.
*   **Technologia:**
    *   **Silnik gry:** wciąż `adventurelib`, ale z bardziej rozbudowaną logiką zarządzania stanem gry (stan gracza, stan świata, historia interakcji).
    *   **AI:** użycie modeli z większym oknem kontekstu (context window) lub implementacja prostego systemu "pamięci" (np. podsumowywanie ostatnich wydarzeń i dodawanie go do każdego nowego promptu).
    *   **Logika:** program musi składać coraz bardziej złożone prompty, które zawierają historię, ekwipunek i aktualne cele gracza.
*   **Wyzwania:** zarządzanie stanem gry, projektowanie efektywnych promptów, unikanie "halucynacji" AI (gdy AI zapomina kluczowych faktów).

### Ścieżka 3: "Żyjący Organizm" (dla zaawansowanych)

*   **Cel:** stworzenie w pełni dynamicznego świata, który reaguje na gracza i ewoluuje.
*   **Technologia:**
    *   **Silnik Gry:** własny silnik napisany w Pythonie lub użycie bardziej zaawansowanych frameworków, które dadzą większą kontrolę.
    *   **AI:** integracja z lokalnie działającymi modelami (np. przez `Ollama`), co daje pełną kontrolę i prywatność. Można też eksperymentować z fine-tuningiem mniejszych modeli do specyficznych zadań (np. model do generowania dialogów, model do generowania opisów).
    *   **Logika:** system, w którym AI ma dostęp do funkcji, które mogą zmieniać stan świata (np. `dodaj_przedmiot_do_lokalizacji()`, `zmień_nastroj_postaci()`). AI nie tylko opisuje, ale *działa* w świecie.
*   **Wyzwania:** bardzo zaawansowane programowanie, zarządzanie złożonością, optymalizacja wydajności i kosztów (zwłaszcza przy API).

### Praktyczne wskazówki i potrzebne zasoby

### Sprzęt

*   **Komputer:** wystarczy praktycznie dowolny komputer z zainstalowanym językiem Python. W przypadku ścieżki 3, mocna karta graficzna (GPU) będzie potrzebna do lokalnego uruchamiania modeli AI.

### Oprogramowanie i umiejętności

*   **Python:** hjęzyk absolutnie kluczowy dla tego projektu.
*   **Biblioteka `adventurelib`:** świetny punkt startowy. Uprości tworzenie parsera poleceń.
*   **Obsługa API:** umiejętność wysyłania zapytań HTTP do API modeli językowych.
*   **Prompt engineering:** to najważniejsza "umiejętność" w tym projekcie. Sztuka pisania poleceń dla AI, by uzyskać pożądane rezultaty.
*   **Struktury danych:** podstawowa znajomość słowników, list i klas w Pythonie do przechowywania stanu gry.

### Ważne wskazówki do realizacji

*   **Zacznij od prostego:** nie próbuj od razu budować żyjącego świata. Zbuduj najpierw jedną lokację, jedną postać i proste polecenia. Gdy to będzie działać, dodawaj kolejne warstwy złożoności.
*   **Kontroluj AI:** AI jest kreatywne, ale też nieprzewidywalne. Daj mu jasne ramy. Prompt "Jesteś mistrzem gry. Opisz to, co widzi gracz, w max 3 zdaniach" jest lepszy niż "Opisz lokalizację".
*   **Bądź gotowy na niespodzianki:** AI wymyśli rzeczy, których się nie spodziewałeś. To część uroku! Czasem te "błędy" i "halucynacje" prowadzą do najbardziej kreatywnych i zabawnych momentów w grze.
