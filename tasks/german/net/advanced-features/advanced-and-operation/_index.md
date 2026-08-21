---
date: 2026-03-16
description: Erfahren Sie, wie Sie mehrere Bedingungen kombinieren und Projektaufgaben
  mithilfe der erweiterten UND-Operation in Aspose.Tasks für .NET filtern.
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: Wie man mehrere Bedingungen mit der erweiterten UND-Operation in Aspose.Tasks
  kombiniert
url: /de/net/advanced-features/advanced-and-operation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erweiterte AND-Operation in Aspose.Tasks

## Einleitung

In diesem Tutorial erfahren Sie **wie Sie mehrere Bedingungen** mit der *erweiterten AND-Operation* in Aspose.Tasks für .NET kombinieren. Am Ende der Anleitung können Sie **Projektaufgaben** anhand mehrerer Kriterien filtern – etwas, das unverzichtbar ist, wenn Sie **Aufgaben filtern** möchten, z. B. Zusammenfassungs‑Einträge, nicht‑null‑Einträge oder benutzerdefinierte Flags in einem einzigen Durchlauf.

## Schnelle Antworten
- **Was macht die erweiterte AND-Operation?** Sie kombiniert zwei oder mehr Filterbedingungen, sodass nur Aufgaben zurückgegeben werden, die *alle* Kriterien erfüllen.  
- **Welche Klasse kombiniert die Bedingungen?** `Util.And<T>` (in der API als `And<T>` bereitgestellt).  
- **Benötige ich eine spezielle Lizenz?** Für den Produktionseinsatz ist eine reguläre Aspose.Tasks‑Lizenz erforderlich; eine kostenlose Testversion ist verfügbar.  
- **Kann ich mehr als zwei Bedingungen verketten?** Ja – `And<T>` akzeptiert beliebig viele Bedingungen.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## Was bedeutet „mehrere Bedingungen kombinieren“ in Aspose.Tasks?

Mehrere Bedingungen zu kombinieren bedeutet, einen zusammengesetzten Filter zu erstellen, der jede Aufgabe gleichzeitig gegen mehrere Regeln prüft. Dieser Ansatz ist deutlich effizienter, als die Aufgabenliste mehrfach zu durchlaufen, weil die Bibliothek die Logik in einem Durchlauf anwendet.

## Warum die erweiterte AND-Operation verwenden?

- **Performance:** Reduziert die Anzahl der Durchläufe über die Aufgabensammlung.  
- **Lesbarkeit:** Hält die Filterlogik deklarativ und leicht wartbar.  
- **Flexibilität:** Sie können integrierte Bedingungen (z. B. `SummaryCondition`) mit benutzerdefinierten Prädikaten mischen.  

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie folgendes haben:

1. Grundkenntnisse in C#‑Programmierung.  
2. Aspose.Tasks für .NET installiert. Falls Sie es noch nicht heruntergeladen haben, erhalten Sie es **[hier](https://releases.aspose.com/tasks/net/)**.  
3. Eine IDE wie Visual Studio (jede Edition ist geeignet).  

## Namespaces importieren

Zuerst importieren Sie die Namespaces, die das Aufgabenmodell und Hilfsklassen bereitstellen:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## Schritt 1: Projekt initialisieren und Aufgaben sammeln

Wir erstellen eine `Project`‑Instanz und verwenden den `ChildTasksCollector`, um jede Aufgabe in der Datei zu sammeln. Dies demonstriert **wie man den Collector** verwendet, um eine flache Aufgabenliste abzurufen.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Schritt 2: Filterbedingungen definieren

Hier definieren wir die einzelnen Bedingungen, die wir anwenden wollen. In diesem Beispiel **filtern wir Zusammenfassungs‑Aufgaben** und stellen zudem sicher, dass das Aufgabenobjekt nicht null ist.

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Schritt 3: Bedingungen mit AND‑Operation kombinieren

Jetzt **kombinieren wir mehrere Bedingungen** mithilfe der Klasse `And<T>`. Dies ist der Kern der **erweiterten AND‑Operation**.

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Schritt 4: Bedingung anwenden und Aufgaben filtern

Mit der zusammengesetzten Bedingung rufen wir `Filter` auf, um **Projektaufgaben** basierend auf der kombinierten Logik zu **filtern**.

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Schritt 5: Gefilterte Aufgaben ausgeben

Abschließend geben wir die Aufgaben aus, die **alle** Bedingungen erfüllt haben. Sie können die `Console.WriteLine`‑Aufrufe durch jede gewünschte benutzerdefinierte Verarbeitung ersetzen.

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## Häufige Probleme und Lösungen

| Problem | Warum es passiert | Schnelllösung |
|-------|----------------|-----------|
| `Filter`‑Methode nicht gefunden | Fehlendes `using Aspose.Tasks.Util;` | Stellen Sie sicher, dass der Util‑Namespace importiert ist (siehe Namespaces importieren). |
| Keine Aufgaben zurückgegeben | Bedingungen sind zu restriktiv (z. B. Filterung von Zusammenfassungs‑Aufgaben, wenn keine vorhanden sind) | Prüfen Sie, ob das Projekt tatsächlich Zusammenfassungs‑Aufgaben enthält oder passen Sie die Bedingungen an. |
| NullReferenceException | `coll.Tasks` enthält null‑Einträge | Die `NotNullCondition` schützt bereits davor; behalten Sie sie in der AND‑Kette. |

## FAQ's

### Q1: Was ist Aspose.Tasks für .NET?

A: Aspose.Tasks für .NET ist eine leistungsstarke API, die Entwicklern ermöglicht, Microsoft‑Project‑Dateien programmgesteuert in .NET‑Anwendungen zu manipulieren.

### Q2: Kann ich mehr als zwei Bedingungen mit Util.And anwenden?

A: Ja, Util.And kann verwendet werden, um beliebig viele Bedingungen zu kombinieren und komplexe Filterkriterien zu erstellen.

### Q3: Gibt es eine kostenlose Testversion von Aspose.Tasks für .NET?

A: Ja, Sie können eine kostenlose Testversion **[hier](https://releases.aspose.com/)** herunterladen.

### Q4: Wo finde ich die Dokumentation für Aspose.Tasks für .NET?

A: Die Dokumentation finden Sie **[hier](https://reference.aspose.com/tasks/net/)**.

### Q5: Wie erhalte ich Support für Aspose.Tasks für .NET?

A: Support erhalten Sie im Aspose.Tasks‑Community‑Forum **[hier](https://forum.aspose.com/c/tasks/15)**.

**Zusätzliche Fragen & Antworten**

**F: Wie filtere ich Aufgaben nach benutzerdefinierten Feldwerten?**  
A: Erstellen Sie eine `CustomFieldCondition` (oder implementieren Sie `ICondition<Task>`) und fügen Sie sie zur `And<T>`‑Kette hinzu.

**F: Kann ich denselben Ansatz zum Filtern von Ressourcen verwenden?**  
A: Ja – ersetzen Sie `Task` durch `Resource` und nutzen Sie die entsprechenden Bedingungsklassen.

## Fazit

Durch die oben beschriebenen Schritte wissen Sie jetzt **wie Sie mehrere Bedingungen** mithilfe der **erweiterten AND‑Operation** in Aspose.Tasks für .NET kombinieren. Diese Technik ermöglicht Ihnen ein effizientes **Filtern von Projektaufgaben**, egal ob Sie Zusammenfassungs‑Einträge, nicht‑null‑Einträge oder beliebige benutzerdefinierte Kriterien anvisieren.

---

**Zuletzt aktualisiert:** 2026-03-16  
**Getestet mit:** Aspose.Tasks für .NET (neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}