---
date: 2026-03-29
description: Leer hoe u project‑PDF‑bestanden kunt maken terwijl u het aantal tijdschalen
  van de Gantt‑grafiek aanpast met Aspose.Tasks voor Java. Deze gids laat u stap‑voor‑stap
  zien hoe u Gantt naar PDF exporteert met volledige controle.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Project-PDF maken – Tijdsschaal van Gantt-diagram aanpassen
url: /nl/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Project-PDF maken – Gantt-diagram tijdschaal aanpassen

## Inleiding
Als u **project-PDF**‑bestanden moet maken die een perfect afgestemd Gantt-diagram weergeven, is het beheersen van het aantal tijdsschaal‑segmenten de sleutel. Met Aspose.Tasks for Java kunt u programmatically de onderste en middelste tijdsschaal‑lagen instellen, tick‑markeringen verbergen, en vervolgens **project opslaan als PDF** voor eenvoudige distributie. In deze tutorial lopen we alles door wat u nodig heeft—van het opzetten van de ontwikkelomgeving tot het genereren van een gepolijste PDF die uw aangepaste Gantt‑weergave toont.

## Snelle antwoorden
- **Wat betekent “customize Gantt chart”?** Het aanpassen van tijdsschaal‑lagen, kleuren en lay‑out om aan uw rapportagebehoeften te voldoen.  
- **Welke API‑methode stelt het aantal van de onderste laag in?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Kan ik rechtstreeks vanuit het project een PDF genereren?** Ja—gebruik `project.save(..., SaveFileFormat.Pdf)`.  
- **Heb ik een licentie nodig voor productiegebruik?** Een commerciële licentie is vereist; een gratis proefversie is beschikbaar.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger werkt met de nieuwste Aspose.Tasks‑bibliotheek.

## Wat betekent “customize Gantt chart” in Aspose.Tasks?
Het aanpassen van een Gantt-diagram betekent programmatically het wijzigen van de visuele componenten—zoals tijdsschaal‑intervallen, tick‑markeringen en taakbalken—zodat het diagram overeenkomt met de manier waarop u **projectvisualisatie wilt beheren**. Door het aantal tijdsschaal‑segmenten te wijzigen, bepaalt u hoeveel dagen, weken of maanden elk segment vertegenwoordigt, waardoor het diagram duidelijker wordt voor verschillende doelgroepen.

## Waarom een project‑PDF maken met een aangepast Gantt-diagram?
- **Stakeholder‑gereed output:** PDF is universeel zichtbaar, waardoor iedereen dezelfde planningslay‑out ziet.  
- **Print‑vriendelijk:** Precieze controle over tijdsschaal‑lagen voorkomt overladen of onduidelijke afdrukken.  
- **Automatisering:** Integreer PDF‑generatie in CI‑pipelines of rapportageservices voor nul handmatige inspanning.  

## Voorvereisten
Zorg ervoor dat u het volgende heeft voordat u begint:

1. **Java Development Environment** – JDK 8 of nieuwer geïnstalleerd.  
2. **Aspose.Tasks for Java Library** – Download deze van [here](https://releases.aspose.com/tasks/java/).  
3. **Basic Java Knowledge** – Vertrouwd met Java‑syntaxis en object‑georiënteerde concepten.

## Importeer pakketten
Importeer de benodigde klassen in uw Java‑project:

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
Definieer waar uw projectbestanden worden gelezen en geschreven:

```java
String dataDir = "Your Data Directory";
```

Vervang `"Your Data Directory"` door het absolute pad op uw machine.

### Stap 2: Nieuwe Project‑instantie maken
Instantieer een nieuw `Project`‑object dat alle taken en weergave‑instellingen zal bevatten:

```java
Project project = new Project();
```

### Stap 3: Gantt-diagramweergave configureren
Maak een `GanttChartView`‑object—hier zult u **generate Gantt view Java** code maken om het uiterlijk van het diagram te regelen:

```java
GanttChartView view = new GanttChartView();
```

### Stap 4: Tijdsschaal‑aantal voor de onderste laag instellen
Stel de onderste laag in om twee intervallen weer te geven en verberg de tick‑markeringen:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Stap 5: Tijdsschaal‑aantal voor de middelste laag instellen
Pas dezelfde configuratie toe op de middelste laag:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Stap 6: Aangepaste weergave aan het project toevoegen
Koppel de weergave die u zojuist hebt geconfigureerd aan de `Project`‑instantie:

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

### Stap 8: Project opslaan als PDF
Exporteer tenslotte het project—incl. uw **customized Gantt chart**—naar een PDF‑bestand:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

De resulterende PDF toont hoe de onderste en middelste tijdsschaal‑lagen zijn **customized**, waardoor stakeholders een duidelijk, afdrukbaar overzicht van de planning krijgen.

## Veelvoorkomende problemen & probleemoplossing
- **PDF is blank** – Zorg ervoor dat het `dataDir`‑pad eindigt met een bestandsseparator (`/` of `\`) en dat de map bestaat.  
- **Ticks still appear** – Controleer of `setShowTicks(false)` op beide lagen wordt aangeroepen.  
- **Duration not applied** – Bevestig dat u `TimeUnitType.Hour` (of de juiste eenheid) gebruikt bij het maken van duurwaarden.

## Veelgestelde vragen

**Q: Kan Aspose.Tasks for Java grote projectbestanden verwerken?**  
A: Ja, de bibliotheek is geoptimaliseerd voor high‑performance verwerking van uitgebreide projectgegevens.

**Q: Is Aspose.Tasks for Java compatibel met verschillende Java‑IDE's?**  
A: Absoluut – het werkt naadloos met Eclipse, IntelliJ IDEA, NetBeans en andere populaire IDE's.

**Q: Kan ik het uiterlijk van Gantt-diagrammen aanpassen buiten de tijdsschaal‑instellingen?**  
A: Ja, Aspose.Tasks biedt uitgebreide stijlopties zoals balkkleuren, lettertypen en rasterlijnen.

**Q: Is er een proefversie beschikbaar voor Aspose.Tasks for Java?**  
A: Ja, u kunt een gratis proefversie downloaden via [here](https://releases.aspose.com/).

**Q: Waar kan ik ondersteuning krijgen voor Aspose.Tasks for Java?**  
A: U kunt ondersteuning en hulp vinden op het Aspose.Tasks‑forum [here](https://forum.aspose.com/c/tasks/15).

**Q: Hoe kan ik programmatically de achtergrondkleur van het Gantt-diagram wijzigen?**  
A: Gebruik de `view.getGanttChartProperties().setBackgroundColor(Color)`‑methode na het importeren van `java.awt.Color`.

## Conclusie
Door deze stappen te volgen heeft u geleerd hoe u **project-PDF**‑bestanden kunt maken met een volledig aangepast Gantt-diagram tijdsschaal, **projectvisualisatie** kunt verbeteren, en **project opslaan als PDF** kunt gebruiken met Aspose.Tasks for Java. Deze aanpak geeft u volledige controle over de visuele output, waardoor het gemakkelijker wordt om duidelijke, professionele planningen te delen met uw team of klanten.

---

**Laatst bijgewerkt:** 2026-03-29  
**Getest met:** Aspose.Tasks for Java (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}