---
title: Task Timephased Data i Aspose.Tasks
linktitle: Task Timephased Data i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Utforska Aspose.Tasks för Java och behärska tidsfasad datahantering. Ladda ner biblioteket, njut av en gratis provperiod och effektivisera din projektspårning.
type: docs
weight: 34
url: /sv/java/task-properties/task-timephased-data/
---
## Introduktion
Inom projektledningssfären är exakt spårning av uppgift tidsfasad data avgörande för effektivt projektgenomförande. Aspose.Tasks för Java framstår som ett kraftfullt verktyg för att effektivisera denna process, och erbjuder robusta funktioner och flexibilitet. Den här handledningen guidar dig genom att använda Aspose.Tasks för Java för att effektivt hantera uppgift tidsfasad data.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Java Development Environment: Se till att du har Java installerat på ditt system.
-  Aspose.Tasks för Java Library: Ladda ner och inkludera Aspose.Tasks-biblioteket i ditt projekt. Du hittar biblioteket[här](https://releases.aspose.com/tasks/java/).
- Dokumentkatalog: Skapa en katalog för dina projektdokument.
## Importera paket
I ditt Java-projekt, importera de nödvändiga paketen för Aspose.Tasks:
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
## Steg 1: Ställ in projektstartdatum
```java
Project project = new Project(dataDir + "project.xml");
// Tilläggskod för paketimport
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Förklaring: Initiera ett kalenderobjekt, ställ in startdatumet och tillämpa det på projektet.
## Steg 2: Definiera uppgift och resurs
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Förklaring: Skapa en uppgift och resurs, ställ in priser för standard och övertid.
## Steg 3: Ställ in uppgiftens varaktighet
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Förklaring: Definiera uppgiftens varaktighet (t.ex. 6 dagar).
## Steg 4: Tilldela resurs till uppgift
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Förklaring: Tilldela resursen till uppgiften.
## Steg 5: Konfigurera resurstilldelning
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Förklaring: Ställ in parametrar som stopp, återuppta och arbetskontur för resurstilldelningen.
## Steg 6: Ställ in baslinje
```java
project.setBaseline(BaselineType.Baseline);
```
Förklaring: Etablera en baslinje för projektet.
## Steg 7: Uppdatera uppgift slutförd
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Förklaring: Ange slutförandeprocenten för uppgiften.
## Steg 8: Hämta tidsfasdata
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Förklaring: Hämta tidsfasdata för uppdragets återstående arbete.
## Steg 9: Visa tidsfasdata
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Ytterligare kod för att visa andra värden
```
Förklaring: Mata ut och visa tidsfasdata.
## Slutsats
Effektiv hantering av uppgift tidsfasad data är oumbärlig för projektets framgång. Aspose.Tasks för Java förenklar denna process och ger en omfattande uppsättning funktioner. Genom att följa denna handledning kan du sömlöst integrera Aspose.Tasks i ditt Java-projekt, vilket säkerställer exakt kontroll över projektets tidslinjer och resursallokering.
## Vanliga frågor
### F: Kan jag använda Aspose.Tasks för Java i vilket Java-projekt som helst?
S: Ja, Aspose.Tasks för Java är kompatibelt med alla Java-baserade projekt.
### F: Var kan jag hitta ytterligare stöd för Aspose.Tasks för Java?
 A: Besök[Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) för stöd och diskussioner.
### F: Finns det en gratis testversion tillgänglig för Aspose.Tasks för Java?
 S: Ja, du kan utforska en gratis provperiod[här](https://releases.aspose.com/).
### F: Hur kan jag få en tillfällig licens för Aspose.Tasks för Java?
 S: Du kan skaffa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### F: Var kan jag köpa Aspose.Tasks för Java?
 S: Du kan köpa Aspose.Tasks för Java[här](https://purchase.aspose.com/buy).