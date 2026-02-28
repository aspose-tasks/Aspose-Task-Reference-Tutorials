---
date: 2026-02-28
description: Lär dig hur du använder Aspose.Tasks för Java för att hantera tidsfasad
  uppgiftsdata, ladda ner biblioteket, prova det gratis och effektivisera projektspårning.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur du använder Aspose.Tasks för att hantera tidsfasad data för uppgifter (Java)
url: /sv/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man använder Aspose.Tasks för tidsfasad uppgiftsdata

## Introduction
Om du letar efter **how to use Aspose** för att ha ett fast grepp om ditt projekts schema, har du kommit till rätt plats. Precisionsspårning av tidsfasad uppgiftsdata är en hörnsten i framgångsrik projektledning, och Aspose.Tasks for Java ger dig verktygen du behöver för att automatisera processen. I den här handledningen går vi igenom ett komplett, end‑to‑end‑exempel som visar hur du använder Aspose.Tasks för att skapa ett projekt, tilldela resurser, sätta baslinjer och slutligen hämta och visa tidsfasad data.

## Quick Answers
- **What does “timephased data” mean?** Det är data uppdelad efter tidsintervall (dagar, veckor, månader) som visar arbete, kostnad eller återstående arbete över projektets tidslinje.  
- **Which library provides this capability?** Aspose.Tasks for Java.  
- **Do I need a license to run the sample?** En gratis provversion fungerar för utveckling; en licens krävs för produktion.  
- **What Java version is required?** Java 8 eller högre.  
- **Can I export the results to Excel?** Ja – du kan iterera `TimephasedData`‑samlingen och skriva värden till vilket format du behöver.

## What is Task Timephased Data?
Task timephased data representerar mängden arbete (eller kostnad) som är schemalagd för en uppgift under varje tidsintervall i projektkalendern. Det gör det möjligt att se hur arbete fördelas, upptäcka överallokering och jämföra planerat mot faktiskt framsteg.

## Why Use Aspose.Tasks to Manage Timephased Data?
- **Full control** – programatiskt skapa, modifiera och fråga tidsfasad information utan att öppna Microsoft Project.  
- **Cross‑platform** – fungerar på alla operativsystem som stödjer Java.  
- **No COM dependencies** – ideal för server‑sidig automatisering.  
- **Rich API** – stödjer baslinjer, arbetskonturer och anpassade fält direkt ur lådan.

## Prerequisites
Innan du dyker ner i koden, se till att du har:

- **Java Development Environment** – JDK 8+ installerat och `JAVA_HOME` konfigurerat.  
- **Aspose.Tasks for Java Library** – Ladda ner och inkludera Aspose.Tasks‑biblioteket i ditt projekt. Du kan hitta biblioteket [here](https://releases.aspose.com/tasks/java/).  
- **Document Directory** – En mapp på din maskin där exempelprojektfilen (`project.xml`) kommer att läsas från och skrivas till.

## Import Packages
I ditt Java‑projekt, importera de nödvändiga Aspose.Tasks‑klasserna:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Explanation:* Vi skapar en `Project`‑instans, initierar en `Calendar` till önskat startdatum och tilldelar den till projektets `START_DATE`‑egenskap.

## Step 2: Define Task and Resource
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Explanation:* En ny uppgift med namnet **Task** läggs till under rotuppgiften. Vi skapar också en resurs kallad **Rsc** och sätter dess standard- och övertidspriser.

## Step 3: Set Task Duration
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Explanation:* Uppgiften är schemalagd för en varaktighet på **6 dagar**.

## Step 4: Assign Resource to Task
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Explanation:* Den tidigare definierade resursen länkas till uppgiften via en `ResourceAssignment`.

## Step 5: Configure Resource Assignment
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Explanation:* Vi sätter tilldelningens stopp‑ och återupptagningsdatum (med ett platshållarvärde) och tillämpar en **Back‑Loaded** arbetskontur, vilket flyttar mer arbete mot slutet av tilldelningen.

## Step 6: Set Baseline
```java
project.setBaseline(BaselineType.Baseline);
```
*Explanation:* Att fånga en baslinje gör att du kan jämföra planerade mot faktiska värden senare.

## Step 7: Update Task Completion
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Explanation:* Uppgiften markeras som **50 % complete**, vilket kommer att påverka beräkningarna av återstående arbete.

## Step 8: Retrieve Timephased Data
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Explanation:* Detta anrop hämtar **remaining work** för tilldelningen, uppdelat efter projektets tidsintervall.

## Step 9: Display Timephased Data
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Explanation:* Vi skriver helt enkelt ut antalet tidsfasade poster och värdet på den första posten. I ett verkligt scenario skulle du iterera listan och exportera data till en rapport eller UI.

## Common Issues and Solutions
- **NullPointerException on `getTimephasedData`** – Säkerställ att tilldelningens `START`‑ och `FINISH`‑datum är satta innan metoden anropas.  
- **Incorrect work contour** – Verifiera att den `WorkContourType` du väljer matchar din schemaläggningsstrategi; `BackLoaded` är bara ett av flera alternativ.  
- **Baseline not reflecting changes** – Kom ihåg att anropa `project.setBaseline` *after* du har definierat uppgifter, resurser och tilldelningar.

## Frequently Asked Questions
### Q: Kan jag använda Aspose.Tasks för Java i vilket Java‑projekt som helst?
A: Ja, Aspose.Tasks för Java är kompatibel med alla Java‑baserade projekt.

### Q: Var kan jag hitta ytterligare support för Aspose.Tasks för Java?
A: Besök [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) för support och diskussioner.

### Q: Finns det en gratis provversion tillgänglig för Aspose.Tasks för Java?
A: Ja, du kan utforska en gratis provversion [here](https://releases.aspose.com/).

### Q: Hur kan jag skaffa en tillfällig licens för Aspose.Tasks för Java?
A: Du kan skaffa en tillfällig licens [here](https://purchase.aspose.com/temporary-license/).

### Q: Var kan jag köpa Aspose.Tasks för Java?
A: Du kan köpa Aspose.Tasks för Java [here](https://purchase.aspose.com/buy).

---

**Senast uppdaterad:** 2026-02-28  
**Testad med:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}