
# Security Policy

## W skrócie

Znalazłeś lukę? Napisz do nas prywatnie, nie rób tego publicznie.
Daj nam chwilę na naprawę, a potem chętnie podziękujemy.

## Obsługiwane wersje

Poprawki bezpieczeństwa wydajemy wyłącznie dla **najnowszej wersji**
danego pluginu, API lub usługi. Starsze wersje nie są wspierane —
jeśli używasz starej, zaktualizuj ją przed zgłoszeniem problemu.

## Jak zgłosić lukę

**Nie zgłaszaj luk przez publiczne issues, pull requesty ani Discorda.**

Zamiast tego użyj jednej z dwóch dróg:

1. **GitHub Private Vulnerability Reporting** — w zakładce „Security”
   repozytorium kliknij „Report a vulnerability”. To najlepsza opcja.
2. **E-mail** — napisz na adres poniżej, jeśli GitHub z jakiegoś powodu
   nie działa.

> **Kontakt:** [security@mcdtm.pl](mailto:security@mcdtm.pl)

W zgłoszeniu podaj:

- opis luki,
- kroki potrzebne do jej odtworzenia,
- potencjalny wpływ (co da się zrobić),
- propozycję poprawki, jeśli ją masz.

Odpowiemy w ciągu **48 godzin** i poinformujemy, co dalej.

## Co uznajemy za lukę

- Sposoby na obejście uprawnień (np. zdobycie rangi bez zakupu).
- Wyciek danych graczy, adresów IP, e-maili.
- Dostęp do sekretów, tokenów lub kluczy API.
- Błędy w kodzie, które pozwalają na zdalne wykonanie kodu (RCE),
  wstrzyknięcie SQL (SQLi) lub cross-site scripting (XSS).
- Luki w zabezpieczeniach backendu i infrastruktury.

**Czego nie uznajemy za lukę:**

- Problemy, które wynikają z użycia starej, niewspieranej wersji.
- Błędy kosmetyczne, literówki, brakujące tłumaczenia.
- Działanie zgodne z dokumentacją, które po prostu ci się nie podoba.
- Luki w zależnościach (dependencies) — zgłoś je bezpośrednio autorom
  tych bibliotek, chyba że nasz kod w konkretny sposób je wykorzystuje.

## Co się stanie po zgłoszeniu

1. **Potwierdzenie** — odpowiemy w ciągu 48 godzin i przyjmiemy zgłoszenie.
2. **Analiza** — ocenimy wagę i wpływ luki.
3. **Poprawka** — opracujemy i przetestujemy rozwiązanie.
4. **Wydanie** — opublikujemy aktualizację z poprawką.
5. **Ujawnienie** — dopiero po wydaniu poprawki publicznie podziękujemy
   zgłaszającemu (jeśli wyrazi zgodę).

Prosimy nie ujawniać luki publicznie przed wydaniem poprawki.

## Aktualizacje bezpieczeństwa

Poprawki bezpieczeństwa wydajemy jako nowe wersje pluginów, API i usług.
Informujemy o nich przez GitHub Releases oraz na naszym Discordzie.
