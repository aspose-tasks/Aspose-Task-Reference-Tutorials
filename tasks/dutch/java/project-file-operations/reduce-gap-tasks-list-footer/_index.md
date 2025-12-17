---
date: 2025-12-17
description: Leer hoe u een project naar PDF exporteert, de voettekstkloof verkleint
  en het project opslaat als afbeelding met Aspose.Tasks voor Java. Optimaliseer moeiteloos
  de lay‑out van uw MS Project.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Project exporteren naar PDF en de ruimte tussen takenlijst en voettekst verkleinen
  in Aspose.Tasks
url: /nl/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Export Project naar PDF en verklein de ruimte tussen takenlijst en voettekst in Aspose.Tasks

## Introductie  
In deze tutorial ontdek je **hoe je een project naar PDF exporteert** terwijl je tevens de ongewenste ruimte tussen de takenlijst en de voettekst in Microsoft Project‑bestanden verkleint. Aan het einde van de gids kun je schone PDF‑bestanden, PNG‑afbeeldingen en HTML‑pagina's genereren met een compacte lay‑out met behulp van Aspose.Tasks voor Java. Laten we stap voor stap door het proces lopen.

## Snelle antwoorden  
- **Wat betekent “export project to PDF”?** Het converteert een MPP‑bestand naar een PDF‑document waarbij taken, tijdlijnen en opmaak behouden blijven.  
- **Waarom de voettekst‑ruimte verkleinen?** Een kleinere ruimte zorgt voor strakkere, professioneler uitziende rapporten, vooral voor afgedrukte of web‑weergave documenten.  
- **Kan ik het project ook als afbeelding opslaan?** Ja – Aspose.Tasks ondersteunt PNG, JPEG en andere afbeeldingsformaten.  
- **Heb ik een speciale licentie nodig?** Een gratis proefversie is beschikbaar; een commerciële licentie is vereist voor productiegebruik.  
- **Welke Java‑versie is vereist?** Java 8 of hoger werkt met de huidige Aspose.Tasks‑bibliotheek.

## Wat is “export project to PDF”?  
Een project naar PDF exporteren zet de interne MPP‑structuur om in een draagbaar document dat op elk apparaat geopend kan worden zonder Microsoft Project. Dit is ideaal voor het delen van statusrapporten, updates voor belanghebbenden of het archiveren van projectplannen.

## Waarom de voettekst‑ruimte verkleinen?  
De standaard voettekst‑ruimte kan onnodige witruimte toevoegen, wat pagineringproblemen en een onevenwichtig uiterlijk veroorzaakt. Het verkleinen van de ruimte zorgt ervoor dat je inhoud de pagina efficiënt benut, waardoor de uiteindelijke PDF of afbeelding beter leesbaar wordt.

## Hoe verklein je de ruimte tussen takenlijst en voettekst?  
Aspose.Tasks biedt een `setReduceFooterGap(true)`‑optie voor afbeelding-, PDF‑ en HTML‑opslaactaken. Het inschakelen van deze vlag vertelt de engine de ruimte tussen de laatste taakrij en de paginavoettekst te comprimeren.

## Project opslaan als afbeelding met Aspose.Tasks  
Als je een visueel momentopname van je planning nodig hebt, kun je **project opslaan als afbeelding** (PNG) terwijl je dezelfde instellingen voor ruimte‑reductie toepast.

## Java‑project export naar PDF  
De volgende secties lopen een volledige **java project export**‑workflow door, van het laden van het MPP‑bestand tot het opslaan in drie verschillende formaten.

## Vereisten  
Voordat we beginnen, zorg dat je de volgende vereisten hebt:  
1. Java Development Kit (JDK) – versie 8 of later.  
2. Aspose.Tasks voor Java‑bibliotheek – download deze van [here](https://releases.aspose.com/tasks/java/).  

## Pakketten importeren  
Voordat we naar het code‑gedeelte gaan, importeren we de benodigde pakketten:  
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

## Stap 1: Geef het pad naar je gegevensmap op  
```java
String dataDir = "Your Data Directory";
```  
Zorg ervoor dat je `"Your Data Directory"` vervangt door het pad naar je eigen gegevensmap waar je Microsoft Project‑bestand (`HomeMovePlan.mpp` in dit voorbeeld) zich bevindt.

## Stap 2: Lees het MPP‑bestand  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
Deze regel code leest het Microsoft Project‑bestand met de naam `HomeMovePlan.mpp`.

## Stap 3: Stel ImageSaveOptions in (Project opslaan als afbeelding)  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
Configureer de opties voor het opslaan van afbeeldingen, waarbij `ReduceFooterGap` op `true` wordt gezet om de ruimte tussen de takenlijst en de voettekst te verkleinen.

## Stap 4: Opslaan als afbeelding  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
Sla het project op als afbeelding met de geconfigureerde opties.

## Stap 5: Stel PdfSaveOptions in (Export Project naar PDF)  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
Definieer de PDF‑opslaopties en zorg ervoor dat `ReduceFooterGap` op `true` staat.

## Stap 6: Opslaan als PDF  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
Sla het project op als PDF met de geconfigureerde opties.

## Stap 7: Stel HtmlSaveOptions in  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
Specificeer de HTML‑opslaopties en zet `ReduceFooterGap` op `true`.

## Stap 8: Opslaan als HTML  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
Sla het project op als HTML‑bestand met de geconfigureerde opties.

## Conclusie  
Samengevat is het verkleinen van de ruimte tussen de takenlijst en de voettekst in Microsoft Project‑bestanden een eenvoudig proces met Aspose.Tasks voor Java. Door de stappen in deze tutorial te volgen, kun je efficiënt **project exporteren naar PDF**, opslaan als afbeelding, of HTML genereren terwijl de lay‑out strak en professioneel blijft.

## Veelgestelde vragen

### Q: Is Aspose.Tasks compatibel met alle versies van Microsoft Project?

A: Aspose.Tasks ondersteunt Microsoft Project 2003‑2019‑formaten, waardoor compatibiliteit met diverse versies gegarandeerd is.

### Q: Kan ik het uiterlijk van de voettekst in mijn projectdocumenten aanpassen?

A: Ja, Aspose.Tasks biedt uitgebreide opties voor het aanpassen van voetteksten, inclusief het verkleinen van ruimtes en het aanpassen van de inhoudsplaatsing.

### Q: Ondersteunt Aspose.Tasks het opslaan van projecten in andere formaten dan PNG, PDF en HTML?

A: Ja, Aspose.Tasks ondersteunt een breed scala aan formaten, waaronder XLSX, XML en MPP, onder andere.

### Q: Is er een proefversie beschikbaar voor Aspose.Tasks?

A: Ja, je kunt een gratis proefversie van Aspose.Tasks downloaden van [here](https://releases.aspose.com/).

### Q: Waar kan ik ondersteuning krijgen als ik problemen ondervind bij het gebruik van Aspose.Tasks?

A: Je kunt hulp krijgen via het Aspose.Tasks community‑forum [here](https://forum.aspose.com/c/tasks/15).

## Veelgestelde vragen (aanvullend)

**Q: Hoe beïnvloedt het verkleinen van de voettekst‑ruimte de paginering?**  
A: Het minimaliseert lege ruimte onderaan elke pagina, waardoor meer taken op één pagina passen en het totale aantal pagina's afneemt.

**Q: Kan ik dezelfde ruimte‑reductie‑instelling alleen op één pagina toepassen?**  
A: Ja, door `setRenderToSinglePage(true)` in `ImageSaveOptions` te zetten kun je de paginering regelen terwijl je de ruimte nog steeds verkleint.

**Q: Is de `setReduceFooterGap`‑optie beschikbaar voor andere uitvoerformaten?**  
A: Momenteel wordt deze ondersteund voor PNG, PDF en HTML exports. Voor andere formaten moet je de lay‑out handmatig aanpassen.

**Q: Wat als mijn project aangepaste velden bevat—worden die behouden?**  
A: Alle aangepaste velden blijven behouden tijdens de export; de lay‑out‑aanpassingen beïnvloeden alleen de spatiëring, niet de data.

**Q: Handelt de bibliotheek grote projecten efficiënt?**  
A: Aspose.Tasks streamt data en kan grote MPP‑bestanden verwerken; zorg echter voor voldoende geheugen bij het exporteren naar afbeeldingen met hoge resolutie.

---

**Laatst bijgewerkt:** 2025-12-17  
**Getest met:** Aspose.Tasks 24.11 voor Java  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}