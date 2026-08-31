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

**2. Datenbank aufsetzen**
Lade den Datenbank-Dump in dein lokales PostgreSQL-System. Dadurch wird die Datenbank `bikes` erstellt und mit Beispieldaten gefüllt:

Linux / macOS / Git Bash:
```bash
psql -U postgres -f bikes.sql
```

Windows (PowerShell):
Falls der Befehl psql direkt nicht gefunden wird, nutze den absoluten Pfad zur PostgreSQL-Installation (passe die Versionsnummer ggf. an):

PowerShell
```bash
& "C:\Program Files\PostgreSQL\18\bin\psql.exe" -U postgres -f bikes.sql
```

**3. Skript ausführbar machen und starten**
Gib der Datei die nötigen Ausführungsrechte und starte das Programm:
Unter Linux / macOS / Git Bash:
```bash
chmod +x bike-shop.sh
./bike-shop.sh
```

Unter Windows (PowerShell):

PowerShell
```bash
bash bike-shop.sh
```
Nun öffnet sich das interaktive Menü in deinem Terminal!
