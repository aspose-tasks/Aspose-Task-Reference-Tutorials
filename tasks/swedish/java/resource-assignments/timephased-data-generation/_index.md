---
date: 2026-01-10
description: Lär dig hur du ändrar kontur och genererar tidsfasade data för resursallokeringar
  med Aspose.Tasks för Java, vilket förbättrar projektledningens effektivitet.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man ändrar kontur i Aspose.Tasks för tidsfasade data
url: /sv/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ändrar kontur i Aspose.Tasks för tidsfasdata

## Introduktion
I den här handledningen kommer du att upptäcka **hur man ändrar kontur** för en resursallokering och generera tidsfasdata med Aspose.Tasks för Java. Tidsfasdata visar hur arbetet fördelas över projektets tidslinje, vilket gör det möjligt att finjustera scheman, balansera arbetsbelastningar och fatta datadrivna beslut.

## Snabba svar
- **Vad är en kontur?** En arbetskontur definierar hur ansträngning fördelas över en uppgifts varaktighet (t.ex. Flat, Turtle, Bell).  
- **Varför ändra en kontur?** För att återspegla realistiska arbetsmönster som front‑loading eller back‑loading av ansträngning.  
- **Vilket bibliotek krävs?** Aspose.Tasks för Java (valfri nyare version).  
- **Behöver jag en licens?** Ja, en giltig Aspose.Tasks‑licens krävs för produktionsanvändning.  
- **Kan jag se resultaten i konsolen?** Exemplet skriver ut startdatum och värden för varje tidsfassegment.

## Vad är “hur man ändrar kontur”?
Att ändra en kontur innebär att uppdatera egenskapen `WORK_CONTOUR` för en `ResourceAssignment`. Aspose.Tasks stöder flera fördefinierade konturer (Flat, Turtle, Bell, etc.) som påverkar hur arbete fördelas över tid.

## Varför använda Aspose.Tasks för att generera tidsfasdata?
- **Noggrann rapportering:** Exportera exakt arbetsfördelning för rapporteringsverktyg.  
- **Scenarioplanering:** Testa olika konturer utan att ändra det ursprungliga schemat.  
- **Automatisering:** Integrera i CI‑pipelines för att automatiskt validera projektets hälsa.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system. Du kan ladda ner och installera JDK från [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks för Java-bibliotek: Du behöver ha Aspose.Tasks för Java-biblioteket. Du kan ladda ner det från [website](https://releases.aspose.com/tasks/java/).

## Importera paket
Först, låt oss importera de nödvändiga paketen för att arbeta med Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Steg 1: Läs in käll‑MPP‑filen
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Steg 2: Hämta uppgift och resursallokering
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Hur man ändrar kontur – Flat (Standard)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Vanliga problem & tips
- **Konturen uppdateras inte?** Se till att du anropar `firstRA.set(Asn.WORK_CONTOUR, …)` *innan* du hämtar tidsfasdata.
- **Oväntade värden?** Verifiera att uppgiftens start- och slutdatum är korrekt inställda i käll‑MPP‑filen.
- **Prestandatips:** Återanvänd samma `Project`‑instans när du itererar genom flera konturer för att undvika onödig fil‑I/O.

## Vanliga frågor
### Kan jag använda Aspose.Tasks med andra Java‑bibliotek?
Ja, Aspose.Tasks kan integreras med andra Java‑bibliotek för att förbättra projektledningsfunktioner.

### Är Aspose.Tasks lämplig för storskaliga företagsprojekt?
Absolut, Aspose.Tasks är designad för att hantera projekt av alla storlekar, inklusive stora företagsinitiativ.

### Tillhandahåller Aspose.Tasks stöd för olika projektfilformat?
Ja, Aspose.Tasks stöder en mängd olika format, såsom MPP, XML och MPX.

### Kan jag anpassa arbetskonturer enligt mina projektkrav?
Ja, du kan definiera anpassade arbetskonturer för att matcha specifika schemaläggningsbehov.

### Finns det ett community‑forum där jag kan få hjälp med Aspose.Tasks?
Ja, du kan besöka [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för support och diskussioner.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}