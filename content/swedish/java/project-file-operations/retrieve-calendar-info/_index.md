---
title: Hämta MS Project Calendar Info i Aspose.Tasks
linktitle: Hämta kalenderinformation i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du hämtar MS Project-kalenderinformation med Aspose.Tasks för Java. Steg-för-steg-guide för att få åtkomst till kalenderdetaljer programmatiskt.
type: docs
weight: 14
url: /sv/java/project-file-operations/retrieve-calendar-info/
---
## Introduktion
I den här handledningen kommer vi att undersöka hur du hämtar kalenderinformation från Microsoft Project-filer med Aspose.Tasks for Java-biblioteket. Aspose.Tasks tillhandahåller kraftfulla funktioner för att manipulera projektdata, inklusive tillgång till kalenderdetaljer som arbetsdagar och timmar.
## Förutsättningar
Innan vi börjar, se till att du har följande:
- Grundläggande kunskaper i Java-programmering.
- Java Development Kit (JDK) installerat på ditt system.
-  Aspose.Tasks för Java-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/java/).
## Importera paket
Först måste du importera de nödvändiga paketen i din Java-kod för att använda Aspose.Tasks-funktioner.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Låt oss nu dela upp exemplet i flera steg för en bättre förståelse.
## Steg 1: Ställ in datakatalog
```java
String dataDir = "Your Data Directory";
```
 Byta ut`"Your Data Directory"` med sökvägen till din projektfilkatalog.
## Steg 2: Definiera tidsenheter
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Dessa konstanter representerar tidsenheter i mikrosekunder.
## Steg 3: Skapa projektinstans
```java
Project project = new Project(dataDir + "project.mpp");
```
 Den här raden skapar en instans av`Project` klass, initialisera den med sökvägen till projektfilen (`project.mpp`).
## Steg 4: Hämta kalendrarinformation
```java
CalendarCollection alCals = project.getCalendars();
```
Här hämtar vi en samling kalendrar som finns i projektfilen.
## Steg 5: Iterera genom kalendrar
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Kalenderinformation
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterera genom veckodagar
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Tid i millisekunder
            double time = ts / (OneHour); // Konvertera till timmar
            if (wd.getDayWorking()) {
                // Visa arbetsdagar och timmar
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Denna loop itererar genom varje kalender och skriver ut dess UID, namn och arbetsdagar med respektive arbetstid.
## Steg 6: Visa meddelande om slutförande
```java
System.out.println("Process completed Successfully");
```
Slutligen visas ett meddelande som indikerar att processen är klar.
## Slutsats
I den här handledningen lärde vi oss hur man hämtar kalenderinformation från MS Project-filer med Aspose.Tasks för Java. Genom att följa dessa steg kan du effektivt komma åt och manipulera projektdata i dina Java-applikationer.

## FAQ's
### F: Kan jag använda Aspose.Tasks med andra programmeringsspråk?
S: Ja, Aspose.Tasks stöder flera plattformar och programmeringsspråk, inklusive .NET, C++, Python och Java.
### F: Finns det en gratis testversion tillgänglig för Aspose.Tasks?
 S: Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
### F: Hur kan jag få support för Aspose.Tasks?
S: Du kan få stöd från Aspose.Tasks communityforum[här](https://forum.aspose.com/c/tasks/15).
### F: Kan jag köpa en tillfällig licens för Aspose.Tasks?
 S: Ja, tillfälliga licenser finns att köpa[här](https://purchase.aspose.com/temporary-license/).
### F: Var kan jag hitta detaljerad dokumentation för Aspose.Tasks?
 S: Du kan hänvisa till dokumentationen[här](https://reference.aspose.com/tasks/java/).