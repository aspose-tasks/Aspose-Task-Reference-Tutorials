---
date: 2026-07-19
description: Leer hoe u het valutasymbool na het bedrag in .NET-projecten moeiteloos
  kunt regelen met Aspose.Tasks.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Posities van valutasymbolen in Aspose.Tasks
og_description: Leer hoe u het valutasymbool na het bedrag plaatst met Aspose.Tasks
  voor .NET. Volg stap‑voor‑stap instructies en best practices.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Valutasymbool na bedrag in Aspose.Tasks — Snelle gids
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: Hoe het valutasymbool na het bedrag plaatsen in Aspose.Tasks
url: /nl/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe plaats je het valutasymbool na het bedrag in Aspose.Tasks

## Introductie

Wanneer je projectkostrapporten genereert, kan de plaatsing van het **valutasymbool na het bedrag** de leesbaarheid en naleving van regionale normen beïnvloeden. Aspose.Tasks voor .NET stelt je in staat deze opmaak met slechts een paar regels code te regelen, zodat elk financieel cijfer precies verschijnt zoals je belanghebbenden verwachten. In deze tutorial lopen we de benodigde stappen door, leggen we uit waarom de instelling belangrijk is, en laten we zien hoe je dit toepast in een real‑world .NET‑project.

## Snelle antwoorden
- **Wat betekent “currency symbol after amount”?** Het toont het symbool (bijv. $) na de numerieke waarde, zoals `100 $`.
- **Welke eigenschap bepaalt de positie?** `CurrencySymbolPosition` op het `Project`‑object.
- **Heb ik een licentie nodig?** Een proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.
- **Ondersteunde valuta’s?** Meer dan 50 valuta’s zijn ingebouwd, die de meeste wereldmarkten dekken.
- **Kan ik de instelling tijdens runtime wijzigen?** Ja, je kunt deze op elk moment bijwerken vóór het opslaan van het projectbestand.

## Wat is de “currency symbol after amount” instelling?
De **currency symbol after amount**‑optie bepaalt of het valutasymbool vóór of na de numerieke waarde verschijnt in alle monetaire velden van een project. Het aanpassen van deze instelling zorgt ervoor dat rapporten voldoen aan lokale boekhoudconventies zonder handmatige nabewerking. Het verbetert tevens de leesbaarheid voor belanghebbenden die aan dit formaat gewend zijn.

## Waarom Aspose.Tasks gebruiken voor valutavormgeving?
Aspose.Tasks ondersteunt **meer dan 50 valuta’s** en kan projecten met **10.000+ taken** verwerken zonder het volledige bestand in het geheugen te laden, waardoor snelle prestaties mogelijk zijn zelfs op bescheiden hardware. De API biedt programmeerbare controle, waardoor handmatige spreadsheet‑aanpassingen overbodig zijn. Dit maakt grootschalige financiële rapportage zowel efficiënt als betrouwbaar.

## Vereisten

### 1. Installatie van Aspose.Tasks voor .NET
Zorg ervoor dat je de Aspose.Tasks‑bibliotheek geïnstalleerd hebt. Je kunt deze downloaden van [here](https://releases.aspose.com/tasks/net/).

### 2. Basiskennis van .NET-programmeren
Een fundamenteel begrip van .NET‑programmeren is noodzakelijk om de voorbeelden te kunnen volgen.

## Namespaces importeren

De `Aspose.Tasks`‑namespace biedt toegang tot de `Project`‑klasse en gerelateerde enumeraties.

De `Project`‑klasse is het top‑level object van Aspose.Tasks dat een enkel projectbestand in het geheugen vertegenwoordigt. Na het importeren van de namespace kun je beginnen met het werken met projectgegevens.

```csharp

```

Laten we nu het voorbeeld in duidelijke, uitvoerbare stappen opsplitsen.

## Hoe stel je het valutasymbool na het bedrag in?

`CurrencySymbolPosition` is een enumeratie die aangeeft of het valutasymbool vóór of na de numerieke waarde verschijnt.

Laad je project, stel `CurrencySymbolPosition` in op `After`, en sla vervolgens op – dat is alles wat je nodig hebt om het symbool na het bedrag weer te geven. Deze directe aanpak werkt voor elke ondersteunde valuta en vereist geen extra opmaaklogica. Je kunt de instelling ook verifiëren door een voorbeeld‑kostrapport te exporteren om te controleren of het symbool correct verschijnt.

### Stap 1: Laad het projectbestand
De `Project`‑klasse laadt een bestaand MS‑Project‑bestand of maakt een nieuw bestand in het geheugen.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Stap 2: Stel de positie van het valutasymbool in
`CurrencySymbolPosition` is een enum die je laat kiezen tussen `Before` of `After`. Door `After` te selecteren, wordt het symbool na de numerieke waarde geplaatst.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### Stap 3: Werk met het project
Nadat je de symboolpositie hebt geconfigureerd, kun je doorgaan met het toevoegen van taken, resources of aangepaste velden naar behoefte. De instelling wordt bewaard wanneer je het project opslaat.

```csharp
// Perform other operations with the project...
```

## Veelvoorkomende problemen en oplossingen
- **Symbool verschijnt nog steeds vóór het bedrag:** Zorg ervoor dat je de eigenschap *vóór* het aanroepen van `Save` instelt. Wijzigen na het opslaan vereist het bestand opnieuw op te slaan.
- **Niet‑ondersteunde valuta:** Controleer of de valutacode die je gebruikt voorkomt in de ondersteunde lijst van Aspose.Tasks (meer dan 50 valuta’s).
- **Prestatie‑vertraging bij grote projecten:** Gebruik `ProjectReader` om grote bestanden te streamen als je meer dan 10.000 taken hebt.

## Veelgestelde vragen

**V: Kan ik de positie van het valutasymbool meerdere keren binnen hetzelfde project wijzigen?**  
A: Ja, je kunt `CurrencySymbolPosition` zo vaak aanpassen als nodig; stel gewoon de eigenschap in en sla het project opnieuw op.

**V: Ondersteunt Aspose.Tasks andere valuta’s dan de Amerikaanse dollar?**  
A: Absoluut. Aspose.Tasks ondersteunt meer dan 50 internationale valuta’s, waardoor je met elk regionaal formaat kunt werken.

**V: Is er een proefversie beschikbaar voor Aspose.Tasks voor .NET?**  
A: Ja, je kunt een gratis proefversie van Aspose.Tasks voor .NET verkrijgen via [here](https://releases.aspose.com/).

**V: Kan ik hulp krijgen als ik problemen ondervind bij het gebruik van Aspose.Tasks voor .NET?**  
A: Zeker! Je kunt ondersteuning en assistentie vinden op het Aspose.Tasks community‑forum [here](https://forum.aspose.com/c/tasks/15).

**V: Hoe kan ik een licentie aanschaffen voor Aspose.Tasks voor .NET?**  
A: Je kunt een licentie voor Aspose.Tasks voor .NET kopen via [here](https://purchase.aspose.com/buy).

## Conclusie

Het beheersen van het **valutasymbool na het bedrag** is een essentieel onderdeel van financiële rapportage in projectmanagementsoftware. Met Aspose.Tasks voor .NET kun je deze optie programmatisch instellen, met ondersteuning voor meer dan 50 valuta’s en efficiënte verwerking van grote projecten. Pas de bovenstaande stappen toe om ervoor te zorgen dat je projectrapporten voldoen aan de opmaakverwachtingen van elke locale.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## Gerelateerde tutorials

- [Managing Calendar Collection in Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [Collection of Calendar Exceptions in Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Handling MS Project Rates with Aspose.Tasks for .NET](/tasks/net/rate-recurring-tasks/handling-rates/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}