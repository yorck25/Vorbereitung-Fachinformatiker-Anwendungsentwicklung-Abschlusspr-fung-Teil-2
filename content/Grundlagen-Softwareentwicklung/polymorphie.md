---
title: "Polymorphie"
date: 2022-08-24T22:51:52-06:00
draft: false
type: docs
description: ""
---

# Bedeutung
Polymorphie bedeutet "Vielgestaltigkeit" und beschreibt die Eigenschaft einer Sache, in verschiedenen Formen oder Gestalten zu existieren. In der Softwareentwicklung wird Polymorphie in der Object Orientierten Programmierung genutzt. Sie bietet den Vorteil einer Klasse eine Funktion mit unterschiedlichen Eigenschaft zuzuweisen.

## Statische Polymorphie
- Wird beim Kompelieren entschieden, welche Methode aufgerufen wird.
- Mehrere Funktionen mit gleichem Namen, haben unterschiedliche Parameter

### Beispiel
```c-sharp
public class Rechner {

  public int Add(int a, int b) {
    return a + b;
  }

  public double Add(double a, double b) {
    return a + b;
  }
}
```

## Dynamische Polymorphie
- Wird zur Laufzeit verändert
- Vererbungen + virtuelle Methoden (virtual / override)

### Beispiel:
```c-sharp
public class Vortbewegungsmittel {
  public int geschwindigkeit {get; private set; }

  public virtual void Vortbewegen(){
    Console.WriteLine("Vortbewegen.");
  }
}

public class Auto: Vortbewegungsmittel {
  public ovveride void Vortbewegen(){
    Console.WriteLine("Das Auto faehrt.");
  }
}

public class Flugzeug: Vortbewegungsmittel {
  public ovveride void Vortbewegen(){
    Console.WriteLine("Das Flugzeug fliegt.");
  }
}
```
