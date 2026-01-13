---
date: 2026-01-13
description: Leer hoe u een aangepast attribuut maakt, een Microsoft Project‑bestand
  laadt, een numerieke waarde instelt in Java en het project opslaat als XML met Aspose.Tasks
  voor Java.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe een aangepast attribuut te maken in MS Project met Aspose.Tasks
url: /nl/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een aangepast attribuut te maken in MS Project met Aspose.Tasks

## Inleiding
In deze tutorial ontdek je hoe je een aangepast attribuut maakt voor resources in een Microsoft Project‑bestand met Aspose.Tasks voor Java. We lopen door het laden van een Microsoft Project‑bestand, het definiëren van een nieuw numeriek attribuut, het toewijzen van een waarde, en tenslotte het opslaan van het project als XML. Aan het einde heb je een duidelijk, hands‑on voorbeeld dat je kunt aanpassen aan je eigen project‑managementoplossingen.

## Snelle antwoorden
- **Wat betekent “custom attribute”?**  
  Een door de gebruiker gedefinieerd veld dat extra informatie opslaat (bijv. Leeftijd, Vaardigheidsniveau) voor een resource of taak.  
- **Welke bibliotheek behandelt dit?**  
  Aspose.Tasks for Java provides a fluent API to create and manage custom attributes.  
- **Heb ik een licentie nodig?**  
  Een gratis tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Kan ik numerieke waarden instellen?**  
  Ja – gebruik `setNumericValue` met een `BigDecimal` (bijv. `30.5345`).  
- **Hoe wordt het project opgeslagen?**  
  Het gewijzigde bestand kan worden opgeslagen als XML met `SaveFileFormat.Xml`.

## Wat is een custom attribute?
Een **custom attribute** (ook wel extended attribute genoemd) is een extra kolom die je kunt toevoegen aan resources of taken in Microsoft Project. Het stelt je in staat gegevens vast te leggen die niet worden gedekt door de ingebouwde velden, zoals de leeftijd van een medewerker, certificeringsniveau, of elke bedrijfsspecifieke metriek.

## Waarom een custom attribute maken in MS Project?
- **Pas projectgegevens aan** de behoeften van uw organisatie aan.  
- **Stel geavanceerde rapportage mogelijk** door waarden op te slaan die later kunnen worden opgevraagd.  
- **Behoud consistentie** over meerdere projecten door programmatically dezelfde attribuutdefinitie toe te passen.

## Vereisten
Voordat u begint, zorg ervoor dat u het volgende heeft:

1. **Java Development Environment** – JDK 8 of hoger geïnstalleerd.  
2. **Aspose.Tasks for Java** – Download de nieuwste versie van [hier](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, of een andere Java‑compatibele IDE.  

## Stapsgewijze handleiding

### Import Packages
Eerst, importeer de Aspose.Tasks‑klassen die u nodig heeft. Deze bieden de kernfunctionaliteit voor het verwerken van projecten, resources en uitgebreide attributen.

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

### Stap 1: Definieer de gegevensdirectory
Stel de map in waar uw bron‑projectbestand zich bevindt en waar de uitvoer wordt weggeschreven.

```java
String dataDir = "Your Data Directory";
```

### Stap 2: Laad Microsoft Project‑bestand
Maak een `Project`‑instantie door het bestaande bestand te laden. Dit is de **load Microsoft project file** stap die u volledige toegang tot de inhoud geeft.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Stap 3: Definieer het aangepaste attribuut
We definiëren een nieuw numeriek attribuut genaamd **Age**. De API controleert of de definitie al bestaat; zo niet, dan maakt hij er een aan.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Stap 4: Stel numerieke waarde in Java in
Maak een instantie van het attribuut voor een specifieke resource en wijs een numerieke waarde toe met `setNumericValue`. Dit demonstreert **set numeric value java** in actie.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Stap 5: Voeg resource toe en koppel het aangepaste attribuut
Voeg een nieuwe resource toe met de naam **R1** en koppel het eerder gemaakte aangepaste attribuut eraan.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Stap 6: Sla project op als XML
Ten slotte, bewaar de wijzigingen door het project op te slaan. Dit is de **save project as xml** stap, die een schone XML‑representatie van het bijgewerkte bestand produceert.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Stap 7: Toon resultaat
Print een vriendelijke bevestiging zodat u weet dat het proces zonder fouten is voltooid.

```java
System.out.println("Process completed Successfully");
```

Door deze stappen te volgen, heeft u met succes **een aangepast attribuut** gemaakt, een Microsoft Project‑bestand geladen, een numerieke waarde ingesteld met Java, en het project opgeslagen als XML.

## Veelvoorkomende valkuilen & tips
- **Attribuut‑ID‑conflicten:** Controleer altijd `getById` voordat u een nieuwe definitie maakt om dubbele ID's te voorkomen.  
- **Precisiebehandeling:** `BigDecimal` behoudt decimale precisie; vermijd het gebruik van `float` of `double` voor exacte waarden.  
- **Bestandspaden:** Gebruik absolute paden of configureer de werkdirectory van uw IDE om `FileNotFoundException` te voorkomen.  

## Veelgestelde vragen

**Q: Kan ik custom attributes maken voor taken evenals voor resources?**  
A: Ja – gebruik `ExtendedAttributeTask` in plaats van `ExtendedAttributeResource` bij het definiëren van het attribuut.

**Q: Is het mogelijk om meerdere custom attributes in één keer toe te voegen?**  
A: Absoluut. Maak afzonderlijke `ExtendedAttributeDefinition`‑objecten voor elk attribuut en koppel ze aan de gewenste resources of taken.

**Q: In welke formaten kan ik het project opslaan?**  
A: Aspose.Tasks ondersteunt XML, MPP, en verschillende andere formaten zoals PDF en HTML. In dit voorbeeld gebruikten we `SaveFileFormat.Xml`.

**Q: Heb ik een licentie nodig voor Aspose.Tasks voor ontwikkel‑builds?**  
A: Een tijdelijke licentie is voldoende voor evaluatie. Voor productie‑implementaties is een volledige licentie vereist.

**Q: Hoe lees ik later de custom attribute‑waarden terug?**  
A: Gebruik `resource.getExtendedAttributes()` om door de gekoppelde attributen te itereren en hun waarden op te halen met `getNumericValue()` of `getTextValue()`.

## Conclusie
Het creëren van een **aangepast attribuut** in Microsoft Project met Aspose.Tasks voor Java is eenvoudig zodra u de workflow begrijpt: laad het project, definieer het attribuut, stel de waarde in, koppel het aan een resource, en sla het bestand op. Deze aanpak stelt u in staat om projectdatamodellen programmatisch uit te breiden, waardoor rijkere rapportage en een strakkere integratie met uw bedrijfsprocessen mogelijk wordt.

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}