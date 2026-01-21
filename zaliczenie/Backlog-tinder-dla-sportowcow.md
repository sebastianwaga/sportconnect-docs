# Backlog Produktu – SportConnect (à la Tinder dla sportowców)

---

## Legenda

**Priorytet:**
- P0 (Must Have): Funkcjonalności krytyczne, bez których produkt nie może istnieć.
- P1 (Should Have): Ważne funkcjonalności, które powinny zostać zaimplementowane wkrótce po starcie.
- P2 (Could Have): Funkcjonalności "nice-to-have", które można zrealizować w późniejszym czasie.

**Status:**
- Do zrobienia: Zaplanowane do realizacji w najbliższym czasie.
- W trakcie: Aktualnie w implementacji.
- Ukończono: Zaimplementowane i przetestowane.
- W backlogu: Pomysły i zadania do późniejszej priorytetyzacji.

**Estymacja:** Złożoność zadania w Story Points (np. 1, 2, 3, 5, 8...).

---

## Epik: Uwierzytelnianie i Konto Użytkownika

| ID     | Tytuł                                   | Priorytet | Estymacja | Status     |
|--------|-----------------------------------------|-----------|-----------|------------|
| US-001 | Rejestracja i logowanie użytkownika     | P0        | 8         | Ukończono  |
| US-002 | Logowanie przez Facebook/Strava (OAuth) | P1        | 8         | Do zrobienia |
| US-003 | Edycja profilu użytkownika (dane + status) | P1     | 5         | W trakcie |
| US-004 | Upload zdjęcia profilowego + zapis w bazie | P0     | 5         | Ukończono  |

---

## Epik: Wyszukiwanie i Dopasowania

| ID     | Tytuł                                                   | Priorytet | Estymacja | Status     |
|--------|---------------------------------------------------------|-----------|-----------|------------|
| US-005 | Wyszukiwanie użytkowników wg statusu, lokalizacji, sportów | P0      | 8         | Ukończono |
| US-006 | Wysyłanie zaproszeń do wspólnego treningu               | P0        | 5         | Ukończono  |
| US-007 | Odpowiadanie na zaproszenia (akceptacja/odrzucenie)     | P0        | 5         | Ukończono  |
| US-008 | Historia zaproszeń i odpowiedzi                         | P1        | 5         | Ukończono  |

---

## Epik: Panel Administracyjny

| ID     | Tytuł                                   | Priorytet | Estymacja | Status     |
|--------|-----------------------------------------|-----------|-----------|------------|
| US-009 | Zarządzanie użytkownikami (podgląd, blokowanie) | P0     | 8         | Ukończono |
| US-010 | Zarządzanie kategoriami sportowymi      | P1        | 5         | Ukończono |
| US-011 | Podgląd logów akcji (ActionLogger)      | P0        | 5         | Ukończono  |
| US-012 | Statystyki zaproszeń (dziennie/tygodniowo/miesięcznie) | P1 | 8 | Ukończono |

---

## Epik: Zadania Techniczne

| ID     | Tytuł                                   | Priorytet | Estymacja | Status     |
|--------|-----------------------------------------|-----------|-----------|------------|
| TECH-01 | Lokalizacja komunikatów (EN/PL)        | P0        | 5         | Ukończono  |
| TECH-02 | Walidacja danych wejściowych (DataAnnotations + resx) | P0 | 5 | Ukończono |
| TECH-03 | Dokumentacja OpenAPI (Swagger)         | P0        | 3         | Ukończono  |
| TECH-04 | Cache dla wybranych endpointów         | P1        | 5         | Do zrobienia |
| TECH-05 | Mailing (np. reset hasła)              | P2        | 5         | W backlogu |
| TECH-06 | Deployment aplikacji                   | P0        | 8         | Do zrobienia |

