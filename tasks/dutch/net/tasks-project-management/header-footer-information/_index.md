---
title: Extraheer kop- en voettekstinformatie met Aspose.Tasks
linktitle: Kop- en voettekstinformatie in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer kop- en voettekstinformatie uit MS Project-bestanden extraheren met Aspose.Tasks voor .NET. Eenvoudige, efficiënte en ontwikkelaarsvriendelijke oplossing.
weight: 29
url: /nl/net/tasks-project-management/header-footer-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraheer kop- en voettekstinformatie met Aspose.Tasks

## Invoering
Aspose.Tasks voor .NET is een krachtige bibliotheek waarmee ontwikkelaars Microsoft Project-bestanden gemakkelijk kunnen manipuleren. In deze zelfstudie leren we hoe u kop- en voettekstinformatie uit MS Project-bestanden kunt ophalen met Aspose.Tasks.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. Visual Studio: Installeer Visual Studio op uw systeem.
2.  Aspose.Tasks voor .NET: Download en installeer de Aspose.Tasks voor .NET-bibliotheek van[hier](https://releases.aspose.com/tasks/net/).
3. Basiskennis van C#: Bekendheid met de programmeertaal C#.

## Naamruimten importeren
Eerst moet u de benodigde naamruimten in uw C#-project importeren. Hierdoor krijgt u toegang tot de klassen en methoden die worden aangeboden door de Aspose.Tasks-bibliotheek.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Stap 1: Initialiseer het projectobject
 Om te beginnen moet u een initialiseren`Project` object door een bestaand MS Project-bestand te laden.
```csharp
// Het pad naar de documentenmap.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Stap 2: Kop- en voettekstinformatie ophalen
 Nadat u het projectbestand heeft geladen, kunt u de kop- en voettekstinformatie ophalen met behulp van de`PageInfo` eigendom.
```csharp
var info = project.DefaultView.PageInfo;
// Kopinformatie
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Voettekstinformatie
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Door deze eenvoudige stappen te volgen, kunt u eenvoudig kop- en voettekstinformatie ophalen uit MS Project-bestanden met behulp van Aspose.Tasks voor .NET.

## Conclusie
In deze zelfstudie hebben we onderzocht hoe u kop- en voettekstinformatie uit MS Project-bestanden kunt extraheren met Aspose.Tasks voor .NET. Deze krachtige bibliotheek vereenvoudigt het werken met Project-bestanden in C#-applicaties en biedt ontwikkelaars robuuste tools voor manipulatie.
### Veelgestelde vragen
### Kan ik de kop- en voettekstinformatie wijzigen met Aspose.Tasks?
Ja, u kunt de kop- en voettekstinformatie programmatisch wijzigen met Aspose.Tasks voor .NET.
### Ondersteunt Aspose.Tasks naast MS Project ook andere projectbestandsformaten?
Ja, Aspose.Tasks ondersteunt verschillende projectbestandsindelingen, waaronder MPP, XML en MPX.
### Is er een gratis proefversie beschikbaar voor Aspose.Tasks?
 Ja, u kunt een gratis proefversie van Aspose.Tasks downloaden van[hier](https://releases.aspose.com/).
### Waar kan ik documentatie voor Aspose.Tasks vinden?
 U kunt de documentatie voor Aspose.Tasks vinden[hier](https://reference.aspose.com/tasks/net/).
### Hoe kan ik ondersteuning krijgen voor Aspose.Tasks?
 U kunt ondersteuning krijgen voor Aspose.Tasks door naar de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
