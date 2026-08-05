---
date: 2026-02-13
description: Leer hoe u een projectrapport kunt genereren door een projectobject in
  Java te maken, uitgebreide attributen toe te voegen en evaluatiefuncties te gebruiken
  met Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Genereer projectrapport – Maak projectobject Java
url: /nl/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ondersteun Evaluatiefuncties in Aspose.Tasks Formules

## Introductie
Aspose.Tasks for Java stelt je in staat om **projectrapporten te genereren** door een **projectobject** in Java te maken en Microsoft Project-functies direct in je code te evalueren. Door deze formules in te sluiten, kun je geavanceerde berekeningen uitvoeren, aangepaste rapporten genereren en projectanalyse automatiseren zonder je ontwikkelomgeving te verlaten. In deze tutorial lopen we door het maken van een projectobject, het toevoegen van een uitgebreid attribuut, en het gebruiken van evaluatiefuncties om **aangepaste veldtaak**-gegevens toe te voegen.

## Snelle Antwoorden
- **Wat betekent “create project object java”?** Het maakt een `Project`‑instantie in het geheugen die je programmatisch kunt manipuleren.  
- **Welke bibliotheek is vereist?** Aspose.Tasks for Java (download van de officiële site).  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige Aspose.Tasks‑licentie is vereist voor productiegebruik; een gratis proefversie is beschikbaar.  
- **Kan ik aangepaste velden gebruiken?** Ja – je kunt **een uitgebreid attribuut toevoegen** aan taken en deze behandelen als aangepaste velden.  
- **Is dit compatibel met alle Project‑bestandsformaten?** Aspose.Tasks ondersteunt MPP-, MPT- en XML‑formaten.

## Vereisten
Voordat je begint, zorg ervoor dat je het volgende hebt:

1. **Java-ontwikkelomgeving** – JDK 8+ en een IDE zoals IntelliJ IDEA of Eclipse.  
2. **Aspose.Tasks for Java‑bibliotheek** – Download en voeg de bibliotheek toe vanaf de [Aspose.Tasks voor Java downloadpagina](https://releases.aspose.com/tasks/java/).

## Importpakketten
Voeg de Aspose.Tasks‑namespace toe aan je Java‑klasse zodat je kunt werken met projecten, taken en uitgebreide attributen:

```java
import com.aspose.tasks.*;
```

## Genereer Projectrapport – Create Project Object Java
Instantieer een nieuw `Project`‑object. Dit dient als container voor alle taken, resources en aangepaste gegevens die je definieert.

```java
Project project = new Project();
```

De bovenstaande regel **creates project object java** die leeg begint en klaar is voor aanpassing.

## Hoe een Uitgebreid Attribuut Toevoegen
Definieer een uitgebreid attribuut dat aangepaste numerieke gegevens (bijv. een sinuswaarde) voor elke taak opslaat.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Hier **add extended attribute** van het type `Number` met de naam “Sine” en koppelen we het aan taken.

## Voeg het Uitgebreide Attribuut toe aan het Project
Registreer de attribuutdefinitie bij het project zodat elke taak ernaar kan verwijzen.

```java
project.getExtendedAttributes().add(attr);
```

## Maak een Nieuwe Taak
Voeg een eenvoudige taak met de naam “Task” toe onder de hoofdtaak van het project.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Koppel het Uitgebreide Attribuut aan de Taak
Koppel het eerder gedefinieerde uitgebreide attribuut aan de nieuw aangemaakte taak.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Nu bevat de taak een aangepast “Sine”‑veld dat je kunt gebruiken in formules of berekeningen. Dit is ook hoe je **add custom field task** gegevens programmatisch toevoegt.

## Waarom Evaluatiefuncties Gebruiken?
Het insluiten van MS Project-functies in Aspose.Tasks‑formules stelt je in staat om:

- Uitvoeren van berekeningen on‑the‑fly (bijv. `Sin([Start])`) zonder externe tools.  
- Alle projectlogica binnen één onderhoudbare codebase houden.  
- Dynamische rapporten genereren die realtime gegevenswijzigingen weerspiegelen, waardoor je **generate project report** automatisch kunt maken.

## Veelvoorkomende Problemen en Oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Formule geeft `NaN` terug** | Controleer of het type van het aangepaste veld overeenkomt met het verwachte numerieke type. |
| **Uitgebreid attribuut niet zichtbaar** | Zorg ervoor dat de attribuutdefinitie aan het project wordt toegevoegd **voordat** taken worden aangemaakt. |
| **Licentie‑exceptie** | Installeer een tijdelijke of volledige **Aspose.Tasks‑licentie**; de proefmodus kan bepaalde functies beperken. |
| **Ontbrekende tijdelijke licentie** | Verkrijg een **tijdelijke Aspose‑licentie** van de Aspose‑website. |

## Veelgestelde Vragen

**V: Kan Aspose.Tasks for Java complexe MS Project‑formules verwerken?**  
A: Ja, Aspose.Tasks for Java ondersteunt de evaluatie van een breed scala aan MS Project‑functies, waardoor complexe berekeningen binnen Java‑applicaties mogelijk zijn.

**V: Is Aspose.Tasks for Java compatibel met verschillende versies van Microsoft Project‑bestanden?**  
A: Ja, Aspose.Tasks for Java ondersteunt diverse versies van Microsoft Project‑bestanden, inclusief MPP-, MPT- en XML‑formaten.

**V: Kan ik Aspose.Tasks for Java uitproberen voordat ik koop?**  
A: Ja, je kunt een gratis proefversie van Aspose.Tasks for Java downloaden vanaf de website [hier](https://purchase.aspose.com/buy).

**V: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks for Java?**  
A: Je kunt ondersteuning krijgen via het Aspose.Tasks‑communityforum [hier](https://forum.aspose.com/c/tasks/15).

**V: Is er een tijdelijke licentie beschikbaar voor Aspose.Tasks for Java?**  
A: Ja, je kunt een tijdelijke licentie voor testdoeleinden verkrijgen via de Aspose‑website [hier](https://purchase.aspose.com/temporary-license/).

## Conclusie
Door deze stappen te volgen heb je geleerd hoe je **create project object**, **add extended attribute** kunt uitvoeren en evaluatiefuncties kunt benutten om **generate project report** automatisch te maken. Je kunt nu deze basis uitbreiden om uitgebreidere projectanalyses, aangepaste dashboards of geautomatiseerde planningshulpmiddelen te bouwen — allemaal aangedreven door Aspose.Tasks for Java.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}