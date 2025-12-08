---
date: 2025-12-07
description: Lär dig hur du sparar projektfil, skriver och läser MS Project‑formler
  samt lägger till anpassade fältformler med Aspose.Tasks för Java.
language: sv
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Spara projektfil och skriv MS Project‑formler med Aspose.Tasks
url: /java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spara projektfil och skriv MS Project-formler med Aspose.Tasks

## Introduction
I projektledning är effektiv hantering av data avgörande. Aspose.Tasks för Java är en robust lösning som underlättar manipulering och extraktion av data från Microsoft Project-filer. En kraftfull funktion den erbjuder är möjligheten att skriva och läsa MS Project-formler. **Du kommer också att lära dig hur du *sparar projektfil* efter att ha tillämpat dessa formler**, vilket säkerställer att dina ändringar bevaras för framtida analys. Denna handledning guidar dig genom processen att utnyttja denna funktionalitet för att förbättra dina projektledningsuppgifter.

## Quick Answers
- **Vad gör “save project file”?** Den skriver alla förändringar i minnet tillbaka till en .mpp-fil på disken.  
- **Kan jag lägga till anpassade fältformler?** Ja – du kan skapa ett anpassat fält och tilldela en formel som exempelvis “double task cost”.  
- **Behöver jag en licens för att köra koden?** En gratis provversion fungerar för utvärdering; en kommersiell licens krävs för produktion.  
- **Vilken IDE fungerar bäst?** Alla Java-IDE (IntelliJ IDEA, Eclipse, VS Code) kan kompilera exemplet.  
- **Är API:et kompatibelt med den senaste MS Project-versionen?** Aspose.Tasks stödjer alla senaste .mpp-format.

## What is “save project file” in Aspose.Tasks?
Att spara en projektfil betyder att persistera `Project`-objektets aktuella tillstånd — inklusive uppgifter, resurser och eventuella anpassade formler — till en fysisk Microsoft Project-fil (`.mpp`). Denna operation är nödvändig efter att du har ändrat data, såsom att lägga till ett anpassat fält eller ändra uppgiftskostnader.

## Why add a custom field and create a custom field formula?
Att lägga till ett anpassat fält ger dig en flexibel behållare för extra information som inte täcks av standardfält. Genom att bifoga en formel — som en som **dubblar uppgiftskostnaden** — automatiserar du beräkningar, minskar manuella fel och håller dina schemadata konsistenta.

## Prerequisites
Innan du dyker ner i den här handledningen, se till att du har följande förutsättningar:

1. **Java Development Kit (JDK)** – Java 8 eller högre installerat på din maskin.  
2. **Aspose.Tasks for Java** – Ladda ner och installera från [here](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Välj din föredragna IDE för Java-utveckling (IntelliJ IDEA, Eclipse, VS Code, etc.).  

## Importing Packages
För att börja, importera de nödvändiga paketen till ditt Java-projekt:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Step 1: Set Up Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Definiera mappen där dina MS Project-filer finns. Detta är där du laddar källfilen och senare **sparar projektfil**.

## Step 2: Load Project File
```java
Project project = new Project(dataDir + "project.mpp");
```
Läs in den befintliga Microsoft Project-filen i ett `Project`-objekt så att du kan läsa eller ändra dess innehåll.

## Step 3: Add Custom Field and Create Custom Field Formula
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
I detta steg **lägger vi till anpassat fält** “Double Costs” och **skapar en anpassad fältformel** som multiplicerar uppgiftens `[Cost]` med 2, vilket effektivt **dubblar uppgiftskostnaden**. Metoden `setFormula` inbäddar beräkningen direkt i projektfilen.

## Step 4: Add Task and Set Cost
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Skapa en ny uppgift och tilldela sedan en grundkostnad på `100`. När projektet sparas kommer det anpassade fältet automatiskt att visa `200` på grund av formeln som definierades tidigare.

## Step 5: Save Project File
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Slutligen **sparar vi projektfil** med alla ändringar. Metoden `save` skriver det uppdaterade projektet, inklusive det nya anpassade fältet och dess beräknade värden, till `saved.mpp`.

## Common Issues and Solutions
| Problem | Orsak | Lösning |
|---------|-------|---------|
| **Formeln tillämpas inte** | Anpassat fält har inte lagts till i projektets `ExtendedAttributes`-samling. | Se till att `project.getExtendedAttributes().add(attr);` körs innan sparning. |
| **Fil ej hittad** | Felaktig `dataDir`-sökväg. | Kontrollera att katalogsträngen avslutas med en sökvägsseparator (`/` eller `\\`). |
| **Kostnad visas som 0** | Uppgiftens kostnad har inte satts innan sparning. | Anropa `task.set(Tsk.COST, ...)` innan `project.save`. |

## Frequently Asked Questions
**Q: Är Aspose.Tasks kompatibelt med alla versioner av MS Project?**  
A: Ja, Aspose.Tasks stödjer ett brett spektrum av MS Project-versioner, från äldre .mpp-format till de senaste releaserna.

**Q: Kan jag integrera Aspose.Tasks i mitt befintliga Java-projekt?**  
A: Absolut. API:et är utformat för sömlös integration; lägg bara till Aspose.Tasks JAR-filen i ditt projekts classpath.

**Q: Finns det några begränsningar för vilka typer av formler jag kan skapa?**  
A: Biblioteket stödjer de flesta inbyggda MS Project-formelsyntaxer, inklusive aritmetiska, logiska och inbyggda funktioner. Komplexa anpassade funktioner kan kräva lösningar.

**Q: Stöder Aspose.Tasks multi‑platformsdistribution?**  
A: Ja, biblioteket körs på alla plattformar som stödjer Java, inklusive Windows, Linux och macOS.

**Q: Hur kan jag få teknisk support för Aspose.Tasks?**  
A: Besök [Aspose.Tasks-forumet](https://forum.aspose.com/c/tasks/15) för gemenskapsstöd, eller öppna ett supportärende om du har en kommersiell licens.

## Conclusion
I den här handledningen gick vi igenom hur man **sparar projektfil**, **lägger till anpassat fält** och **skapar en anpassad fältformel** som **dubblar uppgiftskostnaden** med Aspose.Tasks för Java. Genom att följa dessa steg kan du automatisera beräkningar, berika dina projektdata och säkerställa att alla ändringar sparas för framtida rapportering och analys.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}