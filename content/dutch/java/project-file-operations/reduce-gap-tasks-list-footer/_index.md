---
title: De kloof tussen de takenlijst en de voettekst verkleinen in Aspose.Tasks
linktitle: De kloof tussen de takenlijst en de voettekst verkleinen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u de kloof tussen MS Project-takenlijsten en voetteksten kunt verkleinen met Aspose.Tasks voor Java. Optimaliseer moeiteloos de lay-out van projectdocumenten.
type: docs
weight: 10
url: /nl/java/project-file-operations/reduce-gap-tasks-list-footer/
---
## Invoering
In deze zelfstudie gaan we dieper in op het verkleinen van de kloof tussen de takenlijst en de voettekst in Microsoft Project-bestanden met behulp van Aspose.Tasks voor Java. Door deze stappen te volgen, kunt u de lay-out van uw projectdocumenten moeiteloos optimaliseren.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor Java-bibliotheek: Download de Aspose.Tasks voor Java-bibliotheek en neem deze op in uw project. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
Laten we, voordat we in het codeergedeelte duiken, de benodigde pakketten importeren:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Stap 1: Geef het pad naar uw gegevensmap op
```java
String dataDir = "Your Data Directory";
```
 Zorg ervoor dat u vervangt`"Your Data Directory"` met het pad naar uw daadwerkelijke gegevensmap waar uw Microsoft Project-bestand (`HomeMovePlan.mpp` in dit voorbeeld) bevindt.
## Stap 2: Lees het MPP-bestand
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Deze coderegel leest het Microsoft Project-bestand met de naam`HomeMovePlan.mpp`.
## Stap 3: Stel ImageSaveOptions in
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Configureer de opties voor het opslaan van afbeeldingen, instelling`ReduceFooterGap` naar`true` om de kloof tussen de takenlijst en de voettekst te verkleinen.
## Stap 4: Opslaan als afbeelding
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Sla het project op als afbeelding met de geconfigureerde opties.
## Stap 5: Stel PdfSaveOptions in
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 Definieer opties voor het opslaan van PDF's en zorg ervoor dat deze zijn ingesteld`ReduceFooterGap` naar`true`.
## Stap 6: Opslaan als PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Sla het project op als PDF met de geconfigureerde opties.
## Stap 7: Stel HtmlSaveOptions in
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // ingesteld op waar
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 Geef HTML-opslagopties en instellingen op`ReduceFooterGap` naar`true`.
## Stap 8: Opslaan als HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Sla het project op als HTML-bestand met de geconfigureerde opties.

## Conclusie
Kortom, het verkleinen van de kloof tussen de takenlijst en de voettekst in Microsoft Project-bestanden is een eenvoudig proces met Aspose.Tasks voor Java. Door de stappen in deze tutorial te volgen, kunt u de lay-out van uw projectdocumenten efficiënt optimaliseren.

## Veelgestelde vragen

### Vraag: Is Aspose.Tasks compatibel met alle versies van Microsoft Project?

A: Aspose.Tasks ondersteunt Microsoft Project 2003-2019-formaten, waardoor compatibiliteit tussen verschillende versies wordt gegarandeerd.

### Vraag: Kan ik het uiterlijk van de voettekst in mijn projectdocumenten aanpassen?

A: Ja, Aspose.Tasks biedt uitgebreide opties voor het aanpassen van het uiterlijk van voetteksten, inclusief het verkleinen van gaten en het aanpassen van de plaatsing van de inhoud.

### Vraag: Ondersteunt Aspose.Tasks het opslaan van projecten in andere formaten dan PNG, PDF en HTML?

A: Ja, Aspose.Tasks ondersteunt een breed scala aan formaten, waaronder onder andere XLSX, XML en MPP.

### Vraag: Is er een proefversie beschikbaar voor Aspose.Tasks?

 A: Ja, u kunt een gratis proefversie van Aspose.Tasks downloaden van[hier](https://releases.aspose.com/).

### Vraag: Waar kan ik ondersteuning krijgen als ik problemen ondervind tijdens het gebruik van Aspose.Tasks?

 A: U kunt hulp krijgen van het Aspose.Tasks-communityforum[hier](https://forum.aspose.com/c/tasks/15).