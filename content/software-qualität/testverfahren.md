---
title: "Testverfahren"
date: 2022-08-24T22:51:52-06:00
draft: false
type: docs
description: ""
---

## Unit-Test

### Ziel
Prüft einzelne, isolierte Codeeinheiten (Funktionen, Methoden, Klassen).

### Eigenschaften
- Isolation der kleinsten Softwareeinhaiten
- Gleiche Eingaben müssen gleiche Ausgaben liefern
- Der Unit-Test wird vor dem schreiben des Code erstellt
- Automatisierbar und schnell ausführbar

---

## Schreibtischtest

### Ziel
Manuelle, gedankliche Durchlaufkontrolle eines Alorithmus oder Codes.

### Eigenschaften
- Eintwickler geht den Code Schritt für Schritt manuell durch
- Überprüfen der Ablauflogik, Variablenwerten und Verzweigungen
- Simpel und ohne Tools durchführbar
- Gut zur frühen Fehlererkennung

---

## Black-Box-Test

### Ziel
Testen der Funktionalität ohne Kenntnis der internen Implementierung.

### Eigenschaften
- Fokus auf Eingabe und erwartete Ausgabe
- Tester kenn die interne Struktur nicht
- Ideal für Funktion-, System- oder Abnahmetests
- Prüft die Anforderungen und nicht den Code

---

## White-Box-Test

### Ziel
Testen mit Einblick un die interne Struktur und Logik der Software.

### Eigenschaften
- Testern kennt Code, Kontrollfluss, Datenfliss
- Prüft Bedingungen, Schleifen, Verzweigungen und Pfade
- Deckt versteckte Logikfehler auf
- Wird oft von Entwciklern erstellt
- Hohe Testtiefe, aber teurer als Black-Box-Tests

---

## Integrationstest

### Zeil
Testen der Zusammenarbeit mehrerer Komponenten oder Modulen.

### Eigenschaften
- Prüft das gesamte Systemverhalten
- Orientiert sich an funktionalen und nicht funktionalen Anforderungen
- Keine Betrachtung einzelner Komponenten

---

## Abnahmetest

### Ziel
Bestätigung, dass die Software die Anforderungen des Kunden erfüllt.

### Eigenschaften
- Wird oft vom Kunden oder Fachabteilung durchgeführt
- Entscheidet über Prdouktfreigabe
- Simuliert ein relistisches Nutzungsszenario

---
