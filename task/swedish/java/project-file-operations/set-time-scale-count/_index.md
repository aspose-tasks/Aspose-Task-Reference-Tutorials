---
title: Bemästra MS Project Time Scale Count i Aspose.Tasks
linktitle: Ställ in tidsskalaräkning i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du effektivt hanterar tidsskalaräkning i MS Project med Aspose.Tasks för Java. Optimera projektvisualisering och hantering utan ansträngning.
type: docs
weight: 22
url: /sv/java/project-file-operations/set-time-scale-count/
---
## Introduktion
Hantering av tidsskalaräkning i MS Project kan avsevärt påverka projektvisualisering och -hantering. Med Aspose.Tasks för Java, ett kraftfullt API för att hantera projektledningsuppgifter programmatiskt, kan du effektivt manipulera tidsskaleräkning för att skräddarsy projektvyer efter dina specifika behov.
## Förutsättningar
Innan du börjar, se till att du har följande på plats:
1. Java Development Environment: Se till att du har Java Development Kit (JDK) installerat på ditt system.
2.  Aspose.Tasks for Java Library: Ladda ner och installera Aspose.Tasks for Java-biblioteket. Du kan få det från[här](https://releases.aspose.com/tasks/java/).
3. Grundläggande kunskaper om Java-programmering: Bekantskap med programmeringsspråket Java kommer att vara fördelaktigt.

## Importera paket
Importera nödvändiga paket till ditt Java-projekt:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Steg 1: Ställ in datakatalog
Definiera sökvägen till datakatalogen där dina projektfiler kommer att lagras:
```java
String dataDir = "Your Data Directory";
```
 Byta ut`"Your Data Directory"` med sökvägen till din datakatalog.
## Steg 2: Skapa projektinstans
 Instantiera en ny`Project` objekt:
```java
Project project = new Project();
```
Detta skapar ett nytt projektobjekt.
## Steg 3: Konfigurera Gantt-diagramvy
 Skapa en`GanttChartView` objekt för att konfigurera Gantt-diagramvyn:
```java
GanttChartView view = new GanttChartView();
```
## Steg 4: Ställ in tidsskala för bottennivå
Ställ in antalet och markeringars synlighet för den nedre tidsskalenivån:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Detta anger antalet intervaller och om bockningar ska visas för den nedre nivån.
## Steg 5: Ställ in tidsskala för mellannivå
Konfigurera på samma sätt den mellersta tidsskalanivån:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Steg 6: Lägg till vy till projektet
Lägg till den konfigurerade vyn till projektet:
```java
project.getViews().add(view);
```
Detta lägger till den anpassade vyn till projektet.
## Steg 7: Lägg till testdata till projektet
Lägg till några testdata till projektet för demonstration:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Detta skapar två uppgifter med specificerad varaktighet.
## Steg 8: Spara projektet som PDF
Spara projektet som en PDF-fil:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Detta sparar projektet med de tillämpade konfigurationerna till en PDF-fil.

## Slutsats
Effektiv hantering av tidsskaleräkning i MS Project med Aspose.Tasks för Java ger dig möjlighet att anpassa projektvyer för bättre visualisering och hantering.
## FAQ's
### F: Kan Aspose.Tasks för Java hantera storskaliga projektfiler?
S: Ja, Aspose.Tasks för Java kan hantera storskaliga projektfiler effektivt.
### F: Är Aspose.Tasks för Java kompatibelt med olika Java IDE?
S: Ja, Aspose.Tasks för Java fungerar sömlöst med populära Java Integrated Development Environments (IDE) som Eclipse och IntelliJ IDEA.
### F: Kan jag anpassa utseendet på Gantt-diagram med Aspose.Tasks för Java?
S: Absolut, Aspose.Tasks för Java tillhandahåller omfattande möjligheter för att anpassa utseendet på Gantt-diagram enligt dina krav.
### F: Finns det en testversion tillgänglig för Aspose.Tasks för Java?
 S: Ja, du kan få en gratis testversion från[här](https://releases.aspose.com/).
### F: Var kan jag få support för Aspose.Tasks för Java?
 S: Du kan hitta support och hjälp på Aspose.Tasks-forumet[här](https://forum.aspose.com/c/tasks/15).