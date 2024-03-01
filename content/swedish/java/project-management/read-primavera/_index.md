---
title: Läs MS Project från Primavera med Aspose.Tasks för Java
linktitle: Läs Project från Primavera i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du läser MS Project-filer från Primavera XML sömlöst med Aspose.Tasks för Java. Förbättra din projektledningseffektivitet.
type: docs
weight: 20
url: /sv/java/project-management/read-primavera/
---
## Introduktion
Inom projektledning är interoperabilitet mellan olika programvaruplattformar avgörande för ett smidigt arbetsflöde. Aspose.Tasks för Java ger robust funktionalitet för att läsa Microsoft Project-filer från Primavera XML. Denna handledning guidar dig genom processen att läsa MS Project-filer från Primavera med Aspose.Tasks för Java, så att du kan undersöka uppgifternas Primavera-specifika egenskaper effektivt.
## Förutsättningar
Innan du fortsätter, se till att du har följande förutsättningar installerade och konfigurerade:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system.
2.  Aspose.Tasks for Java: Ladda ner och installera Aspose.Tasks for Java från[här](https://releases.aspose.com/tasks/java/).

## Importera paket
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Steg 1: Konfigurera datakatalog
```java
String dataDir = "Your Data Directory";
```
 Se till att byta ut`"Your Data Directory"` med den faktiska sökvägen till din datakatalog.
## Steg 2: Läs Project från Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Se till att byta ut`"PrimaveraProject.xml"` med det faktiska namnet på din Primavera XML-fil.
## Steg 3: Iterera genom uppgifter och hämta Primavera-specifika egenskaper
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Denna kod itererar genom varje uppgift i projektet och skriver ut relevanta Primavera-specifika egenskaper.

## Slutsats
den här handledningen lärde du dig hur du läser MS Project-filer från Primavera XML med Aspose.Tasks för Java. Denna funktion möjliggör sömlös integrering och analys av projektdata över olika plattformar, vilket förbättrar den övergripande projektledningseffektiviteten.
## FAQ's
### F: Kan jag ändra Primavera-specifika egenskaper för uppgifter med Aspose.Tasks för Java?
S: Ja, Aspose.Tasks för Java tillhandahåller API:er för att modifiera Primavera-specifika egenskaper för uppgifter efter behov.
### F: Stöder Aspose.Tasks for Java läsning av andra projektfilformat?
S: Ja, Aspose.Tasks för Java stöder läsning av olika projektfilformat inklusive MPP, XML och Primavera XML.
### F: Är Aspose.Tasks för Java lämpligt för projektledningsapplikationer på företagsnivå?
S: Absolut, Aspose.Tasks för Java erbjuder robusta funktioner och skalbarhet, vilket gör det lämpligt för projektledningsapplikationer på företagsnivå.
### F: Kan jag extrahera resursinformation från Primavera-projekt med Aspose.Tasks för Java?
S: Ja, Aspose.Tasks för Java låter dig extrahera resursinformation tillsammans med uppgiftsdetaljer från Primavera-projekt.
### F: Var kan jag hitta ytterligare support eller dokumentation för Aspose.Tasks för Java?
 S: Du kan hitta omfattande dokumentation och tillgång till forum för support på[Aspose.Tasks för Java-dokumentation](https://reference.aspose.com/tasks/java/) sida.