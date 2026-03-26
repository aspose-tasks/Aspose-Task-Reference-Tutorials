---
date: 2025-12-21
description: Leer hoe u Gantt-diagramweergaven kunt aanpassen, projectvisualisatie
  kunt beheren en het project kunt opslaan als PDF met Aspose.Tasks voor Java. Pas
  de tijdschaal eenvoudig aan.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Gantt-diagram aanpassen – Beheersing van de tijdschaaltelling in MS Project
  met Aspose.Tasks
url: /nl/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gantt-diagram aanpassen – Beheersing van de tijdschaaltelling in MS Project met Aspose.Tasks

## Inleiding
Als je de **Gantt-diagram**‑visualisaties in Microsoft Project moet **aanpassen**, is het beheersen van het aantal tijdsschaal‑eenheden een essentiële techniek. Met Aspose.Tasks voor Java kun je programmatic matig de onderste en middelste tijdsschaal‑lagen instellen, de zichtbaarheid van de tikken fijn afstellen en vervolgens **het project opslaan als PDF** om te delen met belanghebbenden. Deze tutorial leidt je stap voor stap door het volledige proces – van het opzetten van de omgeving tot het genereren van een gepolijste PDF die jouw aangepaste Gantt-weergave weerspiegelt.

## Snelle antwoorden
- **Wat betekent “Gantt-diagram aanpassen”?** Het aanpassen van tijdsschaal‑lagen, kleuren en lay‑out zodat ze passen bij je rapportagebehoeften.  
- **Welke API‑methode stelt het aantal voor de onderste laag in?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Kan ik direct een PDF genereren vanuit het project?** Ja – gebruik `project.save(..., SaveFileFormat.Pdf)`.  
- **Heb ik een licentie nodig voor productiegebruik?** Een commerciële licentie is vereist; een gratis proefversie is beschikbaar.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger werkt met de nieuwste Aspose.Tasks‑bibliotheek.

## Wat betekent “Gantt-diagram aanpassen” in Aspose.Tasks?
Een Gantt-diagram aanpassen betekent programmatic matig de visuele componenten wijzigen – zoals tijdsschaal‑intervallen, tikken en taakbalken – zodat het diagram overeenkomt met de manier waarop je **projectvisualisatie** wilt beheren. Door het aantal tijdsschaal‑eenheden te wijzigen, bepaal je hoeveel dagen, weken of maanden elk segment vertegenwoordigt, waardoor het diagram duidelijker wordt voor verschillende doelgroepen.

## Voorvereisten
Voordat je begint, zorg dat je het volgende hebt:

1. **Java‑ontwikkelomgeving** – JDK 8 of nieuwer geïnstalleerd.  
2. **Aspose.Tasks voor Java‑bibliotheek** – Download deze van [hier](https://releases.aspose.com/tasks/java/).  
3. **Basiskennis van Java** – Vertrouwd met Java‑syntaxis en object‑georiënteerde concepten.

## Pakketten importeren
Importeer de benodigde klassen in je Java‑project:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Stapsgewijze handleiding

### Stap 1: Gegevensmap instellen
Definieer waar je projectbestanden worden gelezen en geschreven:

```java
String dataDir = "Your Data Directory";
```

Vervang `"Your Data Directory"` door het absolute pad op jouw machine.

### Stap 2: Een nieuw Project‑object maken
Instantieer een nieuw `Project`‑object dat alle taken en weergave‑instellingen zal bevatten:

```java
Project project = new Project();
```

### Stap 3: De Gantt‑diagramweergave configureren
Maak een `GanttChartView`‑object – hiermee **genereer je Gantt‑view Java**‑code om het uiterlijk van het diagram te regelen:

```java
GanttChartView view = new GanttChartView();
```

### Stap 4: Aantal tijdsschaal‑eenheden voor de onderste laag instellen
Pas de onderste laag aan om twee intervallen weer te geven en verberg de tikken:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Stap 5: Aantal tijdsschaal‑eenheden voor de middelste laag instellen
Pas dezelfde configuratie toe op de middelste laag:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Stap 6: De aangepaste weergave aan het project toevoegen
Koppel de weergave die je zojuist hebt geconfigureerd aan de `Project`‑instantie:

```java
project.getViews().add(view);
```

### Stap 7: Voorbeeldtaken toevoegen (testgegevens)
Maak een paar taken met specifieke duur om het aangepaste Gantt-diagram te illustreren:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Stap 8: Het project opslaan als PDF
Exporteer tenslotte het project – inclusief je **aangepaste Gantt-diagram** – naar een PDF‑bestand:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

De resulterende PDF toont hoe de onderste en middelste tijdsschaal‑lagen zijn **aangepast**, waardoor belanghebbenden een duidelijke, afdrukbare weergave van het schema krijgen.

## Veelvoorkomende problemen & foutopsporing
- **PDF is leeg** – Zorg ervoor dat het `dataDir`‑pad eindigt met een scheidingsteken (`/` of `\`) en dat de map bestaat.  
- **Tikken blijven verschijnen** – Controleer of `setShowTicks(false)` op beide lagen is aangeroepen.  
- **Duur niet toegepast** – Verifieer dat je `TimeUnitType.Hour` (of de juiste eenheid) gebruikt bij het aanmaken van duurwaarden.

## Veelgestelde vragen

**V: Kan Aspose.Tasks voor Java grote projectbestanden aan?**  
A: Ja, de bibliotheek is geoptimaliseerd voor high‑performance verwerking van omvangrijke projectdata.

**V: Is Aspose.Tasks voor Java compatibel met verschillende Java‑IDE’s?**  
A: Absoluut – het werkt naadloos met Eclipse, IntelliJ IDEA, NetBeans en andere populaire IDE’s.

**V: Kan ik het uiterlijk van Gantt‑diagrammen verder aanpassen dan de tijdsschaal‑instellingen?**  
A: Ja, Aspose.Tasks biedt uitgebreide stylingopties zoals balkkleuren, lettertypen en rasterlijnen.

**V: Is er een proefversie beschikbaar voor Aspose.Tasks voor Java?**  
A: Ja, je kunt een gratis proefversie verkrijgen via [hier](https://releases.aspose.com/).

**V: Waar kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?**  
A: Ondersteuning en hulp vind je op het Aspose.Tasks‑forum [hier](https://forum.aspose.com/c/tasks/15).

**V: Hoe wijzig ik programmatic matig de achtergrondkleur van het Gantt‑diagram?**  
A: Gebruik de methode `view.getGanttChartProperties().setBackgroundColor(Color)` nadat je `java.awt.Color` hebt geïmporteerd.

## Conclusie
Door deze stappen te volgen heb je geleerd hoe je **Gantt-diagram**‑tijdsschaal‑lagen kunt **aanpassen**, de **projectvisualisatie** kunt verbeteren en **het project opslaan als PDF** met Aspose.Tasks voor Java. Deze aanpak geeft je volledige controle over de visuele output, waardoor het eenvoudiger wordt om heldere, professionele schema’s te delen met je team of klanten.

---

**Laatst bijgewerkt:** 2025-12-21  
**Getest met:** Aspose.Tasks voor Java 24.12 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}