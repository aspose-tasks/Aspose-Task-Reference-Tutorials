---
date: 2026-06-10
description: Lär dig hur du skapar ett utökat attribut i Java, laddar en Microsoft
  Project-fil, sätter numeriska värden och sparar projektet som XML med Aspose.Tasks
  för Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Hantera utökade resursattribut i Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hur man skapar ett utökat attribut i Java med Aspose.Tasks
url: /sv/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar utökat attribut i Java med Aspose.Tasks

## Introduktion
I den här praktiska guiden kommer du att **skapa ett utökat attribut i Java** för en Microsoft Project‑fil med Aspose.Tasks. Vi går igenom hur du laddar ett befintligt projekt, definierar ett nytt numeriskt attribut, tilldelar ett värde till en resurs och slutligen sparar ändringarna som en XML‑fil. När du är klar har du ett återanvändbart kodmönster som kan infogas i vilken Java‑baserad projektledningslösning som helst.

## Snabba svar
- **Vad är ett utökat attribut?**  
  Ett användardefinierat fält (t.ex. Ålder, Kompetensnivå) som lagrar extra data för resurser eller uppgifter.  
- **Vilket API skapar det?**  
  Aspose.Tasks for Java tillhandahåller klassen `ExtendedAttributeDefinition` för att definiera och hantera anpassade attribut.  
- **Behöver jag en licens?**  
  En tillfällig evalueringslicens fungerar för utveckling; en full licens krävs för produktionsdistributioner.  
- **Kan jag lagra siffror?**  
  Ja – använd `setNumericValue(BigDecimal)` för att tilldela exakta decimala värden.  
- **Hur sparar jag ändringarna?**  
  Anropa `project.save("output.xml", SaveFileFormat.Xml)` för att skriva det uppdaterade projektet i XML‑format.

## Vad är ett anpassat attribut?
Ett **anpassat attribut** (även känt som ett utökat attribut) är en extra kolumn du kan lägga till resurser eller uppgifter i Microsoft Project. Det låter dig samla in data som inte täcks av de inbyggda fälten, såsom anställdas ålder, certifieringsnivå eller någon affärsspecifik metrisk.

## Varför skapa ett utökat attribut i Java?
Att skapa ett utökat attribut i Java låter dig programatiskt berika projektdata, säkerställa konsistens mellan filer och möjliggöra automatiserad rapportering. Genom att definiera attributet en gång kan du tillämpa det på ett godtyckligt antal resurser eller uppgifter utan manuell inmatning, vilket sparar tid och minskar fel.

- **Anpassa data till din organisation** – lagra vilken metrisk som helst som är viktig för dig utan manuella Excel‑lösningar.  
- **Möjliggör rikare rapportering** – fråga det anpassade fältet senare för instrumentpaneler eller analyser.  
- **Behåll konsistens** – programatiskt tillämpa samma definition över dussintals projekt, vilket eliminerar mänskliga fel.  
- **Prestandatestad** – Aspose.Tasks bearbetar projekt med upp till 10 000 uppgifter och 5 000 resurser utan att ladda hela filen i minnet, enligt produktens benchmark.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Kit** – JDK 8 eller nyare installerat.  
2. **Aspose.Tasks for Java** – ladda ner den senaste versionen från [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA eller någon Java‑kompatibel utvecklingsmiljö.  

## Hur skapar man ett utökat attribut i Java?
Ladda ditt projekt, definiera attributet, fäst det på en resurs och spara filen – allt i några enkla steg. Följande avsnitt delar upp varje steg i en kort förklaring följt av en platshållare där din faktiska kod finns.

### Steg‑för‑steg‑guide

#### Importera paket
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` och relaterade klasser finns i `com.aspose.tasks`‑namnutrymmet. Importera dem högst upp i din Java‑fil.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### Steg 1: Definiera datakatalog
`Paths` är en verktygsklass som tillhandahåller metoder för att erhålla en filsökväg på ett plattformsoberoende sätt.

```java
String dataDir = "Your Data Directory";
```

#### Steg 2: Ladda Microsoft Project‑fil
`Project` representerar en Microsoft Project‑fil i minnet och möjliggör läs‑ och skrivåtkomst till dess innehåll.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Steg 3: Definiera det anpassade attributet
`ExtendedAttributeDefinition` definierar schemat för ett nytt anpassat fält som kan fästas på resurser eller uppgifter.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Steg 4: Sätt numeriskt värde i Java
`ExtendedAttributeResource` innehåller värdet för ett anpassat attribut för en specifik resursinstans.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Steg 5: Lägg till resurs och fäst det anpassade attributet
`Resource` modellerar en projektresurs såsom en person, utrustning eller material.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Steg 6: Spara projekt som XML
`SaveFileFormat` listar de stödjade utdataformaten för att spara ett projekt, inklusive XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Steg 7: Visa resultat
`System.out.println` skriver ut en rad text till standardkonsolens utskrift.

```java
System.out.println("Process completed Successfully");
```

## Vanliga fallgropar & tips
- **Konflikter med attribut‑ID:** Anropa alltid `project.getExtendedAttributes().getById(id)` innan du skapar en ny definition för att förhindra duplicerade identifierare.  
- **Precisionhantering:** Föredra `BigDecimal` framför `float`/`double` för exakta numeriska värden; detta undviker avrundningsfel i rapportering.  
- **Filsökvägs‑tillförlitlighet:** Använd `Paths.get(...).toAbsolutePath()` eller konfigurera IDE:ns arbetskatalog för att eliminera `FileNotFoundException`.  

## Vanliga frågor

**Q: Kan jag skapa anpassade attribut för uppgifter såväl som resurser?**  
A: Ja – använd `ExtendedAttributeTask` istället för `ExtendedAttributeResource` när du definierar attributschemat.

**Q: Är det möjligt att lägga till flera anpassade attribut på en gång?**  
A: Absolut. Skapa separata `ExtendedAttributeDefinition`‑objekt för varje attribut och fäst dem på önskade resurser eller uppgifter.

**Q: Vilka format kan jag spara projektet i?**  
A: Aspose.Tasks stödjer XML, MPP, PDF, HTML och mer än 30 ytterligare format. I detta exempel använde vi `SaveFileFormat.Xml`.

**Q: Behöver jag en licens för utvecklingsbyggen?**  
A: En tillfällig evalueringslicens är tillräcklig för testning. För någon produktionsdistribution krävs en full kommersiell licens.

**Q: Hur läser jag tillbaka de anpassade attributvärdena senare?**  
A: Anropa `resource.getExtendedAttributes()` och iterera över samlingen; hämta det lagrade värdet med `getNumericValue()` eller `getTextValue()`.

---

**Senast uppdaterad:** 2026-06-10  
**Testad med:** Aspose.Tasks for Java 24.12  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skapar resurser – Resurshantering med Aspose.Tasks för Java](/tasks/java/resource-management/)
- [Skapa anpassat fält Aspose – Hantera utökade attribut](/tasks/java/project-management/extended-attributes/)
- [Hur man skapar projekt – Ställ in nya uppgiftsattribut med Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}