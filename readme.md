# MTCG – Monster Trading Card Game

## Beschreibung

Dieses Projekt ist ein einfacher HTTP-Server in C#, der ein Trading Card Game implementiert.  
Spieler können sich registrieren, Karten kaufen, Decks erstellen und gegeneinander kämpfen.

---

## Architektur

- HTTP Server → verarbeitet Requests  
- Endpoints → enthalten Logik  
- Repositories → Datenbankzugriff  
- PostgreSQL → Speicherung  

---

## Authentifizierung

Token-Format:
Authorization: Bearer username-mtcgToken

---

## Wichtige Endpoints

### User
- POST /users → Registrierung  
- POST /sessions → Login  
- GET /users/{username} → Profil  
- PUT /users/{username} → Profil bearbeiten  

### Packages
- POST /packages → Paket erstellen (Admin)

### Trading
- POST /transactions/packages → Paket kaufen  

### Cards & Deck
- GET /cards → Karten anzeigen  
- GET /deck → Deck anzeigen  
- PUT /deck → Deck konfigurieren (4 Karten)

### Battle
- POST /battles → Kampf starten  

### Stats
- GET /stats → eigene Stats  
- GET /scoreboard → Rangliste  

---

## Spielprinzip

- Kartenpakete kaufen  
- Deck (4 Karten) erstellen  
- Kämpfen und Elo gewinnen  

---

## Technologien

- C# / .NET  
- PostgreSQL  
- Npgsql  
- TCP Sockets  
- JSON  

---

## Start

1. PostgreSQL starten  
2. DB erstellen  
3. Server starten  
4. Programm starten  
5. Mit curl testen  

---

## Lessons Learned

- Klare Architektur (Layering) verbessert Wartbarkeit deutlich  
- Manuelles HTTP-Handling hilft beim Verständnis, ist aber komplex und fehleranfällig  
- Datenbank-Transaktionen sind essenziell für Konsistenz  
- Authentifizierung sollte zentral gelöst werden, nicht pro Endpoint  
- Spiel-Logik und gleichzeitige Zugriffe sind schwieriger als erwartet  
- Automatisierte Tests und Logging wären sinnvoll gewesen , da manuell mit curl-script zu testen umständig ist 

---

## Verbesserungen

- ASP.NET Core  
- JWT Auth  
- Unit Tests  
- bessere Battle-Logik  
