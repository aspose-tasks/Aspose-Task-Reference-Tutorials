---
date: 2026-04-24
description: Lär dig hur du använder Aspose.Tasks Java för att importera Primavera
  XML till MS Project, vilket möjliggör sömlöst datautbyte och förbättrad projektledning.
keywords:
- aspose tasks java
- import xml ms project
- java read project
- java project xml
linktitle: Läs projekt från Primavera i Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Läs Primavera XML i MS Project
url: /sv/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Läs MS Project från Primavera med Aspose.Tasks för Java

## Introduktion
I dagens snabbrörliga projektledningsvärld måste du ofta flytta scheman mellan Primavera P6 och Microsoft Project utan att förlora någon detalj. Denna handledning visar **hur man läser Primavera XML**‑filer och importerar dem till MS Project med hjälp av **aspose tasks java**. I slutet av guiden kommer du att kunna hämta Primavera‑specifika uppgiftsegenskaper till en Java‑applikation, vilket ger dig en enda sanningskälla för analys, rapportering eller vidare automatisering.

## Snabba svar
- **Vad gör Aspose.Tasks for Java?** Den läser och skriver många projektfilformat, inklusive Primavera XML och Microsoft Project (MPP).  
- **Behöver jag en licens?** En gratis provversion fungerar för utvärdering; en licens krävs för produktionsanvändning.  
- **Vilken Java‑version stöds?** Java 8 eller högre krävs.  
- **Kan jag importera andra format förutom Primavera XML?** Ja, aspose tasks java stödjer också MPP, XML och många fler.  
- **Är detta tillvägagångssätt lämpligt för stora företagsprojekt?** Absolut—Aspose.Tasks är designat för högpresterande, företagsklassade scenarier.

## aspose tasks java – Läsa Primavera XML
Att läsa Primavera XML innebär att parsra XML‑exporten från Oracle Primavera P6 för att hämta projektschemaläggningsdata—uppgifter, varaktigheter, resurser och Primavera‑specifika attribut—så att den kan användas av andra verktyg som Microsoft Project.

## Varför använda Aspose.Tasks for Java för att läsa Primavera XML?
- **Fullständig noggrannhet:** Alla Primavera‑specifika egenskaper bevaras.  
- **Inga externa beroenden:** Ren Java‑bibliotek, ingen behov av Primavera- eller MS Project‑installationer.  
- **Skalbar:** Hanterar stora projekt med tusentals uppgifter effektivt.  
- **Plattformsoberoende:** Fungerar på Windows, Linux och macOS.

## Förutsättningar
Innan du börjar, se till att du har följande:
1. **Java Development Kit (JDK)** – Java 8 eller nyare installerat.  
2. **Aspose.Tasks for Java** – Ladda ner det från [här](https://releases.aspose.com/tasks/java/).  
3. En Primavera XML‑fil (t.ex. `PrimaveraProject.xml`) som du vill läsa.

## Hur man läser projektfil java med Aspose.Tasks?
Nedan följer en steg‑för‑steg‑guide som går igenom hela processen.

### Importera paket
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### Steg 1: Ställ in datakatalog
```java
String dataDir = "Your Data Directory";
```
Byt ut `"Your Data Directory"` mot den absoluta sökvägen där din Primavera XML‑fil finns.

### Steg 2: Läs projekt från Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
Uppdatera `"PrimaveraProject.xml"` med det faktiska filnamnet på din Primavera‑export.

### Steg 3: Iterera genom uppgifter och hämta Primavera‑specifika egenskaper
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
Denna loop skriver ut varje uppgifts Primavera‑specifika detaljer, såsom Activity ID, WBS‑sekvens, varaktighetstyper, kostnadsuppdelningar och mer.

## Vanliga problem och lösningar
- **File not found‑fel:** Verifiera att `dataDir` slutar med en sökvägsseparator (`/` eller `\\`) och att XML‑filnamnet är korrekt.  
- **Saknade Primavera‑egenskaper:** Säkerställ att XML‑exporten innehöll alla obligatoriska fält; äldre Primavera‑versioner kan utelämna vissa attribut.  
- **Prestanda på stora filer:** Överväg att öka JVM‑heap‑storleken (`-Xmx2g` eller högre) för projekt med tiotusentals uppgifter.

## Vanliga frågor
### Q: Kan jag ändra de Primavera‑specifika egenskaperna för uppgifter med Aspose.Tasks for Java?
A: Ja, Aspose.Tasks for Java tillhandahåller API:er för att ändra Primavera‑specifika egenskaper för uppgifter vid behov.

### Q: Stöder Aspose.Tasks for Java att läsa andra projektfilformat?
A: Ja, Aspose.Tasks for Java stödjer läsning av olika projektfilformat inklusive MPP, XML och Primavera XML.

### Q: Är Aspose.Tasks for Java lämplig för företagsnivå projektledningsapplikationer?
A: Absolut, Aspose.Tasks for Java erbjuder robusta funktioner och skalbarhet, vilket gör den lämplig för projektledningsapplikationer på företagsnivå.

### Q: Kan jag extrahera resursinformation från Primavera‑projekt med Aspose.Tasks for Java?
A: Ja, Aspose.Tasks for Java låter dig extrahera resursinformation tillsammans med uppgiftsdetaljer från Primavera‑projekt.

### Q: Var kan jag hitta ytterligare support eller dokumentation för Aspose.Tasks for Java?
A: Du kan hitta omfattande dokumentation och tillgång till forum för support på sidan [Aspose.Tasks för Java-dokumentation](https://reference.aspose.com/tasks/java/).

## Slutsats
Du har nu lärt dig **hur man läser primavera xml**‑filer och hämtar detaljerad uppgiftsinformation till en Java‑applikation med hjälp av **aspose tasks java**. Denna funktion överbryggar klyftan mellan Primavera och Microsoft Project, ger dig full insyn över plattformar och ökar den totala projektledningseffektiviteten.

---

**Senast uppdaterad:** 2026-04-24  
**Testat med:** Aspose.Tasks for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}