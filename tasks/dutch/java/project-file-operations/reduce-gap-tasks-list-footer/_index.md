---
date: 2026-05-20
description: Leer hoe u een project naar PDF kunt exporteren, de voettekstkloof kunt
  verkleinen en een project als afbeelding kunt opslaan met Aspose.Tasks voor Java.
  Optimaliseer moeiteloos de lay-out van uw MS Project.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Project exporteren naar PDF en de kloof tussen takenlijst en voettekst
  verkleinen in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Project exporteren naar PDF en de kloof tussen takenlijst en voettekst verkleinen
  in Aspose.Tasks
url: /nl/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Project exporteren naar PDF en de ruimte tussen takenlijst en voettekst verkleinen in Aspose.Tasks

## Introductie  
In deze tutorial ontdek je **hoe je een project naar PDF exporteert** terwijl je ook de ongewenste ruimte tussen de takenlijst en de voettekst in Microsoft Project‑bestanden verkleint. Aan het einde van de gids kun je schone PDF‑bestanden, PNG‑afbeeldingen en HTML‑pagina's genereren met een compacte lay-out met behulp van Aspose.Tasks voor Java. Laten we stap voor stap door het proces lopen, en je zult zien waarom dit belangrijk is voor professionele rapportage.

## Snelle antwoorden  
- **Wat betekent “export project to PDF”?** Het converteert een MPP‑bestand naar een PDF‑document waarbij taken, tijdlijnen en opmaak behouden blijven.  
- **Waarom de voettekst‑ruimte verkleinen?** Een kleinere ruimte zorgt voor strakkere, professioneler uitziende rapporten, vooral voor afgedrukte of web‑bekeken documenten.  
- **Kan ik het project ook opslaan als afbeelding?** Ja – Aspose.Tasks ondersteunt PNG, JPEG en andere afbeeldingsformaten.  
- **Heb ik een speciale licentie nodig?** Er is een gratis proefversie beschikbaar; een commerciële licentie is vereist voor productiegebruik.  
- **Welke Java‑versie is vereist?** Java 8 of hoger werkt met de huidige Aspose.Tasks‑bibliotheek.

## Wat is “export project to PDF”?  
Een project exporteren naar PDF transformeert de interne MPP‑structuur naar een draagbaar document dat op elk apparaat kan worden geopend zonder Microsoft Project te hoeven gebruiken. Dit is ideaal voor het delen van statusrapporten, updates voor belanghebbenden of het archiveren van projectplannen. Het behoudt de oorspronkelijke lay-out, kleuren en taakhiërarchie, waardoor de PDF er identiek uitziet als het bronbestand.

## Waarom de voettekst‑ruimte verkleinen?  
De standaardvoettekst‑ruimte kan onnodige lege ruimte toevoegen, wat pagineringproblemen en een onevenwichtige uitstraling veroorzaakt. Het verkleinen van de ruimte zorgt ervoor dat je inhoud de pagina efficiënt benut, waardoor de uiteindelijke PDF of afbeelding beter leesbaar wordt. Een strakkere lay-out vermindert ook het totale aantal pagina's, wat de afdrukkosten kan verlagen en de navigatie op het scherm kan verbeteren.

## Hoe de ruimte tussen takenlijst en voettekst verkleinen?  
`setReduceFooterGap` is een Boolean‑eigenschap die de voettekst‑afstand tijdens export regelt.  
Aspose.Tasks biedt een `setReduceFooterGap(true)`‑optie voor afbeelding-, PDF- en HTML‑opslaoperaties. Het inschakelen van deze vlag vertelt de engine de ruimte tussen de laatste taakrij en de paginavoettekst te comprimeren. Wanneer ingesteld op true, snijdt de renderer automatisch de marge bij zonder taakgegevens af te knippen, wat resulteert in een schonere paginalay-out.

## Project opslaan als afbeelding met Aspose.Tasks  
`ImageSaveOptions` configureert hoe een project wordt gerenderd naar een afbeeldingsbestand.  
De `ImageSaveOptions`‑klasse stelt je in staat een momentopname van het schema te exporteren als PNG, JPEG of BMP. Wanneer je ook `setReduceFooterGap(true)` inschakelt, weerspiegelt de gegenereerde afbeelding de compacte PDF‑lay-out, waardoor je een schone visual krijgt voor presentaties of dashboards.

## Java‑project exporteren naar PDF  
De volgende secties lopen een volledige **java project export**‑workflow door, van het laden van het MPP‑bestand tot het opslaan in drie verschillende formaten.

## Vereisten
Voordat we beginnen, zorg ervoor dat je de volgende vereisten hebt:
1. Java Development Kit (JDK) – versie 8 of hoger.  
2. Aspose.Tasks for Java Library – download deze van [hier](https://releases.aspose.com/tasks/java/).  

## Pakketten importeren  
Voordat we in het code‑gedeelte duiken, laten we de benodigde pakketten importeren:

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

## Stap 1: Geef het pad naar je gegevensmap op  
```java
String dataDir = "Your Data Directory";
```  
Zorg ervoor dat je `"Your Data Directory"` vervangt door het pad naar je daadwerkelijke gegevensmap waar je Microsoft Project‑bestand (`HomeMovePlan.mpp` in dit voorbeeld) zich bevindt.

## Stap 2: Lees het MPP‑bestand  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
Deze regel code leest het Microsoft Project‑bestand met de naam `HomeMovePlan.mpp`.

## Stap 3: Stel ImageSaveOptions in (Project opslaan als afbeelding)  
`ImageSaveOptions` configureert hoe een project wordt gerenderd naar een afbeeldingsbestand.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
Configureer de afbeeldingsopties, stel `ReduceFooterGap` in op `true` om de ruimte tussen de takenlijst en de voettekst te verkleinen.

## Stap 4: Opslaan als afbeelding  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
Sla het project op als afbeelding met de geconfigureerde opties.

## Stap 5: Stel PdfSaveOptions in (Project exporteren naar PDF)  
`PdfSaveOptions` specificeert instellingen voor het exporteren van een project naar PDF‑formaat.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
Definieer PDF‑opslaopties en zorg ervoor dat `ReduceFooterGap` op `true` wordt ingesteld.

## Stap 6: Opslaan als PDF  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
Sla het project op als PDF met de geconfigureerde opties.

## Stap 7: Stel HtmlSaveOptions in  
`HtmlSaveOptions` regelt de conversie van een project naar HTML, inclusief stijl‑ en lay‑outopties.  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
Specificeer HTML‑opslaopties en stel `ReduceFooterGap` in op `true`.

## Stap 8: Opslaan als HTML  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
Sla het project op als een HTML‑bestand met de geconfigureerde opties.

## Veelvoorkomende gebruikssituaties en tips  
- **Stakeholder‑rapportage:** Exporteren naar PDF met verkleinde voettekst‑ruimte om rapporten beknopt en printervriendelijk te houden.  
- **Dashboard‑momentopnames:** Gebruik de afbeeldingsexport wanneer je een snelle visual nodig hebt voor Power BI of Confluence.  
- **Webpublicatie:** HTML‑export behoudt interactiviteit en kan direct in intranet‑portalen worden ingebed.  
- **Pro‑tip:** Voor zeer grote projecten, verhoog de `Resolution` in `ImageSaveOptions` naar 300 dpi om de helderheid te behouden terwijl je nog steeds profiteert van de verkleinde ruimte.

## Veelgestelde vragen (extra)

**V: Hoe beïnvloedt het verkleinen van de voettekst‑ruimte de paginering?**  
A: Het minimaliseert lege ruimte aan de onderkant van elke pagina, waardoor meer taken op één pagina passen en het totale aantal pagina's wordt verminderd.

**V: Kan ik dezelfde ruimte‑reductie‑instelling alleen op één pagina toepassen?**  
A: Ja, door `setRenderToSinglePage(true)` in `ImageSaveOptions` in te stellen kun je de paginering regelen terwijl je de ruimte nog steeds verkleint.

**V: Is de `setReduceFooterGap`‑optie beschikbaar voor andere uitvoerformaten?**  
A: Momenteel wordt deze ondersteund voor PNG-, PDF- en HTML‑exports. Voor andere formaten moet je de lay-out handmatig aanpassen.

**V: Wat als mijn project aangepaste velden bevat—worden die behouden?**  
A: Alle aangepaste velden worden behouden tijdens export; de lay‑outaanpassingen beïnvloeden alleen de spatiëring, niet de gegevens.

**V: Handelt de bibliotheek grote projecten efficiënt?**  
A: Aspose.Tasks streamt gegevens en kan multi‑honderd‑pagina MPP‑bestanden verwerken zonder het volledige bestand in het geheugen te laden; zorg echter voor voldoende heap‑ruimte bij het exporteren van afbeeldingen met hoge resolutie.

---

**Laatst bijgewerkt:** 2026-05-20  
**Getest met:** Aspose.Tasks 24.11 for Java  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Project opslaan als afbeelding – 24bppRgb-formaat met Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Project opslaan als sjabloon, CSV en tekst met Aspose.Tasks voor Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Hoe een MPP‑bestand maken – Leeg project maken & opslaan in MPP‑formaat met Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}