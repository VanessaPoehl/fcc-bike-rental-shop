# Bike Rental Shop Management System

Ein interaktives Kommandozeilen-Tool (CLI) zur Verwaltung eines Fahrradverleihs, basierend auf Bash und PostgreSQL. Dieses Projekt demonstriert das Zusammenspiel zwischen einer Datenbank und einer Shell-Anwendung, mit einem starken Fokus auf Backend-Logik und Input-Validierung.

## Über das Projekt

Dieses System ermöglicht es Benutzern, über ein interaktives Menü Fahrräder auszuleihen und wieder zurückzugeben. Es simuliert reale Geschäftsprozesse und nutzt eine relationale Datenbank zur Speicherung von Kunden-, Fahrrad- und Ausleihdaten. 

Besonderer Wert wurde auf die **Fehlerbehandlung (Input Validation)** gelegt. Das Skript prüft beispielsweise, ob Benutzereingaben das korrekte Format haben und ob Fahrräder tatsächlich zur Ausleihe verfügbar sind, bevor eine Transaktion in der Datenbank durchgeführt wird.

## Verwendete Technologien
* **Bash Scripting:** Für die interaktive Menüsteuerung, Benutzereingaben und Ablauflogik.
* **PostgreSQL:** Als relationale Datenbank für das Backend.
* **SQL:** Für CRUD-Operationen (Erstellen, Lesen, Aktualisieren) und Tabellen-Verknüpfungen (JOINs).

## Highlights & Features
* **Interaktives CLI-Menü:** Benutzerfreundliche Navigation durch Ausleih- und Rückgabeprozesse.
* **Robuste Validierung:** Regex-Prüfungen stellen sicher, dass Menüauswahlen und IDs gültige Zahlen sind. Fehlerhafte Eingaben werden abgefangen und der Benutzer wird sauber ins Hauptmenü zurückgeleitet.
* **Dynamische Datenbankabfragen:** Das Skript ermittelt in Echtzeit verfügbare Fahrräder und aktuelle Kunden-Ausleihen.
* **Relationales Design:** Saubere Nutzung von Primary und Foreign Keys zwischen den `bikes`, `customers` und `rentals` Tabellen.

## Lokale Installation & Nutzung

Um das Projekt auf deinem eigenen Rechner auszuführen, benötigst du ein Terminal (Bash) und eine lokal installierte **PostgreSQL**-Datenbank.

**1. Repository klonen**
```bash
git clone https://github.com/VanessaPoehl/fcc-bike-rental-shop
cd fcc-bike-rental-shop
```

**2. Datenbank-Nutzer anpassen**
Das Skript wurde ursprünglich für die freeCodeCamp-Umgebung entwickelt. Wenn dein lokaler PostgreSQL-Benutzer anders heißt:
* Öffne die Datei `bike-shop.sh` und ändere in der Variablen `PSQL` (Zeile 2) den Teil `--username=freecodecamp` zu deinem lokalen Nutzernamen (z. B. `--username=DEIN_LOKALER_DB_NUTZER`).

**3. Datenbank aufsetzen**
Lade den Datenbank-Dump in dein lokales PostgreSQL-System. Dadurch wird die Datenbank `bikes` erstellt und mit Beispieldaten gefüllt:
```bash
psql -U DEIN_LOKALER_DB_NUTZER < bikes.sql
```

**4. Skript ausführbar machen und starten**
Gib der Datei die nötigen Ausführungsrechte und starte das Programm:
```bash
chmod +x bike-shop.sh
./bike-shop.sh
```
Nun öffnet sich das interaktive Menü in deinem Terminal!
