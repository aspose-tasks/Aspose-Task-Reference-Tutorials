---
title: Stoppa och återuppta resurstilldelningar i Aspose.Tasks
linktitle: Stoppa och återuppta resurstilldelningar i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du hanterar resurstilldelningar effektivt i Aspose.Tasks för Java med denna steg-för-steg handledning.
type: docs
weight: 23
url: /sv/java/resource-assignments/stop-resume-assignment/
---
## Introduktion
I den här handledningen kommer vi att lära oss hur du stoppar och återupptar resurstilldelningar med Aspose.Tasks för Java. Aspose.Tasks är ett kraftfullt Java API som tillåter utvecklare att arbeta med Microsoft Project-filer utan att behöva Microsoft Project installerat på sina system. Vi delar upp processen i hanterbara steg för att göra det enkelt att följa med.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Java Development Kit (JDK) installerat på ditt system.
-  Aspose.Tasks för Java-biblioteket har laddats ner. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/java/).
- Grundläggande förståelse för Java-programmering.
## Importera paket
Låt oss först importera de nödvändiga paketen till vårt Java-projekt:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Steg 1: Ladda projektfilen
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Data Directory";
// Ladda projektfilen
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 I det här steget laddar vi in projektfilen i en`Project` objekt med hjälp av filsökvägen.
## Steg 2: Iterera genom resurstilldelningar
```java
// Definiera minimidatum
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterera genom resurstilldelningar
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Här definierar vi ett minimidatum och börjar iterera genom varje resurstilldelning i projektet.
## Steg 3: Kontrollera stopp- och återupptadatum
```java
    // Kontrollera stoppdatum
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Kontrollera återuppta datum
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
I det här steget kontrollerar vi om stopp- och återupptagningsdatumen för varje resurstilldelning ligger före minimidatumet. Om de är det skriver vi "NA", annars skriver vi ut respektive datum.
## Slutsats
I den här handledningen har vi lärt oss hur man stoppar och återupptar resurstilldelningar i Aspose.Tasks för Java. Genom att följa de medföljande stegen kan du enkelt implementera den här funktionen i dina Java-projekt.

## FAQ's
### Kan jag använda Aspose.Tasks utan Microsoft Project installerat?
Ja, Aspose.Tasks låter dig arbeta med Microsoft Project-filer utan att behöva Microsoft Project installerat på ditt system.
### Var kan jag hitta mer dokumentation?
 Du kan hitta detaljerad dokumentation[här](https://reference.aspose.com/tasks/java/).
### Finns det en gratis provperiod?
 Ja, du kan få en gratis provperiod[här](https://releases.aspose.com/).
### Hur kan jag få support om jag stöter på några problem?
Du kan få stöd från samhället[här](https://forum.aspose.com/c/tasks/15).
### Kan jag köpa en tillfällig licens?
 Ja, du kan köpa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).