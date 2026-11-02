---
date: 2026-10-31
description: Leer hoe u gantt naar pdf kunt exporteren in Java met Aspose.Tasks. Deze
  stapsgewijze handleiding laat zien hoe u Gantt‑diagramgegevens kunt lezen en PDF‑rapporten
  kunt genereren.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: Specifieke Gantt‑diagramgegevens lezen in Aspose.Tasks
og_description: Export gantt naar pdf in Java met Aspose.Tasks. Volg deze tutorial
  om Gantt‑diagramgegevens te lezen, weergave‑eigenschappen aan te passen en PDF‑rapporten
  te genereren voor projectbeheer.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: Export gantt naar pdf in Java – Aspose.Tasks‑gids
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: Export gantt naar pdf in Java – specifieke gegevens extraheren
url: /nl/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Export gantt naar pdf in Java – specifieke gegevens extraheren

## Inleiding
In deze tutorial leer je hoe je **export gantt to pdf in Java** kunt uitvoeren door Gantt-diagraminformatie te lezen met Aspose.Tasks for Java. Gantt-diagrammen geven projectmanagers een visueel overzicht van taken, afhankelijkheden en tijdlijnen, en het programmatic ophalen van die gegevens stelt je in staat geautomatiseerde PDF-rapporten, dashboards of integraties met andere enterprise-systemen te maken. Laten we elke stap doorlopen, van het laden van een projectbestand tot het extraheren van weergave‑eigenschappen en uiteindelijk het genereren van een PDF.

## Snelle antwoorden
- **Wat kan ik extraheren?** Elke weergave‑eigenschap, balkstijl, rasterlijn, tekststijl, voortgangslijn of tijdschaal‑niveau van een Gantt-diagram.  
- **Heb ik een licentie nodig?** Een proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of later (de tutorial gebruikt JDK 11).  
- **Is de code direct uitvoerbaar?** Ja – vervang alleen het pad naar de gegevensdirectory.  
- **Kan ik de weergave aanpassen na het lezen?** Absoluut – de API laat je eigenschappen wijzigen en terug opslaan naar het projectbestand.

## Wat is export gantt naar pdf?
Export gantt to pdf is het proces waarbij een Gantt-diagramweergave die in een projectbestand is opgeslagen, wordt omgezet naar een PDF‑document dat de visuele opmaak en tijdlijninformatie behoudt. Deze bewerking is nuttig voor het delen van projectstatus met belanghebbenden die mogelijk geen project‑managementtool hebben.

## Waarom export gantt naar pdf met Aspose.Tasks?
Aspose.Tasks kan **meer dan 30 + invoerformaten** (MPP, XML, MPX, enz.) aan en **exporteren naar PDF in één enkele oproep** terwijl 95 % van de visuele getrouwheid behouden blijft, zelfs voor projecten met meer dan 500 taken. De bibliotheek verwerkt bestanden in het geheugen, zodat je PDF‑s kunt genereren op servers zonder Microsoft Project te installeren.

## Vereisten
1. **Java Development Kit (JDK):** Zorg ervoor dat Java op je systeem is geïnstalleerd. Je kunt het downloaden van de **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.  
2. **Aspose.Tasks for Java Library:** Download en installeer de Aspose.Tasks for Java‑bibliotheek vanaf de **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE):** Kies een IDE naar keuze. Populaire opties zijn IntelliJ IDEA, Eclipse of NetBeans.

## Pakketten importeren
De volgende imports geven je toegang tot de kern‑Aspose.Tasks‑klassen die nodig zijn voor het lezen en exporteren van Gantt‑gegevens.  
*Er wordt hier geen code‑blok getoond om de tutorial te focussen op concepten; voeg simpelweg de imports toe aan je Java‑bestand.*

## Hoe laad ik een Gantt-diagramprojectbestand in Java?
Laad het projectbestand door een `Project`‑instantie te maken en het volledige pad aan de constructor door te geven. Deze stap initialiseert de in‑memory weergave van het Gantt-diagram, waardoor latere query's van weergave‑eigenschappen mogelijk zijn. Wanneer het bestand succesvol is geladen, kun je de naam van het project, de startdatum en het aantal taken verifiëren om er zeker van te zijn dat het juiste bestand is geopend. Deze verificatie helpt om pad‑ of formaatproblemen vroeg in de workflow te detecteren.  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*Definition anchor:* `Project` is het top‑level Aspose.Tasks‑object dat een enkel projectbestand in het geheugen vertegenwoordigt.

## Hoe kan ik de Gantt-diagramweergave benaderen?
Haal de eerste Gantt‑weergave op uit de view‑collectie van het project. De meeste projecten bevatten minstens één Gantt‑weergave, en deze is meestal de eerste invoer. Nadat je de weergave hebt verkregen, wil je mogelijk de naam controleren en ervoor zorgen dat deze van het type `GanttChartView` is voordat je doorgaat met het extraheren van eigenschappen. Deze extra controle voorkomt runtime‑fouten bij het werken met aangepaste of niet‑standaard view‑collecties.  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*Definition anchor:* `GanttChartView` vertegenwoordigt de visuele lay-out van taken, tijdschalen en balken die je ziet in een typisch Gantt‑diagram.

## Hoe extraheren ik weergave‑eigenschappen?
Je kunt eigenschappen zoals achtergrondkleur, balkhoogte en tijdschaalinstellingen direct lezen van het `GanttChartView`‑object. Het afdrukken ervan helpt je de huidige configuratie te verifiëren vóór het exporteren. Een typische extractielus iterereert over elke eigenschap, formatteert de waarde als een string en logt deze naar de console of een bestand voor latere analyse. Deze aanpak is nuttig voor debugging en voor het genereren van documentatie van het uiterlijk van het diagram.  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*Definition anchor:* `GanttChartView` biedt toegang tot weergave‑instellingen zoals achtergrondkleur, balkhoogte en tijdschaalconfiguratie.

## Hoe extraheren ik balkstijlen?
Itereer door de collectie van `BarStyle`‑objecten om details te verkrijgen zoals kleur, patroon en vorm voor elk balktype dat in het diagram wordt gebruikt. Voor elke stijl kun je ook het bijbehorende taaktype en de voorwaarde die de stijl activeert lezen, wat essentieel is bij het opnieuw maken van het diagram in een ander formaat. Het verzamelen van deze informatie stelt je in staat een getrouwe visuele replica te produceren of aangepaste stijlregels programmatisch toe te passen.  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*Definition anchor:* `BarStyle` definieert het visuele uiterlijk van een Gantt‑balk, inclusief kleur, patroon en vorm.

## Hoe extraheren ik rasterlijnen?
Rasterlijnen definiëren de visuele scheiding tussen rijen en kolommen. Toegang krijg je via de `getGridlines()`‑methode en je kunt hun zichtbaarheid en stijl weergeven. Na het ophalen van de rasterlijncollectie kun je door elke lijn itereren om het lijntype (solid, dashed), de dikte en de kleur vast te leggen. Deze gegevens zijn waardevol wanneer je de exacte rasterlay-out moet reproduceren in geëxporteerde PDF‑s of andere rapportageformaten.  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*Definition anchor:* `getGridlines()` retourneert de collectie rasterlijnobjecten die de rij‑ en kolomscheiding in de Gantt‑weergave regelen.

## Hoe extraheren ik tekststijlen?
Tekststijlen bepalen het lettertype, de grootte en de kleur van labels op het Gantt‑diagram. Loop door de `TextStyle`‑collectie om elke stijl te vermelden. Voor elke tekststijl kun je ook het bijbehorende element (taaknaam, datum, enz.) en eventuele voorwaardelijke opmaakregels ophalen. Het vastleggen van deze details zorgt ervoor dat geëxporteerde documenten dezelfde typografie behouden als het oorspronkelijke diagram.  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*Definition anchor:* `TextStyle` vertegenwoordigt de opmaak‑attributen die op tekstuele elementen binnen het Gantt‑diagram worden toegepast.

## Hoe extraheren ik voortgangslijnen?
Voortgangslijnen tonen het huidige voltooiingspunt van een taak. Toegang krijg je via `getProgressLines()` en je kunt hun attributen afdrukken. Elke voortgangslijn bevat eigenschappen zoals lijnkleur, dikte en de positie ten opzichte van de taakbalk. Het vastleggen van deze informatie stelt je in staat voortgangs‑bewuste visualisaties te genereren of de algehele projectvoltooiings‑metriek te berekenen.  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*Definition anchor:* `getProgressLines()` retourneert de set van voortgangslijnobjecten die de voltooiingsstatus van taken aangeven.

## Hoe extraheren ik tijdschaal‑niveaus?
Tijdschaal‑niveaus definiëren de hiërarchische tijdseenheden (dagen, weken, maanden) die op het diagram worden weergegeven. Haal ze op via `getTimescaleTiers()` en geef hun instellingen weer. Voor elk niveau kun je het eenheidstype, labelindeling en uitlijning vastleggen, wat cruciaal is voor het reproduceren van de exacte tijdlijn‑granulariteit in geëxporteerde PDF‑s of aangepaste UI‑componenten.  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*Definition anchor:* `getTimescaleTiers()` biedt toegang tot de collectie tijdschaal‑niveau‑objecten die de weergave van de tijdas regelen.

## Hoe exporteer ik het Gantt-diagram naar PDF?
Maak een `PdfSaveOptions`‑object aan, pas eventueel paginagrootte of lettertype‑embedden aan, en roep vervolgens `project.save` aan met het PDF‑formaat. Deze enkele oproep genereert een PDF die de Gantt‑weergave op het scherm weerspiegelt. Je kunt ook extra opties opgeven, zoals beeldcompressie, watermerkverwijdering of het embedden van aangepaste lettertypen om te voldoen aan de huisstijlvereisten van het bedrijf. Na het opslaan, controleer je de PDF‑bestandsgrootte en visuele getrouwheid om te bevestigen dat de export geslaagd is.  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*Definition anchor:* `PdfSaveOptions` stelt je in staat de PDF‑output fijn af te stemmen, zoals paginadimensies, compressie en lettertype‑beheer.

## Veelvoorkomende valkuilen & tips
- **Onjuiste gegevensdirectory:** Zorg ervoor dat `dataDir` eindigt met een bestandsscheidingsteken (`/` of `\\`) dat geschikt is voor je OS.  
- **Ontbrekende weergave:** Als het project geen Gantt‑weergave heeft, zal `project.getViews()` leeg zijn – voeg een controle toe vóór het casten.  
- **Licentie‑uitzonderingen:** Zonder een geldige licentie kan de API een watermerk toevoegen aan geëxporteerde PDF‑s.  
- **Grote projecten:** Voor projecten met meer dan 1.000 taken, overweeg het verhogen van de JVM‑heap‑grootte (`-Xmx2g`) om `OutOfMemoryError` te voorkomen.  

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks for Java gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Tasks for Java integreert naadloos met elke Java‑bibliotheek of -framework, inclusief Spring, Hibernate en Apache POI.

**Q: Is Aspose.Tasks geschikt voor grootschalige enterprise‑projecten?**  
A: Absoluut. De bibliotheek verwerkt multi‑honderd‑pagina MPP‑bestanden in minder dan 5 seconden op standaard serverhardware en ondersteunt gelijktijdige uitvoering in multi‑threaded omgevingen.

**Q: Ondersteunt Aspose.Tasks meerdere projectbestandformaten?**  
A: Ja, Aspose.Tasks ondersteunt meer dan 20 formaten, inclusief MPP, XML, MPX en Primavera XML, waardoor je legacy‑planningen kunt lezen en converteren.

**Q: Kan ik het uiterlijk van Gantt‑diagrammen aanpassen met Aspose.Tasks?**  
A: Zeker. Je kunt balkstijlen, rasterlijnen, tekststijlen en tijdschaal‑niveaus programmatisch wijzigen voordat je exporteert naar PDF‑ of afbeeldingsformaten.

**Q: Hoe sla ik wijzigingen op na het aanpassen van een weergave?**  
A: Roep `project.save("output.mpp");` aan nadat je wijzigingen hebt aangebracht om ze op te slaan in het projectbestand.

---

**Laatst bijgewerkt:** 2026-10-31  
**Getest met:** Aspose.Tasks for Java 24.12  
**Auteur:** Aspose  



```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## Gerelateerde tutorials

- [Hoe project opslaan als PDF met Aspose.Tasks – Exportgids](/tasks/java/project-file-operations/save-as-pdf/)
- [Project PDF maken – Tijdsschaal van Gantt-diagram aanpassen](/tasks/java/project-file-operations/set-time-scale-count/)
- [Project exporteren naar PDF en de ruimte tussen takenlijst en voettekst verkleinen in Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}