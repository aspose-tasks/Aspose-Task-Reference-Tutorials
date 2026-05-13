---
date: 2026-01-10
description: Leer hoe u de tariefschaal kunt lezen en resource‑toewijzingen kunt beheren
  in Aspose.Tasks voor Java. Definieer materiële resources, hoe u de schaal instelt
  en resources toewijst aan een taak.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe tariefschaal lezen en tariefschaal schrijven voor resource‑toewijzingen
  in Aspose.Tasks
url: /nl/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe Rate Scale Lezen en Rate Scale Schrijven voor Resource Assignments in Aspose.Tasks

In deze tutorial ontdek je **hoe je rate**-schaalinstellingen leest en aanpast voor resource assignments met Aspose.Tasks voor Java. Of je nu een planner, een rapportagetool bouwt, of simpelweg projectupdates moet automatiseren, het beheersen van rate‑scale manipulatie geeft je fijnmazige controle over materiaal‑ en werkresources.

## Snelle Antwoorden
- **Wat is de primaire klasse voor rate handling?** `ResourceAssignment` met de `Asn.RATE_SCALE` eigenschap.  
- **Welke enum definieert de schaalopties?** `RateScaleType` (Day, Week, Month, etc.).  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis evaluatielicentie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Kan ik de schaal wijzigen na het opslaan?** Ja – laad het project opnieuw en wijzig `Asn.RATE_SCALE` zoals getoond.  
- **Ondersteunde IDE's?** Elke Java IDE (IntelliJ IDEA, Eclipse, NetBeans) kan de code compileren.

## Wat is Rate Scale?
Rate scale bepaalt de tijdseenheid (dag, week, maand, etc.) waarop de kostprijs van een resource wordt toegepast. Het aanpassen van de schaal stelt je in staat om materiaalverbruik of arbeidsinzet nauwkeurig te modelleren.

## Waarom rate scale lezen en schrijven?
Het lezen van de huidige schaal helpt je bestaande planningen te auditen, terwijl het schrijven van een nieuwe schaal je in staat stelt resources af te stemmen op de facturatie‑ of consumptie‑beleid van het project. Dit is vooral nuttig bij het **definiëren van materiaalresource** kosten of wanneer je de **schaal moet instellen** voor niet‑standaard werkcalendars.

## Voorvereisten
Voordat we beginnen, zorg dat je de volgende voorvereisten hebt:
1. **Java Development Environment** – JDK 8 of hoger geïnstalleerd.  
2. **Aspose.Tasks for Java Library** – Download en installeer de bibliotheek van [hier](https://releases.aspose.com/tasks/java/).

## Pakketten Importeren
Eerst importeer je de benodigde Aspose.Tasks klassen.

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

## Stap 1: Stel je Java‑project in
Maak een Maven‑ of Gradle‑project aan en voeg de Aspose.Tasks JAR toe aan je classpath. Deze stap zorgt ervoor dat de compiler de geïmporteerde klassen kan vinden.

## Stap 2: Laad het Project‑bestand
Laad het bestaande Microsoft Project‑bestand waarmee je wilt werken.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Stap 3: Voeg een Taak toe
Maak een nieuwe taak aan die later resource assignments zal ontvangen.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Stap 4: Definieer Resources
Hier **definiëren we een materiaalresource** en een reguliere werkresource. Let op het gebruik van `ResourceType.Material` voor de materiaal‑type resource.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Stap 5: Wijs Resources toe aan Taak
Nu **wijzen we resources toe aan de taak** en specificeren we **hoe de schaal in te stellen** door `RateScaleType.Week` te gebruiken. Dit illustreert zowel het lezen als het schrijven van de rate scale.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Stap 6: Sla het Project op
Sla de wijzigingen op in een nieuw bestand zodat we later de opgeslagen rate scale kunnen verifiëren.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Stap 7: Haal Resource Assignments op
Laad het opgeslagen project opnieuw en **lees de rate** scale om te bevestigen dat deze correct is weggeschreven.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Veelvoorkomende Valkuilen & Tips
- **UID Mismatch** – Zorg ervoor dat bij het ophalen van assignments op UID de UID‑waarden overeenkomen met die tijdens de creatie zijn toegewezen.  
- **Incorrect Resource Type** – Het gebruik van `ResourceType.Material` voor een werkresource zal ervoor zorgen dat rate‑berekeningen onverwacht gedrag vertonen.  
- **Saving Format** – Sla altijd op met `SaveFileFormat.Mpp` (of een ander ondersteund formaat) om aangepaste velden zoals rate scale te behouden.

## Conclusie
Het beheren en inspecteren van de rate scale voor resource assignments in Aspose.Tasks voor Java is eenvoudig zodra je de relevante klassen en eigenschappen kent. Door deze gids te volgen kun je **rate**‑informatie **lezen**, **materiaalresource**‑objecten **definiëren**, de **schaal instellen**, en **resources toewijzen aan taak** met vertrouwen.

## Veelgestelde Vragen

**Q: Kan ik Aspose.Tasks voor Java met elke Java IDE gebruiken?**  
A: Ja, Aspose.Tasks voor Java is compatibel met alle grote Java IDE's, inclusief IntelliJ IDEA, Eclipse en NetBeans.

**Q: Ondersteunt Aspose.Tasks andere bestandsformaten naast MPP?**  
A: Ja, Aspose.Tasks ondersteunt verschillende bestandsformaten, waaronder MPP, XML en HTML.

**Q: Is Aspose.Tasks geschikt voor enterprise‑level projectmanagement?**  
A: Absoluut, Aspose.Tasks biedt uitgebreide functionaliteit voor het beheren van projecten van elke omvang, waardoor het geschikt is voor enterprise‑level projectmanagement.

**Q: Kan ik resource assignments verder aanpassen naast rate scale?**  
A: Ja, Aspose.Tasks biedt uitgebreide mogelijkheden om resource assignments aan te passen, inclusief kosten, werk en duur aanpassingen.

**Q: Is er een community‑forum voor Aspose.Tasks‑ondersteuning?**  
A: Ja, je kunt ondersteuning vinden en met andere gebruikers communiceren op het Aspose.Tasks‑forum [hier](https://forum.aspose.com/c/tasks/15).

---

**Laatst bijgewerkt:** 2026-01-10  
**Getest met:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}