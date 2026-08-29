---
date: 2026-08-29
description: Lär dig hur du läser baslinjedata och schemalägger uppgifter med Aspose.Tasks
  för Java, så att du kan jämföra planerat med faktiskt framsteg på ett effektivt
  sätt.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Schemaläggning av baslinjeuppgifter i Aspose.Tasks
og_description: Lär dig hur du läser baslinjedata och schemalägger uppgifter med Aspose.Tasks
  för Java, vilket möjliggör exakt jämförelse av planerat och faktiskt framsteg.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Hur man läser baslinje och schemalägger uppgifter med Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Hur man läser baslinje och schemalägger uppgifter med Aspose.Tasks
url: /sv/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser baslinje och schemalägger uppgifter med Aspose.Tasks

I den här guiden kommer du att upptäcka **hur man läser baslinje**-information och schemalägger uppgifter programmässigt med Aspose.Tasks för Java. I slutet av handledningen kommer du att kunna fånga den ursprungliga projektplanen, jämföra den med faktisk framdrift och generera avvikelserapporter — allt utan att behöva ha Microsoft Project installerat.

## Introduktion till projektledningsbaslinje
Att hantera en **projektledningsbaslinje** är en hörnsten i effektiv projektledning. Den låter dig fånga den ursprungliga planen och senare jämföra **planerad vs faktisk framdrift** så att du kan upptäcka avvikelser tidigt. I den här handledningen går vi igenom hur man schemalägger uppgiftsbaslinjer med Aspose.Tasks för Java, vilket ger dig verktygen för att **hantera projektbaslinjer** med självförtroende och hålla dina projekt på rätt spår.

## Snabba svar
- **Vad representerar en projektledningsbaslinje?**  
  Den registrerar den godkända tidsplanen, kostnaden och omfattningen vid projektstart och ger en referens för avvikelseranalys.  
- **Vilket bibliotek hanterar baslinjeschemaläggning i Java?**  
  Aspose.Tasks för Java erbjuder ett rent Java‑API som stöder 45+ in‑ och utdataformat och projekt med upp till 100 000 uppgifter.  
- **Behöver jag en licens för att köra koden?**  
  En gratis provversion fungerar för testning; en kommersiell licens krävs för produktionsanvändning.  
- **Vad är de viktigaste förutsättningarna?**  
  Java Development Kit (JDK) 11+ och Aspose.Tasks för Java‑biblioteket.  
- **Kan jag se baslinjedatum efter att de har satts?**  
  Ja — använd `TaskBaseline`‑objektet för att läsa start-, slut‑ och varaktighetsvärden.

## Vad är en projektledningsbaslinje?
En projektledningsbaslinje registrerar den godkända tidsplanen, budgeten och omfattningen vid start av genomförandet. Den fungerar som en referenspunkt för att mäta prestanda och identifiera avvikelser under hela projektets livscykel. Den inkluderar planerade start- och slutdatum, total kostnad och omfattningsdetaljer, vilket ger en omfattande ögonblicksbild för framtida jämförelser.

## Varför använda Aspose.Tasks för baslinjeschemaläggning?
Aspose.Tasks tillhandahåller ett rent Java‑API som fungerar utan att Microsoft Project är installerat. Det stöder **45+ in‑ och utdataformat**, kan bearbeta projekt med **upp till 100 000 uppgifter** i minnes‑effektivt läge, och erbjuder inbyggda metoder för att läsa och skriva baslinjedata — vilket gör automatiserad rapportering och integration enkel.

## Förutsättningar
- **Java Development Kit (JDK)** – installera JDK 11 eller senare. Du kan ladda ner det från [webbplatsen](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks för Java‑bibliotek** – ladda ner den senaste versionen från [nedladdningssidan](https://releases.aspose.com/tasks/java/) och lägg till JAR‑filen i ditt projekts classpath.

## Importera paket
`Project`, `Task` och `TaskBaseline`‑klasserna finns i `com.aspose.tasks`‑namnutrymmet. Importera dem högst upp i din källfil:

`Project`‑klassen är Aspose.Tasks översta objekt som representerar en enskild projektfil i minnet. Den ger åtkomst till uppgifter, resurser och baslinjesamlingar.

## Hur läser man baslinje?
Läs in projektet och fråga sedan `TaskBaseline`‑samlingen för varje uppgift. `TaskBaseline`‑objektet returnerar baslinjens start, slut och varaktighet som fångades när du anropade `setBaseline`. Detta direkta tillvägagångssätt låter dig läsa baslinjevärden utan att parsra XML‑ eller binära filer.

## Steg 1: skapa en ny projektinstans
`Project`‑klassen representerar hela projektfilen i minnet.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## Steg 2: definiera en uppgift och sätt baslinje
`Task` representerar ett individuellt arbetsobjekt, och `setBaseline` fångar dess aktuella schema som en baslinje.
```java
Project project = new Project();
```

## Steg 3: åtkomst till baslinjeinformation
`TaskBaseline` innehåller de sparade start-, slut- och varaktighetsvärdena för en baslinje.
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Steg 4: visa baslinjens varaktighet
`Duration` representerar tidslängden för en uppgift eller baslinje.
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Steg 5: visa baslinjens startdatum
`Start` är baslinjens planerade startdatum.
```java
System.out.println(baseline.getDuration().toString());
```

## Steg 6: visa baslinjens slutdatum
`Finish` är baslinjens planerade slutförandedatum.
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Vanliga problem och lösningar
- **Baslinje inte satt:** Se till att du anropar `project.setBaseline(BaselineType.Baseline)` **efter** att ha lagt till uppgifter; annars blir baslinjesamlingen tom.  
- **Null‑värden:** Om `task.getBaselines()` returnerar en tom lista, verifiera att uppgiften har lagts till i projektets hierarki innan baslinjen sätts.  
- **Datumformat:** Metoderna `getStart()` och `getFinish()` returnerar `java.util.Date`‑objekt. Använd `SimpleDateFormat` om du behöver ett eget visningsformat.

## Vanliga frågor
**Q: Hur skapar jag en ny projektinstans i Aspose.Tasks?**  
A: Instansiera `Project`‑klassen (`Project project = new Project();`). Detta skapar en ny projektfil redo för uppgifter och baslinjer.

**Q: Vad är skillnaden mellan `BaselineType.Baseline` och andra baslinjetyper?**  
A: `BaselineType.Baseline` avser den primära baslinjen (Baseline 1). Aspose.Tasks stödjer även Baseline 2‑10 för ytterligare ögonblicksbilder.

**Q: Kan jag exportera baslinjedatan till Excel eller CSV?**  
A: Ja, du kan iterera över `TaskBaseline`‑objekt och skriva värdena till en CSV‑fil med standard Java‑I/O.

**Q: Påverkar inställning av en baslinje befintliga uppgiftsdatum?**  
A: Att sätta en baslinje fångar de aktuella datumen men ändrar inte uppgiftens aktiva schema. Du kan fortfarande justera start‑/slutdatum efter att baslinjen har satts.

**Q: Är det möjligt att jämföra flera baslinjer programmässigt?**  
A: Absolut. Hämta varje baslinje via `task.getBaselines().get(index)` och jämför deras `Start`, `Finish` och `Duration`‑egenskaper.

---

**Senast uppdaterad:** 2026-08-29  
**Testat med:** Aspose.Tasks for Java 24.12  
**Författare:** Aspose  








```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Relaterade handledningar

- [Skapa uppgiftslista Java – MS Project-baslinje med Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Hur man ställer in baslinjevaraktighet i Aspose.Tasks för Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Skapa MPP-projekt Java – Ändra uppgiftens framsteg med Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}