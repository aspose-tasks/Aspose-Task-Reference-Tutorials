---
date: 2026-09-30
description: Leer hoe u een task extended attribute maakt met Aspose.Tasks voor Java,
  de toonaangevende java project management library voor het toevoegen van aangepaste
  task fields.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Hoe een task extended attribute maken met Aspose.Tasks Java
og_description: Leer hoe u een task extended attribute maakt met Aspose.Tasks voor
  Java, de toonaangevende java project management library voor het toevoegen van aangepaste
  task fields.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Hoe een task extended attribute maken met Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Hoe een task extended attribute maken met Aspose.Tasks Java
url: /nl/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een taak‑uitgebreid attribuut met Aspose.Tasks Java

## Inleiding
In deze tutorial leer je hoe je **een taak‑uitgebreid attribuut** maakt in een Microsoft Project‑bestand met behulp van Aspose.Tasks voor Java. Het toevoegen van aangepaste velden stelt je in staat project‑specifieke gegevens vast te leggen die niet door de ingebouwde kolommen worden gedekt, waardoor je fijnmazigere controle krijgt over rapportage en resource‑planning. Aan het einde van de gids kun je platte‑tekst, lookup‑geactiveerde en duur‑attributen toevoegen aan elke taak.

## Snelle antwoorden
- **Wat betekent “extended attribute”?** Het is een aangepast veld dat je definieert en koppelt aan taken, resources of toewijzingen.  
- **Welke bibliotheek voegt deze mogelijkheid toe?** Aspose.Tasks for Java, een Java projectmanagementbibliotheek.  
- **Heb ik een licentie nodig om het te proberen?** Ja – een gratis proefperiode van 30 dagen is beschikbaar op de Aspose‑website.  
- **Kan ik lookup‑waarden toevoegen?** Absoluut; je kunt een lijst met toegestane waarden leveren voor tekst‑ of duur‑velden.  
- **Is de API compatibel met Java 8 en later?** Ja, het ondersteunt Java 8+ en draait op alle belangrijke besturingssystemen.

## Wat is een taak‑uitgebreid attribuut?
Een taak‑uitgebreid attribuut is een door de gebruiker gedefinieerde kolom die extra informatie opslaat voor elke taak in een Project‑bestand. Het gedraagt zich als een ingebouwd veld, maar kan elk datatype bevatten dat je nodig hebt, zoals tekst, cijfers, datums of duur.

## Waarom Aspose.Tasks voor Java gebruiken?
Aspose.Tasks ondersteunt **meer dan 50 bestandsformaten** en kan projecten met **meer dan 10.000 taken** verwerken zonder dat Microsoft Project geïnstalleerd hoeft te zijn. De bibliotheek werkt volledig offline, waardoor gegevensprivacy en deterministische prestaties voor enterprise‑scale oplossingen worden gegarandeerd.

## Voorvereisten
- Basiskennis van Java-programmeren.  
- De Aspose.Tasks for Java‑bibliotheek geïnstalleerd. Je kunt deze downloaden van de [website](https://releases.aspose.com/tasks/java/).  
- Een Java‑IDE (IntelliJ IDEA, Eclipse of VS Code) geïnstalleerd op je machine.

## Importeer pakketten
De `import`‑statements geven je toegang tot de kernklassen die je nodig hebt, zoals `Project`, `ExtendedAttributeDefinition` en `ExtendedAttribute`.  

`Project` vertegenwoordigt een Microsoft Project‑bestand en biedt methoden om het te lezen, te wijzigen en op te slaan.  
`ExtendedAttributeDefinition` definieert een aangepast veld dat kan worden gekoppeld aan taken, resources of toewijzingen.  
`ExtendedAttribute` is een instantie van een definitie die de werkelijke waarde voor een specifieke entiteit bevat.

## Hoe voeg je een platte‑tekst uitgebreid attribuut toe aan een taak?
Om een platte‑tekst uitgebreid attribuut toe te voegen, laad je eerst het project, maak je vervolgens een definitie van het type Text, voeg je deze toe aan de collectie van het project, maak je een taak, instantiateer je het attribuut vanuit de definitie, stel je de tekstwaarde in, koppel je het aan de taak en sla je ten slotte het project op.

### 1. Stel het pad van de documentmap in
Geef aan waar je bron‑ en uitvoerbestanden zich bevinden.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Maak een nieuw project
Instantieer een `Project`‑object, eventueel door een bestaand .mpp‑bestand te laden.

```java
String dataDir = "Your Document Directory";
```

### 3. Maak een uitgebreid attribuutdefinitie van type Text1
Definieer het aangepaste veld als een platte‑tekst kolom met de naam “Text1”.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Voeg de definitie toe aan de collectie van uitgebreide attributen van het project
Registreer de nieuwe definitie zodat het project deze herkent.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Voeg een taak toe aan het project
Maak een taak die het aangepaste veld zal ontvangen.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Maak een uitgebreid attribuut vanuit de attribuutdefinitie
Genereer een instantie die je kunt koppelen aan een specifieke taak.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Wijs een waarde toe aan het gegenereerde uitgebreide attribuut
Stel de daadwerkelijke tekst in die je wilt opslaan, bijv. “Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Voeg het uitgebreide attribuut toe aan de taak
Koppel de attribuut‑instantie aan de `ExtendedAttributes`‑collectie van de taak.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Sla het project op
Schrijf het bijgewerkte project terug naar de schijf in het gewenste formaat.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Hoe voeg je een tekstattribuut met een lookup‑optie toe?
Bij het toevoegen van een tekstattribuut met een lookup volg je dezelfde stappen als voor een platte‑tekst attribuut, maar voordat je de definitie toevoegt, vul je de `LookupValues`‑collectie met de toegestane tekenreeksen. Deze waarden verschijnen als een vervolgkeuzelijst in Microsoft Project, waardoor gegevensconsistentie wordt gegarandeerd.

## Hoe voeg je een duur‑attribuut met een lookup‑optie toe?
Om een duur‑attribuut met een lookup toe te voegen, vervang je het type `Text1` door `Duration2` bij het maken van de definitie, en vul je vervolgens de `LookupValues`‑collectie met duur‑strings zoals “1 day”, “2 days”, enz. Nadat de definitie aan het project is toegevoegd, maak je de attribuut‑instantie, stel je een duurwaarde in, koppel je deze aan een taak en sla je het bestand op.

## Veelvoorkomende problemen en foutopsporing
- **Lookup values not appearing** – Zorg ervoor dat je elke lookup‑entry toevoegt aan de `LookupValues`‑collectie *voordat* je `project.getExtendedAttributes().add(definition)` aanroept.  
- **Attribute value not saved** – Controleer dat je de `ExtendedAttribute`‑instantie toevoegt aan de taak *nadat* je de waarde hebt ingesteld.  
- **File size grows unexpectedly** – Bij het werken met zeer grote projecten, overweeg om `project.setSaveOptions(new ProjectSaveOptions())` aan te roepen om incrementeel opslaan mogelijk te maken.

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks voor Java gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Tasks voor Java integreert naadloos met elk Java‑ecosysteem, inclusief Spring, Hibernate en Apache POI.

**Q: Is Aspose.Tasks voor Java geschikt voor grootschalige projectmanagementtoepassingen?**  
A: Absoluut. De bibliotheek is ontworpen om projecten met duizenden taken te verwerken en ondersteunt streaming om het geheugenverbruik laag te houden.

**Q: Zijn er licentie‑overwegingen voor het gebruik van Aspose.Tasks voor Java in een commercieel project?**  
A: Ja, je hebt een geldige commerciële licentie nodig. Je kunt de details bekijken op de [Aspose.Tasks website](https://purchase.aspose.com/buy).

**Q: Hoe kan ik ondersteuning of hulp krijgen voor Aspose.Tasks voor Java?**  
A: Bezoek het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) voor community‑hulp, of open een support‑ticket via je Aspose‑account.

**Q: Kan ik Aspose.Tasks voor Java uitproberen voordat ik het koop?**  
A: Ja, je kunt een gratis proefversie krijgen op de [Aspose.Tasks gratis proefpagina](https://releases.aspose.com/).

**Last updated:** 2026-09-30  
**Tested with:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Gerelateerde tutorials

- [Aangepaste kolommen en uitgebreide attributen in Java projectmanagement](/tasks/java/project-management/extended-attributes/)
- [Uitgebreide taak‑attributen lezen met Aspose.Tasks voor Java](/tasks/java/task-properties/extended-task-attributes/)
- [Hoe een project maken met aspose.tasks – Nieuwe taak‑attributen instellen](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}