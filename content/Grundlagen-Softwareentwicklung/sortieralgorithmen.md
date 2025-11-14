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
- Lange Laufzeit O(n^2)
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

---

## Merge Sort
Merge Sort ist ein effizienter Sortieralgorithmus der nach dem "Teile und Herrscher"-Prinzip funktioniert.
Eine List wird rekursiv in immer kleinere Teile zerlegt, bis jede nur noch noch ein Element enthält. Anschließend werden wieder alle teile sortiert in eine Liste zusammen gefühgt.

### Vorteile
- Effiziente Laufzeit O(n log n)
- Bleibt schnell auch bei Großen Datenmengen
- Kann Daten sequenziell durcharbeiten, weswegen auch verkettete Listen sortiert werden könenn

### Nachteile
- Es wird zusätzlicher Speicher benötigt in größer der zu sortierenden Datenmenge
- Bei vorsortierten Datensätzen ineffizienter
- Komplexe Implementation

### Beispiel
```c-sharp
Auto[] Merge(Auto[] left, Auto[] right)
{
    Auto[] result = new Auto[left.Length + right.Length];

    int i = 0, j = 0, k = 0;

    while (i < left.Length && j < right.Length)
    {
        if (left[i].Leistung <= right[j].Leistung)
        {
            result[k++] = left[i++];
        }
        else
        {
            result[k++] = right[j++];
        }
    }

    while (i < left.Length)
    {
        result[k++] = left[i++];
    }

    while (j < right.Length)
    {
        result[k++] = right[j++];
    }

    return result;
}

Auto[] MergeSort(Auto[] array)
{
    if (array.Length <= 1)
        return array;

    int half = array.Length / 2;

    Auto[] left  = new Auto[half];
    Auto[] right = new Auto[array.Length - half];

    Array.Copy(array, 0, left, 0, half);
    Array.Copy(array, half, right, 0, array.Length - half);

    left  = MergeSort(left);
    right = MergeSort(right);

    return Merge(left, right);
}
```

---

## Selection Sort
Selection Sort ist ein Sortieralgorithmus, der eine Liste duch wiederholtes suchen des kleinsten Elemente im unsortierten Teil un dessen Tauscht diesen mit der aktuellenPosition in der Liste

### Vorteile
- Einfache Implementierung
- Geringer Speicherbedarf

### Nachteile
- Hohe Laufzeit. Laufzeit ist immer O(n^2)
- Instabil da bei Werten mit gleichem Wert die Reihenfolge der ganzen Liste verändert werden kann.

### Beispiel
```c-sharp
public static void SelectionSort(Auto[] array)
{
    for (int i = 0; i < array.Length - 1; i++)
    {
        int minIndex = i;

        for (int j = i + 1; j < array.Length; j++)
        {
            if (array[j].Leistung < array[minIndex].Leistung)
            {
                minIndex = j;
            }
        }

        if (minIndex != i)
        {
            Auto temp = array[i];
            array[i] = array[minIndex];
            array[minIndex] = temp;
        }
    }
}
```

---

## Quick Sort
Quick Sort ist ein schneller, rekursiver Sortieralgorithmus und basiert auf dem "Teile und Herrscher"-Prinzip. Er wählt ein Element als Pivotelement aus und teilt die Liste rekursiv in zwei Teillisten auf. Eine Liste für Elemente welche kleiner sind als das Pivotelement und eine weiter für alle Element die größer als das Pivotelement sind.

### Vorteile
- Hohe durchschnittliche Geschwindigkeit O(n log n)
- Effiziente In-Place-Speichernutzung

### Nachteile
- Worst-Case-Laufzeit (wenn das Pivotelement in einer soriterten Liste ganz hinten ist O(n^2))
- Komplexe Implementation

### Beispiel
```c-sharp
public static void QuickSort(Auto[] array, int left, int right)
{
    if (left >= right)
        return;

    int pivotIndex = Teilen(array, left, right);

    QuickSort(array, left, pivotIndex - 1);
    QuickSort(array, pivotIndex + 1, right);
}

private static int Teilen(Auto[] array, int left, int right)
{
    int pivot = array[right].Leistung;
    int i = left - 1;

    for (int j = left; j < right; j++)
    {
        if (array[j].Leistung <= pivot)
        {
            i++;
            Swap(array, i, j);
        }
    }

    Swap(array, i + 1, right);
    return i + 1;
}

private static void Swap(Auto[] array, int a, int b)
{
    var temp = array[a];
    array[a] = array[b];
    array[b] = temp;
}
```

---
