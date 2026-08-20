---
date: 2026-03-14
description: Leer hoe u nullable booleans gebruikt in Aspose.Tasks voor .NET, inclusief
  het converteren van nullable boolean‑waarden en het instellen van nullable boolean‑eigenschappen.
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hoe nullable Booleans te gebruiken in Aspose.Tasks
url: /nl/net/advanced-concepts/nullable-booleans/
weight: 21
---

 shortcodes unchanged.

Now produce final output with all translated content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe nullable booleans te gebruiken in Aspose.Tasks

In deze tutorial laten we **zien hoe je nullable** booleans kunt gebruiken bij het werken met de Aspose.Tasks .NET API. Nullable booleans geven je drie mogelijke toestanden—`true`, `false` of *undefined*—wat vooral handig is voor project‑niveau instellingen die mogelijk niet expliciet zijn gespecificeerd. Je zult zien hoe je nullable boolean‑waarden maakt, converteert en **nullable boolean instellen**, en waarom het correct afhandelen van nullable booleans onverwacht gedrag in je planningsapplicaties kan voorkomen.

## Snelle antwoorden
- **Wat is een nullable boolean?** Een type dat `true`, `false` of undefined kan bevatten.  
- **Waarom nullable booleans gebruiken in Aspose.Tasks?** Ze laten je optionele projecteigenschappen weergeven zonder een standaardwaarde te raden.  
- **Hoe converteer je een nullable boolean naar een reguliere bool?** Gebruik de impliciete conversie of controleer eerst `IsDefined`.  
- **Wat is de primaire klasse?** `NullableBool` in de `Aspose.Tasks` namespace.  
- **Heb ik een licentie nodig?** Ja, een geldige Aspose.Tasks‑licentie is vereist voor productiegebruik.

## Wat is een Nullable Boolean?

Een nullable boolean (`NullableBool`) breidt het reguliere `bool`‑type uit met een *IsDefined*‑vlag. Wanneer `IsDefined` `false` is, wordt de waarde beschouwd als undefined, waardoor je kunt onderscheiden tussen “false” en “not set”.

## Waarom nullable booleans afhandelen in projectinstellingen?

Veel projectopties—zoals **ActualsInSync** of **HonorConstraints**—zijn optioneel. Het gebruik van een gewone `bool` dwingt je om `true` of `false` te kiezen, wat per ongeluk de intentie van een gebruiker kan overschrijven. Door **nullable booleans af te handelen**, behoud je de oorspronkelijke staat en vermijd je onbedoelde configuratiewijzigingen.

## Vereisten

Voordat we beginnen, zorg ervoor dat je het volgende hebt:

1. **Visual Studio** (of een andere .NET‑compatibele IDE).  
2. **Aspose.Tasks for .NET** – download het van [hier](https://releases.aspose.com/tasks/net/).

## Namespaces importeren

Importeer eerst de benodigde namespaces:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

Laten we nu elk voorbeeld stap voor stap doorlopen.

## Werken met `NullableBool`

### Stap 1: Maak een nieuwe `Project`‑instantie.

```csharp
var project = new Project();
```

### Stap 2: Instantieer een `NullableBool`‑object met opgegeven waarden.

```csharp
var actualsInSync = new NullableBool(false, false);
```

### Stap 3: Controleer de waarde en de gedefinieerde status van het `NullableBool`‑object.

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### Stap 4: **Nullable boolean instellen** op het project.

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### Stap 5: Instantieer een ander `NullableBool`‑object met een enkele waarde.

```csharp
var honorConstraints = new NullableBool(true);
```

### Stap 6: Toon de stringrepresentatie van het `NullableBool`‑object.

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### Stap 7: Gebruik de `NullableBool`‑instantie door deze in het project in te stellen.

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## Vergelijken van `NullableBool`‑instanties

### Stap 1: Instantieer twee `NullableBool`‑objecten.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Stap 2: Controleer de stringrepresentatie van elk `NullableBool`‑object.

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### Stap 3: Impliciete conversie naar `bool` en druk het resultaat af.

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### Stap 4: Vergelijk de twee `NullableBool`‑objecten op gelijkheid.

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## De hashcode van `NullableBool` ophalen

### Stap 1: Instantieer twee `NullableBool`‑objecten.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Stap 2: Print de hashcode voor elk `NullableBool`‑object.

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## Veelvoorkomende valkuilen & tips

- **Veronderstel nooit dat een nullable boolean gedefinieerd is.** Controleer altijd `IsDefined` voordat je `Value` gebruikt.  
- **Converteren naar een reguliere bool** zonder controle kan een uitzondering veroorzaken als de waarde undefined is. Gebruik de impliciete conversie alleen wanneer je zeker weet dat deze gedefinieerd is.  
- **Bij het instellen van projecteigenschappen**, gebruik de `Set`‑methode met een `NullableBool` om de undefined‑status te behouden indien nodig.

## Veelgestelde vragen

**Q: Wat is een nullable boolean?**  
A: Een nullable boolean kan `true`, `false` of een undefined‑status vertegenwoordigen, waardoor drie verschillende uitkomsten mogelijk zijn.

**Q: Hoe kan ik een nullable boolean veilig naar een reguliere bool converteren?**  
A: Controleer eerst `IsDefined`, gebruik daarna de `Value`‑eigenschap of vertrouw op de impliciete conversie wanneer je zeker bent dat deze gedefinieerd is.

**Q: Waarom zou ik nullable booleans gebruiken in plaats van gewone bools in Aspose.Tasks?**  
A: Ze laten je optionele projectinstellingen onaangeroerd houden, waardoor onbedoelde overschrijvingen worden voorkomen.

**Q: Kan ik een nullable boolean op undefined zetten?**  
A: Ja—gebruik de constructor die alleen de defined‑vlag accepteert, bijv. `new NullableBool(false, false)`.

**Q: Waar kan ik meer documentatie vinden over Aspose.Tasks voor .NET?**  
A: Gedetailleerde documentatie vind je [hier](https://reference.aspose.com/tasks/net/).

---

**Laatst bijgewerkt:** 2026-03-14  
**Getest met:** Aspose.Tasks for .NET (latest release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}