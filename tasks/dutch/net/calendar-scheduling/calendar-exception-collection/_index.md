---
title: Verzameling van agenda-uitzonderingen in Aspose.Tasks
linktitle: Verzameling van agenda-uitzonderingen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u agenda-uitzonderingen in uw .NET-projecten efficiënt kunt afhandelen met behulp van Aspose.Tasks, zodat u verzekerd bent van nauwkeurige planning en resourcebeheer.
weight: 13
url: /nl/net/calendar-scheduling/calendar-exception-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verzameling van agenda-uitzonderingen in Aspose.Tasks

## Invoering

Bij projectmanagement is nauwkeurige planning essentieel voor succes. Real-world scenario's vereisen echter vaak afwijkingen van de standaardschema's vanwege vakanties, speciale evenementen of andere factoren. Aspose.Tasks voor .NET biedt een robuuste oplossing voor het beheren van dergelijke uitzonderingen via de functie Agenda-uitzonderingen verzamelen. Deze tutorial begeleidt u stap voor stap bij het gebruik van deze functionaliteit.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1.  Aspose.Tasks voor .NET: Zorg ervoor dat de bibliotheek is geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/tasks/net/).
2. Basiskennis van C#: Bekendheid met de programmeertaal C# zal nuttig zijn bij het begrijpen van de voorbeelden.
3. Ontwikkelomgeving: Stel de ontwikkelomgeving van uw voorkeur in, zoals Visual Studio of JetBrains Rider.

## Naamruimten importeren

Voordat u met Aspose.Tasks voor .NET gaat werken, moet u de vereiste naamruimten in uw project importeren. Met deze stap krijgt u toegang tot de klassen en methoden die nodig zijn voor het beheren van agenda-uitzonderingen.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Laten we het gegeven voorbeeld nu in meerdere stappen opsplitsen:

## Stap 1: Project laden en kalender ophalen

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

In deze stap laden we een projectbestand en halen we de gewenste kalender op via de UID.

## Stap 2: Wis bestaande uitzonderingen en stel de standaardkalender in

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Met deze stap worden eventuele bestaande uitzonderingen uit de agenda gewist en ingesteld op een standaardconfiguratie.

## Stap 3: Werktijduitzondering definiëren en toevoegen

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

Deze stap definieert een uitzondering voor de werktijd met specifieke begin- en einddatums, samen met werktijden binnen die datums, en voegt deze toe aan de kalender.

## Stap 4: Uitzonderingen voor niet-werktijd definiëren en toevoegen

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Voeg indien nodig meer uitzonderingen toe

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

Met deze stap worden uitzonderingen op niet-werktijden, zoals feestdagen, gedefinieerd en aan de kalender toegevoegd.

## Stap 5: Agenda-uitzonderingen weergeven

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

In deze stap worden de toegevoegde agenda-uitzonderingen weergegeven, samen met hun details.

## Stap 6: verwijder alle uitzonderingen

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Ten slotte verwijdert deze stap alle uitzonderingen uit de kalender.

## Conclusie

Het beheren van kalenderuitzonderingen is cruciaal voor een nauwkeurige projectplanning. Aspose.Tasks voor .NET vereenvoudigt deze taak door een uitgebreide reeks functies te bieden, waaronder de Calendar Exception Collection. Door de stappen in deze zelfstudie te volgen, kunt u efficiënt omgaan met verschillende planningsscenario's binnen uw projecten.

## Veelgestelde vragen

### V1: Kan ik meerdere uitzonderingen toevoegen aan één kalender?

 A1: Ja, u kunt meerdere uitzonderingen aan een kalender toevoegen met behulp van de`AddRange` methode.

### Vraag 2: Hoe ga ik om met terugkerende uitzonderingen, zoals wekelijkse vakanties?

A2: U kunt terugkerende uitzonderingen programmatisch berekenen en deze met behulp van aangepaste logica aan de agenda toevoegen.

### Vraag 3: Is het mogelijk om agenda-uitzonderingen uit externe bronnen te importeren?

A3: Ja, u kunt kalenderuitzonderingen uit externe bronnen zoals databases of CSV-bestanden lezen en deze in uw project integreren.

### Vraag 4: Wat gebeurt er als er overlappende uitzonderingen in de kalender voorkomen?

A4: Met Aspose.Tasks voor .NET kunt u overlappende uitzonderingen afhandelen door prioriteiten te definiëren of conflicten op te lossen op basis van uw projectvereisten.

### Vraag 5: Kan ik de werktijden voor elke dag aanpassen, behoudens uitzonderingen?

A5: Ja, u kunt aangepaste werktijden opgeven voor individuele dagen binnen een uitzondering om tegemoet te komen aan specifieke planningsbehoeften.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
