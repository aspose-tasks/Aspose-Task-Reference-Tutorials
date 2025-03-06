---
title: Uppdatera och boka om MS-projektet i Aspose.Tasks
linktitle: Uppdatera projekt och schemalägg om oavslutat arbete i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du uppdaterar och schemalägger MS Project-filer programmatiskt med Aspose.Tasks för Java.
type: docs
weight: 23
url: /sv/java/project-file-operations/update-project-reschedule-work/
---
## Introduktion
Microsoft Project är en mycket använd projektledningsprogramvara som låter användare hantera uppgifter, resurser och tidslinjer effektivt. Aspose.Tasks för Java tillhandahåller en kraftfull uppsättning API:er för att manipulera Microsoft Project-filer programmatiskt. I den här handledningen kommer vi att lära oss hur du uppdaterar MS Project-filer och schemalägger ofullbordat arbete med Aspose.Tasks för Java.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1. Java Development Kit (JDK) installerat på ditt system.
2.  Aspose.Tasks för Java-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/java/).
3. Grundläggande förståelse för programmeringsspråket Java.

## Importera paket
Importera först de nödvändiga paketen i din Java-kod:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Steg 1: Konfigurera projektet
Initiera ett nytt projektobjekt och definiera uppgifter inom det tillsammans med deras varaktigheter och beroenden.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Definiera uppgifter och deras varaktighet
// ...
// Definiera uppgiftsberoenden
// ...
// Spara den ursprungliga projektstatusen
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Steg 2: Uppdatera projektarbete
Uppdatera projektarbetet för att markera det som färdigt fram till ett visst datum.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Spara det uppdaterade projektet
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Steg 3: Boka om oavslutat arbete
Planera om allt ofullbordat arbete för att starta efter ett angivet datum.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Spara det omplanerade projektet
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Slutsats
I den här handledningen har vi lärt oss hur man uppdaterar MS Project-filer och schemalägger ofullbordat arbete med Aspose.Tasks för Java. Detta kan vara särskilt användbart i scenarier där projekttidslinjer behöver justeras baserat på framsteg eller ändrade prioriteringar.

## FAQ's
### F: Kan Aspose.Tasks för Java hantera komplexa projektstrukturer?
S: Ja, Aspose.Tasks för Java tillhandahåller robusta API:er för att effektivt hantera uppgifter, beroenden, resurser och andra projektelement.
### F: Finns det en testversion tillgänglig för Aspose.Tasks för Java?
 S: Ja, du kan få en gratis provperiod från[här](https://releases.aspose.com/).
### F: Hur kan jag få support för Aspose.Tasks för Java?
 A: Du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för all hjälp eller frågor.
### F: Kan jag köpa en tillfällig licens för Aspose.Tasks för Java?
 S: Ja, tillfälliga licenser finns att köpa[här](https://purchase.aspose.com/temporary-license/).
### F: Var kan jag hitta detaljerad dokumentation för Aspose.Tasks för Java?
 S: Du kan hänvisa till dokumentationen[här](https://reference.aspose.com/tasks/java/) för omfattande guider och API-referenser.