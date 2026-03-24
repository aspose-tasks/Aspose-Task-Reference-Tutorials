---
date: 2026-03-24
description: Leer hoe u de berekeningsmodus instelt in Aspose.Tasks voor .NET, met
  uitleg over automatische, handmatige en geen modus om taakafhankelijkheden te beheren.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Hoe de berekeningsmodus instellen in Aspose.Tasks voor .NET
url: /nl/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe de berekeningsmodus in te stellen in Aspose.Tasks voor .NET

## Inleiding

Aspose.Tasks for .NET is een krachtige API waarmee u programmatisch met Microsoft Project‑bestanden kunt werken. Een van de belangrijkste instellingen die u tegenkomt is de **berekeningsmodus**, die bepaalt hoe taakdatums en projectschema's worden bijgewerkt. In deze tutorial leert u **hoe u de berekening** instelt, verkent u **automatische berekeningsmodus**, **handmatige berekeningsmodus** en **geen berekeningsmodus**, en ziet u hoe deze opties invloed hebben op **het beheren van taakafhankelijkheden**, **het aanmaken van de projectstartdatum**, en **het koppelen van taak‑eind‑aan‑start** relaties.

## Snelle antwoorden
- **Wat is berekeningsmodus?** Het bepaalt of taakdatums automatisch, handmatig of helemaal niet opnieuw worden berekend.  
- **Waarom handmatige berekeningsmodus gebruiken?** Om volledige controle te hebben over wanneer het schema wordt ververst, handig bij bulk‑updates.  
- **Welke modus is standaard?** Automatische berekeningsmodus, die datums direct bijwerkt na wijzigingen.  
- **Kan ik de modus tijdens runtime wijzigen?** Ja—stel simpelweg de `CalculationMode`‑eigenschap in op het `Project`‑object.  
- **Heb ik een licentie nodig?** Een geldige Aspose.Tasks‑licentie is vereist voor productiegebruik.

## Wat is “hoe de berekening in te stellen” in Aspose.Tasks?

Het instellen van de berekeningsmodus is zo eenvoudig als een enum‑waarde toewijzen aan de eigenschap `Project.CalculationMode`. De enum biedt drie opties: `Automatic`, `Manual` en `None`. De juiste modus kiezen hangt af van uw workflow—of u directe updates, batchverwerking of volledige controle wilt.

## Vereisten

1. **Visual Studio** – elke recente versie (2019, 2022 of later).  
2. **Aspose.Tasks for .NET** – download en installeer de bibliotheek van [hier](https://releases.aspose.com/tasks/net/).  
3. **Basiskennis van C#** – u moet vertrouwd zijn met het maken van console‑applicaties en het gebruiken van NuGet‑pakketten.

## Namespaces importeren

Voordat we beginnen met werken met Aspose.Tasks voor .NET, importeren we de benodigde namespaces:

```csharp
using Aspose.Tasks;
using System;
```

## Hoe de berekeningsmodus in te stellen

Hieronder vindt u stapsgewijze voorbeelden voor elke berekeningsmodus. De codeblokken blijven ongewijzigd ten opzichte van de oorspronkelijke tutorial; de omliggende uitleg is uitgebreid voor meer duidelijkheid.

### Toepassen van automatische berekeningsmodus

De automatische modus herberekent datums direct wanneer u taken of koppelingen wijzigt.

#### Stap 1: Maak een nieuw Project‑object

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Stap 2: Stel de projectstartdatum in en voeg taken toe

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Stap 3: Koppel taken (eind‑aan‑start)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Stap 4: Controleer herberekende datums

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Toepassen van handmatige berekeningsmodus

De handmatige modus schakelt automatische updates uit, waardoor u wijzigingen in batches kunt verwerken voordat u een herberekening afdwingt.

#### Stap 1: Maak een nieuw Project‑object

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Stap 2: Stel de projectstartdatum in en voeg taken toe

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Stap 3: Controleer taak‑eigenschappen

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Stap 4: Koppel taken en controleer datums (geen automatische herberekening)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Toepassen van geen berekeningsmodus

De geen‑modus schakelt alle interne berekeningen uit. Gebruik deze wanneer u alleen gegevens wilt lezen of exporteren zonder enige schema‑wijzigingen.

#### Stap 1: Maak een nieuw Project‑object

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Stap 2: Voeg een nieuwe taak toe

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Stap 3: Controleer taak‑eigenschappen (geen automatische ID’s)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| Datums worden niet bijgewerkt na het koppelen van taken | Project staat in **Manual** of **None** modus | Stel `project.CalculationMode = CalculationMode.Automatic` in of roep `project.Calculate()` handmatig aan |
| Taak‑ID’s blijven op 0 | Gebruik van **None** modus voorkomt ID‑generatie | Schakel over naar **Automatic** of **Manual** modus en rekeneer opnieuw |
| Koppelen mislukt met `ArgumentException` | De startdatum van de voorganger is later dan die van de opvolger bij gebruik van **Manual** modus zonder herberekening | Zorg voor correcte startdatums of rekeneer opnieuw na het toevoegen van koppelingen |

## Veelgestelde vragen

**Q1: Kan ik de berekeningsmodus dynamisch tijdens runtime wijzigen?**  
A1: Ja, u kunt de eigenschap `CalculationMode` op elk moment in uw code aanpassen en vervolgens `project.Calculate()` aanroepen als u een onmiddellijke update nodig heeft.

**Q2: Ondersteunt Aspose.Tasks andere projectmanagement‑bestandsformaten naast Microsoft Project?**  
A2: Aspose.Tasks richt zich voornamelijk op Microsoft Project‑formaten, maar ondersteunt ook Primavera P6 XML, Primavera DB en Asta Powerproject XML.

**Q3: Is Aspose.Tasks geschikt voor zowel kleinschalige als enterprise‑projecten?**  
A3: Absoluut. De API schaalt van eenvoudige takenlijsten tot complexe, meerfasige enterprise‑schema's.

**Q4: Kan ik Aspose.Tasks integreren met andere .NET‑bibliotheken en -frameworks?**  
A4: Ja, u kunt Aspose.Tasks combineren met ASP.NET, WPF, Xamarin of elke andere .NET‑technologie om rijke project‑managementoplossingen te bouwen.

**Q5: Is er een community‑forum of ondersteuningskanaal beschikbaar voor Aspose.Tasks‑gebruikers?**  
A5: Ja, u kunt het [Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) bezoeken voor community‑ondersteuning en discussies.

---

**Laatst bijgewerkt:** 2026-03-24  
**Getest met:** Aspose.Tasks 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}