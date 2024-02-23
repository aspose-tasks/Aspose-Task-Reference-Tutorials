---
title: MS-projectresourcetoewijzingen afhandelen in Aspose.Tasks
linktitle: Resourcetoewijzingen afhandelen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u MS Project-brontoewijzingen efficiënt kunt afhandelen met Aspose.Tasks voor .NET. Deze uitgebreide versie biedt stapsgewijze begeleiding voor ontwikkelaars.
type: docs
weight: 11
url: /nl/net/resource-risk-analysis/resource-assignments/
---
## Invoering
In deze zelfstudie gaan we in op de manier waarop u efficiënt met Microsoft Project-resourcetoewijzingen kunt omgaan met Aspose.Tasks voor .NET. Aspose.Tasks is een krachtige API waarmee ontwikkelaars Microsoft Project-bestanden programmatisch kunnen manipuleren. Door deze stappen te volgen, leert u hoe u resourcetoewijzingen effectief kunt beheren binnen uw .NET-applicaties.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

## Naamruimten importeren
Ten eerste moet u de benodigde naamruimten importeren om de Aspose.Tasks-functionaliteiten in uw .NET-project te gebruiken. Dit bevat:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
Laten we nu het gegeven voorbeeld opsplitsen in meerdere stappen voor een uitgebreid begrip van hoe u MS Project-resourcetoewijzingen kunt afhandelen met behulp van Aspose.Tasks.
## Stap 1: Stel project- en kalenderinstellingen in
Maak om te beginnen een nieuw Project-exemplaar en stel de kalenderinstellingen van het project in:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## Stap 2: Voeg een taak toe aan het project
Voeg vervolgens een nieuwe taak toe aan de hoofdtaak van het project:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## Stap 3: Resourcetoewijzing creëren en tijdgebonden gegevens genereren
Maak nu een nieuwe resourcetoewijzing voor de taak en genereer tijdgebonden gegevens:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## Stap 4: Splits de taak
Splits de taak op in meerdere delen door begin- en einddatums op te geven:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## Stap 5: Werkcontour instellen
Stel het werkcontourtype voor de opgave in:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## Stap 6: Sla het project op
Sla ten slotte het projectbestand op met de aangebrachte wijzigingen:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Conclusie
Kortom, het afhandelen van Microsoft Project-resourcetoewijzingen met Aspose.Tasks voor .NET is een eenvoudig proces. Door de stappen in deze zelfstudie te volgen, kunt u resourcetoewijzingen binnen uw .NET-toepassingen efficiënt beheren.
## Veelgestelde vragen
### Kan Aspose.Tasks complexe projectstructuren aan?
Ja, Aspose.Tasks biedt uitgebreide functionaliteiten om complexe projectstructuren efficiënt af te handelen.
### Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project?
Ja, Aspose.Tasks ondersteunt verschillende versies van Microsoft Project, waardoor compatibiliteit tussen verschillende omgevingen wordt gegarandeerd.
### Kan ik resourcetoewijzingen aanpassen op basis van specifieke vereisten?
Absoluut, Aspose.Tasks biedt uitgebreide aanpassingsmogelijkheden voor resourcetoewijzingen om aan specifieke projectbehoeften te voldoen.
### Ondersteunt Aspose.Tasks het exporteren van projectgegevens naar andere formaten?
Ja, met Aspose.Tasks kunt u projectgegevens exporteren naar verschillende formaten, zoals onder andere XML, PDF en HTML.
### Is er technische ondersteuning beschikbaar voor Aspose.Tasks-gebruikers?
Ja, Aspose biedt speciale technische ondersteuning via het forum en andere kanalen om gebruikers te helpen met eventuele vragen of problemen.