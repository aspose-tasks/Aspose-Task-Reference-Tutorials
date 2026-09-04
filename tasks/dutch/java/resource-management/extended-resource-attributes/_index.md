---
date: 2026-06-10
description: Leer hoe je een uitgebreid attribuut maakt in Java, een Microsoft Project‑bestand
  laadt, numerieke waarden instelt en het project opslaat als XML met Aspose.Tasks
  voor Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Beheer uitgebreide resource‑attributen in Aspose.Tasks
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
title: Hoe een uitgebreid attribuut te creëren in Java met Aspose.Tasks
url: /nl/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een uitgebreid attribuut in Java maken met Aspose.Tasks

## Introductie
In deze praktische gids **maak je een uitgebreid attribuut in Java** voor een Microsoft Project‑bestand met Aspose.Tasks. We lopen door het laden van een bestaand project, het definiëren van een nieuw numeriek attribuut, het toewijzen van een waarde aan een resource, en uiteindelijk het opslaan van de wijzigingen als een XML‑bestand. Aan het einde heb je een herbruikbaar code‑patroon dat in elke Java‑gebaseerde project‑managementoplossing kan worden geïntegreerd.

## Snelle antwoorden
- **Wat is een uitgebreid attribuut?**  
  Een door de gebruiker gedefinieerd veld (bijv. Leeftijd, Vaardigheidsniveau) dat extra gegevens opslaat voor resources of taken.  
- **Welke API maakt het?**  
  Aspose.Tasks for Java biedt de `ExtendedAttributeDefinition`‑klasse om aangepaste attributen te definiëren en te beheren.  
- **Heb ik een licentie nodig?**  
  Een tijdelijke evaluatielicentie werkt voor ontwikkeling; een volledige licentie is vereist voor productie‑implementaties.  
- **Kan ik getallen opslaan?**  
  Ja – gebruik `setNumericValue(BigDecimal)` om precieze decimale waarden toe te wijzen.  
- **Hoe sla ik de wijzigingen op?**  
  Roep `project.save("output.xml", SaveFileFormat.Xml)` aan om het bijgewerkte project in XML‑formaat te schrijven.

## Wat is een aangepast attribuut?
Een **aangepast attribuut** (ook wel een uitgebreid attribuut genoemd) is een extra kolom die je kunt toevoegen aan resources of taken in Microsoft Project. Het stelt je in staat gegevens vast te leggen die niet door de ingebouwde velden worden gedekt, zoals de leeftijd van een medewerker, certificatieniveau, of een bedrijfs‑specifieke metric.

## Waarom een uitgebreid attribuut in Java maken?
Het maken van een uitgebreid attribuut in Java stelt je in staat projectgegevens programmatically te verrijken, consistentie over bestanden te waarborgen en geautomatiseerde rapportage mogelijk te maken. Door het attribuut één keer te definiëren, kun je het toepassen op een willekeurig aantal resources of taken zonder handmatige invoer, waardoor tijd wordt bespaard en fouten worden verminderd.

- **Pas gegevens aan jouw organisatie aan** – sla elke metriek op die voor jou van belang is zonder handmatige Excel‑omwegen.  
- **Maak rijkere rapportage mogelijk** – query later het aangepaste veld voor dashboards of analyses.  
- **Behoud consistentie** – pas programmatically dezelfde definitie toe over tientallen projecten, waardoor menselijke fouten worden geëlimineerd.  
- **Prestatietest** – Aspose.Tasks verwerkt projecten met tot 10.000 taken en 5.000 resources zonder het volledige bestand in het geheugen te laden, volgens de productbenchmarks.

## Voorvereisten
1. **Java Development Kit** – JDK 8 of nieuwer geïnstalleerd.  
2. **Aspose.Tasks for Java** – download de nieuwste release van [hier](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, of een andere Java‑compatibele ontwikkelomgeving.  

## Hoe maak je een uitgebreid attribuut in Java?
Laad je project, definieer het attribuut, koppel het aan een resource en sla het bestand op – alles in een paar eenvoudige stappen. De volgende secties splitsen elke stap op in een beknopte uitleg, gevolgd door de placeholder waar je eigen code staat.

### Stapsgewijze handleiding

#### Pakketten importeren
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` en gerelateerde klassen bevinden zich in de `com.aspose.tasks` namespace. Importeer ze bovenaan je Java‑bestand.

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

#### Stap 1: Definieer gegevensdirectory
`Paths` is een hulpprogrammaklasse die methoden biedt om een bestandssysteempad op een platform‑onafhankelijke manier te verkrijgen.

```java
String dataDir = "Your Data Directory";
```

#### Stap 2: Laad Microsoft Project‑bestand
`Project` vertegenwoordigt een Microsoft Project‑bestand in het geheugen, waardoor lezen en schrijven van de inhoud mogelijk is.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Stap 3: Definieer het aangepaste attribuut
`ExtendedAttributeDefinition` definieert het schema van een nieuw aangepast veld dat kan worden gekoppeld aan resources of taken.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Stap 4: Numerieke waarde instellen in Java
`ExtendedAttributeResource` bevat de waarde van een aangepast attribuut voor een specifieke resource‑instantie.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Stap 5: Voeg resource toe en koppel het aangepaste attribuut
`Resource` modelleert een projectresource zoals een persoon, uitrusting of materiaal.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Stap 6: Sla project op als XML
`SaveFileFormat` somt de ondersteunde uitvoerformaten op voor het opslaan van een project, inclusief XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Stap 7: Resultaat weergeven
`System.out.println` drukt een regel tekst af naar de standaard console‑output.

```java
System.out.println("Process completed Successfully");
```

## Veelvoorkomende valkuilen & tips
- **Conflicten met attribuut‑ID's:** Roep altijd `project.getExtendedAttributes().getById(id)` aan voordat je een nieuwe definitie maakt om dubbele identifiers te voorkomen.  
- **Precisiebehandeling:** Geef de voorkeur aan `BigDecimal` boven `float`/`double` voor exacte numerieke waarden; dit voorkomt afrondingsfouten in rapportage.  
- **Betrouwbaarheid van bestandspaden:** Gebruik `Paths.get(...).toAbsolutePath()` of configureer de werkmap van je IDE om `FileNotFoundException` te voorkomen.  

## Veelgestelde vragen

**Q: Kun ik aangepaste attributen maken voor taken evenals resources?**  
A: Ja – gebruik `ExtendedAttributeTask` in plaats van `ExtendedAttributeResource` bij het definiëren van het attribuut‑schema.

**Q: Is het mogelijk om meerdere aangepaste attributen in één keer toe te voegen?**  
A: Absoluut. Maak aparte `ExtendedAttributeDefinition`‑objecten voor elk attribuut en koppel ze aan de gewenste resources of taken.

**Q: In welke formaten kan ik het project opslaan?**  
A: Aspose.Tasks ondersteunt XML, MPP, PDF, HTML en meer dan 30 extra formaten. In dit voorbeeld hebben we `SaveFileFormat.Xml` gebruikt.

**Q: Heb ik een licentie nodig voor ontwikkel‑builds?**  
A: Een tijdelijke evaluatielicentie is voldoende voor testen. Voor elke productie‑implementatie is een volledige commerciële licentie vereist.

**Q: Hoe lees ik later de waarden van het aangepaste attribuut terug?**  
A: Roep `resource.getExtendedAttributes()` aan en doorloop de collectie; haal de opgeslagen waarde op met `getNumericValue()` of `getTextValue()`.

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Gerelateerde tutorials

- [Hoe resources maken – Resourcebeheer met Aspose.Tasks voor Java](/tasks/java/resource-management/)
- [Aangepast veld maken Aspose - Uitgebreide attributen verwerken](/tasks/java/project-management/extended-attributes/)
- [Hoe een project maken – Nieuwe taak‑attributen instellen met Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}