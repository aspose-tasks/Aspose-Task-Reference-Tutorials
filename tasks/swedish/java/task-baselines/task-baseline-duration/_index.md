---
date: 2026-08-29
description: Lär dig hur du ställer in baseline duration och spårar project progress
  med Aspose.Tasks for Java. Denna steg‑för‑steg guide hjälper dig att hantera task
  baselines effektivt.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Hur man ställer in Baseline Duration i Aspose.Tasks for Java
og_description: Lär dig hur du ställer in baseline duration och spårar project progress
  med Aspose.Tasks for Java. Följ den här detaljerade guiden för att hantera task
  baselines effektivt.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Hur man ställer in baseline duration för att spåra project progress
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Hur man ställer in baseline duration för att spåra project progress
url: /sv/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in baslinjeduration för att spåra projektframsteg

## Introduktion
Att spåra projektframsteg börjar med en solid baslinje. I den här handledningen kommer du att upptäcka **hur man ställer in baslinjeduration** för uppgifter i Microsoft Project‑filer med hjälp av Aspose.Tasks‑biblioteket för Java, och förstå varför det är viktigt att etablera en baslinje tidigt för att övervaka schemaläggningsavvikelser, kostnadsavvikelser och resursöverskridanden under projektets hela livscykel.

## Snabba svar
- **Vad betyder “set baseline”?** Det registrerar den ursprungliga start‑, slut‑ och varaktigheten för en uppgift så att du kan jämföra framtida förändringar.  
- **Vilken Aspose.Tasks‑klass skapar ett projekt?** `Project`‑klassen – du kommer också att lära dig hur du **skapar en projektinstans** på rätt sätt.  
- **Behöver jag en licens för att köra koden?** En gratis utvärderingslicens fungerar för testning; en kommersiell licens krävs för produktion.  
- **Kan jag hämta interim‑baslinjer?** Ja, Aspose.Tasks låter dig fråga efter interim‑baslinjer och deras fasta kostnader.  
- **Vilken Java‑version krävs?** Java 8 eller senare rekommenderas.  
- **Hur hjälper detta mig att spåra projektframsteg?** När baslinjen är satt kan du omedelbart jämföra faktiska datum mot den ursprungliga planen med inbyggda rapportfunktioner.

## Vad är en uppgiftsbaslinje och varför sätta den?
En uppgiftsbaslinje fångar det planerade schemat (startdatum, slutdatum och varaktighet) vid en specifik tidpunkt. Genom att sätta en baslinje skapar du en referenspunkt som gör det enkelt att upptäcka schemaläggningsavvikelser, kostnadsöverskridanden och resursöverskridanden när projektet utvecklas.

## Varför använda Aspose.Tasks för baslinjehantering?
Aspose.Tasks erbjuder **full .mpp‑kompatibilitet** – du kan läsa och skriva inhemska Microsoft Project‑filer utan att behöva Microsoft Office installerat. API‑et ger dig programmatisk åtkomst till **50+ in‑ och utdataformat**, stödjer **interim‑baslinjer 1‑10**, och kan hantera **projekt med hundratals sidor** utan att ladda hela filen i minnet, vilket är avgörande för högpresterande batch‑behandling.

## Förutsättningar
1. **Java‑utvecklingsmiljö** – JDK 8+ installerad och konfigurerad.  
2. **Aspose.Tasks för Java** – ladda ner biblioteket från [Aspose.Tasks för Java nedladdningssida](https://releases.aspose.com/tasks/java/).  
3. **IDE eller byggverktyg** – Maven, Gradle eller någon IDE du föredrar.

## Importera paket
Följande import‑satser tar in de centrala Aspose.Tasks‑klasserna som behövs för att arbeta med projekt, uppgifter, baslinjer och tidsfasdata.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Steg 1: skapa en projektinstans
`Project`‑klassen representerar en Microsoft Project‑fil i minnet och är ingångspunkten för alla operationer.

```java
Project project = new Project();
```

## Steg 2: skapa en uppgiftsbaslinje
En `TaskBaseline` lagrar den planerade start‑, slut‑ och varaktigheten för en specifik uppgift.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Steg 3: visa information om uppgiftsbaslinjen
Metoden `getBaselines()` returnerar samlingen av baslinjer som är associerade med en uppgift.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Steg 4: kontrollera interim‑baslinje och fast kostnad
`BaselineType` enumererar de primära och interim‑baslinjerna (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Steg 5: skriv ut tidsfasdata
`TimephasedData` representerar ett stycke schemainformation för ett specifikt tidsintervall.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Genom att följa dessa steg kan du **ställa in baslinjeduration** för vilken uppgift som helst och hämta detaljerad baslinjeinformation med Aspose.Tasks för Java, vilket ger dig ett pålitligt sätt att **spåra projektframsteg** genom hela projektets livscykel.

## Vanliga problem och lösningar
- **Baslinjen visas inte i MS Project:** Se till att du anropade `project.setBaseline(BaselineType.Baseline)` **efter** att uppgiften lagts till.  
- **NullPointerException på `getBaselines()`:** Verifiera att uppgiften lades till i projektet innan baslinjen sattes.  
- **Tidsenhetsmismatch:** Använd `TimeUnitType` för att formatera varaktigheten korrekt, särskilt när du arbetar med anpassade kalendrar.

## Vanliga frågor
### Vad är en uppgiftsbaslinje i MS Project?
En uppgiftsbaslinje i MS Project är en ögonblicksbild av det ursprungliga planerade schemat för en uppgift, inklusive startdatum, slutdatum och varaktighet.

### Varför är hantering av uppgiftsbaslinjer viktig?
Hantera uppgiftsbaslinjer hjälper till att jämföra det planerade schemat med projektets faktiska framsteg, vilket underlättar bättre spårning och beslutsfattande.

### Kan jag ändra en uppgiftsbaslinje när den väl är satt?
Ja, du kan ändra uppgiftsbaslinjer i MS Project för att återspegla förändringar i projektplanen. Det är dock viktigt att dokumentera eventuella avvikelser från den ursprungliga baslinjen.

### Stöder Aspose.Tasks andra projektledningsfunktioner?
Ja, Aspose.Tasks erbjuder ett brett utbud av funktioner för projektledning, inklusive uppgiftsschemaläggning, resursallokering och Gantt‑diagramgenerering.

### Var kan jag hitta support för Aspose.Tasks?
Du kan hitta support för Aspose.Tasks på [Aspose.Tasks‑forumet](https://forum.aspose.com/c/tasks/15), där du kan ställa frågor och interagera med andra användare.

## Ytterligare vanliga frågor
**Q: Måste jag anropa `setBaseline` för varje uppgift individuellt?**  
A: Nej. Att anropa `project.setBaseline(BaselineType.Baseline)` registrerar baslinjen för alla uppgifter i projektet på en gång.

**Q: Hur kan jag sätta en interim‑baslinje för en specifik uppgift?**  
A: Använd `project.setBaseline(BaselineType.Baseline1)` (eller Baseline2‑Baseline10) efter att ha uppdaterat uppgiftens schema.

**Q: Är det möjligt att exportera baslinjedata till CSV?**  
A: Ja. Iterera över `task.getBaselines()` och skriv önskade fält till en CSV‑fil med standard‑Java‑I/O.

**Q: Kan jag läsa en befintlig .mpp‑fil som redan innehåller baslinjer?**  
A: Absolut. Ladda filen med `new Project("myproject.mpp")` och få sedan åtkomst till varje uppgifts baslinjer som visas ovan.

**Q: Hanterar Aspose.Tasks multi‑projekt‑filer?**  
A: Aspose.Tasks arbetar med enskilda .mpp‑filer. För multi‑projekt‑scenarier kombineras projekten programmässigt.

---

**Senast uppdaterad:** 2026-08-29  
**Testad med:** Aspose.Tasks för Java 24.12  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa uppgiftslista Java – MS Project-baslinje med Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Skapa MPP‑projekt Java – Ändra uppgiftens framsteg med Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Projektledningens baslinje – Uppgiftsschemaläggning med Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}