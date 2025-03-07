---
title: Converteer MS-project als JPEG in Aspose.Tasks
linktitle: Sla het project op als JPEG in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u eenvoudig Microsoft Project-bestanden naar JPEG-afbeeldingen kunt converteren met Aspose.Tasks voor Java. Verhoog uw productiviteit.
weight: 20
url: /nl/java/project-file-operations/save-as-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converteer MS-project als JPEG in Aspose.Tasks

## Invoering
In deze zelfstudie onderzoeken we hoe u een Microsoft Project-bestand kunt opslaan als een JPEG-afbeelding met Aspose.Tasks voor Java. Dit kan met name handig zijn voor het delen van projectvisualisaties of het integreren van projectgegevens in rapporten of presentaties.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1.  Java Development Kit (JDK): Zorg ervoor dat Java op uw systeem is geïnstalleerd. U kunt de nieuwste versie downloaden en installeren vanaf de[Java-website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks voor Java: Download en configureer Aspose.Tasks voor Java door de instructies te volgen in de[documentatie](https://reference.aspose.com/tasks/java/).

## Pakketten importeren
Importeer eerst de benodigde pakketten naar uw Java-bestand:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## Stap 1: Definieer de gegevensdirectory
Stel het pad in naar uw gegevensmap waar uw MS Project-bestand zich bevindt.
```java
String dataDir = "Your Data Directory";
```
## Stap 2: MS-projectbestand laden
Laad het MS Project-bestand met Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## Stap 3: JPEG-kwaliteit configureren (optioneel)
 Als u de JPEG-kwaliteit wilt aanpassen, kunt u dit instellen met behulp van de`ImageSaveOptions` klas. De kwaliteit varieert van 0 tot 100.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Stel de JPEG-kwaliteit in op 50
```
## Stap 4: Project opslaan als JPEG
Sla het MS Project-bestand op als een JPEG-afbeelding.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een Microsoft Project-bestand kunt opslaan als een JPEG-afbeelding met Aspose.Tasks voor Java. Deze functie maakt het eenvoudig delen en integreren van projectgegevens in verschillende documenten en presentaties mogelijk.
## Veelgestelde vragen
### Vraag: Kan ik de kwaliteit van de JPEG-afbeelding aanpassen?
 A: Ja, u kunt de kwaliteit aanpassen met behulp van de`setJpegQuality()` methode, met een bereik van 0 tot 100.
### Vraag: Wat moet ik doen als ik de JPEG-kwaliteit niet opgeef?
A: Als u de kwaliteit niet opgeeft, wordt de standaardkwaliteit gebruikt.
### Vraag: Is Aspose.Tasks voor Java gratis te gebruiken?
 A: Aspose.Tasks voor Java is een commerciële bibliotheek, maar u kunt de functies ervan verkennen met een gratis proefversie. Bezoek de[gratis proefpagina](https://releases.aspose.com/) voor meer informatie.
### Vraag: Waar kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?
A: U kunt ondersteuning krijgen van het Aspose.Tasks-communityforum[hier](https://forum.aspose.com/c/tasks/15).
### Vraag: Kan ik een tijdelijke licentie kopen voor Aspose.Tasks?
 A: Ja, u kunt een tijdelijke licentie kopen bij[hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
