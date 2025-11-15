---
title: "SQL Grundlagen"
date: 2022-08-24T22:51:52-06:00
draft: false
type: docs
description: ""
---

# Data Definition Language (DDL)
Wird genutzt, um Datenbankstrukturen zu erstellen oder zu verändern.

## Wichtige Befehle
- *Create Table*
```SQL
CREATE TABLE benutzer (id int Primary Key, name varchar(128));
```
- *Alter Table*
```SQL
ALTER TABLE benutzer ADD COLUMN email varchar(255);
```
- *Drop Table*
```SQL
DROP TABLE benutzer;
```
---

# Data Manipulation Langauge (DML)
Wird zu bearbeitung der Daten innerhalb der Tabellen genutzt.

## Wichtige Befehle
- *INSERT INTO*: Daten Satz/ Sätze in Tabelle einfügen
```SQL
INSERT INTO benutzer (id, name) VALUES (0, 'Max Mustermann');
```
- *UPDATE*: Einen oder mehrere bestimmte Datenstze verändern
```SQL
UPDATE benutzer SET name = 'Erika Mustermann' WHERE id = 0;
```
- *Delete*: Einen oder mehrere Datensätzte aus einer Tabelle löschen
```SQL
DELETE FROM benutzer WHERE id = 0;
```

---

# Data Query Langauge (DQL)
Wird für das abrufen von Daten aus einer oder mehreren Tabellen genutzt.

## Wichtige Befehle
- *SELECT*: Daten aus einer Tabelle abrufen
```SQL
SELECT * FROM benutzer;
```

## Grundstruktur des Befehls
```SQL
SELECT *
FROM benutzer
WHERE id = 0
GROUP BY id
ORDER BY id DESC;
```

---

# SQL Konzepte

## 1. Primärschlüssel (PRIMARY KEY)
Eindeutige Identifikation eines Datensatzes.

## 2. Fremdschlüssel (FOREIGN KEY)
Verweis auf Primärschlüssel einer anderen Tabelle.

## 3. Datentypen
Beispiele: INT, VARCHAR(n), DATE, BOOLEAN, DECIMAL.

## 4. Bedingungen (WHERE)
Vergleichsoperatoren: =, <>, <, >, <=, >=
Logische Operatoren: AND, OR, NOT

## 5. Aggregatfunktionen
COUNT(), SUM(), AVG(), MIN(), MAX()

## 6. Joins
Verknüpfen mehrere Tabellen anhand gemeinsamer Schlüssel.
### Typen
*INNER JOIN* – nur passende Datensätze
*LEFT JOIN* – alle links + passende rechts
*RIGHT JOIN* – alle rechts + passende links
*FULL OUTER JOIN* – alle Datensätze beider Tabellen
