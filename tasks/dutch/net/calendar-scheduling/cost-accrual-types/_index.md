---
date: 2026-07-05
description: Leer hoe u projectbudget kunt volgen en projectkosten kunt beheren met
  Aspose.Tasks voor .NET. Definieer Cost Accrual Types voor nauwkeurige kostentracking.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Cost Accrual Types in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Volg projectbudget met Cost Accrual Types in Aspose.Tasks
url: /nl/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Volg het projectbudget met kosttoerekeningssoorten in Aspose.Tasks

## Introductie

Accuraat **projectbudget bijhouden** is de ruggengraat van een succesvolle projectlevering. Wanneer kostinformatie op het juiste moment wordt vastgelegd, kun je overschrijdingen voorspellen, middelen aanpassen en belanghebbenden informeren. Aspose.Tasks voor .NET geeft ontwikkelaars fijnmazige controle over kosttoerekening, zodat je kunt bepalen *wanneer* een kost wordt geregistreerd—of dit nu bij de start van het werk is, continu, of alleen wanneer het werk is voltooid. Deze tutorial leidt je door de concepten, laat zien hoe je een toerekeningssoort instelt, en demonstreert best practices voor betrouwbare budgetbewaking.

## Snelle antwoorden
- **Wat is het primaire doel van kosttoerekeningssoorten?** Ze bepalen het moment in de levenscyclus van een taak waarop kosten worden erkend, waardoor nauwkeurige budgetbewaking mogelijk is.  
- **Welke enum-waarde vertraagt kosten tot het werk is voltooid?** `CostAccrualType.End`.  
- **Heb ik een licentie nodig om de code uit te voeren?** Ja, een geldige Aspose.Tasks-licentie is vereist voor productiegebruik.  
- **Kan ik toerekeningssoorten voor veel resources tegelijk wijzigen?** Ja—loop door de `Resources`-collectie en wijs het gewenste type toe.  
- **Welke .NET-versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is kosttoerekeningssoort?
Een **kosttoerekeningssoort** vertelt Aspose.Tasks wanneer de kost van een resource op het projectbudget moet worden toegepast. Het wordt vertegenwoordigd door de `CostAccrualType`-enumeratie en kan per resource of per taak worden ingesteld. Het kiezen van de juiste soort zorgt ervoor dat kostgegevens overeenkomen met de factureringsrichtlijnen van je organisatie, of je nu kosten wilt registreren bij de start van het werk, proportioneel over de duur, of alleen na voltooiing.

## Waarom projectbudget bijhouden met kosttoerekeningssoorten?
Aspose.Tasks ondersteunt **vier** toerekeningsopties—`Start`, `Prorated`, `Duration` en `End`—die het volledige scala aan typische projectboekhoudscenario's dekken. Het selecteren van de juiste optie stelt je in staat om kostherkenning af te stemmen op contractuele factureringscycli, variatie in financiële rapporten te verminderen en kostoverzichten te genereren die naadloos integreren met ERP‑systemen, terwijl het geheugenverbruik laag blijft voor grote projecten.

## Voorvereisten

Voordat we beginnen, zorg ervoor dat je de volgende voorwaarden hebt:

### 1. Installeer Aspose.Tasks voor .NET
Om te starten, moet je Aspose.Tasks voor .NET geïnstalleerd hebben in je ontwikkelomgeving. Je kunt de bibliotheek downloaden van de [download page](https://releases.aspose.com/tasks/net/) en de installatie‑instructies volgen die daar worden gegeven.

### 2. Vertrouwdheid met .NET Framework
Basiskennis van het .NET‑framework en de programmeertaal C# is vereist om de voorbeelden in deze tutorial te kunnen volgen.

## Hoe kosttoerekeningssoort instellen voor een resource?

Laad het project, lokaliseer de doel‑resource en wijs de gewenste `CostAccrualType` toe. Het twee‑regelige patroon hieronder is de standaardaanpak: maak een `Project`‑instantie, haal de resource op via zijn ID, en stel vervolgens `CostAccrualType` in. Deze beknopte volgorde zorgt ervoor dat je **projectbudget nauwkeurig** bijhoudt vanaf het moment dat de resource wordt toegevoegd.

### Stap 1: Namespaces importeren
Laten we beginnen met het importeren van de benodigde namespaces om Aspose.Tasks‑functionaliteit in ons .NET‑project te gebruiken:

```csharp

```

Nu de namespaces klaar zijn, kunnen we doorgaan met het laden van een projectbestand.

### Stap 2: Projectbestand laden
De `Project`‑klasse vertegenwoordigt een Microsoft Project‑bestand en biedt toegang tot de taken, resources en andere gegevens.

```csharp
var project = new Project("Project2.mpp");
```

Eerst moeten we het projectbestand in onze applicatie laden. We maken een nieuw `Project`‑object aan en initialiseren het met het pad naar ons projectbestand.

### Stap 3: Resource benaderen
De `Resources`‑collectie bevat alle resources die in het project zijn gedefinieerd. De `GetById`‑methode haalt een resource op via zijn unieke identifier.

```csharp
var resource = project.Resources.GetById(1);
```

Vervolgens benaderen we de resource waaraan we de kosttoerekeningssoort willen toepassen. We gebruiken de `GetById`‑methode van de `Resources`‑collectie en geven de resource‑ID als argument door. Dit demonstreert **resource op ID benaderen**, een veelvoorkomende vereiste bij het automatiseren van kostupdates.

### Stap 4: Kosttoerekeningssoort instellen
De `Set`‑methode kent een waarde toe aan een resource‑veld.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Hier stellen we de kosttoerekeningssoort voor de resource in. In dit voorbeeld stellen we deze in op `CostAccrualType.End`, wat betekent dat kosten pas worden toegekend wanneer het resterende werk nul is. Het kiezen van `End` is ideaal wanneer je **projectbudget** alleen wilt bijhouden nadat een taak volledig is voltooid.

### Stap 5: Doorgaan met het project
Na het instellen van de kosttoerekeningssoort kun je doorgaan met het project zoals nodig, aanvullende bewerkingen of berekeningen uitvoeren, zoals het genereren van kostrapporten, het bijwerken van toewijzingen of het exporteren van het bestand.

## Veelvoorkomende valkuilen en pro‑tips
- **Pro tip:** Roep altijd `project.Save` aan na het wijzigen van toerekeningssoorten om de wijzigingen op te slaan.  
- **Valkuil:** Het instellen van `CostAccrualType.Start` op een resource die nooit aan het werk gaat, zal de budgetrapporten opblazen—controleer eerst de taakplanningen.  
- **Pro tip:** Gebruik `project.Resources.ToList()` wanneer je veel resources in één batch moet bijwerken; dit voorkomt herhaalde collectie‑opzoekingen en verbetert de prestaties bij grote projecten.

## Veelgestelde vragen

**Q: Kan ik de kosttoerekeningssoort voor meerdere resources tegelijk wijzigen?**  
A: Ja, loop door `project.Resources` en wijs de gewenste `CostAccrualType` toe aan elke resource binnen een `foreach`‑lus.

**Q: Wat zijn de andere beschikbare kosttoerekeningssoorten naast `End`?**  
A: Aspose.Tasks biedt `Start`, `Prorated` en `Duration`—elk sluit aan bij een andere factureringsstrategie.

**Q: Hoe kan ik de huidige kosttoerekeningssoort voor een specifieke resource bepalen?**  
A: Haal de waarde op via `resource.Get(TskResource.CostAccrualType)`; dit retourneert de enum die de huidige instelling weergeeft.

**Q: Is het mogelijk om verschillende kosttoerekeningssoorten toe te passen op verschillende taken in hetzelfde project?**  
A: Absoluut. Zowel taken als resources exposen een `CostAccrualType`‑eigenschap, waardoor onafhankelijke configuratie per entiteit mogelijk is.

**Q: Ondersteunt Aspose.Tasks aangepaste kosttoerekeningssoorten?**  
A: Nee, de bibliotheek ondersteunt momenteel alleen de vier ingebouwde soorten; aangepaste logica moet extern worden geïmplementeerd indien nodig.

---

**Laatst bijgewerkt:** 2026-07-05  
**Getest met:** Aspose.Tasks 24.8 for .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Aspose.Tasks Calendar and Scheduling](/tasks/net/calendar-scheduling/)
- [Handling MS Project Rates with Aspose.Tasks for .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Effortlessly Manage MS Project Resources with Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}