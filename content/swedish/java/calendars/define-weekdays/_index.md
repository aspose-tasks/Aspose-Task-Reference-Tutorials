---
title: Definiera veckodagar i kalendern med Aspose.Tasks
linktitle: Definiera veckodagar i kalendern med Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du definierar veckodagar i MS Project Calendar med Aspose.Tasks för Java. Anpassa arbetsdagar och tider utan ansträngning.
type: docs
weight: 12
url: /sv/java/calendars/define-weekdays/
---
## Introduktion
den här handledningen kommer vi att gå igenom processen att definiera veckodagar i en MS Project Calendar med Aspose.Tasks för Java. Aspose.Tasks är ett kraftfullt Java-bibliotek som gör det möjligt för utvecklare att manipulera Microsoft Project-filer programmatiskt.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar på plats:
1.  Java Development Kit (JDK): Se till att du har JDK installerat på ditt system. Du kan ladda ner den från[Oracle hemsida](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) om du inte redan har gjort det.
2.  Aspose.Tasks for Java Library: Ladda ner och installera Aspose.Tasks for Java-biblioteket från[nedladdningssida](https://releases.aspose.com/tasks/java/). Följ installationsinstruktionerna i dokumentationen.

## Importera paket
För att börja, importera de nödvändiga paketen som krävs för att arbeta med Aspose.Tasks i ditt Java-projekt:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## Steg 1: Skapa en projektinstans
Instantiera ett Project-objekt, som representerar MS Project-filen du kommer att arbeta med:
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## Steg 2: Definiera kalender
Skapa en ny kalenderinstans och lägg till den i projektet:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## Steg 3: Lägg till arbetsdagar
Definiera arbetsdagarna genom att lägga till måndag till torsdag med standardtider:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## Steg 4: Ställ in anpassad arbetsdag
Definiera lördag och söndag som arbetsdagar:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Steg 5: Ställ in kort arbetsdag
Ange fredag som en kort arbetsdag med anpassade arbetstider:
```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```
## Steg 6: Spara projektet
Spara det modifierade projektet till en XML-fil:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Slutsats
Grattis! Du har framgångsrikt definierat veckodagar i en MS Project-kalender med Aspose.Tasks för Java. Du kan nu integrera den här funktionen i dina Java-applikationer för att manipulera MS Project-filer programmatiskt.
## FAQ's
### F1: Kan jag definiera anpassade icke-arbetsdagar med Aspose.Tasks för Java?
 S: Ja, du kan definiera anpassade icke-arbetsdagar genom att ställa in`DayWorking` egendom till`false` för respektive veckodag.
### F2: Hur kan jag lägga till helgdagar i kalendern?
 S: Du kan lägga till helgdagar genom att skapa instanser av`CalendarExceptions`och ange de icke-arbetande datumen.
### F3: Är Aspose.Tasks kompatibel med olika versioner av MS Project-filer?
S: Ja, Aspose.Tasks stöder olika versioner av MS Project-filer, inklusive MPP-, MPT- och XML-format.
### F4: Kan jag ändra befintliga kalendrar i en MS Project-fil?
S: Ja, du kan ladda ett befintligt projekt med kalendrar, göra ändringar och sedan spara ändringarna tillbaka till den ursprungliga filen.
### F5: Ger Aspose.Tasks stöd för återkommande uppgifter?
S: Ja, Aspose.Tasks låter dig arbeta med återkommande uppgifter, inklusive att definiera deras återkommande mönster och varaktighet.