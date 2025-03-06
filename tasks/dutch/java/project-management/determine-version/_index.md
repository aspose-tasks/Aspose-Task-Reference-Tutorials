---
title: Bepaal de MS Project-versie met Aspose.Tasks
linktitle: Bepaal de projectversie met Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u de versie van MS Project-bestanden programmatisch kunt bepalen met Aspose.Tasks voor Java. Stapsgewijze handleiding met codevoorbeelden.
weight: 12
url: /nl/java/project-management/determine-version/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bepaal de MS Project-versie met Aspose.Tasks

## Invoering
Deze tutorial begeleidt u stap voor stap bij het gebruik van Aspose.Tasks voor Java om de versie van een MS Project-bestand te bepalen. Aspose.Tasks is een krachtige Java API waarmee ontwikkelaars Microsoft Project-bestanden kunnen manipuleren zonder dat Microsoft Project hoeft te worden geïnstalleerd.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1. Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor Java JAR-bestand: Download de Aspose.Tasks voor Java-bibliotheek van de[website](https://releases.aspose.com/tasks/java/) en voeg het toe aan uw Java-project.
3. MS Project-bestand: bereid een MS Project-bestand (XML-formaat) voor om te testen.

## Pakketten importeren
Laten we, voordat we in de code duiken, de benodigde pakketten importeren:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Stap 1: Stel het project in
```java
// Het pad naar de documentenmap.
String dataDir = "Your Data Directory";
```
 Vervangen`"Your Data Directory"` met het pad naar de map met uw MS Project-bestand.
## Stap 2: Laad het project
```java
Project project = new Project(dataDir + "input.xml");
```
 Vervangen`"input.xml"` met de naam van uw MS Project-bestand.
## Stap 3: Bepaal de projectversie
```java
//Projectversie-eigenschap weergeven
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Met dit codefragment worden de versie en de laatst opgeslagen datum van het MS Project-bestand opgehaald en afgedrukt.
## Stap 4: Resultaat weergeven
```java
//Resultaat van conversie weergeven.
System.out.println("Process completed Successfully");
```
Deze lijn geeft de voltooiing van het proces aan.

## Conclusie
In deze zelfstudie hebt u geleerd hoe u de versie van een MS Project-bestand kunt bepalen met behulp van Aspose.Tasks voor Java. Door de stapsgewijze handleiding te volgen, kunt u probleemloos efficiënt werken met MS Project-bestanden in uw Java-applicaties.

## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks met andere programmeertalen gebruiken?
A: Ja, Aspose.Tasks ondersteunt meerdere programmeertalen, waaronder .NET, Java en C++.
### Vraag: Is Aspose.Tasks geschikt voor grootschalige projecten?
A: Absoluut, Aspose.Tasks is ontworpen om projecten van elke omvang met gemak aan te kunnen.
### Vraag: Kan ik projectgegevens aanpassen met Aspose.Tasks?
A: Ja, u kunt projectgegevens manipuleren, taken, bronnen en nog veel meer wijzigen met Aspose.Tasks.
### Vraag: Vereist Aspose.Tasks de installatie van Microsoft Project?
A: Nee, Aspose.Tasks werkt onafhankelijk en vereist geen installatie van Microsoft Project.
### Vraag: Is er technische ondersteuning beschikbaar voor Aspose.Tasks?
 A: Ja, u kunt technische ondersteuning krijgen van het Aspose.Tasks-forum op[hier](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
