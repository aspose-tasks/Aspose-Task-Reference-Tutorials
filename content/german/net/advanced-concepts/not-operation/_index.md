---
title: Arbeiten mit der NOT-Operation in Aspose.Tasks
linktitle: Arbeiten mit der NOT-Operation in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie die NOT-Operation in Aspose.Tasks für .NET verwenden, um Aufgaben effektiv zu filtern. Erweitern Sie jetzt Ihre Projektmanagementfähigkeiten.
type: docs
weight: 20
url: /de/net/advanced-concepts/not-operation/
---
## Einführung

In diesem Tutorial erfahren Sie, wie Sie die NOT-Operation in Aspose.Tasks für .NET verwenden. Mit der NOT-Operation können wir eine Filterbedingung umkehren und so Elemente auswählen, die ein bestimmtes Kriterium nicht erfüllen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Visual Studio: Sie benötigen eine funktionierende Installation von Visual Studio, um den Codebeispielen folgen zu können.
2.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek von herunter und installieren Sie sie[Webseite](https://releases.aspose.com/tasks/net/).
3. Grundlegendes Verständnis von C#: Vertrautheit mit der Programmiersprache C# wird für das Verständnis der Codebeispiele hilfreich sein.

## Namespaces importieren

Importieren wir zunächst die notwendigen Namespaces für unseren Code:

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

 Wir beginnen mit dem Laden einer Projektdatei mit dem Namen „Project2.mpp“ mithilfe von`Project` Klasse, bereitgestellt von Aspose.Tasks. Stellen Sie sicher, dass die Projektdatei im angegebenen Verzeichnis vorhanden ist.

## Schritt 2: Projektaufgaben sammeln

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Hier erstellen wir eine`ChildTasksCollector` Objekt, um alle Aufgaben innerhalb des Projekts zu sammeln. Wir verwenden dann`TaskUtils.Apply` Methode, um die Aufgabenhierarchie des Projekts zu durchlaufen und alle untergeordneten Aufgaben zu sammeln.

## Schritt 3: Filterbedingung definieren

```csharp
var filter = new NullCondition();
```

 Wir definieren eine Filterbedingung mithilfe einer benutzerdefinierten Klasse namens`NullCondition`. Diese Bedingung wählt Aufgaben aus, die einen Nullwert haben.

## Schritt 4: Wenden Sie die NOT-Operation an

```csharp
var condition = new Not<Task>(filter);
```

 Wir wenden die NOT-Operation auf die Filterbedingung an, indem wir verwenden`Not<T>`Klasse, bereitgestellt von Aspose.Tasks. Dadurch wird die Filterbedingung umgekehrt und Aufgaben ausgewählt, die keinen Nullwert haben.

## Schritt 5: Aufgaben filtern

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 Wir filtern die gesammelten Aufgaben basierend auf der angewendeten Bedingung mithilfe einer benutzerdefinierten Funktion`Filter` Methode. Diese Methode verwendet eine aufzählbare Sammlung von Aufgaben und eine Filterbedingung als Eingabeparameter und gibt eine Liste von Aufgaben zurück, die die Bedingung erfüllen.

## Schritt 6: Gefilterte Aufgaben verarbeiten

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Arbeiten Sie mit anderen Eigenschaften...
}
```

Abschließend durchlaufen wir die gefilterten Aufgaben und führen alle gewünschten Vorgänge aus. In diesem Beispiel geben wir einfach die Namen der Aufgaben auf der Konsole aus.

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit der NOT-Operation in Aspose.Tasks für .NET arbeitet. Durch die Umkehrung der Filterbedingungen können wir selektiv Elemente auswählen, die bestimmte Kriterien nicht erfüllen, was unsere Flexibilität bei der Aufgabenbearbeitung innerhalb von Projekten erhöht.

## FAQs

### F1: Kann ich Aspose.Tasks mit anderen .NET-Frameworks verwenden?

A: Ja, Aspose.Tasks unterstützt verschiedene .NET Frameworks, einschließlich .NET Core, .NET Standard und .NET Framework.

### F2: Gibt es eine kostenlose Testversion für Aspose.Tasks?

 A: Ja, Sie können eine kostenlose Testversion herunterladen[Webseite](https://releases.aspose.com/).

### F3: Wie kann ich Unterstützung für Aspose.Tasks erhalten?

 A: Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Supportanfragen oder technische Hilfe.

### F4: Kann ich eine temporäre Lizenz für Aspose.Tasks erwerben?

 A: Ja, Sie können eine temporäre Lizenz bei erwerben[Kaufseite](https://purchase.aspose.com/temporary-license/).

### F5: Wo finde ich eine umfassende Dokumentation für Aspose.Tasks?

 A: Sie können auf die vollständige Dokumentation zugreifen[Aspose.Tasks-Dokumentationsseite](https://reference.aspose.com/tasks/net/).