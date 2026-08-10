---
date: 2026-06-25
description: Lär dig hur du lägger till en uppgift och uppdaterar MPP-filer med Aspose.Tasks
  för Java, ett Java-bibliotek för projektledning som låter dig skapa Microsoft Project-uppgiftsfiler
  och spara projektet som MPP.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Hur man lägger till en uppgift och uppdaterar MPP-fil i Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hur man lägger till en uppgift och uppdaterar MPP-fil i Aspose.Tasks
url: /sv/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till uppgift och uppdaterar MPP-fil i Aspose.Tasks

## Introduktion
I den här handledningen kommer du att lära dig **hur man lägger till uppgift** i en befintlig Microsoft Project (MPP)-fil och sedan spara det uppdaterade schemat med Aspose.Tasks för Java, ett ledande **java projektstyrningsbibliotek**. Oavsett om du bygger en anpassad schemaläggare, automatiserar massuppdateringar eller integrerar projektdata i ett större system, visar steg‑för‑steg‑guiden nedan exakt hur du laddar ett projekt, infogar en ny uppgift, anger dess datum och sparar resultatet som ett nytt MPP‑dokument.

## Snabba svar
- **Vad betyder “how to add task” i detta sammanhang?** Det betyder att programatiskt skapa ett nytt arbetsobjekt i en befintlig MPP‑fil.  
- **Vilket bibliotek hanterar operationen?** Aspose.Tasks for Java, ett robust java projektstyrningsbibliotek.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Kan jag spara resultatet som MPP?** Ja—använd `project.save(..., SaveFileFormat.Mpp)` för att **spara projekt som mpp**.  
- **Vilken Java-version krävs?** Java 8 eller senare.

## Vad är “how to add task” i en MPP-fil?
Att lägga till en uppgift innebär att infoga ett nytt arbetsobjekt i projektets hierarki, definiera dess start‑/slutdatum och spara förändringen tillbaka till MPP‑filen. Aspose.Tasks abstraherar de lågnivå‑filformatdetaljerna, så att du kan fokusera på affärslogik medan det automatiskt hanterar resursallokeringar, kalendrar och beroendekalkyler. Det uppdaterar också eventuella relaterade tilldelningar och räknar om projektschemat för att bibehålla konsistens mellan beroende uppgifter.

## Varför använda Aspose.Tasks för Java?
- **Full kompatibilitet**: Stöder 100 % av funktionerna i Microsoft Project 2007‑2021 (över 150 uppgiftstyper och 200 resursfält).  
- **Zero‑dependency**: Inga COM-, Office- eller inhemska bibliotek krävs—ren Java‑API körs var JRE än finns.  
- **Rik funktionuppsättning**: Inkluderar uppgiftslänkning, resursallokering, anpassade fält och inbyggd rapportering.  
- **Hög prestanda**: Bearbetar projekt med upp till 10 000 uppgifter med mindre än 200 MB RAM, vilket gör det idealiskt för server‑sidig automatisering.

## Förutsättningar
1. **Java-utvecklingsmiljö** – JDK 8+ installerad och konfigurerad.  
2. **Aspose.Tasks for Java** – Ladda ner från [download page](https://releases.aspose.com/tasks/java/).  
3. **Grundläggande Java‑kunskaper** – Bekantskap med klasser, objekt och datumhantering.  

## Importera paket
Först importerar du de klasser du behöver. Detta ger dig åtkomst till projektmanipulation, uppgiftsegenskaper och datumhantering.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` representerar en Microsoft Project‑fil som är laddad i minnet. `SaveFileFormat` listar de format du kan spara till, såsom MPP eller PDF. `Task` modellerar ett enskilt arbetsobjekt inom projektets hierarki. `Tsk` tillhandahåller konstanter för uppgiftsfält som används vid sättning eller hämtning av värden. `Calendar` erbjuder datum‑tid‑verktyg för att definiera scheman.

## Steg 1: Definiera datakatalog
```java
String dataDir = "Your Data Directory";
```  
Byt ut `"Your Data Directory"` mot den absoluta sökvägen där din käll‑MPP‑fil finns.

## Steg 2: Läs befintligt projekt
`Project`‑klassen är Aspose.Tasks kärnobjekt som representerar en Microsoft Project‑fil i minnet.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
Konstruktorn laddar **SampleMSP2010.mpp**, vilket ger dig en fullt manipulerbar objektmodell.

## Steg 3: Skapa en ny uppgift (how to add task)
`Task`‑klassen representerar ett enskilt arbetsobjekt i projektets hierarki.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Denna rad **creates task in mpp** genom att lägga till ett barn med namnet *Task1* till rotuppgiften.

## Steg 4: Ställ in start- och slutdatum
`Calendar`‑klassen erbjuder datum‑tid‑verktyg; månader är nollbaserade (t.ex. `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Här definierar vi schemat för den nyinfogade uppgiften. Justera datumen så de matchar ditt projekts tidslinje.

## Steg 5: Spara projektet (save project as mpp)
`SaveFileFormat.Mpp` talar om för Aspose.Tasks att skriva filen tillbaka i Microsoft Projects inhemska format.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
Det uppdaterade projektet, som nu innehåller den nya uppgiften, sparas som **AfterLinking.mpp**.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Fil ej hittad** | Verifiera att `dataDir` slutar med en sökvägsseparator (`/` eller `\\`) och att filnamnet är korrekt. |
| **Felaktiga datum** | Kom ihåg att `Calendar`‑månader är nollbaserade; `Calendar.JULY` är korrekt för juli. |
| **Licensundantag** | Installera en giltig Aspose.Tasks‑licens innan du anropar något API för att undvika utvärderingsvattenstämplar. |

## Vanliga frågor
**Q: Hur lägger jag till flera uppgifter på en gång?**  
A: Loopa över en samling av uppgiftsnamn och upprepa “create task”-blocket i loopen.

**Q: Kan jag ange anpassade fält för den nya uppgiften?**  
A: Ja—använd `task.set(Tsk.CUSTOM_FIELD_x, value)` där *x* är fältindexet.

**Q: Är det möjligt att kopiera en befintlig uppgift som mall?**  
A: Klona källuppgiften (`Task cloned = sourceTask.clone();`) och lägg sedan till den i önskad förälder.

**Q: Vad gör jag om jag måste uppdatera en befintlig uppgift istället för att lägga till en ny?**  
A: Hämta uppgiften med ID (`Task existing = project.getRootTask().getChildren().getById(id);`) och ändra dess egenskaper.

**Q: Stöder Aspose.Tasks att spara till andra format som PDF eller PNG?**  
A: Ja—använd `project.save("output.pdf", SaveFileFormat.Pdf);` eller `SaveFileFormat.Png` för visuella representationer.

---

**Senast uppdaterad:** 2026-06-25  
**Testad med:** Aspose.Tasks for Java 24.12  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skapar MPP-fil – Skapa & spara tomt projekt i MPP-format med Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Hur man skapar projekt – Ställ in nya uppgiftsattribut med Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Skapa uppgiftslista Java – MS Project-baslinje med Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}