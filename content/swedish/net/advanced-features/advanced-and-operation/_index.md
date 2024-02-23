---
title: Advanced AND Operation i Aspose.Tasks
linktitle: Advanced AND Operation i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du utför avancerade AND-operationer i Aspose.Tasks för .NET för att effektivt filtrera projektuppgifter baserat på flera kriterier.
type: docs
weight: 10
url: /sv/net/advanced-features/advanced-and-operation/
---
## Introduktion

 I den här handledningen kommer vi att fördjupa oss i den avancerade AND-driften i Aspose.Tasks för .NET, ett kraftfullt verktyg för att hantera uppgifter och projekt. Vi kommer att utforska hur man filtrerar projektuppgifter baserat på flera förhållanden med hjälp av`Util.And` klass.

## Förutsättningar

Innan vi börjar, se till att du har följande:

1. Grundläggande kunskaper i programmeringsspråket C#.
2.  Installerade Aspose.Tasks för .NET. Om inte kan du ladda ner den från[här](https://releases.aspose.com/tasks/net/).
3. Integrerad utvecklingsmiljö (IDE) som Visual Studio.

## Importera namnområden

Låt oss först importera de nödvändiga namnrymden till vårt C#-projekt:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## Steg 1: Initiera projekt och samla in uppgifter

Börja med att initiera ett nytt Aspose.Tasks-projekt och samla alla uppgifter inom det:

```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Steg 2: Definiera filtervillkor

Definiera sedan filtervillkoren. För det här exemplet skapar vi två villkor: ett för att filtrera sammanfattningsuppgifter och ett annat för att filtrera uppgifter som inte är noll:

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Steg 3: Kombinera villkor med OCH-drift

 Kombinera nu villkoren med hjälp av`Util.And` klass för att skapa ett sammansatt villkor:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Steg 4: Tillämpa villkor och filteruppgifter

Tillämpa det kombinerade villkoret på de insamlade uppgifterna och filtrera dem därefter:

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Steg 5: Skriv ut filtrerade uppgifter

Slutligen, mata ut de filtrerade uppgifterna:

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Ytterligare bearbetning kan göras här
}
```

## Slutsats

 I den här handledningen lärde vi oss hur man utför avancerade AND-operationer i Aspose.Tasks för .NET. Genom att kombinera förhållanden med hjälp av`Util.And` klass kan vi filtrera uppgifter effektivt baserat på flera kriterier.

## FAQ's

### F1: Vad är Aspose.Tasks för .NET?

S: Aspose.Tasks för .NET är ett robust API som tillåter utvecklare att manipulera Microsoft Project-filer programmatiskt i .NET-applikationer.

### F2: Kan jag tillämpa fler än två villkor med Util.And?

S: Ja, Util.And kan användas för att kombinera valfritt antal villkor för att skapa komplexa filtreringskriterier.

### F3: Finns det en gratis testversion tillgänglig för Aspose.Tasks för .NET?

 S: Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).

### F4: Var kan jag hitta dokumentation för Aspose.Tasks för .NET?

 S: Du kan hitta dokumentationen[här](https://reference.aspose.com/tasks/net/).

### F5: Hur kan jag få support för Aspose.Tasks för .NET?

 S: Du kan få stöd från Aspose.Tasks communityforum.[här](https://forum.aspose.com/c/tasks/15).