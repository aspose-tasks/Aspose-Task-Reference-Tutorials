---
date: 2026-04-13
description: Leer hoe u werktijden instelt en kalendercollecties beheert in Aspose.Tasks
  voor .NET. Importeer kalenders uit Microsoft Project, verwijder een kalenderproject
  en haal eenvoudig een kalender op basis van de naam.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Kalendercollectie beheren in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Werkuren instellen in Aspose.Tasks‑kalendercollectie
url: /nl/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Instellen van werktijden in Aspose.Tasks Kalenderverzameling

In deze tutorial leer je hoe je **werktijden instelt** en kalenderverzamelingen beheert met Aspose.Tasks voor .NET. Kalenders definiëren werkdagen, feestdagen en uitzonderingen, dus door ze onder de knie te krijgen kun je projectplanningen nauwkeurig beheersen. We laten ook zien hoe je kalenders uit Microsoft Project importeert, een kalender uit een project verwijdert en een kalender op naam opvraagt.

## Snelle antwoorden
- **Wat is de primaire klasse voor kalenders?** `Project.Calendars` collection.
- **Hoe stel ik werktijden in?** Maak of wijzig een `Calendar` object en definieer zijn `WorkingTime`.
- **Kan ik kalenders importeren vanuit Microsoft Project?** Ja – laad een MPP‑bestand en krijg toegang tot de kalenders.
- **Hoe verwijder ik een kalender uit een project?** Gebruik `Project.Calendars.Remove(calendar)`.
- **Hoe haal ik een kalender op op naam?** Roep `Project.Calendars.GetByName("YourCalendar")` aan.

## Vereisten

Voordat we beginnen, zorg ervoor dat je het volgende hebt:

1. Visual Studio: Installeer Visual Studio of een andere compatibele IDE voor .NET‑ontwikkeling.  
2. Aspose.Tasks voor .NET: Download en installeer Aspose.Tasks voor .NET van [here](https://releases.aspose.com/tasks/net/).  
3. Basiskennis van C#: Vertrouwdheid met de programmeertaal C# is nuttig.

## Namespaces importeren

Eerst importeren we de benodigde namespaces om met Aspose.Tasks te werken:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Een nieuwe kalender maken

### Stap 1: Initialiseer een nieuw `Project` object.
```csharp
var project = new Project();
```

### Stap 2: Voeg kalenders toe aan de kalenderverzameling van het project.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Stap 3: Loop door de kalenders en toon hun namen.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Hoe werktijden instellen voor een kalender?

Om **werktijden in te stellen**, wijzig je de `WorkingTime` collectie van een `Calendar`.  
Bijvoorbeeld, je kunt een standaard werkdag van 9 uur tot 17 uur definiëren of aangepaste uitzonderingen toevoegen.  
De code hiervoor is identiek aan de voorbeelden die later worden getoond wanneer we een standaardkalender maken.

## Een kalender vervangen door een nieuwe kalender

### Stap 1: Laad een bestaand project.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Stap 2: Verwijder de bestaande kalender (indien aanwezig).  
Dit demonstreert het **verwijderen van een kalender uit een project** scenario.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Stap 3: Voeg een nieuwe kalender toe.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Een kalender ophalen op naam of ID

### Stap 1: Laad het project.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Stap 2: Haal kalenders op op naam of UID.  
Dit illustreert de **ophalen van een kalender op naam** operatie.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Stap 3: Toon kalenderdetails.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Door kalenders itereren

### Stap 1: Laad het project.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Stap 2: Haal het aantal kalenders op.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Stap 3: Loop door de kalenderverzameling en toon namen.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Een standaardkalender maken

### Stap 1: Initialiseer een nieuw project.
```csharp
var project = new Project();
```

### Stap 2: Definieer een nieuwe kalender en maak deze standaard.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Stap 3: Sla het project op.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Veelvoorkomende problemen en oplossingen

- **Kalender niet gevonden bij gebruik van `GetByName`** – Zorg ervoor dat de exacte naam overeenkomt met de hoofdlettergevoeligheid die werd gebruikt toen de kalender werd toegevoegd.  
- **Werktijden niet toegepast** – Nadat je `WorkingTime` hebt ingesteld, vergeet niet het project op te slaan; anders blijven de wijzigingen alleen in het geheugen.  
- **Importeren van kalenders uit een MPP‑bestand mislukt** – Controleer of het bronbestand een geldig Microsoft Project‑bestand is en of je leesrechten hebt.

## Veelgestelde vragen

### V1: Kan ik aangepaste werkdagen maken in Aspose.Tasks?

A1: Ja, je kunt aangepaste werkdagen maken door uitzonderingen toe te voegen aan kalenders.

### V2: Is het mogelijk om kalenders te importeren uit Microsoft Project‑bestanden?

A2: Absoluut, Aspose.Tasks ondersteunt het importeren van kalenders uit Microsoft Project‑bestanden.

### V3: Hoe kan ik een specifieke kalender uit een project verwijderen?

A3: Je kunt een kalender verwijderen door deze uit de collectie te halen en vervolgens de `Remove`‑methode aan te roepen.

### V4: Ondersteunt Aspose.Tasks het exporteren van kalenders naar verschillende formaten?

A4: Ja, Aspose.Tasks maakt het mogelijk om kalenders te exporteren naar verschillende formaten zoals XML, MPP, enz.

### V5: Kan ik werktijden aanpassen voor specifieke dagen in een kalender?

A5: Zeker, je kunt werktijden definiëren voor individuele dagen door uitzonderingen in de kalender te gebruiken.

## Veelgestelde vragen

**V: Wat is de beste manier om een 24‑uur shift‑kalender in te stellen?**  
A: Maak een nieuwe kalender, verwijder bestaande `WorkingTime`‑items, en voeg een enkele `WorkingTime`‑reeks toe van 00:00 tot 24:00 voor elke werkdag.

**V: Kan ik een kalender van het ene project naar het andere kopiëren?**  
A: Ja—exporteer de kalender naar XML met `project.Save` en importeer deze vervolgens in een ander project met `new Project(xmlPath)`.

**V: Hoe importeer ik programmatically kalenders uit Microsoft Project?**  
A: Laad het MPP‑bestand met `new Project("source.mpp")`; de kalenders zijn beschikbaar via `project.Calendars`.

**V: Is er een limiet aan het aantal kalenders in een project?**  
A: Praktisch gezien niet; de collectie kan zoveel kalenders bevatten als het geheugen toelaat, maar houd de lijst beheersbaar voor de prestaties.

**V: Werken wijzigingen aan een kalender automatisch door naar taken die deze gebruiken?**  
A: Ja—taken die gekoppeld zijn aan een kalender weerspiegelen de bijgewerkte werktijden nadat je het project hebt opgeslagen.

---

**Last Updated:** 2026-04-13  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}