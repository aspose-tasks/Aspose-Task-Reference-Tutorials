---
date: 2026-06-10
description: Lär dig hur du läser rate och hur du skriver rate scale för resursuppdrag
  med Aspose.Tasks för Java. Stöder materialresurser, flera format och stora projekt.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Läs och skriv rate scale för resursuppdrag i Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hur man läser rate och skriver rate scale för resursuppdrag i Aspose.Tasks
url: /sv/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser och skriver hastighetsskala för resursuppdrag i Aspose.Tasks

I den här handledningen kommer du att upptäcka **hur man läser hastighet**-skala inställningar och justera dem för resursuppdrag med Aspose.Tasks för Java. Oavsett om du bygger ett schemaläggningsverktyg, ett rapporteringsverktyg eller helt enkelt behöver automatisera projektuppdateringar, ger behärskning av hastighetsskala-manipulation fin‑grained kontroll över material- och arbetsresurser.

## Snabba svar
`ResourceAssignment` länkar en uppgift till en resurs och innehåller uppdrags‑specifik data.  
`Asn` innehåller konstanter för uppdragsfält, inklusive `RATE_SCALE`.  
`RateScaleType` enum listar möjliga tidsenheter för hastighetsskala.  

- **Vad är den primära klassen för hastighetshantering?** `ResourceAssignment` with the `Asn.RATE_SCALE` property.  
- **Vilken enum definierar skalanalternativen?** `RateScaleType` (Day, Week, Month, etc.).  
- **Behöver jag en licens för att köra exemplet?** En gratis utvärderingslicens fungerar för testning; en kommersiell licens krävs för produktion.  
- **Kan jag ändra skalan efter sparning?** Ja – ladda om projektet och modifiera `Asn.RATE_SCALE` som visat.  
- **Stödda IDE:er?** Alla Java-IDE (IntelliJ IDEA, Eclipse, NetBeans) kan kompilera koden.

## Hur man läser hastighetsskala för resursuppdrag?

Läs in projektet, lokalisera önskad `ResourceAssignment` och anropa `getRateScale()` – detta returnerar ett `RateScaleType`‑värde som visar om hastigheten tillämpas per dag, vecka, månad eller en annan enhet. Svaret är omedelbart och kräver endast två API‑anrop, vilket gör det idealiskt för granskningsskript eller UI‑visningar.

## Hur man skriver hastighetsskala för resursuppdrag?

Skapa eller hämta ett `ResourceAssignment`‑objekt, sätt dess `Asn.RATE_SCALE`‑egenskap till önskad `RateScaleType` (t.ex. `RateScaleType.Week`), och spara sedan projektet. Denna enkla egenskapsändring uppdaterar automatiskt kostnadsberäkningar och bevaras i alla stödda filformat. Efter att ha ställt in skalan kan du även behöva justera resursens standardhastighet eller övertidshastighet för att återspegla den nya tidsenheten, så att kostnadsberäkningarna förblir korrekta.

## Vad är hastighetsskala?

Hastighetsskala bestämmer tidsenheten (dag, vecka, månad, etc.) som en resurs kostnadshastighet tillämpas på. Att justera skalan låter dig modellera materialförbrukning eller arbetsinsats exakt. Till exempel innebär att sätta skalan till Week att kostnadshastigheten tolkas som kostnad per vecka, och den totala kostnaden för en uppgift beräknas baserat på antalet veckor resursen är tilldelad.

## Varför läsa och skriva hastighetsskala?

Att läsa den aktuella skalan hjälper dig att granska befintliga scheman, medan att skriva en ny skala låter dig anpassa resurserna till projektets fakturerings‑ eller förbrukningspolicyer. Detta är särskilt användbart när du **definierar materialresurs**‑kostnader eller när du behöver **sätta skala** för icke‑standard arbetskalendrar.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. **Java Development Environment** – JDK 8 eller högre installerad.  
2. **Aspose.Tasks for Java Library** – Ladda ner och installera biblioteket från [here](https://releases.aspose.com/tasks/java/).

## Importera paket
`ResourceAssignment`-klassen representerar en länk mellan en uppgift och en resurs, medan `RateScaleType` enumererar de möjliga tidsenheterna för en hastighet. Importera de nödvändiga Aspose.Tasks‑klasserna innan du börjar koda.  

`Project` är huvudobjektet som läser in och sparar Microsoft Project‑filer.  
`Resource` definierar en projektresurs såsom arbete eller material.  
`ResourceType` enum specificerar om en resurs är arbete eller material.  
`Task` representerar ett arbetsobjekt i projektplanen.  
`SaveFileFormat` enum definierar utdataformatet för att spara ett projekt.

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

## Steg 2: Läs in projektfilen
Läs in den befintliga Microsoft Project‑filen som du vill arbeta med.

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
Här **definierar vi materialresurs** och en vanlig arbetsresurs. Notera användningen av `ResourceType.Material` för material‑typen resurs.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Steg 5: Tilldela resurser till uppgift
Nu **tilldelar vi resurser till uppgift** och specificerar **hur man sätter skala** genom att använda `RateScaleType.Week`. Detta illustrerar både läsning och skrivning av hastighetsskalan.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Steg 6: Spara projektet
Spara ändringarna till en ny fil så att vi senare kan verifiera den lagrade hastighetsskalan.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Steg 7: Hämta resursuppdrag
Läs in det sparade projektet igen och **läs hastigheten**‑skala för att bekräfta att den skrevs korrekt.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Vanliga fallgropar & tips
- **UID Mismatch** – När du hämtar uppdrag via UID, säkerställ att UID‑värdena matchar de som tilldelades under skapandet.  
- **Incorrect Resource Type** – Att använda `ResourceType.Material` för en arbetsresurs kommer att få kostnadsberäkningarna att bete sig oväntat.  
- **Saving Format** – Spara alltid med `SaveFileFormat.Mpp` (eller ett annat stödt format) för att bevara anpassade fält som hastighetsskala.  
- **Large Projects** – Aspose.Tasks kan bearbeta filer med **500+ sidor** utan att ladda hela dokumentet i minnet, tack vare dess streaming‑arkitektur.

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks för Java med vilken Java‑IDE som helst?**  
A: Ja, Aspose.Tasks för Java är kompatibel med alla större Java‑IDE:er, inklusive IntelliJ IDEA, Eclipse och NetBeans.

**Q: Stöder Aspose.Tasks andra filformat förutom MPP?**  
A: Ja, Aspose.Tasks stöder olika filformat, inklusive MPP, XML och HTML.

**Q: Är Aspose.Tasks lämplig för projektledning på företagsnivå?**  
A: Absolut, Aspose.Tasks erbjuder omfattande funktioner för att hantera projekt av alla storlekar, vilket gör den lämplig för projektledning på företagsnivå.

**Q: Kan jag anpassa resursuppdrag ytterligare utöver hastighetsskala?**  
A: Ja, Aspose.Tasks tillhandahåller omfattande möjligheter att anpassa resursuppdrag, inklusive kostnad, arbete och varaktighetsjusteringar.

**Q: Finns det ett community‑forum för Aspose.Tasks‑support?**  
A: Ja, du kan hitta support och interagera med andra användare på Aspose.Tasks‑forumet [here](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Relaterade handledningar

- [Skapa resursuppdrag i Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Hur man modifierar uppdrag – Läs delade resurser med Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Hur man lägger till anteckningar till resursuppdrag i Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}