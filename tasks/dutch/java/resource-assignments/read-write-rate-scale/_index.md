---
date: 2026-06-10
description: Leer hoe je rate kunt lezen en hoe je rate scale kunt schrijven voor
  resource assignments met Aspose.Tasks voor Java. Ondersteunt materiële resources,
  meerdere formaten en grote projecten.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Rate Scale lezen en schrijven voor Resource Assignments in Aspose.Tasks
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
title: Hoe Rate Scale lezen en Rate Scale schrijven voor Resource Assignments in Aspose.Tasks
url: /nl/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe de Rate Scale lezen en de Rate Scale schrijven voor resource‑toewijzingen in Aspose.Tasks

## Snelle antwoorden
`ResourceAssignment` koppelt een taak aan een resource en bevat toewijzingsspecifieke gegevens.  
`Asn` bevat constanten voor toewijzingsvelden, inclusief `RATE_SCALE`.  
`RateScaleType`‑enum geeft mogelijke tijdseenheden voor rate‑schaalering weer.  

- **Wat is de primaire klasse voor het verwerken van tarieven?** `ResourceAssignment` met de eigenschap `Asn.RATE_SCALE`.  
- **Welke enum definieert de schaalopties?** `RateScaleType` (Day, Week, Month, enz.).  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis evaluatielicentie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Kan ik de schaal wijzigen na het opslaan?** Ja – laad het project opnieuw en wijzig `Asn.RATE_SCALE` zoals getoond.  
- **Ondersteunde IDE's?** Elke Java‑IDE (IntelliJ IDEA, Eclipse, NetBeans) kan de code compileren.

## Hoe de rate‑scale lezen voor resource‑toewijzingen?

Laad het project, zoek de gewenste `ResourceAssignment` en roep `getRateScale()` aan – dit retourneert een `RateScaleType`‑waarde die aangeeft of het tarief per dag, week, maand of een andere eenheid wordt toegepast. Het antwoord is direct en vereist slechts twee API‑aanroepen, waardoor het ideaal is voor auditscripts of UI‑weergaven.

## Hoe de rate‑scale schrijven voor resource‑toewijzingen?

Maak of haal een `ResourceAssignment`‑object op, stel de eigenschap `Asn.RATE_SCALE` in op de gewenste `RateScaleType` (bijv. `RateScaleType.Week`), en sla vervolgens het project op. Deze enkele eigenschapswijziging werkt automatisch de kostencalculaties bij en wordt bewaard in alle ondersteunde bestandsformaten. Na het instellen van de schaal moet u mogelijk ook het standaardtarief of overurenttarief van de resource aanpassen om de nieuwe tijdseenheid weer te geven, zodat de kostencalculaties nauwkeurig blijven.

## Wat is Rate Scale?

Rate scale bepaalt de tijdseenheid (dag, week, maand, enz.) waaraan het kostentarief van een resource wordt toegepast. Het aanpassen van de schaal stelt u in staat om materiaalverbruik of arbeidsinspanning nauwkeurig te modelleren. Bijvoorbeeld, het instellen van de schaal op Week betekent dat het kostentarief wordt geïnterpreteerd als kosten per week, en de totale kosten voor een taak worden berekend op basis van het aantal weken dat de resource is toegewezen.

## Waarom rate‑scale lezen en schrijven?

Het lezen van de huidige schaal helpt u bestaande planningen te auditen, terwijl het schrijven van een nieuwe schaal u in staat stelt resources af te stemmen op de facturatie‑ of consumptie‑policy van het project. Dit is vooral nuttig bij het **definiëren van materiaalkosten** of wanneer u de **schaal moet instellen** voor niet‑standaard werk‑kalenders.

## Vereisten
Voordat we beginnen, zorg ervoor dat u de volgende vereisten heeft:
1. **Java Development Environment** – JDK 8 of hoger geïnstalleerd.  
2. **Aspose.Tasks for Java Library** – Download en installeer de bibliotheek van [here](https://releases.aspose.com/tasks/java/).

## Importeer pakketten
De `ResourceAssignment`‑klasse vertegenwoordigt een koppeling tussen een taak en een resource, terwijl `RateScaleType` de mogelijke tijdseenheden voor een tarief opsomt. Importeer de benodigde Aspose.Tasks‑klassen voordat u begint met coderen.  

`Project` is het hoofdobject dat Microsoft Project‑bestanden laadt en opslaat.  
`Resource` definieert een projectresource zoals werk of materiaal.  
`ResourceType`‑enum specificeert of een resource werk of materiaal is.  
`Task` vertegenwoordigt een werkitem in de projectschema.  
`SaveFileFormat`‑enum definieert het uitvoerformaat voor het opslaan van een project.

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

## Stap 1: Stel uw Java‑project in
Maak een Maven‑ of Gradle‑project en voeg de Aspose.Tasks‑JAR toe aan uw classpath. Deze stap zorgt ervoor dat de compiler de geïmporteerde klassen kan vinden.

## Stap 2: Laad het projectbestand
Laad het bestaande Microsoft Project‑bestand dat u wilt bewerken.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Stap 3: Voeg een taak toe
Maak een nieuwe taak die later resource‑toewijzingen zal ontvangen.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Stap 4: Definieer resources
Hier **definiëren we een materiaalsource** en een reguliere werkresource. Let op het gebruik van `ResourceType.Material` voor de materiaalsource.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Stap 5: Wijs resources toe aan taak
Nu **wijzen we resources toe aan de taak** en specificeren we **hoe de schaal in te stellen** door `RateScaleType.Week` te gebruiken. Dit illustreert zowel het lezen als het schrijven van de rate‑scale.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Stap 6: Sla het project op
Sla de wijzigingen op in een nieuw bestand zodat we later de opgeslagen rate‑scale kunnen verifiëren.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Stap 7: Haal resource‑toewijzingen op
Laad het opgeslagen project opnieuw en **lees de rate‑scale** om te bevestigen dat deze correct is geschreven.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Veelvoorkomende valkuilen & tips
- **UID‑mismatch** – Bij het ophalen van toewijzingen op UID, zorg ervoor dat de UID‑waarden overeenkomen met die tijdens creatie zijn toegewezen.  
- **Onjuiste resource‑type** – Het gebruik van `ResourceType.Material` voor een werkresource zal ervoor zorgen dat tariefberekeningen onverwacht gedrag vertonen.  
- **Opslagformaat** – Sla altijd op met `SaveFileFormat.Mpp` (of een ander ondersteund formaat) om aangepaste velden zoals rate‑scale te behouden.  
- **Grote projecten** – Aspose.Tasks kan bestanden met **500+ pagina's** verwerken zonder het volledige document in het geheugen te laden, dankzij de streaming‑architectuur.

## Veelgestelde vragen

**V: Kan ik Aspose.Tasks voor Java met elke Java‑IDE gebruiken?**  
A: Ja, Aspose.Tasks voor Java is compatibel met alle grote Java‑IDE's, inclusief IntelliJ IDEA, Eclipse en NetBeans.

**V: Ondersteunt Aspose.Tasks andere bestandsformaten naast MPP?**  
A: Ja, Aspose.Tasks ondersteunt diverse bestandsformaten, waaronder MPP, XML en HTML.

**V: Is Aspose.Tasks geschikt voor enterprise‑level projectmanagement?**  
A: Absoluut, Aspose.Tasks biedt uitgebreide functionaliteit voor het beheren van projecten van elke omvang, waardoor het geschikt is voor enterprise‑level projectmanagement.

**V: Kan ik resource‑toewijzingen verder aanpassen naast de rate‑scale?**  
A: Ja, Aspose.Tasks biedt uitgebreide mogelijkheden voor het aanpassen van resource‑toewijzingen, inclusief kosten, werk en duur.

**V: Is er een community‑forum voor Aspose.Tasks‑ondersteuning?**  
A: Ja, u kunt ondersteuning vinden en met andere gebruikers communiceren op het Aspose.Tasks‑forum [here](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Gerelateerde tutorials

- [Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [How to Modify Assignments – Read Shared Resources with Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [How to Add Notes to Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}