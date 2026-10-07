
# Contributing

## W skrócie

Chcesz coś dodać, naprawić albo zgłosić? Super. Przeczytaj poniższe zasady,
żebyśmy wszyscy mieli łatwiej. Jeśli coś jest niejasne — pytaj, nie zgaduj.

## Zanim zaczniesz

- **Poznaj projekt** — obejrzyj istniejące pliki i sprawdź, jak wygląda styl
  w danym repozytorium. Każde repo może mieć inne konwencje.
- **Sprawdź issues** — może ktoś już pracuje nad tym samym.
- **Duże zmiany najpierw omów** — nowa funkcja, refaktor, zmiana API? Otwórz
  issue albo napisz na Discordzie, zanim poświęcisz czas na kod. Chcemy uniknąć
  sytuacji, w której ktoś pisze 500 linii, a potem się okazuje, że to nie pasuje.
- **Małe poprawki** — literówki, błędy w dokumentacji, drobne bugi — śmiało,
  możesz od razu otworzyć pull request.

## Zgłaszanie błędów

Bug report to też wkład w projekt. Żeby był użyteczny, podaj:

- **tytuł** — krótki i opisowy, np. „NullPointerException przy pustej konfiguracji”,
- **co się stało** i czego się spodziewałeś,
- **kroki do odtworzenia** — numerowana lista,
- **środowisko** — system operacyjny, wersja Javy, wersja serwera Minecrafta,
- **logi lub stack trace** — bez tego ciężko cokolwiek zdziałać.

Przed zgłoszeniem sprawdź, czy problem nie został już opisany i czy używasz
najnowszej wersji z głównej gałęzi.

Błędy bezpieczeństwa zgłaszaj przez [SECURITY.md](SECURITY.md), nie przez
publiczne issues.

## Proponowanie funkcji

Opisz **problem** (co chcesz osiągnąć i po co), **propozycję** (jak miałoby
to działać), **alternatywy** (co jeszcze rozważałeś) i **kontekst** (przykłady,
linki do podobnych rozwiązań).

Nie każda propozycja zostanie zrealizowana. To nie znaczy, że jest zła —
czasem nie pasuje do zakresu projektu albo wymaga za dużo pracy. Jeśli nie masz
pewności, otwórz dyskusję w GitHub Discussions.

## Środowisko deweloperskie

Wymagania różnią się między projektami. **Sprawdź `README.md` oraz plik build**
danego repozytorium (`build.gradle.kts`, `pom.xml`, `pyproject.toml` — zależnie
od technologii). Tam znajdziesz wymaganą wersję środowiska, sposób budowania
i dodatkowe zależności.

Szybki start dla większości projektów w Javie z Gradle:

    git clone https://github.com/mcdtm/nazwa-projektu.git
    cd nazwa-projektu
    ./gradlew build

Dla Mavena zamiast `./gradlew` użyj `./mvnw`.

## Nazwy gałęzi

| Typ | Format | Przykład |
|-----|--------|----------|
| Nowa funkcja | `feature/krotki-opis` | `feature/command-handler` |
| Poprawka błędu | `fix/krotki-opis` | `fix/null-config-crash` |
| Refaktoryzacja | `refactor/krotki-opis` | `refactor/service-layer` |
| Dokumentacja | `docs/krotki-opis` | `docs/installation-guide` |
| Testy | `test/krotki-opis` | `test/edge-cases` |

## Proces Pull Request

1. **Fork i klon** — zrób fork repozytorium przez GitHub i sklonuj go lokalnie.
2. **Gałąź** — utwórz gałąź według schematu powyżej.
3. **Zmiany** — wprowadź zmiany, podążając za stylem istniejącym w projekcie.
4. **Testy** — uruchom `./gradlew check` (lub odpowiednik dla Mavena).
5. **Commit** — opisany w sekcji poniżej.
6. **Push i Pull Request** — wyślij zmiany i otwórz pull request.
7. **Code review** — reaguj na uwagi, wprowadzaj poprawki.
8. **Po merge** — zaktualizuj lokalne `main` i usuń gałąź.

W opisie pull requesta zawrzyj **co** zmieniasz, **dlaczego**, **jak**
przetestować oraz odwołania do issues (np. `Closes #42`).

**Jeden pull request = jedna sprawa.** Nie łącz refaktoru, nowej funkcji
i poprawki buga w jednym pull requeście — ciężko się to recenzuje i jeszcze
ciężej wycofuje, jeśli coś pójdzie nie tak.

Recenzent może poprosić o zmiany. To normalne, nie traktuj tego osobiście.

## Standardy kodu

**Najważniejsza zasada: nie wprowadzaj własnego stylu.** Każde repozytorium
może mieć inny styl, inne narzędzia i inne konwencje. Twoim zadaniem jest je
**odtworzyć i podążać za nimi**, a nie narzucać swoje.

Zanim napiszesz pierwszą linię kodu, sprawdź `README.md`, pliki konfiguracyjne
(`.editorconfig`, `checkstyle.xml`, `build.gradle.kts`), istniejący kod oraz
sposób, w jaki recenzowane są inne pull requesty. To powie ci więcej niż
jakikolwiek uniwersalny przewodnik.

Jeśli projekt nie ma żadnej konfiguracji ani wyraźnej konwencji, kieruj się
tymi ogólnymi zasadami:

- **Formatowanie** — 2 spacje, UTF-8, LF, maksymalnie 120 znaków w linii.
- **Nazewnictwo** — klasy `PascalCase`, metody i zmienne `camelCase`,
  stałe `UPPER_SNAKE_CASE`, pakiety `lowercase`.
- **Importy** — bez gwiazdek, nieużywane usuwaj.
- **Wyjątki** — nie łap `Exception` bez powodu, bez pustych `catch`,
  zawsze z kontekstem w komunikacie.
- **Komentarze** — komentuj **dlaczego**, nie **co**. Javadoc dla publicznych API.

To punkt wyjścia, nie zamiennik istniejącego stylu. Jeśli projekt ma własny —
**on ma priorytet**.

**Czego nie robić:**

- Nie reformatuj plików, których nie dotyka Twoja zmiana — robi się z tego
  ogromny diff, który utrudnia recenzję.
- Nie mieszaj kilku stylów w jednym pliku.
- Nie zmieniaj konfiguracji formatowania bez wcześniejszej dyskusji w issue.
- Nie wyłączaj linterów ani nie dodawaj wyjątków, żeby Twój kod przeszedł —
  napraw kod. Jeśli uważasz, że reguła jest błędna, otwórz issue.

**Język w kodzie:** kod, nazwy zmiennych, komentarze i commit messages po
angielsku. Issues, pull requesty i dyskusje — po polsku lub po angielsku,
jak wolisz.

## Konwencje commitów

Używamy [Conventional Commits](https://www.conventionalcommits.org/).

    <typ>(<zakres>): <krótki opis>

    <opcjonalny dłuższy opis>

    <opcjonalne stopki>

| Typ | Opis |
|-----|------|
| `feat` | Nowa funkcja |
| `fix` | Poprawka błędu |
| `docs` | Zmiany w dokumentacji |
| `style` | Formatowanie, brak zmian w kodzie |
| `refactor` | Refaktoryzacja bez zmiany zachowania |
| `perf` | Poprawa wydajności |
| `test` | Dodanie lub poprawa testów |
| `build` | Zmiany w systemie budowania i zależnościach |
| `ci` | Zmiany w CI/CD |
| `chore` | Pozostałe zadania |
| `revert` | Cofnięcie wcześniejszego commita |

Przykłady:

    feat(commands): dodaj obsługę komend z argumentami
    fix(config): napraw NullPointerException przy pustym pliku
    docs(readme): zaktualizuj instrukcję instalacji

Zmiana łamiąca kompatybilność? Dodaj `!` po typie i stopkę `BREAKING CHANGE`:

    feat(api)!: zmień sygnaturę metody execute

    BREAKING CHANGE: metoda execute przyjmuje teraz dwa argumenty zamiast jednego.

> **Uwaga:** niektóre repozytoria mogą mieć własne konwencje commitów. Sprawdź
> `README.md` lub historię commitów w danym projekcie — jeśli są tam inne
> zasady, one mają priorytet.

## Testy

- **Testy jednostkowe** — w `src/test/java`, używaj JUnit 5.
- **Nazwy metod** — opisowe, np. `shouldReturnNullWhenInputIsEmpty`.
- **Pokrycie** — dąż do rozsądnego pokrycia dla nowego kodu. Nie gonimy za
  liczbami, ale brak testów dla nowej logiki to zwykle problem.
- **Testy integracyjne** — jeśli projekt je ma, uruchom je przed wysłaniem
  pull requesta.

    ./gradlew test
    ./gradlew test --tests "com.example.MyClassTest"

Dla Mavena odpowiednik to `./mvnw test`. Szczegóły zawsze w `README.md`.

## Dokumentacja

- **Javadoc** — pisz dla wszystkich publicznych klas i metod.
- **Komentarze** — tylko dla nietrywialnej logiki.
- **CHANGELOG.md** — jeśli projekt go prowadzi, dopisz wpis przy nowej wersji.
- **README.md** — aktualizuj przy zmianach w publicznym API.

## Sekrety

Przypomnienie, bo to najczęstszy błąd przy pull requestach: **nigdy nie
wrzucaj do repozytorium haseł, tokenów, kluczy API ani danych z `mcdtm.pl`**.
Cały nasz kod jest otwartoźródłowy poza sekretami. Jeśli przez pomyłkę coś
takiego trafi do commita, od razu napisz do maintainera — usunięcie z historii
Git jest trudniejsze niż się wydaje, a klucz trzeba unieważnić.

## Licencja

Wysyłając pull request, zgadzasz się, że Twoja zmiana będzie objęta licencją
projektu, do którego ją wysyłasz. Sprawdź plik `LICENSE` w danym repozytorium.

## Kodeks postępowania

Obowiązuje nasz [Code of Conduct](CODE_OF_CONDUCT.md). Przeczytaj go, zanim
zaczniesz kontrybuować — jest krótki.

## Pytania

- **GitHub Issues** — problemy i propozycje.
- **GitHub Discussions** — pytania, dyskusje, pomoc.
- **Discord** — jeśli link jest w `README.md` danego projektu.
- **E-mail** — sprawy poufne (adres w profilu maintainera).
