---
title: Projectgegevens beheren met Aspose.Tasks
linktitle: Werken met projectgegevens in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u Microsoft Project-gegevens kunt manipuleren met Aspose.Tasks in .NET. Creëer eenvoudig taken, voeg resources toe en sla projecten op.
type: docs
weight: 16
url: /nl/net/project-management-integration/project-data/
---
## Invoering
In deze zelfstudie onderzoeken we hoe u met Microsoft Project-gegevens kunt werken met behulp van de Aspose.Tasks-bibliotheek voor .NET. Aspose.Tasks biedt krachtige functies voor het manipuleren van projectbestanden, waaronder het maken van taken, het toevoegen van bronnen, het instellen van eigenschappen en het opslaan van projecten in verschillende formaten.
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
1.  Installatie van Aspose.Tasks-bibliotheek: Download en installeer de Aspose.Tasks-bibliotheek van[hier](https://releases.aspose.com/tasks/net/).
2. Ontwikkelomgeving: Zorg ervoor dat u een .NET-ontwikkelomgeving hebt ingesteld.
3. Basiskennis van C#: Bekendheid met de programmeertaal C# is een voordeel.

## Naamruimten importeren
Voordat u met Aspose.Tasks gaat werken, importeert u de benodigde naamruimten in uw project:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Stap 1: Initialiseer het projectobject
```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Deze regel initialiseert een nieuw exemplaar van de`Project` klasse, die een Microsoft Project-bestand vertegenwoordigt.
## Stap 2: Projecteigenschappen instellen
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Deze regels laten zien hoe u eigenschappen van het project instelt, zoals het werkformaat en de modus voor het maken van taken.
## Stap 3: Taken toevoegen
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Hier wordt een nieuwe taak met de naam "Taak 1" toegevoegd aan de hoofdtaak van het project.
## Stap 4: Taakeigenschappen instellen
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Deze regels stellen de startdatum, duur en einddatum in voor "Taak 1".
## Stap 5: Bronnen toevoegen
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
In dit deel wordt gedemonstreerd hoe u een werkresource aan het project toevoegt.
## Stap 6: Resources toewijzen aan taken
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Deze regels laten zien hoe u de eerder toegevoegde werkresource kunt toewijzen aan "Taak 1" met specifieke start-, werk- en einddatums.
## Stap 7: Project opslaan
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Ten slotte wordt het project opgeslagen in het Microsoft Project XML-bestandsformaat.

## Conclusie
In deze zelfstudie hebben we geleerd hoe u met Microsoft Project-gegevens kunt werken met behulp van de Aspose.Tasks-bibliotheek in .NET. Door de stapsgewijze handleiding te volgen, kunt u projectbestanden manipuleren, taken en bronnen toevoegen, bronnen aan taken toewijzen en projecten in verschillende formaten opslaan.
## Veelgestelde vragen
### Vraag: Kan Aspose.Tasks complexe projectstructuren aan?
A: Ja, Aspose.Tasks biedt uitgebreide ondersteuning voor complexe projectstructuren, waardoor u taken, bronnen en opdrachten efficiënt kunt beheren.
### Vraag: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project?
A: Aspose.Tasks ondersteunt een breed scala aan Microsoft Project-versies, waardoor compatibiliteit tussen verschillende omgevingen wordt gegarandeerd.
### Vraag: Kan ik Aspose.Tasks integreren met andere .NET-bibliotheken?
A: Absoluut, Aspose.Tasks kan naadloos worden geïntegreerd met andere .NET-bibliotheken, waardoor flexibiliteit in uw ontwikkelingsprojecten wordt geboden.
### Vraag: Biedt Aspose.Tasks ondersteuning voor algoritmen voor projectplanning?
A: Ja, Aspose.Tasks bevat geavanceerde planningsalgoritmen waarmee u de projecttijdlijnen en het gebruik van resources kunt optimaliseren.
### Vraag: Is er een communityforum voor Aspose.Tasks-gebruikers?
 A: Ja, u kunt nuttige bronnen vinden en in contact komen met andere Aspose.Tasks-gebruikers op de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15).