---
date: 2026-03-14
description: Erfahren Sie, wie Sie Aufgaben, die keine Operation sind, in Aspose.Tasks
  für .NET filtern, und entdecken Sie, wie Sie einen Nicht‑Filter mit einer angewandten
  Nicht‑Bedingung für flexible Aufgabenabfragen nutzen.
linktitle: Working with NOT Operation in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aufgaben filtern, keine Operation in Aspose.Tasks
url: /de/net/advanced-concepts/not-operation/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Filteraufgaben nicht Operation in Aspose.Tasks

## Einführung

In diesem Tutorial lernen Sie **wie man die Filteraufgaben‑Nicht‑Operation** mit Aspose.Tasks für .NET verwendet. Die NOT‑Operation ermöglicht es Ihnen, eine Filterbedingung umzukehren, sodass Sie jede Aufgabe auswählen können, die **nicht** einem bestimmten Kriterium entspricht. Diese Fähigkeit ist unverzichtbar, wenn Sie bestimmte Elemente ausschließen müssen – beispielsweise Aufgaben ohne Wert – oder wenn Sie komplexe Abfragen erstellen wollen, ohne zusätzlichen Code zu schreiben.

## Schnellantworten
- **Was macht die NOT‑Operation?** Sie kehrt eine Filterbedingung um und gibt Elemente zurück, die den ursprünglichen Test nicht bestehen.  
- **Warum die Filteraufgaben‑Nicht‑Operation verwenden?** Sie vereinfacht die Ausschlusslogik und hält Ihren Code lesbar.  
- **Welcher Namespace stellt die NOT‑Klasse bereit?** `Aspose.Tasks.Util`.  
- **Benötige ich eine Lizenz für die Produktion?** Ja, für die Nutzung außerhalb der Testversion ist eine gültige Aspose.Tasks‑Lizenz erforderlich.  
- **Kann ich NOT mit anderen Bedingungen kombinieren?** Absolut – kombinieren Sie sie mit `AndCondition`, `OrCondition` usw.

## Was ist die Filteraufgaben‑Nicht‑Operation?
Die **Filteraufgaben‑Nicht‑Operation** ist eine logische Negation, die auf einen Aufgabenfilter angewendet wird. Anstatt Aufgaben auszuwählen, die einer Bedingung entsprechen, wählt sie diejenigen aus, die *nicht* entsprechen. Das ist besonders praktisch, wenn Sie Aufgaben mit leeren Feldern, bestimmten Statuswerten oder anderen Attributen, die Sie ausschließen möchten, ignorieren wollen.

## Warum eine NOT‑Bedingung beim Filtern von Aufgaben anwenden?
Durch das Anwenden einer **NOT‑Bedingung** reduziert sich die Notwendigkeit mehrerer Durchläufe über Ihre Projektdaten. Sie können kompakte, wartbare Code‑Snippets schreiben und die Leistung verbessern, indem die Auswertung an die optimierte Engine von Aspose.Tasks delegiert wird.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. Visual Studio: Sie benötigen eine funktionierende Installation von Visual Studio, um den Code‑Beispielen folgen zu können.  
2. Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks‑Bibliothek für .NET von der [Website](https://releases.aspose.com/tasks/net/) herunter und installieren Sie sie.  
3. Grundlegendes Verständnis von C#: Vertrautheit mit der Programmiersprache C# ist hilfreich, um die Code‑Beispiele zu verstehen.

## Namespaces importieren

Zuerst importieren wir die erforderlichen Namespaces für unseren Code:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Projekt und Aufgaben einrichten

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

Wir beginnen damit, eine Projektdatei namens **Project2.mpp** mithilfe der `Project`‑Klasse von Aspose.Tasks zu laden. Stellen Sie sicher, dass die Projektdatei im angegebenen Verzeichnis vorhanden ist.

## Schritt 2: Projektaufgaben sammeln

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

Hier erstellen wir ein `ChildTasksCollector`‑Objekt, um alle Aufgaben im Projekt zu sammeln. Anschließend verwenden wir `TaskUtils.Apply`, um die Aufgabenhierarchie des Projekts zu durchlaufen und jede Unteraufgabe zu erfassen.

## Schritt 3: Filterbedingung definieren

```csharp
var filter = new NullCondition();
```

Wir definieren eine Filterbedingung mit einer benutzerdefinierten Klasse namens `NullCondition`. Diese Bedingung wählt Aufgaben aus, die einen **null**‑Wert besitzen.  

> **Pro‑Tipp:** Ersetzen Sie `NullCondition` durch eine andere Bedingung (z. B. `EqualsCondition`), um unterschiedliche Attribute zu adressieren.

## Schritt 4: NOT‑Operation anwenden

```csharp
var condition = new Not<Task>(filter);
```

Wir wenden die **NOT‑Operation** auf die Filterbedingung mithilfe der `Not<T>`‑Klasse von Aspose.Tasks an. Dadurch wird die ursprüngliche Bedingung umgekehrt, sodass der Filter jetzt Aufgaben auswählt, die **nicht** einen null‑Wert haben. Das ist das Kernstück der **how to use not filter**‑Technik.

## Schritt 5: Aufgaben filtern

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

Wir filtern die gesammelten Aufgaben anhand der angewendeten Bedingung mit einer benutzerdefinierten `Filter`‑Methode. Die Methode erhält eine aufzählbare Sammlung von Aufgaben und eine Filterbedingung und gibt eine Liste von Aufgaben zurück, die die **apply not condition** erfüllen.

## Schritt 6: Gefilterte Aufgaben verarbeiten

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Work with other properties...
}
```

Abschließend iterieren wir über die gefilterten Aufgaben und führen gewünschte Operationen aus. In diesem Beispiel geben wir lediglich die Namen der Aufgaben in der Konsole aus, Sie können diesen Block jedoch erweitern, um Felder zu aktualisieren, Aufgaben zu verschieben oder Berichte zu erstellen.

## Häufige Anwendungsfälle

- **Abgeschlossene Aufgaben ausschließen**, wenn Sie eine Liste ausstehender Arbeiten erstellen.  
- **Aufgaben mit fehlenden benutzerdefinierten Feldern finden** (z. B. eine null‑„Owner“‑Spalte).  
- **Mit anderen Bedingungen kombinieren**, um anspruchsvolle Abfragen zu bauen, etwa „Aufgaben, die nicht null sind und ein Startdatum vor heute haben“.

## Fehlersuche & Tipps

| Problem | Ursache | Lösung |
|---------|---------|--------|
| Keine Aufgaben zurückgegeben | Die ursprüngliche Bedingung ist zu restriktiv. | Überprüfen Sie die Logik der Bedingung oder testen Sie mit einem einfacheren Filter wie `new TrueCondition()`. |
| `NullReferenceException` | Der Pfad `DataDir` ist falsch. | Stellen Sie sicher, dass `DataDir` auf den Ordner zeigt, der *Project2.mpp* enthält. |
| Unerwartete Ergebnisse | `Not<T>` wurde falsch mit anderen Bedingungen kombiniert. | Verwenden Sie Klammern: `new AndCondition(new Not<Task>(filter), otherCondition)`. |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Tasks mit anderen .NET‑Frameworks verwenden?**  
A: Ja, Aspose.Tasks unterstützt .NET Core, .NET Standard und das klassische .NET Framework.

**F: Gibt es eine kostenlose Testversion von Aspose.Tasks?**  
A: Ja, Sie können eine kostenlose Testversion von der [Website](https://releases.aspose.com/) herunterladen.

**F: Wie erhalte ich Support für Aspose.Tasks?**  
A: Besuchen Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Support‑Anfragen oder technische Hilfe.

**F: Kann ich eine temporäre Lizenz für Aspose.Tasks erwerben?**  
A: Ja, Sie können eine temporäre Lizenz über die [Kaufseite](https://purchase.aspose.com/temporary-license/) erwerben.

**F: Wo finde ich umfassende Dokumentation zu Aspose.Tasks?**  
A: Die vollständige Dokumentation steht auf der [Aspose.Tasks‑Dokumentationsseite](https://reference.aspose.com/tasks/net/).

## Fazit

Durch das Beherrschen der **Filteraufgaben‑Nicht‑Operation** und das Erlernen von **how to use not filter** mit der **apply not condition** erhalten Sie eine feinkörnige Kontrolle über die Aufgabenauswahl in Aspose.Tasks. Das ermöglicht Ihnen, saubereren Code zu schreiben, manuelle Ausschlüsse zu vermeiden und leistungsstarke Projekt‑Management‑Werkzeuge zu erstellen.

---

**Zuletzt aktualisiert:** 2026-03-14  
**Getestet mit:** Aspose.Tasks 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}