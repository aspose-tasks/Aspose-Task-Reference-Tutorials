---
date: 2026-09-25
description: Lär dig hur du hämtar valutakoder från MS Project-filer med Aspose.Tasks
  för Java – det snabba sättet att få den valutakod som Java‑utvecklare behöver.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Hantera valutakoder i Aspose.Tasks
og_description: Hämta valutakod java från MS Project-filer med Aspose.Tasks. Denna
  guide visar hur du läser projektet, extraherar ISO‑valutaidentifieraren och använder
  den i Java‑applikationer.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Hämta valutakod java från MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Hämta valutakod java från MS Project med Aspose.Tasks
url: /sv/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hämta valutakod java från MS Project med Aspose.Tasks

## Introduktion
I den här handledningen kommer du att lära dig **hur man hämtar valutakod java** från en MS Project‑fil genom att använda Aspose.Tasks Java‑API. Oavsett om du behöver skapa multivaluta‑finansrapporter, konsolidera projekt över olika regioner, eller helt enkelt visa rätt valutasymbol i ett efterföljande system, så tar stegen nedan dig från miljöinställning till det enkellinje‑anrop som returnerar ISO‑valutaidentifieraren. I slutet av guiden kommer du att känna dig bekväm med att ladda vilken som helst av de stödjade Project‑filformaten och extrahera den tre‑bokstaviga valutakoden såsom `USD`, `EUR` eller `GBP`.

## Snabba svar
- **Vad gör API:et?** Det läser MS Project‑filer och exponerar egenskaper såsom valutakoden.  
- **Vilket språk används?** Java, via Aspose.Tasks för Java‑biblioteket.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Kan jag hämta koden i en rad?** Ja—`prj.get(Prj.CURRENCY_CODE)` returnerar valutakodens sträng omedelbart.  
- **Är det kompatibelt med alla Project‑versioner?** Aspose.Tasks stöder mer än 20 inmatningsformat, inklusive äldre MPP, XML och XER‑filer.

## Vad är en läst MS Project‑fil?
Att läsa en MS Project‑fil innebär att programmässigt öppna en *.mpp* (eller något annat stödformat såsom XML eller XER) och komma åt dess interna datastrukturer. Dessa strukturer inkluderar uppgifter, resurser, kalendrar, kostnadstabeller och finansiella inställningar. Genom att parsra filen kan du extrahera information utan att starta Microsoft Project, vilket möjliggör automatiserad rapportering, migrering och integrationsarbetsflöden.

## Varför använda Aspose.Tasks för att läsa msproject‑filer?
Aspose.Tasks erbjuder en ren Java‑lösning som eliminerar behovet av COM‑interop eller en lokal Microsoft Project‑installation. Det stöder mer än 20 filformat, kan hantera projekt med tusentals uppgifter samtidigt som det använder under 100 MB minne, och tillhandahåller en rik objektmodell. Direkt åtkomst till konstanter som `Prj.CURRENCY_CODE` låter dig hämta valutainformation omedelbart och pålitligt.

## Förutsättningar
Innan vi dyker ner i koden, se till att du har följande:

### Java Development Kit (JDK) installerat
En aktuell JDK (11 eller senare) krävs. Ladda ner den från den officiella Oracle‑sidan: [här](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks för Java‑bibliotek
Skaffa de senaste Aspose.Tasks för Java‑binärerna och lägg till dem i ditt projekts classpath. Den fullständiga dokumentationen och nedladdningslänkarna finns tillgängliga [här](https://reference.aspose.com/tasks/java/).

## Importera paket
`Project`‑klassen och `Prj`‑konstanterna finns i `com.aspose.tasks`‑namnrymden. Importera dem högst upp i din Java‑källfil:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Steg‑för‑steg‑guide

### Steg 1: ange datakatalog
Definiera mappen som innehåller din *.mpp*-fil. Justera sökvägen så att den matchar din miljö så att körningen kan hitta projektfilen.

```java
String dataDir = "Your Data Directory";
```

### Steg 2: läs in projektfilen
`Project`‑klassen är Aspose.Tasks översta objekt som representerar en enskild MS Project‑fil i minnet. Att skapa en instans läser filen och bygger en minnesmodell som du kan fråga.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Steg 3: hämta valutakod
`Prj.CURRENCY_CODE`‑konstanten identifierar egenskapen som lagrar ISO‑valutaidentifieraren. Att anropa `prj.get(Prj.CURRENCY_CODE)` returnerar den tre‑bokstavskoden i ett enda anrop.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Utdata blir den tre‑bokstavs ISO‑valutakoden (t.ex. `USD`, `EUR`, `GBP`) som projektet är konfigurerat att använda.

### Steg 4: hur man hämtar valutakod i Java (ytterligare kontext)
Läs in ditt projekt, anropa `prj.get(Prj.CURRENCY_CODE)` och lagra resultatet i en `String`. Du kan sedan skicka detta värde till någon finansiell tjänst, rapporteringsmotor eller UI‑komponent som kräver en valutaidentifierare.

### Steg 5: (valfritt) använd valutakoden
Typiska efterföljande scenarier inkluderar:

- **Rapportgenerering** – lägg till koden före kostnadskolumner (`USD 1,200`).  
- **API‑integration** – skicka ISO‑koden till betalningsgateways som kräver en valutaparameter.  
- **Datakonsolidering** – gruppera flera projekt efter valuta för portfölj‑nivåanalys.

## Vanliga problem och lösningar
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null‑utdata** | Projektfilen definierar ingen valuta (standard är tom). | Ställ in valutan i Microsoft Project eller tilldela den via `prj.set(Prj.CURRENCY_CODE, "USD");` innan du läser. |
| **Fil ej hittad** | Felaktig `dataDir`‑sökväg. | Verifiera sökvägen och säkerställ att filnamnet matchar exakt, inklusive skiftlägeskänslighet. |
| **Ej stöd för filversion** | Mycket gammal eller korrupt *.mpp*-fil. | Uppgradera till den senaste Aspose.Tasks‑versionen eller konvertera filen till ett nyare format i Microsoft Project först. |

## Vanliga frågor

**Q: Kan Aspose.Tasks hantera komplexa projektstrukturer?**  
A: Ja, API:et läser flernivå‑uppgiftshierarkier, resurspooler, anpassade fält och kalendrar utan begränsning.

**Q: Är Aspose.Tasks kompatibelt med olika versioner av MS Project‑filer?**  
A: Absolut. Det stöder MPP, XML, XER och andra format från Project 98 till de senaste Office‑utgåvorna.

**Q: Tillhandahåller Aspose.Tasks dokumentation och support?**  
A: Omfattande API‑referens, kodexempel och dedikerad teknisk support finns tillgängliga på Aspose‑webbplatsen.

**Q: Kan jag prova Aspose.Tasks innan jag köper?**  
A: En gratis provversion erbjuds så att du kan utvärdera alla funktioner, inklusive extrahering av valutakod.

**Q: Var kan jag få en tillfällig licens för utvärdering?**  
A: Tillfälliga licenser finns tillgängliga på [webbplatsen](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2026-09-25  
**Testad med:** Aspose.Tasks för Java (senaste versionen)  
**Författare:** Aspose

## Relaterade handledningar

- [Projektegenskaper Java – Läs metadata med Aspose.Tasks](/tasks/java/project-properties/)
- [Hur man läser projektinformation från Microsoft Project med Aspose.Tasks för Java](/tasks/java/project-properties/read-project-info/)
- [Hämta MS Project‑konturkoder i Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}