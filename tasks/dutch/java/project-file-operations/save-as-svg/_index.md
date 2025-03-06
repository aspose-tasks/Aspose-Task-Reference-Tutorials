---
title: Converteer MS-project naar SVG in Java
linktitle: Opslaan als SVG in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u Microsoft Project-bestanden opslaat als SVG in Java met behulp van de Aspose.Tasks-bibliotheek. Stapsgewijze handleiding met codevoorbeelden.
type: docs
weight: 18
url: /nl/java/project-file-operations/save-as-svg/
---
## Invoering
Aspose.Tasks voor Java is een krachtige bibliotheek voor het werken met projectbeheerbestanden, waarmee ontwikkelaars projectgegevens kunnen manipuleren, verschillende bewerkingen kunnen uitvoeren en efficiënt rapporten kunnen genereren. In deze zelfstudie onderzoeken we hoe u een project als SVG kunt opslaan met Aspose.Tasks voor Java. SVG (Scalable Vector Graphics) is een veelgebruikt formaat voor de weergave van vectorafbeeldingen op internet en biedt schaalbaarheid en weergave van hoge kwaliteit.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
### Java-ontwikkelomgeving
Zorg ervoor dat Java Development Kit (JDK) op uw systeem is geïnstalleerd. U kunt JDK downloaden en installeren vanaf de Oracle-website.
### Aspose.Tasks voor Java-bibliotheek
 Download en installeer de Aspose.Tasks voor Java-bibliotheek vanaf de website. U vindt de downloadlink in de meegeleverde documentatie[hier](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
Eerst moet u de benodigde pakketten in uw Java-programma importeren om met de Aspose.Tasks-functionaliteiten te kunnen werken.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Laten we nu het gegeven voorbeeld in meerdere stappen opsplitsen:
## Stap 2: Definieer de gegevensdirectory
```java
String dataDir = "Your Data Directory";
```
 Vervangen`"Your Data Directory"`met het pad naar de map waar uw projectbestand zich bevindt.
## Stap 3: Projectbestand laden
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Met deze stap wordt het projectbestand met de naam "HomeMovePlan.mpp" geladen vanuit de opgegeven gegevensmap.
## Stap 4: Opslaan als SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Met deze stap wordt het geladen project opgeslagen als SVG-indeling met de naam "project5.svg" in de opgegeven gegevensmap.

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een project als SVG kunt opslaan met Aspose.Tasks voor Java. Door de aangegeven stappen te volgen, kunt u projectbestanden efficiënt naar SVG-indeling converteren, waardoor naadloze integratie met webgebaseerde toepassingen of visualisatietools mogelijk wordt.
## Veelgestelde vragen
### Is Aspose.Tasks voor Java compatibel met alle versies van Microsoft Project-bestanden?
Ja, Aspose.Tasks voor Java ondersteunt verschillende versies van Microsoft Project-bestanden, waaronder MPP-, MPT- en XML-formaten.
### Kan ik het uiterlijk van de SVG-uitvoer aanpassen?
Ja, u kunt het uiterlijk van de SVG-uitvoer aanpassen door parameters zoals lettertypen, kleuren en lay-outconfiguraties aan te passen.
### Heeft Aspose.Tasks voor Java een licentie nodig voor commercieel gebruik?
 Ja, voor commercieel gebruik van Aspose.Tasks voor Java is een geldige licentie vereist. U kunt een licentie verkrijgen via de website[hier](https://purchase.aspose.com/temporary-license/).
### Kan ik Aspose.Tasks voor Java uitproberen voordat ik het aanschaf?
 Ja, u kunt via de website een gratis proefversie van Aspose.Tasks voor Java aanvragen[hier](https://purchase.aspose.com/buy) om de kenmerken en mogelijkheden ervan te evalueren.
### Waar kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?
 U kunt ondersteuning krijgen voor Aspose.Tasks voor Java door het forum te bezoeken[hier](https://forum.aspose.com/c/tasks/15), waar u vragen kunt stellen en kunt communiceren met de community.