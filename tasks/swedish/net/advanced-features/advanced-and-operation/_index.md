---
date: 2026-03-16
description: Lär dig hur du kombinerar flera villkor och filtrerar projektuppgifter
  med den avancerade OCH‑operationen i Aspose.Tasks för .NET.
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: Hur man kombinerar flera villkor med avancerad OCH‑operation i Aspose.Tasks
url: /sv/net/advanced-features/advanced-and-operation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Avancerad OCH-operation i Aspose.Tasks

## Introduktion

I den här handledningen kommer du att upptäcka **hur man kombinerar flera villkor** med den *avancerade OCH-operationen* i Aspose.Tasks för .NET. I slutet av guiden kommer du att kunna **filtrera projektuppgifter** baserat på flera kriterier—något som är avgörande när du behöver **filtrera uppgifter** som sammanfattningsobjekt, icke‑null‑poster eller anpassade flaggor i ett enda pass.

## Snabba svar
- **Vad gör den avancerade OCH-operationen?** Den slår ihop två eller fler filtervillkor så att endast uppgifter som uppfyller *alla* kriterier returneras.  
- **Vilken klass kombinerar villkoren?** `Util.And<T>` (exponerad som `And<T>` i API:et).  
- **Behöver jag en speciell licens?** En vanlig Aspose.Tasks-licens krävs för produktionsbruk; en gratis provversion finns tillgänglig.  
- **Kan jag kedja fler än två villkor?** Ja—`And<T>` accepterar ett godtyckligt antal villkor.  
- **Vilken version av .NET stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## Vad betyder “kombinera flera villkor” i Aspose.Tasks?

Att kombinera flera villkor innebär att skapa ett sammansatt filter som utvärderar varje uppgift mot flera regler samtidigt. Detta tillvägagångssätt är mycket mer effektivt än att iterera genom uppgiftslistan flera gånger eftersom biblioteket tillämpar logiken i ett enda pass.

## Varför använda den avancerade OCH-operationen?

- **Prestanda:** Minskar antalet passeringar över uppgiftskollektionen.  
- **Läsbarhet:** Håller filterlogiken deklarativ och lätt att underhålla.  
- **Flexibilitet:** Du kan blanda inbyggda villkor (t.ex. `SummaryCondition`) med anpassade predikat.  

## Förutsättningar

1. Grundläggande kunskap i C#-programmering.  
2. Aspose.Tasks för .NET installerat. Om du ännu inte har laddat ner det, hämta det **[här](https://releases.aspose.com/tasks/net/)**.  
3. En IDE som Visual Studio (alla utgåvor fungerar).  

## Importera namnrymder

First, import the namespaces that provide the task model and utility classes:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## Steg 1: Initiera projekt och samla uppgifter

Vi skapar en `Project`-instans och använder `ChildTasksCollector` för att samla alla uppgifter i filen. Detta demonstrerar **hur man använder collector** för att hämta en platt lista med uppgifter.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Steg 2: Definiera filtervillkor

Här definierar vi de enskilda villkoren vi vill tillämpa. I detta exempel **filtrerar vi sammanfattningsuppgifter** och säkerställer också att uppgiftsobjektet inte är null.

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Steg 3: Kombinera villkor med OCH-operation

Nu **kombinerar vi flera villkor** med hjälp av `And<T>`-klassen. Detta är kärnan i den **avancerade OCH-operationen**.

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Steg 4: Tillämpa villkor och filtrera uppgifter

När det sammansatta villkoret är klart anropar vi `Filter` för att **filtrera projektuppgifter** baserat på den kombinerade logiken.

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Steg 5: Visa filtrerade uppgifter

Till sist visar vi de uppgifter som uppfyllde **alla** villkor. Du kan ersätta `Console.WriteLine`-anropen med någon anpassad bearbetning du behöver.

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## Vanliga problem och lösningar

| Problem | Varför det händer | Snabb åtgärd |
|-------|----------------|-----------|
| `Filter`-metoden hittades inte | Saknar `using Aspose.Tasks.Util;` | Se till att Util-namnrymden importeras (se Importera namnrymder). |
| Inga uppgifter returneras | Villkoren är för restriktiva (t.ex. filtrering av sammanfattningsuppgifter när inga finns) | Verifiera att projektet faktiskt innehåller sammanfattningsuppgifter eller justera villkoren. |
| NullReferenceException | `coll.Tasks` innehåller null‑poster | `NotNullCondition` skyddar redan mot detta; behåll den i OCH‑kedjan. |

## Vanliga frågor

### Q1: Vad är Aspose.Tasks för .NET?

Aspose.Tasks för .NET är ett robust API som låter utvecklare manipulera Microsoft Project‑filer programmässigt i .NET‑applikationer.

### Q2: Kan jag använda mer än två villkor med Util.And?

Ja, Util.And kan användas för att kombinera ett godtyckligt antal villkor för att skapa komplexa filterkriterier.

### Q3: Finns det en gratis provversion av Aspose.Tasks för .NET?

Ja, du kan ladda ner en gratis provversion **[här](https://releases.aspose.com/)**.

### Q4: Var kan jag hitta dokumentation för Aspose.Tasks för .NET?

Du kan hitta dokumentationen **[här](https://reference.aspose.com/tasks/net/)**.

### Q5: Hur kan jag få support för Aspose.Tasks för .NET?

Du kan få support via Aspose.Tasks‑community‑forumet **[här](https://forum.aspose.com/c/tasks/15)**.

**Additional Q&A**

**Q: Hur filtrerar jag uppgifter efter anpassade fältvärden?**  
A: Skapa ett `CustomFieldCondition` (eller implementera `ICondition<Task>`) och lägg till det i `And<T>`‑kedjan.

**Q: Kan jag använda samma tillvägagångssätt för att filtrera resurser?**  
A: Ja—byt ut `Task` mot `Resource` och använd motsvarande villkorsklasser.

## Slutsats

Genom att följa stegen ovan vet du nu **hur man kombinerar flera villkor** med hjälp av den **avancerade OCH-operationen** i Aspose.Tasks för .NET. Denna teknik låter dig **filtrera projektuppgifter** effektivt, oavsett om du riktar in dig på sammanfattningsobjekt, icke‑null‑poster eller någon anpassad kriterium du definierar.

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Tasks for .NET (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}