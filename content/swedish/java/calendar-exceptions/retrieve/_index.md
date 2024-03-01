---
title: Hämta kalenderundantag med Aspose.Tasks
linktitle: Hämta kalenderundantag med Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du hämtar kalenderundantag från MS Project med Aspose.Tasks för Java. Steg-för-steg handledning för sömlös integration.
type: docs
weight: 13
url: /sv/java/calendar-exceptions/retrieve/
---
## Introduktion
I den här handledningen kommer vi att utforska hur man hämtar kalenderundantag från MS Project med hjälp av Aspose.Tasks-biblioteket för Java. Aspose.Tasks är ett kraftfullt verktyg som låter utvecklare manipulera Microsoft Project-filer programmatiskt. Vi guidar dig genom processen steg för steg och delar upp varje exempel i flera steg för enkel förståelse.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system.
2.  Aspose.Tasks for Java: Ladda ner och installera Aspose.Tasks for Java från[här](https://releases.aspose.com/tasks/java/).
3. Integrated Development Environment (IDE): Du kan använda vilken IDE du vill, som IntelliJ IDEA eller Eclipse.

## Importera paket
Först måste du importera de nödvändiga paketen för att arbeta med Aspose.Tasks:
```java
import com.aspose.tasks.*;
```
## Steg 1: Konfigurera din datakatalog
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Data Directory";
```
 Se till att byta ut`"Your Data Directory"` med sökvägen till din katalog som innehåller MS Project-filen.
## Steg 2: Ladda MS Project File
```java
Project project = new Project(dataDir + "project.mpp");
```
 Denna rad initierar en ny`Project` objekt genom att ladda MS Project-filen som anges av sökvägen.
## Steg 3: Hämta kalenderundantag
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
Här itererar vi genom varje kalender i projektet och sedan genom varje kalenderundantag inom den kalendern. Vi skriver ut start- och slutdatum för varje undantag.

## Slutsats
I den här handledningen har vi lärt oss hur man hämtar kalenderundantag från MS Project med Aspose.Tasks för Java. Genom att följa dessa enkla steg kan du sömlöst integrera denna funktion i dina Java-applikationer.
## Vanliga frågor
### Kan Aspose.Tasks hantera olika versioner av MS Project-filer?
Ja, Aspose.Tasks stöder olika versioner av MS Project-filer, inklusive MPP-, MPT- och XML-format.
### Finns det en gratis testversion tillgänglig för Aspose.Tasks?
 Ja, du kan ladda ner en gratis testversion av Aspose.Tasks från[här](https://releases.aspose.com/).
### Var kan jag hitta dokumentation för Aspose.Tasks för Java?
 Du kan hänvisa till dokumentationen[här](https://reference.aspose.com/tasks/java/).
### Hur kan jag få support för Aspose.Tasks?
 Du kan få stöd från gemenskapsforumet[här](https://forum.aspose.com/c/tasks/15).
### Finns det ett alternativ för tillfälliga licenser för Aspose.Tasks?
 Ja, du kan få tillfälliga licenser från[här](https://purchase.aspose.com/temporary-license/).