---
date: 2026-01-10
description: Lär dig hur du läser taxa‑skalan och hanterar resursallokeringar i Aspose.Tasks
  för Java. Definiera materialresurs, hur du ställer in skalan och tilldelar resurser
  till en uppgift.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man läser prisskala och skriver prisskala för resursuppdrag i Aspose.Tasks
url: /sv/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser och skriver taktskala för resursuppdrag i Aspose.Tasks

I den här handledningen kommer du att upptäcka **how to read rate** scale settings och justerar dem för resursuppdrag med Aspose.Tasks för Java. Oavsett om du bygger ett schemaläggningsverktyg, ett rapporteringsverktyg eller helt enkelt behöver automatisera projektuppdateringar, ger behärskning av taktskala-manipulering dig fin‑granulär kontroll över material‑ och arbetsresurser.

## Snabba svar
- **Vad är den primära klassen för rate‑hantering?** `ResourceAssignment` med egenskapen `Asn.RATE_SCALE`.  
- **Vilken enum definierar skalanalternativen?** `RateScaleType` (Day, Week, Month, etc.).  
- **Behöver jag en licens för att köra exemplet?** En gratis utvärderingslicens fungerar för testning; en kommersiell licens krävs för produktion.  
- **Kan jag ändra skalan efter sparning?** Ja – ladda om projektet och ändra `Asn.RATE_SCALE` som visas.  
- **Stödda IDE‑er?** Alla Java‑IDE:er (IntelliJ IDEA, Eclipse, NetBeans) kan kompilera koden.

## Vad är Rate Scale?
Rate scale bestämmer tidsenheten (dag, vecka, månad, etc.) som en resurs kostnads‑rate tillämpas på. Genom att justera skalan kan du modellera materialförbrukning eller arbetsinsats exakt.

## Varför läsa och skriva rate scale?
Att läsa den aktuella skalan hjälper dig att granska befintliga scheman, medan att skriva en ny skala låter dig anpassa resurser till projektets fakturerings‑ eller förbrukningspolicyer. Detta är särskilt användbart när du **definierar materialresurs**‑kostnader eller när du behöver **sätta skala** för icke‑standard arbetskalendrar.

## Förutsättningar
1. **Java‑utvecklingsmiljö** – JDK 8 eller högre installerad.  
2. **Aspose.Tasks för Java‑bibliotek** – Ladda ner och installera biblioteket från [here](https://releases.aspose.com/tasks/java/).

## Importera paket
Först, importera de nödvändiga Aspose.Tasks‑klasserna.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Steg 1: Ställ in ditt Java‑projekt
Skapa ett Maven‑ eller Gradle‑projekt och lägg till Aspose.Tasks‑JAR‑filen i din classpath. Detta steg säkerställer att kompilatorn kan hitta de importerade klasserna.

## Steg 2: Ladda projektfilen
Ladda den befintliga Microsoft Project‑filen som du vill arbeta med.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Steg 3: Lägg till en uppgift
Skapa en ny uppgift som senare kommer att få resursuppdrag.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Steg 4: Definiera resurser
Här **definierar vi materialresurs** och en vanlig arbetsresurs. Observera användningen av `ResourceType.Material` för material‑typen resurs.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Steg 5: Tilldela resurser till uppgift
Nu **tilldelar vi resurser till uppgift** och specificerar **hur man sätter skala** genom att använda `RateScaleType.Week`. Detta illustrerar både läsning och skrivning av rate scale.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Steg 6: Spara projektet
Spara ändringarna till en ny fil så att vi senare kan verifiera den lagrade rate scale.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Steg 7: Hämta resursuppdrag
Ladda om det sparade projektet och **läs rate**‑skalan för att bekräfta att den skrevs korrekt.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Vanliga fallgropar & tips
- **UID‑mismatch** – När du hämtar uppdrag med UID, se till att UID‑värdena matchar de som tilldelades under skapandet.  
- **Fel resurstyp** – Att använda `ResourceType.Material` för en arbetsresurs kommer att få rate‑beräkningarna att bete sig oväntat.  
- **Sparformat** – Spara alltid med `SaveFileFormat.Mpp` (eller ett annat stödformat) för att bevara anpassade fält som rate scale.

## Slutsats
Att hantera och inspektera rate scale för resursuppdrag i Aspose.Tasks för Java är enkelt när du känner till de relevanta klasserna och egenskaperna. Genom att följa den här guiden kan du **läsa rate**‑information, **definiera materialresurs**‑objekt, **sätta skala**, och **tilldela resurser till uppgift** med förtroende.

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks för Java med någon Java‑IDE?**  
A: Ja, Aspose.Tasks för Java är kompatibel med alla större Java‑IDE:er, inklusive IntelliJ IDEA, Eclipse och NetBeans.

**Q: Stöder Aspose.Tasks andra filformat förutom MPP?**  
A: Ja, Aspose.Tasks stöder olika filformat, inklusive MPP, XML och HTML.

**Q: Är Aspose.Tasks lämplig för projektledning på företagsnivå?**  
A: Absolut, Aspose.Tasks erbjuder omfattande funktioner för att hantera projekt av alla storlekar, vilket gör den lämplig för projektledning på företagsnivå.

**Q: Kan jag anpassa resursuppdrag ytterligare utöver rate scale?**  
A: Ja, Aspose.Tasks ger omfattande möjligheter att anpassa resursuppdrag, inklusive kostnad, arbete och varaktighetsjusteringar.

**Q: Finns det ett community‑forum för Aspose.Tasks‑support?**  
A: Ja, du kan hitta support och interagera med andra användare på Aspose.Tasks‑forumet [here](https://forum.aspose.com/c/tasks/15).

---

**Senast uppdaterad:** 2026-01-10  
**Testad med:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}