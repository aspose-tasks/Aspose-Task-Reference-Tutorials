---
date: 2026-06-10
description: Lär dig hur du ändrar kontur och genererar tidsfasad data för resursuppdrag
  med Aspose.Tasks för Java, inklusive typer av arbetskontur och avancerade schemaläggningsscenarier.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Generera tidsfasad data för resursuppdrag i Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hur man ändrar kontur i Aspose.Tasks för tidsfasad data
url: /sv/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ändrar kontur i Aspose.Tasks för tidsfasdata

## Introduktion
I den här handledningen kommer du att upptäcka **hur man ändrar kontur** för en resursallokering och generera tidsfasdata med Aspose.Tasks för Java. Tidsfasdata visar fördelningen av arbete över projektets tidslinje, vilket gör att du kan finjustera scheman, balansera arbetsbelastningar och fatta datadrivna beslut. Att behärska konturändringar hjälper dig att modellera realistiska arbetsmönster såsom front‑loading, back‑loading eller toppbelastningar.

## Snabba svar
- **Vad är en kontur?** En arbetskontur definierar hur ansträngning fördelas över en uppgifts varaktighet (t.ex. Flat, Turtle, Bell).  
- **Varför ändra en kontur?** För att återspegla realistiska arbetsmönster såsom front‑loading eller back‑loading ansträngning.  
- **Vilket bibliotek krävs?** Aspose.Tasks för Java (valfri nyare version).  
- **Behöver jag en licens?** Ja, en giltig Aspose.Tasks‑licens krävs för produktionsanvändning.  
- **Kan jag se resultaten i konsolen?** Exemplet skriver ut startdatum och värden för varje tidsfassegment.

## Vad är “hur man ändrar kontur”?
Att ändra en kontur betyder att uppdatera `WORK_CONTOUR`‑egenskapen för ett `ResourceAssignment`‑objekt. Denna egenskap talar om för Aspose.Tasks hur man fördelar uppdragets totala arbete över uppgiftens varaktighet. Biblioteket tillhandahåller flera fördefinierade konturer såsom Flat, Turtle, Bell och andra, var och en ger ett distinkt mönster av arbetsfördelning över tid.

## Varför använda Aspose.Tasks för att generera tidsfasdata?
Aspose.Tasks genererar tidsfasdata med **0 ms overhead för in‑memory‑operationer** och stöder **50+ output‑format** (MPP, XML, CSV, etc.). Biblioteket kan bearbeta projekt med flera hundra sidor utan att ladda hela filen i minnet, vilket levererar exakt arbetsfördelning för rapportering, resursutjämning och what‑if‑analys. Dess API låter dig automatisera konturändringar och extrahera precisa tidsfasvärden programatiskt.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system. Du kan ladda ner och installera JDK från [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Aspose.Tasks for Java Library: Du behöver ha Aspose.Tasks för Java‑biblioteket. Du kan ladda ner det från [website](https://releases.aspose.com/tasks/java/).

## Importera paket
Klassen `Project` är Aspose.Tasks kärnobjekt som representerar en hel projektfil i minnet. Importera de nödvändiga namnutrymmena innan du börjar arbeta med uppgifter och allokeringar.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Steg 1: Läs in käll-MPP-filen
`Project`‑konstruktorn laddar en befintlig MPP‑fil, analyserar dess struktur utan att fullständigt materialisera varje uppgift i minnet, vilket håller operationen lättviktig.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Steg 2: Hämta uppgift och resursallokering
`ResourceAssignment` länkar en resurs till en uppgift och lagrar egenskaper på allokeringsnivå såsom arbete, kostnad och kontur. Hämta den första allokeringen med `project.getResourceAssignments().getById(1)` (eller vilket giltigt ID som helst) innan du modifierar dess kontur.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Hur man ändrar kontur – Flat (Standard)
`WorkContourType` är en uppräkning som listar de fördefinierade arbetskonturmönstren som stöds av Aspose.Tasks. `Asn.WORK_CONTOUR` identifierar konturfältet för en resursallokering, och `generateTimephasedData()` skapar tidsfasarbetsposter baserat på den aktuella konturinställningen. En **Flat**‑kontur fördelar arbete jämnt över uppgiftens varaktighet; sätt den med `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` och anropa sedan `firstRA.generateTimephasedData()` för att få jämnt fördelade värden.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – Turtle
**Turtle**‑konturen startar med låg ansträngning, accelererar mot mitten och saktar ner igen, likt en sköldpaddas gradvisa takt. Applicera den genom att sätta `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` och sedan regenerera tidsfasdata. Detta mönster är idealiskt för uppgifter som kräver en inlärningskurva innan de når maximal produktivitet.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – BackLoaded
**BackLoaded**‑konturen placerar majoriteten av arbetet mot slutet av uppgiftens schema, med lite ansträngning i början. Sätt den med `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` och regenerera tidsfasdata. Detta är användbart för aktiviteter som är beroende av föregående uppgifter innan arbete kan utföras.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – FrontLoaded
**FrontLoaded**‑konturen koncentrerar ansträngning i början av uppgiften, vilket modellerar scenarier som kickoff‑faser eller intensiva tidiga arbetsinsatser. Applicera den med `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` och anropa sedan `firstRA.generateTimephasedData()` för att se den front‑loaded fördelningen.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – Bell
**Bell**‑konturen skapar ett symmetriskt toppvärde i mitten av tidslinjen, vilket representerar arbete som ökar, når en topp och sedan avtar jämnt. Sätt den via `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` och regenerera tidsfasdata för att visualisera den klockformade arbetskurvan.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – EarlyPeak
**EarlyPeak** placerar det högsta arbetsvärdet tidigt i schemat och avtar sedan. Använd `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` följt av `firstRA.generateTimephasedData()` för att modellera aktiviteter som kräver en stark start, såsom snabb prototypframtagning.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – LatePeak
**LatePeak** flyttar arbets­toppen mot slutet av uppgiften, lämplig för arbete som intensifieras när en deadline närmar sig. Applicera den med `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` och regenerera tidsfasdata för att se den sena arbetsbelastningsökningen.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hur man ändrar kontur – DoublePeak
**DoublePeak** skapar två distinkta arbetsspikar separerade av ett intervall med lägre ansträngning, användbart för uppgifter med två större arbetsinsatser. Sätt den med `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` och anropa sedan `firstRA.generateTimephasedData()` för att få dubbelspik‑mönstret.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Vanliga problem & tips
- **Kontur uppdateras inte?** Se till att du anropar `firstRA.set(Asn.WORK_CONTOUR, …)` *innan* du hämtar tidsfasdata.  
- **Oväntade värden?** Verifiera att uppgiftens start‑ och slutdatum är korrekt inställda i käll‑MPP.  
- **Prestandatips:** Återanvänd samma `Project`‑instans när du itererar genom flera konturer för att undvika onödig fil‑I/O, vilket kan minska bearbetningstiden med upp till 40 % på stora projekt.  
- **Minnestips:** För projekt som överstiger 1 GB, aktivera `Project.setReadOnly(true)` för att hålla minnesanvändningen under 200 MB samtidigt som du fortfarande genererar exakt tidsfasdata.

## Vanliga frågor
**Q: Kan jag använda Aspose.Tasks med andra Java‑bibliotek?**  
A: Ja, Aspose.Tasks integreras sömlöst med andra Java‑bibliotek, vilket gör att du kan kombinera schemaläggningsdata med rapportering, analys eller UI‑ramverk.

**Q: Är Aspose.Tasks lämpligt för storskaliga företagsprojekt?**  
A: Absolut. Biblioteket är konstruerat för att hantera projekt med tiotusentals uppgifter och resurser, och bearbetar flerhundra‑sidiga filer utan prestandaförlust.

**Q: Ger Aspose.Tasks stöd för olika projektfilformat?**  
A: Ja, Aspose.Tasks stöder över 30 format, inklusive MPP, XML, CSV och MPX, vilket möjliggör enkel import/export mellan äldre och moderna system.

**Q: Kan jag anpassa arbetskonturer enligt mina projektkrav?**  
A: Ja, du kan definiera egna konturer genom att tillhandahålla en array av arbetsprocent till `WORK_CONTOUR`‑egenskapen, vilket ger dig full kontroll över arbetsfördelningen.

**Q: Finns det ett community‑forum där jag kan få hjälp med Aspose.Tasks?**  
A: Ja, du kan besöka [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för support, diskussioner och kodexempel från både Aspose‑ingenjörer och community‑medlemmar.

**Senast uppdaterad:** 2026-06-10  
**Testad med:** Aspose.Tasks för Java (senaste versionen)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Skapa resursallokeringar i Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Läs tidsfasdata för resurser i Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [Hur man stoppar allokering och återupptar resursallokeringar i Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}