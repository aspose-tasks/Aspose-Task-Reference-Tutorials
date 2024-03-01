---
title: Hantera MS Project Properties effektivt i Aspose.Tasks
linktitle: Hantera standardprojektegenskaper i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du hanterar standardegenskaper för MS Project med Aspose.Tasks för Java. Effektivisera ditt arbetsflöde för projektledning utan ansträngning.
type: docs
weight: 11
url: /sv/java/project-management/default-properties/
---
## Introduktion
Vill du effektivisera din projektledningsprocess med Aspose.Tasks för Java? Att hantera standardegenskaper i Microsoft Project-filer kan förbättra effektiviteten avsevärt. I den här handledningen kommer vi att gå igenom steg-för-steg-instruktioner om hur man hanterar standardegenskaper för MS Project med Aspose.Tasks.
## Förutsättningar
Innan vi går in i handledningen, se till att du har följande förutsättningar:
### 1. Java Development Kit (JDK)
   - Se till att JDK är installerat på ditt system.
   -  Du kan ladda ner den från[här](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tasks för Java Library
   - Ladda ner och inkludera Aspose.Tasks för Java-biblioteket i ditt projekt.
   -  Du kan ladda ner den från[hemsida](https://releases.aspose.com/tasks/java/).
## Importera paket
Importera först de nödvändiga paketen i din Java-fil:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
Låt oss dela upp processen i hanterbara steg:
## Steg 1: Ladda projektfilen
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Steg 2: Visa standardegenskaper
```java
// Visa standardegenskaper
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## Steg 3: Ställ in standardegenskaper
```java
// Ställ in standardegenskaper
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## Steg 4: Spara projekt i XML-format
```java
// Spara projektet i XML-format
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## Steg 5: Visa resultat
```java
// Visa resultatet av konvertering.
System.out.println("Process completed Successfully");
```
Genom att följa dessa steg kan du effektivt hantera MS Projects standardegenskaper med Aspose.Tasks för Java.
## Slutsats
I den här handledningen har vi lärt oss hur man hanterar standardegenskaper för MS Project med Aspose.Tasks för Java. Genom att använda dessa tekniker kan du optimera ditt arbetsflöde för projektledning och förbättra produktiviteten och organisationen.
## FAQ's
### F1: Kan jag använda Aspose.Tasks med andra programmeringsspråk?
S1: Ja, Aspose.Tasks stöder olika programmeringsspråk som .NET, Python och Java.
### F2: Är Aspose.Tasks lämpligt för både personligt och företagsbruk?
A2: Absolut! Oavsett om du hanterar små personliga projekt eller storskaliga företagsinitiativ, vänder sig Aspose.Tasks till alla.
### F3: Erbjuder Aspose.Tasks kundsupport?
S3: Ja, du kan hitta hjälp och stöd från samhället på[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
### F4: Kan jag prova Aspose.Tasks innan jag köper?
 A4: Självklart! Du kan utnyttja en gratis provperiod från[hemsida](https://releases.aspose.com/).
### F5: Hur kan jag få en tillfällig licens för Aspose.Tasks?
 A5: Du kan få en tillfällig licens från[köpsidan](https://purchase.aspose.com/temporary-license/) för test- och utvärderingsändamål.