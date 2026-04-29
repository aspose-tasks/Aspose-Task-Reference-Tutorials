---
date: 2026-01-18
description: Lär dig hur du skapar en uppgiftslista i Java och lägger till en uppgift
  i Microsoft Project, sätter en baslinje utan MS Project med Aspose.Tasks.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Skapa uppgiftslista i Java – MS Project-baslinje med Aspose.Tasks
url: /sv/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa uppgiftslista Java – MS Project-baslinje med Aspose.Tasks

## Introduktion
I den här handledningen kommer du att **create task list Java** genom att generera en Microsoft Project-uppgiftsbaslinje med Aspose.Tasks för Java. Aspose.Tasks låter dig arbeta med Project-filer utan att ha Microsoft Project installerat, så du kan **add task to Microsoft Project**, manipulera resurser och till och med **set baseline without MS Project**—allt från ren Java‑kod.

## Snabba svar
- **What does Aspose.Tasks do?** Det tillhandahåller ett Java‑API för att skapa, läsa och redigera Microsoft Project‑filer utan MS Project.  
- **Do I need Microsoft Project installed?** Nej, Aspose.Tasks fungerar oberoende.  
- **Which Java version is required?** JDK 8 eller högre.  
- **Can I set a baseline for a single task?** Ja, använd `setBaseline` med en uppgiftslista.  
- **Is a license needed for production?** Ja, en kommersiell licens tar bort utvärderingsgränserna.

## Vad är en uppgiftsbaslinje?
En uppgiftsbaslinje registrerar de ursprungliga planerade start-, slut- och arbetsvärdena för en uppgift. Den fungerar som en referenspunkt för att jämföra faktiskt framsteg mot den ursprungliga planen.

## Varför använda Aspose.Tasks för att skapa task list Java?
- **No MS Project dependency** – ideal för server‑sidig automatisering.  
- **Full control** över uppgifter, resurser och kalendrar via Java‑kod.  
- **Cross‑version compatibility** med Project‑filer från 2007‑2024.

## Förutsättningar
1. **Java Development Kit (JDK)** – installera JDK 8 eller nyare.  
2. **Aspose.Tasks for Java** – ladda ner biblioteket från [download link](https://releases.aspose.com/tasks/java/).  

## Importera paket
För att börja arbeta med Aspose.Tasks i ditt Java‑projekt, importera de nödvändiga paketen:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Steg 1: Skapa ett Project‑objekt
```java
Project project = new Project();
```
Här instansierar vi ett nytt `Project`‑objekt – detta representerar MS Project‑filen som kommer att innehålla vår uppgiftslista.

## Steg 2: Lägg till en uppgift i projektet
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Genom att använda `getRootTask()` får vi åtkomst till roten i projektets hierarki och **add task to Microsoft Project**. Strängen `"Task"` är uppgiftens namn; du kan ersätta den med vilken beskrivning du behöver.

## Steg 3: Ställ in baslinje för specificerade uppgifter
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
För att **set baseline without MS Project**, skapa en lista med de uppgifter du vill baslinjera (här `myList`) och skicka den till `setBaseline`. Fyll `myList` med de uppgifter du lagt till om du bara behöver en selektiv baslinje.

## Steg 4: Ställ in baslinje för hela projektet
```java
project.setBaseline(BaselineType.Baseline);
```
Om du föredrar att baslinjera hela projektet i ett anrop, anropa helt enkelt `setBaseline` med önskad `BaselineType`.

## Hur man lägger till uppgift i Microsoft Project med Aspose.Tasks
Utöver den enskilda uppgift som visas ovan kan du lägga till flera uppgifter, deluppgifter och tilldela resurser. Varje anrop till `add()` returnerar ett `Task`‑objekt som du kan konfigurera vidare (varaktighet, startdatum osv.).

## Hur man ställer in baslinje utan MS Project
Aspose.Tasks möjliggör skapande av baslinjer helt via kod. Du kan ange olika baslinjetyper (Baseline, Baseline1‑Baseline10) genom att ändra `BaselineType`‑enum, vilket låter dig spåra flera revisionsbaslinjer utan att någonsin öppna MS Project.

## Vanliga problem och lösningar
- **Baseline not appearing:** Se till att du anropar `project.save("output.mpp")` efter att ha ställt in baslinjen (sparsteg utelämnat här för korthet).  
- **Task list appears empty:** Verifiera att du lägger till uppgifter i rätt förälder (`getRootTask()` eller en deluppgift).  
- **Version mismatch errors:** Använd den senaste Aspose.Tasks‑JAR‑filen för att garantera kompatibilitet med nyare .mpp‑format.

## Vanliga frågor

**Q: Can I use Aspose.Tasks for Java without Microsoft Project installed?**  
A: Ja, Aspose.Tasks fungerar oberoende och kräver inte Microsoft Project på värddatorn.

**Q: Is Aspose.Tasks for Java compatible with different versions of Microsoft Project?**  
A: Absolut. Biblioteket stödjer Project‑filer från 2007 till de senaste 2024‑utgåvorna.

**Q: Can I manipulate project resources using Aspose.Tasks for Java?**  
A: Ja, du kan lägga till, uppdatera och ta bort resurser programatiskt, precis som uppgifter.

**Q: Does Aspose.Tasks for Java support setting task dependencies?**  
A: Ja, du kan definiera föregångare‑efterföljare‑relationer med hjälp av `TaskLink`‑klassen.

**Q: Is technical support available for Aspose.Tasks for Java?**  
A: Ja, du kan få hjälp via [support forum](https://forum.aspose.com/c/tasks/15), där Aspose‑personal och communityn svarar på frågor.

## Slutsats
Genom att följa dessa steg har du lärt dig hur man **create task list Java**, **add task to Microsoft Project**, och **set baseline without MS Project** med Aspose.Tasks. Detta tillvägagångssätt förenklar projektautomatisering, eliminerar behovet av skrivbordsinstallationer av Project och ger dig full programmatisk kontroll över dina projektdata.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2026-01-18  
**Testad med:** Aspose.Tasks for Java 24.12  
**Författare:** Aspose  

---