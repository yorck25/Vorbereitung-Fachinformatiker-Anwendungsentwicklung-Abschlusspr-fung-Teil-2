---
title: "Sortieralgorithmen"
date: 2022-08-24T22:51:52-06:00
draft: false
type: docs
description: ""
---

## Bubble Sort

Bubble Sort ist ein einfacher Sortieralgorithmus, der benachbarte Elemente in einer Liste wiederholt vergleicht und
tauscht, wenn sie nicht in der richtigen Reihenfolge sind. Dieser Vergleich und Tausch Vorgang wird so lange wiederholt
bis die Liste in vollständig sortiert ist.

### Vorteile

- Einfache Implementierung
- Speichereffizient

### Nachteile

- Lange Laufzeit (O(n^2))
- Selten in der Praxis angewendet

### Beispiel

```c-sharp
class Auto
{
    public string Name { get; set; }
    public int Leistung { get; set; } // in PS
}

Auto[] autoListe = {
    new Auto { Name = "Audi RS6", Leistung = 630 },
    new Auto { Name = "BMW M2", Leistung = 365 },
    new Auto { Name = "Audi A4", Leistung = 210 }
};

public Auto[] Sort(autos) {
    for(int i = 0; i < autos.Length; i++) {
        for(int c = 0; c < autos.Length - 1; c++) {
            if(autos[c].Leistung > autos[c +1].Leistung){
                Auto temp = autos[c];
                autos[c] = autos[c+1];
                autos[c+1] = temp;
            }
        }
    }
    
   return autos;
}

Sort(autoListe);
```
