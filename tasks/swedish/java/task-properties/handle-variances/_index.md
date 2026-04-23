---
date: 2026-02-20
description: Lär dig hur du anger projektets startdatum och hanterar projektavvikelser
  med Aspose.Tasks för Java. Denna guide visar också hur du effektivt anger uppgiftens
  varaktighet.
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ställ in projektets startdatum och hantera uppgiftsavvikelser Aspose.Tasks
url: /sv/java/task-properties/handle-variances/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ange projektets startdatum & hantera uppgiftsavvikelser Aspose.Tasks

## Introduction
I projektledningsvärlden är **set project start date** en av de första åtgärderna du gör för att ge ditt schema en solid grund. Aspose.Tasks for Java gör detta steg—och den efterföljande hanteringen av uppgiftsavvikelser—enkelt och pålitligt. I den här handledningen kommer du att lära dig hur du anger projektets startdatum, anger uppgiftens varaktighet och hanterar projektavvikelser effektivt.

## Quick Answers
- **Vad är den primära metoden för att ange projektets startdatum?** Use `project.set(Prj.START_DATE, …)` with a `java.util.Calendar` instance.  
- **Vilken klass representerar en baseline för avvikelsespårning?** `BaselineType.Baseline`.  
- **Kan jag justera uppgiftens start- och stoppdatum efter att baseline har satts?** Yes, simply update `Tsk.START` and `Tsk.STOP`.  
- **Behöver jag en licens för utvecklingsbruk?** A temporary license is available for evaluation.  
- **Vilken version av Aspose.Tasks fungerar med denna kod?** The latest Aspose.Tasks for Java release.

## What is **set project start date**?
Att ange projektets startdatum definierar kalenderdagen från vilken alla uppgiftsdatum beräknas. Det påverkar schemaläggningsberäkningar, kritisk‑väg‑analys och skapandet av baseline, vilket gör det avgörande för exakt avvikelsehantering.

## Why set project start date and manage variances?
- **Förutsägbarhet:** Etablerar en känd baseline för att jämföra faktisk framdrift.  
- **Flexibilitet:** Gör det möjligt att justera enskilda uppgiftsdatum utan att förlora den ursprungliga planen.  
- **Rapportering:** Möjliggör tydliga avvikelserapporter som framhäver schemaavvikelser eller tidiga avslut.  

## Prerequisites
Innan vi dyker ner, se till att du har följande:

- Java-utvecklingsmiljö – en installerad JDK och en IDE eller byggverktyg redo.  
- Aspose.Tasks-bibliotek – download the library **[here](https://releases.aspose.com/tasks/java/)**.  

## Import Packages
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Setting Up the Project
Skapa en ny `Project`-instans som kommer att innehålla alla uppgifter och schemainformation.

```java
Project project = new Project();
```

## Step 2: Adding a Task
Lägg till en uppgift under rotuppgiften. Detta blir arbetsobjektet som vi senare justerar.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Step 3: Setting Start Date and Duration
Definiera projektets startdatum och ge uppgiften en varaktighet. Detta demonstrerar **set task duration** i praktiken.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## Step 4: Setting Baseline
Skapa en baseline så att du senare kan jämföra planerade mot faktiska datum—avgörande för **manage project variances**.

```java
project.setBaseline(BaselineType.Baseline);
```

## Step 5: Adjusting Task Start and Stop Dates
Ändra uppgiftens start- och stoppdatum för att simulera ett avvikelsesscenario.

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*Känn dig fri att justera datumen och varaktigheterna så att de matchar ditt projekts specifika behov.*

## Common Issues & Tips
- **Baseline måste sättas innan datum justeras.** Om du ändrar datum först, kommer baseline att fånga det ändrade schemat istället för den ursprungliga planen.  
- **Kalendermånader är nollbaserade.** Kom ihåg att `Calendar.FEBRUARY` motsvarar månad 1, inte 2.  
- **Varaktighetsenheter:** `project.getDuration(2)` skapar en varaktighet på två dagar som standard; justera enheten om du behöver timmar eller veckor.

## Conclusion
Genom att behärska hur man **set project start date**, **set task duration** och **manage project variances**, får du full kontroll över ditt projekts schema med Aspose.Tasks for Java. Stegen ovan ger en solid grund som du kan bygga vidare på för mer komplexa scenarier såsom flerfasprojekt, resursallokering och automatiserad rapportering.

## Frequently Asked Questions
### Är Aspose.Tasks lämpligt för alla projektledningsbehov?
Aspose.Tasks är ett mångsidigt verktyg som passar ett brett spektrum av projektledningskrav, och erbjuder flexibilitet samt robusta funktioner.

### Kan jag integrera Aspose.Tasks i mitt befintliga Java‑projekt?
Ja, du kan enkelt integrera Aspose.Tasks i ditt Java‑projekt genom att följa den medföljande dokumentationen **[here](https://reference.aspose.com/tasks/java/)**.

### Finns en tillfällig licens tillgänglig för Aspose.Tasks?
Ja, du kan skaffa en tillfällig licens för Aspose.Tasks **[here](https://purchase.aspose.com/temporary-license/)**.

### Var kan jag få support för Aspose.Tasks?
För support och diskussioner, besök Aspose.Tasks‑forumet **[here](https://forum.aspose.com/c/tasks/15)**.

### Kan jag ladda ner Aspose.Tasks för Java?
Ja, ladda ner den senaste versionen av Aspose.Tasks för Java **[here](https://releases.aspose.com/tasks/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2026-02-20  
**Testat med:** Aspose.Tasks senaste Java‑utgåva  
**Författare:** Aspose