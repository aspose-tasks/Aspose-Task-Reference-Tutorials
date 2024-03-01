---
title: MS Project-formules met Aspose.Tasks voor Java
linktitle: Werken met formules in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u MS Project-bestanden in Java kunt manipuleren met behulp van de Aspose.Tasks-bibliotheek. Creëer, wijzig en bereken eenvoudig attributen.
type: docs
weight: 11
url: /nl/java/formulas/work-with-formulas/
---
## Invoering
In deze zelfstudie gaan we dieper in op het werken met MS Project-formules met behulp van Aspose.Tasks voor Java. Aspose.Tasks is een krachtige bibliotheek waarmee ontwikkelaars Microsoft Project-bestanden programmatisch kunnen manipuleren. Dankzij de uitgebreide functies kunt u eenvoudig projectbestanden in Java-toepassingen maken, lezen, wijzigen en converteren.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
### Java-ontwikkelomgeving
Zorg ervoor dat er een Java Development Kit (JDK) op uw systeem is geïnstalleerd. U kunt de nieuwste JDK downloaden en installeren vanaf de Oracle-website.
### Aspose.Takenbibliotheek
 moet de Aspose.Tasks-bibliotheek aan uw Java-project hebben toegevoegd. U kunt de bibliotheek downloaden via de[Aspose.Tasks voor Java-downloadpagina](https://releases.aspose.com/tasks/java/) en neem het op in de afhankelijkheden van uw project.

## Pakketten importeren
Voordat u in de voorbeelden duikt, importeert u de benodigde pakketten naar uw Java-code:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Laten we het gegeven voorbeeld in meerdere stappen opsplitsen:
## Stap 1: Maak een testproject met een aangepast veld
```java
Project project = CreateTestProjectWithCustomField();
```
 Maak eerst een testproject met een aangepast veld met behulp van de`CreateTestProjectWithCustomField()` methode. Deze methode retourneert een Project-object dat het nieuw gemaakte project vertegenwoordigt.
## Stap 2: Definieer een uitgebreide attribuutdefinitie
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Haal de uitgebreide attribuutdefinitie op uit het project en stel de alias en formule in. In dit voorbeeld definiëren we een attribuut om het aantal dagen vanaf de einddatum tot de deadline te berekenen.
## Stap 3: Stel de deadline voor een taak in
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Maak een kalenderobject en stel de deadlinedatum in. Haal vervolgens een taak op uit het project en stel de deadline in met behulp van het object Kalender.
## Stap 4: Sla het project op
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Sla het project ten slotte op in een bestand met de opgegeven naam en indeling. In dit geval slaan we het op als een MPP-bestand.

## Conclusie
In deze zelfstudie hebben we geleerd hoe u met MS Project-formules kunt werken met behulp van Aspose.Tasks voor Java. Door deze stappen te volgen, kunt u projectbestanden effectief programmatisch manipuleren, aangepaste velden toevoegen en attributen berekenen op basis van formules.

## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks met andere programmeertalen gebruiken?
A: Ja, Aspose.Tasks ondersteunt verschillende programmeertalen, waaronder Java, .NET en meer.
### Vraag: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?
 A: Ja, u kunt een gratis proefversie van Aspose.Tasks downloaden van[hier](https://releases.aspose.com/).
### Vraag: Waar kan ik documentatie vinden voor Aspose.Tasks?
 A: U kunt de documentatie voor Aspose.Tasks vinden[hier](https://reference.aspose.com/tasks/java/).
### Vraag: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks?
 A: Voor ondersteuning kunt u terecht op de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15).
### Vraag: Heb ik een tijdelijke licentie nodig voor het gebruik van Aspose.Tasks?
A: Als u extra functies nodig heeft, kunt u een tijdelijke licentie verkrijgen bij[hier](https://purchase.aspose.com/temporary-license/).