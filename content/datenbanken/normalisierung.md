---
title: "Normalisierung"
date: 2022-08-24T22:51:52-06:00
draft: false
type: docs
description: "Hinweis: Es werden nur Normalform 1 bis 3 Betrachtet. "
---

## Definition
Normalisierung ist ein Prozess, der Daten in einer Datenverarbeitenden Umgebung (insbesondere Datenbanken), strukturiert und bereinigen soll. Das Zeil ist es Redundanzen und Abhängigkeiten zu reduzieren und die Datenintergrität zu verbessern.

## Zeile
- Reduktion von Redundanzen
- Vermeidung von Anomalien (Einfühge-, Änderungs-, Löschanomalie)
- Sicherstellen einer eindeutigen und konsistenten Datenstruktur

## Begriffe
|        **Begriffe**                  |           **Beschreibung**                         |
|--------------------------------------|----------------------------------------------------|
| Attribut                             |   Spalte einer Tabelle                             |
| Schlüsselattribut (primary key (pk)) | Eindeutige indetifikation eines Datensatzes        |
| Fremdschlüssel                       | Verweise auf primarschlüssel einer anderen Tabelle |
| Funktionale Abhängigkeit             | Ein Attribut x bestimmt y eindeutig x -> y         |

## Normaleformen

### 1. Normalform (1NF)
**Anforderung**
- Alle Attribute sind atomar (keine Mehrfachwerte, keine Listen, keine zusammengesetzten Werte).
- Jeder Datensatz enthält für jedes Attribut genau einen Wert.

**Beispiel Fehler**
| **mitarbeiter_name** | **mitarbeiter_plz** | **mitarbeiter_stadt** |
|----------------------|---------------------|-----------------------|
| Max Musterman        | 31249               | Hohenhameln           |
| Emilia Musterman     | 31249               | Peine                 |

**Fix**
- Aufteilen in verschiedene Tabellen falls nichtschlüssel Attribute abhängig vom zusammengesteten Primarschlüssel ist.

### 2. Normalform (2NF)
**Anforderung**
- Die Tabelle muss in der 1NF sein.
- Kein Nicht-Schlüsselattribut hängt von einem Teil eines zusammengesteten Primärschlüssels ab.

**Beispiel Fehler**
| **mitarbeiter_name** | **mitarbeiter_plz** | **mitarbeiter_stadt** |
|----------------------|---------------------|-----------------------|
| Max Musterman        | 31249               | Hohenhameln           |
| Emilia Musterman     | 31249               | Peine                 |

**Fix**
** Aufteilen in verschiedene Tabellen falls sie transitiv Abhängigkeit aufweisen

### 3. Normalform (3NF)
**Anforderungen**
- Die 2NF ist gegeben
- Keine Transitiven Abhängigkeiten

**Biespiel**
| **mitarbeiter_name** | **mitarbeiter_plz** |
|----------------------|---------------------|
| Max Musterman        | 31249               |
| Emilia Musterman     | 31224               |


| **mitarbeiter_plz** | **mitarbeiter_stadt** |
|---------------------|-----------------------|
| 31249               | Hohenhameln           |
| 31224               | Peine                 |
