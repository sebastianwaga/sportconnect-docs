# Event Storming – SportConnect (wersja próbna)

Event Storming to technika służąca do modelowania procesów domenowych.  
Poniżej przedstawiono cyfrową wersję warsztatu przeprowadzonego dla aplikacji SportConnect.

---

## Cel warsztatu
Zmapowanie kluczowych procesów w aplikacji SportConnect:  
- rejestracja i logowanie,  
- zarządzanie sportami użytkownika,  
- ustawianie lokalizacji,  
- wyszukiwanie partnerów treningowych,  
- dopasowania (match),  
- administracja.

---

# Zdarzenia Domenowe (Events)

1. **Użytkownik zarejestrowany**
2. **Użytkownik zalogowany**
3. **Profil użytkownika zaktualizowany**
4. **Sport dodany do profilu**
5. **Sport usunięty z profilu**
6. **Dystans sportu zaktualizowany**
7. **Lokalizacja ustawiona**
8. **Promień wyszukiwania ustawiony**
9. **Status „trenuję teraz” ustawiony**
10. **Użytkownicy wyszukani**
11. **Partner treningowy dopasowany**
12. **Użytkownik zablokowany**
13. **Użytkownik odblokowany**
14. **Cache sportów użytkownika odświeżony**
15. **Cache listy sportów odświeżony**

---

# Komendy (Commands)

1. **Zarejestruj użytkownika**
2. **Zaloguj użytkownika**
3. **Zaktualizuj profil**
4. **Dodaj sport**
5. **Usuń sport**
6. **Zaktualizuj dystans sportu**
7. **Ustaw lokalizację**
8. **Ustaw promień wyszukiwania**
9. **Ustaw status dostępności**
10. **Wyszukaj użytkowników**
11. **Dopasuj użytkowników**
12. **Zablokuj użytkownika**
13. **Odblokuj użytkownika**
14. **Odśwież cache sportów użytkownika**
15. **Odśwież cache listy sportów**

---

# Agregaty (Aggregates)

1. **User**
   - Id  
   - Name  
   - Email  
   - Sports[]  
   - Location  
   - SearchRadius  
   - AvailabilityStatus  
   - IsBlocked  

2. **UserSport**
   - UserId  
   - SportId  
   - TypicalDistanceKm  

3. **Sport**
   - Id  
   - Name  
   - Description  
   - DefaultDistanceKm  

4. **Location**
   - Latitude  
   - Longitude  

---

# Polityki (Policies)

1. **Jeśli sport dodany → odśwież cache sportów użytkownika**
2. **Jeśli sport usunięty → odśwież cache sportów użytkownika**
3. **Jeśli dystans zaktualizowany → odśwież cache sportów użytkownika**
4. **Jeśli admin edytuje sport → odśwież cache listy sportów**
5. **Jeśli użytkownik ustawi lokalizację → przelicz dopasowania**
6. **Jeśli użytkownik zostanie zablokowany → usuń go z wyników wyszukiwania**
7. **Jeśli użytkownik zmieni status „trenuję teraz” → zaktualizuj widok wyszukiwania**

---

# Widoki (Views)

1. **Profil użytkownika**
2. **Lista sportów**
3. **Moje sporty**
4. **Ustawienia lokalizacji**
5. **Wyszukiwarka użytkowników**
6. **Lista dopasowanych partnerów**
7. **Panel administratora**

---

# Systemy zewnętrzne (opcjonalnie)

1. **Facebook OAuth**
2. **Strava OAuth**

---

# Pytania / Problemy (opcjonalnie)

1. Czy dopasowania powinny być liczone w czasie rzeczywistym?  
2. Czy użytkownik może mieć wiele lokalizacji?  
3. Czy powinniśmy dodać poziomy zaawansowania sportowego?  
4. Czy w przyszłości dodajemy czat?  

---

# Podsumowanie

Powyższy Event Storming przedstawia kluczowe procesy domenowe aplikacji SportConnect.  
Może zostać rozszerzony o diagramy, szczegółowe przepływy oraz powiązania między agregatami.

