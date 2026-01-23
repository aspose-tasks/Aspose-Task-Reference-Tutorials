---
date: 2026-01-23
description: Lär dig hur du ställer in baslinjeduration och skapar ett projektinstans
  med Aspose.Tasks för Java. Denna steg‑för‑steg‑guide hjälper dig att hantera uppgiftsbaslinjer
  effektivt.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Hur man ställer in baslinjeduration i Aspose.Tasks för Java
url: /sv/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in baslinjeduration i Aspose.Tasks för Java

## Introduktion
Att sätta en baslinje är ett grundläggande steg för att följa projektets framsteg mot den ursprungliga planen. I den här handledningen kommer du att lära dig **hur man ställer in baslinjeduration** för uppgifter i Microsoft Project med hjälp av Aspose.Tasks-biblioteket för Java, och se varför det är fördelaktigt att etablera en baslinje tidigt kan spara dig tid och huvudvärk senare.

## Snabba svar
- **Vad betyder “set baseline”?** Det registrerar den ursprungliga start-, slut- och varaktigheten för en uppgift så att du kan jämföra framtida förändringar.  
- **Vilken Aspose.Tasks-klass skapar ett projekt?** `Project`-klassen – du kommer också att lära dig hur man **skapar projektinstans** korrekt.  
- **Behöver jag en licens för att köra koden?** En gratis utvärderingslicens fungerar för testning; en kommersiell licens krävs för produktion.  
- **Kan jag interimbaslinjer?** Ja, Aspose.Tasks låter dig fråga efter interimbaslinjer och deras fasta kostnader.  
- **Vilken Java-version krävs?** Java 8 eller senare rekommenderas.

## Vad är en uppgiftsbaslinje och varför sätta den?
En uppgiftsbaslinje fångar den planerade tidsplanen (startdatum, slutdatum och varaktighet) vid en specifik tidpunkt. Genom att sätta en baslinje skapar du en referenspunkt som görursöverschemaläggning när projektför använda Aspose.Tasks för baslinjehantering?
- **attformsoberoende** – fungerar på Windows, Linux och macOS med vilken standard‑JDK som helst.

## Förutsättningar
1. **Java-utvecklingsmiljö** – JDK 8+ installerad och konfigurerad.  
2. **Aspose.Tasks för Java** – ladda ner biblioteket från [here](https://releases.aspose.com/tasks/java/).  
3. **IDE eller byggverktyg** – Maven, Gradle eller någon IDE du föredrar.

## Importera paket
Först, importera de nödvändiga klasserna till ditt Java‑projekt:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Steg 1: Skapa en projektinstans
Att skapa en projektinstans är grunden för all vidare manipulation. Detta steg visar hur man **skapar projektinstans** med Aspose.Tasks:

```java
Project project = new Project();
```

## Steg 2: Skapa en uppgiftsbaslinje
Lägg till en ny uppgift i projektets rot och sätt dess baslinje. Detta registrerar den ursprungliga tidsplanen för uppgiften:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Steg 3: Visa information om uppgiftsbaslinje
Hämta baslinjen du just skapade och skriv ut dess nyckelegenskaper. Detta hjälper dig att verifiera att baslinjen har satts korrekt:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Steg 4: Kontrollera interimbaslinje och fast kostnad
Om du arbetar med interimbaslinjer kan du fråga om den aktuella baslinjen är interim och eventuell tillhörande fast kostnad:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Steg 5: Skriv ut tidsfasad data
Tidsfasad data visar hur baslinjen fördelas över tid. Loop igenom samlingen för att inspektera varje post:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Genom att följa dessa steg kan du **ställa in baslinjeduration** för vilken uppgift som helst och hämta detaljerad baslinjeinformation med Aspose.Tasks för Java.

## Vanliga problem och lösningar
- **Baslinjen visas inte i MS Project:** Se till att du anropade `project.setBaseline(BaselineType.Baseline)` **efter** att ha lagt till uppgiften.  
- **NullPointerException på `getBaselines()`:** Verifiera att uppgiften lades till i projektet innan baslinjen sattes.  
- **Tidsenhetsmismatch:** Använd `TimeUnitType` för att formatera varaktigheten korrekt, särskilt när du arbetar med anpassade kalendrar.

## Vanliga frågor
### Vad är en uppgiftsbaslinje i MS Project?
En uppgiftsbaslinje i MS Project är en ögonblicksbild av den ursprungliga planerade tidsplanen för en uppgift, inklusive dess startdatum, slutdatum och varaktighet.

### Varför är hantering av uppgiftsbaslinjer viktig?
Att hantera uppgiftsbaslinjer hjälper till att jämföra den planerade tidsplanen med projektets faktiska framsteg, vilket underlättar bättre uppföljning och beslutsfattande.

### Kan jag ändra en uppgiftsbaslinje när den är satt?
Ja, du kan ändra uppgiftsbaslinjer i MS Project för att återspegla förändringar i projektplanen. Det är dock viktigt att dokumentera eventuella avvikelser från den ursprungliga baslinjen.

### Stöder Aspose.Tasks andra projektledningsfunktioner?
Ja, Aspose.Tasks erbjuder ett brett utbud av funktioner för projektledning, inklusive uppgiftsschemaläggning, resursallokering och generering av Gantt-diagram.

### Var kan jag hitta support för Aspose.Tasks?
Du kan hitta support för Aspose.Tasks på [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15), där du kan ställa frågor och interagera med andra användare.

## Ytterligare vanliga frågor
**Q: Måste jag anropa `setBaseline` för varje uppgift individuellt?**  
A: Nej. Att anropa `project.setBaseline(BaselineType.Baseline)` registrerar baslinjen för alla uppgifter i projektet på en gång.

**Q: Hur kan jag sätta en interimbaslinje för en specifik uppgift?**  
A: Använd `project.setBaseline(BaselineType.Baseline1)` (eller Baseline2‑Baseline10) efter att ha uppdaterat uppgiftens schema.

**Q: Är det möjligt att exportera baslinjedatan till CSV?**  
A: Ja. Iterera över `task.getBaselines()` och skriv de önskade fälten till en CSV‑fil med standard Java I/O.

**Q: Kan jag läsa en befintlig .mpp‑fil som redan innehåller baslinjer?**  
A: Absolut. Ladda filen med `new Project("myproject.mpp")` och få sedan åtkomst till varje uppgifts baslinjer som visas ovan.

**Q: Hanterar Aspose.Tasks multi‑projekt‑filer?**  
A: Aspose.Tasks fungerar med enkla .mpp‑filer. För multi‑projekt‑scenarier, kombinera projekten programatiskt.

**Senast uppdaterad:** 2026-01-23  
**Testad med:** Aspose.Tasks for Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}