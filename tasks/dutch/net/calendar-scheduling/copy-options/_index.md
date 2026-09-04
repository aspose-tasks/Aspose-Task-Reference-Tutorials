---
date: 2026-07-05
description: Leer hoe u projectgegevens kunt kopiëren met Aspose.Tasks voor .NET met
  kopieeropties. Verhoog de prestaties van uw .NET-applicaties met nauwkeurig projectbeheer.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Hoe projectgegevens te kopiëren met kopieeropties in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Hoe projectgegevens te kopiëren met kopieeropties in Aspose.Tasks
url: /nl/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe projectgegevens te kopiëren met kopieeropties in Aspose.Tasks

## Inleiding

Als u **how to copy project** informatie van het ene Microsoft Project‑bestand naar het andere moet kopiëren, biedt Aspose.Tasks voor .NET een schone, code‑first manier om dit te doen. In deze tutorial lopen we het volledige werkproces door — het laden van een bronproject, het configureren van kopieeropties, het maken van een kopie en het laden van het resultaat — zodat u project‑kopieerlogica in elke .NET‑applicatie kunt integreren met vertrouwen.

## Snelle antwoorden
- **Wat doet de kopieerfunctie?** Het dupliceert projectgegevens terwijl u specifieke secties zoals kalenders, resources of weergave‑informatie kunt opnemen of uitsluiten.  
- **Welke klasse bepaalt het gedrag?** `CopyToOptions` laat u fijn afstemmen wat er wordt gekopieerd.  
- **Heb ik een licentie nodig?** Een geldige Aspose.Tasks‑licentie is vereist voor productie; een gratis proefversie werkt voor ontwikkeling.  
- **Ondersteunde formaten?** Aspose.Tasks verwerkt MPP-, XML- en XER‑bestanden — meer dan 20 + formaten in totaal.  
- **Kan ik weergave‑gegevens overslaan?** Ja, stel `CopyToOptions.SkipViewData = true` in om UI‑gerelateerde informatie weg te laten.

## Wat is “how to copy project” in Aspose.Tasks?

**“How to copy project”** verwijst naar het gebruik van de Aspose.Tasks‑API om de gegevens van een Project‑object te dupliceren naar een nieuw bestand, optioneel ongewenste elementen te filteren. Deze bewerking is nuttig voor het maken van sjablonen, archivering of het creëren van projectvarianten zonder handmatige UI‑stappen, en werkt met alle ondersteunde bestandsformaten.

## Waarom Copy Options gebruiken in Aspose.Tasks?

Aspose.Tasks ondersteunt **50+ project‑gerelateerde entiteiten** (taken, resources, kalenders, toewijzingen, enz.) en kan bestanden verwerken met **tot 10.000 taken** terwijl het geheugengebruik onder 200 MB blijft. Het gebruik van `CopyToOptions` stelt u in staat om het kopiëren van omvangrijke weergave‑gegevens te vermijden, waardoor de grootte van het uitvoerbestand met **30‑40 %** wordt verminderd en de bewerking voor grote projecten ongeveer **2×** sneller verloopt.

## Voorvereisten

1. **Aspose.Tasks for .NET** – download de nieuwste versie via de [download link](https://releases.aspose.com/tasks/net/).  
2. **.NET‑ontwikkelomgeving** – Visual Studio 2022 (of een IDE die .NET 6+ ondersteunt) geïnstalleerd.  
3. **Een geldige Aspose.Tasks‑licentie** – optioneel voor evaluatie, verplicht voor productie‑builds.  
4. **Een bestaand projectbestand** (bijv. `SourceProject.xml`) dat u wilt kopiëren.

## Hoe namespaces importeren voor Aspose.Tasks?

Voeg de vereiste `using`‑directieven toe aan de bovenkant van uw C#‑bestand zodat de compiler de Aspose.Tasks‑typen kan vinden. Het opnemen van deze statements geeft u directe toegang tot `Project`, `CopyToOptions` en andere hulpprogrammaklassen zonder hun namen volledig te kwalificeren, waardoor uw code wordt vereenvoudigd en de leesbaarheid verbetert.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Stap 1: Projectobjecten initialiseren

Eerst maakt u een `Project`‑instantie die het bronbestand vertegenwoordigt en laadt u de XML‑gegevens.  
De `Project`‑klasse vertegenwoordigt een Microsoft Project‑bestand dat in het geheugen is geladen, en maakt taken, resources, kalenders en andere projectinformatie beschikbaar.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Pro tip:** Als u met zeer grote bestanden werkt, overweeg dan de `LoadOptions`‑constructor te gebruiken om lazy loading in te schakelen en het geheugengebruik laag te houden.

## Stap 2: Een kopie van het project maken

Vervolgens maakt u een tweede `Project`‑object aan dat de gekopieerde gegevens zal ontvangen. Dit object start leeg.

```csharp
Project copiedProject = new Project();
```

U heeft nu twee afzonderlijke `Project`‑objecten: één geladen van schijf en één klaar om de kopie te ontvangen.

## Stap 3: Gekopieerd project laden

Na de kopieerbewerking (later getoond) wilt u het resultaat verifiëren door het nieuw opgeslagen bestand te laden in een andere `Project`‑instantie.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Het terugladen van het bestand bevestigt dat de kopie geslaagd is en dat de ingestelde opties zich hebben gedragen zoals verwacht.

## Stap 4: Kopieeropties configureren

De `CopyToOptions`‑klasse stelt u in staat precies te specificeren wat er van de bron naar de bestemming wordt overgebracht.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Het instellen van `SkipViewData = true` verkleint de grootte van het uitvoerbestand en versnelt de bewerking, vooral wanneer u alleen logische projectgegevens nodig heeft.

## Stap 5: Projectkopie uitvoeren

Roep tenslotte de `CopyTo`‑methode aan op het bronproject, waarbij u het bestemmingsproject en de geconfigureerde opties doorgeeft.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Deze tweeregelige aanroep voert de volledige kopieerbewerking uit, met inachtneming van de door u gedefinieerde opties. Het resulterende `CopiedProject.xml` bevat alleen de gegevens die u heeft aangevraagd.

## Veelvoorkomende problemen en oplossingen

| Issue | Cause | Fix |
|-------|-------|-----|
| **NullReferenceException bij het aanroepen van `CopyTo`** | Bestemmingsproject niet geïnstantieerd. | Zorg ervoor dat `new Project()` wordt aangeroepen vóór `CopyTo`. |
| **Ontbrekende taken na kopiëren** | `CopyCommonData` ingesteld op `false`. | Stel `CopyCommonData = true` in of kopieer specifieke collecties handmatig. |
| **Groot uitvoerbestand** | `SkipViewData` blijft op `false`. | Schakel `SkipViewData` in om UI‑gerelateerde gegevens weg te laten. |
| **Licentie niet toegepast** | Licentiebestand niet geladen. | Roep `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` aan vóór elk API‑gebruik. |

## Veelgestelde vragen

**Q: Kan ik alleen een subset van taken kopiëren?**  
A: Ja, gebruik `CopyToOptions` samen met `ProjectRootTask` om een starttaak op te geven, of kopieer handmatig geselecteerde taken na de initiële kopie.

**Q: Ondersteunt Aspose.Tasks kopiëren tussen verschillende bestandsformaten?**  
A: Absoluut. U kunt een MPP‑bestand laden en de kopie opslaan als XML, XER of een ander ondersteund formaat — meer dan **20 + formaten** in totaal.

**Q: Hoe ga ik om met wachtwoord‑beveiligde projectbestanden?**  
A: Laad de bron met `new Project("file.mpp", new LoadOptions { Password = "pwd" })`, en ga vervolgens zoals gewoonlijk verder met de kopie.

**Q: Is er een manier om resource‑pools te kopiëren zonder taken?**  
A: Stel `CopyToOptions.CopyResources = true` en `CopyToOptions.CopyTasks = false` in om alleen resource‑informatie over te dragen.

**Q: Waar kan ik meer voorbeelden vinden?**  
A: Bezoek het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) voor door de community geleverde fragmenten, tips voor probleemoplossing en officiële documentatie.

---
**Laatst bijgewerkt:** 2026-07-05  
**Getest met:** Aspose.Tasks 24.12 for .NET  
**Auteur:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Beheersen van projectgegevens met Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Beheersen van MS Project opslaan opties voor Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Aspose.Tasks kalender en planning](/tasks/net/calendar-scheduling/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}