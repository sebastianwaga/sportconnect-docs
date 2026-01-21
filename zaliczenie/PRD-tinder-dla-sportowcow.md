# PRD: Aplikacja SportConnect – Platforma do Umawiania Wspólnych Treningów
**Autor:** Sebastian 
**Data:** 2026-01-05  
**Status:** Zatwierdzony  

---

## 1. Podsumowanie

SportConnect to aplikacja umożliwiająca użytkownikom znajdowanie partnerów treningowych w swojej okolicy na podstawie wspólnych sportów, dystansów, dostępności oraz lokalizacji.  
Obecnie osoby chcące trenować wspólnie korzystają z chaotycznych grup na Facebooku lub komunikatorów, co jest nieskuteczne i frustrujące.  
Celem projektu jest stworzenie **prostej, szybkiej i społecznościowej platformy**, która pozwoli użytkownikom umawiać się na wspólne aktywności sportowe.

---

## 2. Opis Problemu

### Jaki problem rozwiązujemy?

- Brak centralnego miejsca do znajdowania partnerów treningowych.  
- Brak możliwości filtrowania po dystansie, poziomie czy dostępności.  
- Trudność w znalezieniu kogoś „tu i teraz”.  
- Osoby początkujące lub starsze boją się trenować same.  
- Grupy na Facebooku są chaotyczne i nieaktualne.

SportConnect rozwiązuje te problemy, oferując **dedykowaną platformę do łączenia ludzi przez sport**.

---

### Dla kogo jest ten produkt?

**Michał – zapracowany sportowiec amator**  
Chce trenować, kiedy ma wolne okienko, i szybko znaleźć kogoś dostępnego w tym samym czasie.

**Karolina – entuzjastka fitness i social media**  
Chce poznawać ludzi, trenować w grupie i dzielić się aktywnościami.

**Zofia – seniorka aktywna fizycznie**  
Chce czuć się bezpiecznie i trenować z kimś, kto ją poprowadzi.

---

## 3. Cele i Mierniki Sukcesu

### Cele projektu

- Ułatwić użytkownikom znajdowanie partnerów treningowych.  
- Zwiększyć liczbę wspólnych aktywności sportowych.  
- Zbudować społeczność lokalnych sportowców.  
- Zapewnić prosty i intuicyjny interfejs dla osób w każdym wieku.  
- Umożliwić szybkie umawianie treningów „tu i teraz”.

---

### Mierniki sukcesu

- **Match rate:** min. 70% użytkowników znajdzie partnera w pierwszym tygodniu.  
- **Aktywność użytkowników:** min. 50% aktywnych użytkowników tygodniowo.  
- **Czas znalezienia partnera:** średnio poniżej 5 minut.  
- **CSAT:** min. 4.5/5.  
- **Retencja 30-dniowa:** min. 40%.

---

## 4. Wymagania i Zakres

### Kluczowe historyjki użytkownika

- **US-001:** Logowanie przez e-mail, Facebook i Strava.  
- **US-003:** Dodawanie sportów i ustawianie typowego dystansu.  
- **US-006:** Ustawianie lokalizacji i promienia wyszukiwania.  
- **US-008:** Wyszukiwanie partnerów treningowych po sporcie, dystansie i dostępności.  
- **US-009:** System dopasowań (match).  
- **US-007:** Status „trenuję teraz”.  
- **US-010:** Blokowanie użytkowników przez administratora.

---

### Zakres projektu

#### In Scope

- Logowanie przez e-mail, Facebook i Strava.  
- Edycja profilu użytkownika.  
- Dodawanie i usuwanie sportów.  
- Ustawianie typowego dystansu.  
- Ustawianie lokalizacji i promienia wyszukiwania.  
- Wyszukiwanie użytkowników po sportach i dostępności.  
- System dopasowań (match).  
- Status „trenuję teraz”.  
- Panel administratora (blokowanie użytkowników).  
- Cache dla sportów i sportów użytkownika.

#### Out of Scope

- Czat w czasie rzeczywistym.  
- System wydarzeń sportowych.  
- Integracja z Garmin/Polar.  
- Zaawansowane statystyki treningowe.  
- System rankingów i odznak.

---

## 5. Doświadczenie Użytkownika (UX)

### Przepływ użytkownika – znalezienie partnera treningowego

1. Logowanie przez Facebook/Strava.  
2. Uzupełnienie profilu (sporty, dystanse, opis).  
3. Ustawienie lokalizacji i promienia wyszukiwania.  
4. Wybór sportu.  
5. Filtrowanie użytkowników po dostępności i dystansie.  
6. Otrzymanie listy dopasowanych osób.  
7. Kontakt poza aplikacją (MVP).

---

### Kluczowe zasady projektowe

- **Prostota:** minimalna liczba kroków.  
- **Przejrzystość:** duże przyciski, czytelne listy.  
- **Dostępność:** przyjazne dla osób starszych.  
- **Szybkość:** natychmiastowe filtrowanie.  
- **Bezpieczeństwo:** logowanie przez zweryfikowane konta.

---

## 6. Kwestie Techniczne

### Architektura

- **Frontend:** Vue 3, TypeScript, Vite
- **Backend:** ASP.NET Core 8, PostgreSQL, EF Core, JWT.  
- **Cache:** MemoryCache (sporty, sporty użytkownika).  
- **Integracje:** Facebook Login, Strava OAuth.

### Bezpieczeństwo

- Tokeny JWT z rolami.  
- Brak przechowywania haseł z social login.  
- Walidacja danych wejściowych.  
- Blokowanie użytkowników łamiących regulamin.

---

## 7. Otwarte Pytania i Ryzyka

### Otwarte pytania

- Czy dodajemy czat w aplikacji?  
- Czy użytkownicy powinni mieć możliwość zgłaszania innych?  
- Czy dodajemy poziomy zaawansowania sportowego?

---

### Ryzyka i plany mitygacji

**Ryzyko:** Niska aktywność w mniejszych miastach.  
**Mitigacja:** Promocja lokalna, integracja z wydarzeniami sportowymi.

**Ryzyko:** Nadużycia lub fałszywe profile.  
**Mitigacja:** Logowanie tylko przez zweryfikowane konta.

**Ryzyko:** Problemy z dokładnością lokalizacji.  
**Mitigacja:** Możliwość ręcznego ustawienia lokalizacji.

---

## Podsumowanie

PRD definiuje kluczowe cele, funkcje i wymagania aplikacji SportConnect.  
Dokument stanowi podstawę do planowania sprintów, tworzenia dokumentacji technicznej i dalszego rozwoju produktu.

