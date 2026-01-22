# Historyjki Użytkownika – Projekt SportConnect

Poniżej znajdują się historyjki użytkownika (User Stories) podzielone na epiki.  
Każda historyjka zawiera jasny cel użytkownika oraz kryteria akceptacji.

---

## Epik: Uwierzytelnianie i Zarządzanie Kontem

### US-001: Rejestracja i logowanie użytkownika
**Jako** nowy użytkownik  
**Chcę** zarejestrować się za pomocą e-maila lub konta społecznościowego (Facebook/Strava)  
**Aby** móc korzystać z aplikacji i umawiać się na wspólne treningi  

**Kryteria akceptacji:**
- Użytkownik może zarejestrować się przez e-mail i hasło.
- Użytkownik może zalogować się przez Facebook.
- Użytkownik może zalogować się przez Strava.
- System waliduje poprawność adresu e-mail.
- Hasło musi mieć minimum 8 znaków.
- Po rejestracji użytkownik może uzupełnić swój profil (opis, wiek, zdjęcie).
- Po zalogowaniu użytkownik otrzymuje token JWT.

---

### US-002: Edycja profilu użytkownika
**Jako** zalogowany użytkownik  
**Chcę** edytować swój profil (imię, opis, wiek, zdjęcie)  
**Aby** inni mogli mnie łatwiej znaleźć i poznać  

**Kryteria akceptacji:**
- Użytkownik może zmienić imię, opis i wiek.
- Użytkownik może zmienić zdjęcie profilowe.
- Zmiany są widoczne natychmiast po zapisaniu.
- System waliduje poprawność danych (np. wiek > 0).
- Zmiany są zapisywane w bazie i odświeżane w cache.

---

## Epik: Sporty i Preferencje Treningowe

### US-003: Dodawanie sportów do profilu
**Jako** użytkownik  
**Chcę** dodać sporty, które uprawiam  
**Aby** inni mogli mnie znaleźć na podstawie wspólnych dyscyplin  

**Kryteria akceptacji:**
- Użytkownik może dodać sport z listy dostępnych sportów.
- Użytkownik może ustawić typowy dystans dla danego sportu.
- System nie pozwala dodać tego samego sportu dwa razy.
- Po dodaniu sportu cache użytkownika jest czyszczony.
- Zmiana jest widoczna w GET /me/sports.

---

### US-004: Edycja typowego dystansu
**Jako** użytkownik  
**Chcę** zmienić typowy dystans dla wybranego sportu  
**Aby** inni wiedzieli, na jakie treningi jestem gotowy  

**Kryteria akceptacji:**
- Użytkownik może zmienić dystans w kilometrach.
- System waliduje, że dystans jest liczbą dodatnią.
- Po zmianie dystansu cache użytkownika jest czyszczony.
- GET /me/sports zwraca zaktualizowaną wartość.

---

### US-005: Usuwanie sportu z profilu
**Jako** użytkownik  
**Chcę** usunąć sport z mojego profilu  
**Aby** nie wyświetlać dyscyplin, których już nie trenuję  

**Kryteria akceptacji:**
- Użytkownik może usunąć sport jednym kliknięciem.
- System usuwa relację UserSport z bazy.
- Cache użytkownika jest czyszczony.
- Sport znika z listy w GET /me/sports.

---

## Epik: Lokalizacja i Dostępność

### US-006: Ustawienie lokalizacji użytkownika
**Jako** użytkownik  
**Chcę** ustawić swoją lokalizację i promień wyszukiwania  
**Aby** znajdować partnerów treningowych w mojej okolicy  

**Kryteria akceptacji:**
- Użytkownik może ustawić współrzędne GPS (lat/long).
- Użytkownik może ustawić promień wyszukiwania w km.
- System zapisuje dane w profilu użytkownika.
- Dane są wykorzystywane w wyszukiwaniu partnerów.

---

### US-007: Ustawienie dostępności „trenuję teraz”
**Jako** użytkownik  
**Chcę** ustawić status „dostępny teraz”  
**Aby** inni mogli mnie znaleźć, gdy jestem gotowy do treningu  

**Kryteria akceptacji:**
- Użytkownik może włączyć/wyłączyć status dostępności.
- Status jest widoczny w wyszukiwaniu użytkowników.
- System zapisuje zmianę w bazie.
- Status jest aktualizowany w czasie rzeczywistym.

---

## Epik: Wyszukiwanie i Matchowanie

### US-008: Wyszukiwanie partnerów treningowych
**Jako** użytkownik  
**Chcę** wyszukiwać osoby trenujące ten sam sport  
**Aby** znaleźć partnerów do wspólnych aktywności  

**Kryteria akceptacji:**
- Użytkownik może filtrować po sporcie.
- Użytkownik może filtrować po dostępności.
- Użytkownik może filtrować po promieniu wyszukiwania.
- Wyniki zawierają: imię, sport, dystans, dostępność.
- System zwraca tylko użytkowników niezablokowanych.

---

### US-009: Automatyczne dopasowanie użytkowników (Match)
**Jako** użytkownik  
**Chcę** zobaczyć listę osób, które najlepiej pasują do moich preferencji  
**Aby** szybko znaleźć idealnego partnera treningowego  

**Kryteria akceptacji:**
- System dopasowuje użytkowników na podstawie:
  - wspólnych sportów,
  - podobnych dystansów,
  - dostępności,
  - lokalizacji.
- Lista jest sortowana według trafności.
- Użytkownik nie widzi osób zablokowanych lub blokujących.

---

## Epik: Administracja i Moderacja

### US-010: Blokowanie użytkownika przez administratora
**Jako** administrator  
**Chcę** blokować użytkowników łamiących regulamin  
**Aby** zapewnić bezpieczeństwo społeczności  

**Kryteria akceptacji:**
- Administrator może zablokować użytkownika.
- Zablokowany użytkownik nie może się zalogować.
- Zablokowany użytkownik nie pojawia się w wyszukiwaniu.
- Akcja jest logowana w systemie.

---

### US-011: Zarządzanie sportami (Admin)
**Jako** administrator  
**Chcę** dodawać, edytować i usuwać sporty  
**Aby** utrzymywać aktualną listę dyscyplin  

**Kryteria akceptacji:**
- Admin może dodać nowy sport.
- Admin może edytować nazwę, opis i typowy dystans.
- Admin może usunąć sport.
- Cache listy sportów jest czyszczony po każdej zmianie.

---

# Podsumowanie
Historyjki użytkownika opisują kluczowe funkcje aplikacji SportConnect:  
uwierzytelnianie, profile, sporty, lokalizację, wyszukiwanie partnerów oraz administrację.

