---
date: 2026-03-24
description: Erfahren Sie, wie Sie den Berechnungsmodus in Aspose.Tasks für .NET einstellen,
  einschließlich automatischem, manuellem und keinem Modus, um Aufgabenabhängigkeiten
  zu verwalten.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Wie man den Berechnungsmodus in Aspose.Tasks für .NET festlegt
url: /de/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man den Berechnungsmodus in Aspose.Tasks für .NET festlegt

## Einleitung

Aspose.Tasks for .NET ist eine leistungsstarke API, die Ihnen ermöglicht, programmgesteuert mit Microsoft Project‑Dateien zu arbeiten. Eine der wichtigsten Einstellungen, die Sie antreffen, ist der **calculation mode**, der steuert, wie Aufgabendaten und Projektpläne aktualisiert werden. In diesem Tutorial lernen Sie **how to set calculation** mode, erkunden **automatic calculation mode**, **manual calculation mode** und **none calculation mode** und sehen, wie diese Optionen **manage task dependencies**, **create project start date** und **link tasks finish‑start** Beziehungen beeinflussen.

## Schnelle Antworten
- **What is calculation mode?** Es bestimmt, ob Aufgabendaten automatisch, manuell oder überhaupt nicht neu berechnet werden.  
- **Why use manual calculation mode?** Um die volle Kontrolle darüber zu haben, wann der Zeitplan aktualisiert wird, nützlich bei Massenupdates.  
- **Which mode is default?** Automatic calculation mode, das Daten sofort nach Änderungen aktualisiert.  
- **Can I change the mode at runtime?** Ja – setzen Sie einfach die `CalculationMode`‑Eigenschaft des `Project`‑Objekts.  
- **Do I need a license?** Für den Produktionseinsatz ist eine gültige Aspose.Tasks‑Lizenz erforderlich.

## Was bedeutet „how to set calculation“ in Aspose.Tasks?

Das Festlegen des Berechnungsmodus ist so einfach wie das Zuweisen eines Enum‑Werts zur `Project.CalculationMode`‑Eigenschaft. Das Enum bietet drei Optionen: `Automatic`, `Manual` und `None`. Die Wahl des richtigen Modus hängt von Ihrem Workflow ab – ob Sie sofortige Updates, Stapelverarbeitung oder vollständige Kontrolle benötigen.

## Voraussetzungen

1. **Visual Studio** – jede aktuelle Version (2019, 2022 oder neuer).  
2. **Aspose.Tasks for .NET** – laden Sie die Bibliothek von [here](https://releases.aspose.com/tasks/net/) herunter und installieren Sie sie.  
3. **Basic C# knowledge** – Sie sollten mit der Erstellung von Konsolenanwendungen und der Verwendung von NuGet‑Paketen vertraut sein.

## Namespaces importieren

Bevor wir mit Aspose.Tasks für .NET arbeiten, importieren wir die erforderlichen Namespaces:

```csharp
using Aspose.Tasks;
using System;
```

## Wie man den Berechnungsmodus festlegt

Im Folgenden finden Sie Schritt‑für‑Schritt‑Beispiele für jeden Berechnungsmodus. Die Codeblöcke bleiben unverändert gegenüber dem Original‑Tutorial; die begleitenden Erklärungen wurden zur Klarheit erweitert.

### Anwenden des automatischen Berechnungsmodus

Der automatische Modus berechnet Daten sofort neu, sobald Sie Aufgaben oder Verknüpfungen ändern.

#### Schritt 1: Erstellen einer neuen Project‑Instanz

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Schritt 2: Projektstartdatum festlegen und Aufgaben hinzufügen

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Schritt 3: Aufgaben verknüpfen (Finish‑to‑Start)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Schritt 4: Neu berechnete Daten überprüfen

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Anwenden des manuellen Berechnungsmodus

Der manuelle Modus deaktiviert automatische Updates und gibt Ihnen die Möglichkeit, Änderungen stapelweise zu verarbeiten, bevor Sie eine Neuberechnung erzwingen.

#### Schritt 1: Erstellen einer neuen Project‑Instanz

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Schritt 2: Projektstartdatum festlegen und Aufgaben hinzufügen

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Schritt 3: Aufgabeneigenschaften überprüfen

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Schritt 4: Aufgaben verknüpfen und Daten überprüfen (keine automatische Neuberechnung)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Anwenden des Keine‑Berechnungsmodus

Der Keine‑Modus schaltet alle internen Berechnungen aus. Verwenden Sie ihn, wenn Sie Daten nur lesen oder exportieren müssen, ohne dass sich der Zeitplan ändert.

#### Schritt 1: Erstellen einer neuen Project‑Instanz

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Schritt 2: Eine neue Aufgabe hinzufügen

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Schritt 3: Aufgabeneigenschaften überprüfen (keine automatischen IDs)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Häufige Probleme und Lösungen

| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| Daten werden nach dem Verknüpfen von Aufgaben nicht aktualisiert | Projekt befindet sich im **Manual**‑ oder **None**‑Modus | Setzen Sie `project.CalculationMode = CalculationMode.Automatic` oder rufen Sie `project.Calculate()` manuell auf |
| Aufgaben‑IDs bleiben bei 0 | Die Verwendung des **None**‑Modus verhindert die ID‑Erzeugung | Wechseln Sie zu **Automatic**‑ oder **Manual**‑Modus und führen Sie anschließend eine Neuberechnung durch |
| Verknüpfung schlägt mit `ArgumentException` fehl | Das Startdatum des Vorgängers ist später als das des Nachfolgers, wenn der **Manual**‑Modus ohne Neuberechnung verwendet wird | Stellen Sie korrekte Startdaten sicher oder führen Sie nach dem Hinzufügen von Verknüpfungen eine Neuberechnung durch |

## Häufig gestellte Fragen

**Q1: Kann ich den Berechnungsmodus zur Laufzeit dynamisch ändern?**  
A1: Ja, Sie können die `CalculationMode`‑Eigenschaft jederzeit in Ihrem Code ändern und anschließend `project.Calculate()` aufrufen, wenn Sie eine sofortige Aktualisierung benötigen.

**Q2: Unterstützt Aspose.Tasks neben Microsoft Project weitere Projektmanagement‑Dateiformate?**  
A2: Aspose.Tasks konzentriert sich hauptsächlich auf Microsoft Project‑Formate, unterstützt aber auch Primavera P6 XML, Primavera DB und Asta Powerproject XML.

**Q3: Ist Aspose.Tasks sowohl für kleine als auch für Unternehmens‑Projekte geeignet?**  
A3: Absolut. Die API skaliert von einfachen Aufgabenlisten bis hin zu komplexen, mehrphasigen Unternehmenszeitplänen.

**Q4: Kann ich Aspose.Tasks mit anderen .NET‑Bibliotheken und -Frameworks integrieren?**  
A4: Ja, Sie können Aspose.Tasks mit ASP.NET, WPF, Xamarin oder jeder anderen .NET‑Technologie kombinieren, um umfangreiche Projektmanagement‑Lösungen zu erstellen.

**Q5: Gibt es ein Community‑Forum oder einen Support‑Kanal für Aspose.Tasks‑Benutzer?**  
A5: Ja, Sie können das [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) besuchen, um Community‑Support und Diskussionen zu erhalten.

---

**Zuletzt aktualisiert:** 2026-03-24  
**Getestet mit:** Aspose.Tasks 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}