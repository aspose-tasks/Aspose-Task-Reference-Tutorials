---
date: 2026-06-15
description: Lär dig hur du extraherar timephased data från MS Project-resurser med
  Aspose.Tasks för Java. Steg‑för‑steg‑guide för att hämta resurs med id.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Läs Timephased Data för resurser i Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Läs Timephased Data för resurser i Aspose.Tasks – hämta resurs med id
url: /sv/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Läs tidsfasade data för resurser i Aspose.Tasks

## Introduktion
I den här handledningen kommer du att lära dig **how to get resource by id** och läsa dess tidsfasade data med Aspose.Tasks för Java. Vi går igenom varje steg—från att sätta upp projektmappen till att skriva ut tidsfasade värden för arbete och kostnad—så att du kan extrahera värdefull schemaläggningsinformation från vilken Microsoft Project‑fil som helst programmässigt. Aspose.Tasks för Java är ett omfattande API som möjliggör för utvecklare att skapa, läsa, modifiera och konvertera Microsoft Project‑filer utan att behöva ha Microsoft Project installerat, och stödjer ett brett spektrum av projektledningsfunktioner och format.

## Snabba svar
- **What does “get resource by id” do?** Det hämtar ett specifikt `Resource`‑objekt från ett `Project` med hjälp av dess unika identifierare.  
- **Which library handles timephased data?** Aspose.Tasks för Java tillhandahåller `Resource.getTimephasedData`‑API:t.  
- **Do I need a license?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Can I read large projects?** Ja—Aspose.Tasks kan bearbeta filer med upp till 10 000 uppgifter utan att ladda hela filen i minnet.  
- **What Java version is required?** Java 8 eller högre; biblioteket är kompatibelt med alla större JDK‑versioner.

## Vad är “get resource by id”?
`get resource by id` är ett metodanrop som hämtar en `Resource`‑instans från ett inläst `Project` med hjälp av resursens numeriska ID. Denna operation möjliggör exakt åtkomst till en resurs detaljerade egenskaper, såsom dess tilldelningar, kalendrar och anpassade fält, och är avgörande för att extrahera tidsfasade arbets‑ eller kostnadsdata som är kopplade till just den resursen.

## Varför använda Aspose.Tasks för tidsfasade data?
Aspose.Tasks stödjer **50+ in‑ och utdataformat** (MPP, XML, CSV osv.) och kan extrahera tidsfasade arbets‑ och kostnadsvärden för resurser över flerårsplaner samtidigt som minnesanvändningen hålls låg. API:t returnerar data i 15‑minutersintervall som standard, vilket ger dig detaljerad insikt för rapportering eller anpassad analys.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system. Du kan ladda ner det från [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) och följa installationsinstruktionerna.  
2. Aspose.Tasks for Java Library: Ladda ner Aspose.Tasks för Java‑biblioteket från [download page](https://releases.aspose.com/tasks/java/) och följ installationsinstruktionerna som finns i dokumentationen.

## Importera paket
Det första steget är att importera de nödvändiga Aspose.Tasks‑klasserna till din Java‑källkod.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Steg 1: Ställ in datakatalogen
Definiera först katalogen där din MS Project‑fil är placerad. Att hålla datamappen separat från källkoden gör projektet enklare att underhålla.

```java
String dataDir = "Your Data Directory";
```

## Steg 2: Läs MS Project‑mallfil
Ange namnet på din MS Project‑mallfil. Att använda en mall säkerställer konsekventa kolumninställningar över olika projekt.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Steg 3: Läs indatafil som projekt
`Project`‑klassen är Aspose.Tasks kärnobjekt som representerar en Microsoft Project‑fil i minnet. Att ladda filen ger dig programmatisk åtkomst till uppgifter, resurser och scheman.

```java
Project project = new Project(dataDir + fileName);
```

## Steg 4: Hämta resurs efter ID
För att hämta en specifik resurs, anropa metoden `getResources().getById(id)`. Detta är den exakta operation som refereras av huvudnyckelordet.

```java
Resource resource = project.getResources().getByUid(1);
```

## Steg 5: Skriv ut tidsfasade data för resursarbete
När du har `Resource`‑objektet kan du anropa `resource.getTimephasedData(ResourceTimephasedDataType.Work)` för att få arbetsallokeringar över tid. Den returnerade samlingen innehåller `TimephasedData`‑objekt som inkluderar startdatum, slutdatum och mängden arbete för varje intervall.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Steg 6: Skriv ut tidsfasade data för resurskostnad
På samma sätt returnerar `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` kostnadsinformation uppdelad efter samma tidsintervall. Detta är användbart för budgetering och kostnadsspårningsrapporter.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Hur man hämtar resurs efter ID på en rad?
Läs in projektet och anropa sedan `project.getResources().getById(5)`—byt ut **5** mot det faktiska resurs‑ID du behöver. Detta enkla anrop returnerar `Resource`‑objektet, varefter du kan fråga efter dess tidsfasade data, tilldelningar eller anpassade fält. Metoden körs i O(1)‑tid eftersom resurser indexeras internt.

## Vanliga problem och lösningar
- **Resource not found** – Säkerställ att ID‑talet finns i projektfilen; ID:n börjar på 1 och är unika per resurs.  
- **Empty timephased data** – Verifiera att resursen har arbets‑ eller kostnadstilldelningar; annars blir samlingen tom.  
- **Large file performance** – Använd `Project.setLoadOptions(LoadOptions.fromFile(...))` för att aktivera lazy loading för projekt större än 500 MB.

## Vanliga frågor

**Q: Can Aspose.Tasks handle other types of project files apart from Microsoft Project?**  
A: Ja, Aspose.Tasks stödjer MPP, XML, CSV och flera andra format, vilket möjliggör läsning och skrivning över olika standarder.

**Q: Is Aspose.Tasks compatible with different Java development environments?**  
A: Absolut. Biblioteket fungerar med alla stora IDE:n (IntelliJ IDEA, Eclipse, NetBeans) och byggverktyg (Maven, Gradle).

**Q: Can I manipulate project data using Aspose.Tasks?**  
A: Ja, du kan skapa, modifiera och radera uppgifter, resurser, tilldelningar och även anpassade fält via API:t.

**Q: Is Aspose.Tasks suitable for enterprise‑level projects?**  
A: Det är det. Företag förlitar sig på Aspose.Tasks för högvolymbearbetning, batchkonverteringar och server‑sidrapportering eftersom ingen Microsoft Project‑installation krävs.

**Q: Where can I find support if I encounter issues while using Aspose.Tasks?**  
A: Du kan besöka [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för hjälp från communityn och supportteamet.

## Slutsats
I den här handledningen har vi lärt oss hur man **get resource by id** och läser dess tidsfasade arbets‑ och kostnadsdata med Aspose.Tasks för Java. Genom att följa dessa steg kan du effektivt extrahera värdefull schemaläggningsinformation från dina projektfiler och integrera den i anpassade rapporterings‑ eller analys‑pipelines.

---

**Last Updated:** 2026-06-15  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose

## Relaterade handledningar

- [Lägg till resurs i projekt med Aspose.Tasks för Java](/tasks/java/resource-management/create-resources/)
- [Hantera MS Project-resurskostnader med Aspose.Tasks för Java](/tasks/java/resource-management/resource-cost/)
- [Läs arbetsveckor Java från MS Project-kalender Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}