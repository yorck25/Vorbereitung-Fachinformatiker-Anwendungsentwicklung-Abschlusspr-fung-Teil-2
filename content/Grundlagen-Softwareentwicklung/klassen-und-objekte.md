---
title: "Klassen und Objekte"
date: 2022-08-24T22:51:52-06:00
draft: false
type: docs
description: ""
---
# Definitionen

## Defintion Klasse
Eine Klasse ist eine Vorlage oder ein Bauplan, der EIgenschaften und das Verhalten einer Art von Objekten definiert.

## Definition Objekt
Ein Objekt ist eine konkrete, individuelle Instanz dieser Klasse, die auf den Vorgaben der Klasse basiert und spezifische Werte für ihre Attribute hat.

## Beispiel

```c-sharp
// Auto ist die Klasse (Bauplan)
public class Auto {
  public string Farbe;
  public int Sitze;

  public void Fahren(){
    Console.WriteLine("Das Auto fährt.");
  }
}

// auto ist das Objekt
Auto auto = new Auto();
auto.Farbe = "Rot";
auto.Sitze = 5;
Auto.Fahren();

```
