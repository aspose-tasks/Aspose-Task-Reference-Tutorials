---
date: 2026-09-25
description: Lär dig hur du skapar projektschema i Java med Aspose.Tasks. Den här
  guiden visar hur du lägger till summary tasks, hanterar project hierarchy och ställer
  in document directory på ett effektivt sätt.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Skapa uppgifter i Aspose.Tasks
og_description: Lär dig hur du skapar projektschema i Java med Aspose.Tasks. Följ
  steg‑för‑steg‑instruktioner för att lägga till summary tasks, hantera hierarchy
  och ställa in document directory.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Hur man skapar projektschema med Aspose.Tasks för Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Hur man skapar projektschema med Aspose.Tasks för Java
url: /sv/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar projektschema med Aspose.Tasks för Java

## Introduktion
I den här handledningen kommer du att lära dig hur du **skapar projektschema** i en Java‑applikation med Aspose.Tasks. Oavsett om du bygger en enkel att‑göra‑lista eller en komplex företagsnivå‑planerare, går stegen nedan igenom hur du lägger till sammanfattningsuppgifter, hanterar projekt‑hierarkin och anger dokumentkatalogen — allt med tydliga, körbara kodexempel. I slutet har du ett fullständigt strukturerat schema redo för vidare manipulation eller export.

## Snabba svar
- **Vad hanterar Aspose.Tasks?** Den hanterar uppgiftshierarkier, resurser, kalendrar och projektfilformat (MS‑Project, Primavera osv.).  
- **Behöver jag en licens för utveckling?** En gratis tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Vilken Java‑version stöds?** Java 8 och nyare stöds fullt ut.  
- **Kan jag lägga till anpassade fält till uppgifter?** Ja, du kan utöka uppgifter med användardefinierade fält via API‑et.  
- **Finns inbyggt stöd för Gantt‑diagram?** Aspose.Tasks kan exportera till PDF/HTML som inkluderar Gantt‑visualiseringar.

## Vad är ett projektschema i Aspose.Tasks?
Ett projektschema är den kompletta uppsättningen av uppgifter, beroenden och tidslinjer som definierar hur arbetet ska utföras. Aspose.Tasks lagrar denna information i ett `Project`‑objekt som du kan läsa, ändra och spara i olika format. Det inkluderar start‑ och slutdatum, begränsningar och resursallokeringar, vilket möjliggör omfattande planering och rapportering.

## Varför använda Aspose.Tasks för Java‑projektledning?
Aspose.Tasks stöder **30+ in‑ och utdataformat** och kan bearbeta projekt med **upp till 10 000 uppgifter** utan att läsa in hela filen i minnet, vilket ger hög prestanda för storskaliga Java‑projektledningsscenarier.

## Förutsättningar
Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:
- **Java Development Kit (JDK)** – JDK 8 eller senare installerat på din maskin.  
- **Aspose.Tasks for Java library** – Ladda ner och installera biblioteket från [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
- **Integrated Development Environment (IDE)** – Använd Eclipse, IntelliJ IDEA eller någon annan Java‑vänlig IDE du föredrar.

## Importera paket
`Project`, `Task` och relaterade klasser finns i namnområdet `com.aspose.tasks`. Importera dem högst upp i din Java‑fil:

`Project`‑klassen representerar ett komplett projektschema och tillhandahåller metoder för att manipulera uppgifter och resurser.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

`Project`‑klassen är ingångspunkten för alla operationer på en projektfil.

## Hur man skapar projektschema med Aspose.Tasks?

Läs in en ny `Project`‑instans, ange dokumentkatalogen och börja lägga till uppgifter. Detta direkta svar‑avsnitt förklarar huvudflödet: du skapar ett `Project`, konfigurerar dess `RootFolder` (dokumentkatalogen), sedan lägger du till en sammanfattningsuppgift följt av underuppgifter. Alla ändringar hålls i minnet tills du anropar `save` för att spara schemat till en fil.

### Steg 1: ange dokumentkatalogen
Definiera var den resulterande projektfilen ska skrivas. Att ange katalogen tidigt säkerställer att alla efterföljande sparoperationer använder en konsekvent sökväg.

`RootFolder`‑egenskapen specificerar basmappen där projektfiler läses från eller skrivs till.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Steg 2: skapa ett nytt projekt
Instansiera ett nytt `Project`‑objekt som kommer att innehålla ditt schema. Du kan valfritt ange en befintlig filsökväg för att läsa in ett existerande schema för modifiering.

`Project`‑konstruktorn skapar ett tomt schema redo för att lägga till uppgifter.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Steg 3: lägg till en sammanfattningsuppgift
En sammanfattningsuppgift grupperar relaterade underuppgifter och visas som en hopfällbar nod i Gantt‑diagram. Använd `Task`‑klassen och sätt `IsSummary` till `true`.

`addTask`‑metoden skapar en ny uppgift under en angiven förälder och returnerar dess ID.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Steg 4: lägg till en underuppgift
Underuppgifter ärver start‑/slutdatum från sin överordnade sammanfattningsuppgift om du inte åsidosätter dem. Att lägga till en underuppgift är så enkelt som att anropa `addTask` igen och ange föräldra‑ID.

Att anropa `addTask` med ett föräldra‑ID lägger till en underuppgift under den sammanfattningsuppgiften.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Fortsätt att lägga till så många uppgifter och underuppgifter som behövs för ditt projekt. Varje steg bidrar till att bygga en strukturerad projekt‑hierarki som kan exporteras till MS‑Project, PDF eller andra stödda format.

## Vanliga problem och lösningar
- **Problem:** “Dokumentkatalogen hittades inte.”  
  **Solution:** Verifiera att sökvägen du tilldelar `RootFolder` finns på filsystemet och att din Java‑process har skrivrättigheter.
- **Problem:** Underuppgifter visas inte under sammanfattningsuppgiften.  
  **Solution:** Se till att du skickar rätt föräldra‑uppgifts‑ID när du anropar `addTask`. API‑et kräver föräldra‑ID som det andra argumentet.
- **Problem:** Stora projekt orsakar OutOfMemoryError.  
  **Solution:** Aspose.Tasks bearbetar uppgifter i ett strömningsläge; öka JVM‑heap‑storleken (`-Xmx2g`) eller dela upp schemat i flera filer.

## Vanliga frågor
**Q:** Är Aspose.Tasks lämplig för småskaliga projekt?  
**A:** Absolut. Biblioteket skalar från en enkel uppgiftslista till företagsnivå‑scheman med tusentals uppgifter.

**Q:** Var kan jag hitta detaljerad dokumentation för Aspose.Tasks för Java?  
**A:** Se dokumentationen [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**Q:** Hur får jag en tillfällig licens för Aspose.Tasks?  
**A:** Besök [temporary license request page](https://purchase.aspose.com/temporary-license/) för en tidsbegränsad licens som fungerar för utveckling och testning.

**Q:** Kan jag anpassa uppgiftsattribut med Aspose.Tasks?  
**A:** Ja, du kan utöka uppgifter med anpassade fält, tilldela resurser och ändra kalendrar programatiskt.

**Q:** Finns det ett supportcommunity för Aspose.Tasks‑användare?  
**A:** Absolut! Gå med i Aspose.Tasks‑communityn på [the support forum](https://forum.aspose.com/c/tasks/15).

---

**Senast uppdaterad:** 2026-09-25  
**Testat med:** Aspose.Tasks 24.12 for Java  
**Författare:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Relaterade handledningar

- [Ställ in projektets startdatum i MS Project med Aspose.Tasks för Java](/tasks/java/project-properties/write-project-info/)
- [Skapa uppgiftsberoenden för projektledning i Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Hur man lägger till resurs i projekt och skapar resursallokeringar i Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}