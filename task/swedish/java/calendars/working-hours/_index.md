---
title: Få arbetstimmar från Kalender med Aspose.Tasks
linktitle: Få arbetstimmar från Kalender med Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Extrahera arbetstimmar från MS Projects kalendrar enkelt med Aspose.Tasks för Java. Förenkla projektledningsuppgifter.
type: docs
weight: 13
url: /sv/java/calendars/working-hours/
---
## Introduktion
Att hantera projektkalendrar och extrahera arbetstimmar är avgörande för effektiv projektledning. Aspose.Tasks för Java ger robusta funktioner för att enkelt hämta arbetstimmar från MS Projects kalendrar. I denna handledning guidar vi dig genom processen steg för steg.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
1. Java Development Kit (JDK) installerat på ditt system.
2.  Aspose.Tasks för Java-bibliotek har laddats ner och lagts till i ditt projekt. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/java/).
3. Grundläggande förståelse för programmeringsspråket Java.
## Importera paket
Importera först de nödvändiga paketen för att arbeta med Aspose.Tasks för Java:
```java
import com.aspose.tasks.*;
```
## Steg 1: Ladda projektfilen
Börja med att ladda din MS Project-fil:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Steg 2: Hämta uppgift och kalenderinformation
Extrahera uppgift och kalenderdetaljer från projektet:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Steg 3: Definiera start- och slutdatum
Ställ in start- och slutdatum för uppgiften:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Steg 4: Iterera genom datum
Iterera genom datum inom uppgiftens varaktighet:
```java
java.util.Calendar tempDate = calStartDate;
```
## Steg 5: Beräkna varaktighet
Beräkna varaktighet i minuter, timmar och dagar:
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## Slutsats
den här handledningen har vi täckt hur man hämtar arbetstimmar från en MS Project-kalender med Aspose.Tasks för Java. Genom att följa dessa steg kan du effektivt hantera projektscheman och beräkna uppgiftens varaktighet med lätthet.
## FAQ's
### F: Kan Aspose.Tasks för Java hantera komplexa projektstrukturer?
S: Ja, Aspose.Tasks för Java tillhandahåller omfattande stöd för att hantera komplexa projektstrukturer, inklusive uppgifter, resurser och kalendrar.
### F: Är Aspose.Tasks för Java kompatibelt med olika versioner av MS Project?
S: Absolut, Aspose.Tasks för Java stöder olika versioner av MS Project, vilket säkerställer kompatibilitet mellan olika miljöer.
### F: Kan jag anpassa arbetstider och helgdagar i projektkalendrar?
S: Ja, du kan enkelt anpassa arbetstider och helgdagar efter dina projektkrav med Aspose.Tasks för Java API:er.
### F: Erbjuder Aspose.Tasks för Java support och dokumentation?
S: Ja, Aspose.Tasks för Java tillhandahåller omfattande dokumentation och dedikerade supportforum för att hjälpa utvecklare att använda dess funktioner effektivt.
### F: Finns det en testversion tillgänglig för Aspose.Tasks för Java?
 S: Ja, du kan komma åt en gratis testversion av Aspose.Tasks för Java från[här](https://releases.aspose.com/).