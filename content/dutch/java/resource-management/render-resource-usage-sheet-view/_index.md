---
title: Render resourcegebruik en bladweergave in Aspose.Tasks
linktitle: Render resourcegebruik en bladweergave in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u MS Project Resource Usage- en Sheet-weergaven kunt weergeven in Aspose.Tasks voor Java. Volg onze stapsgewijze handleiding om moeiteloos gedetailleerde PDF-rapporten te genereren.
type: docs
weight: 16
url: /nl/java/resource-management/render-resource-usage-sheet-view/
---
## Invoering
In deze zelfstudie leren we hoe u Aspose.Tasks voor Java kunt gebruiken om MS Project Resource Usage- en Sheet-weergaven weer te geven. Aspose.Tasks is een krachtige Java-bibliotheek waarmee ontwikkelaars met Microsoft Project-bestanden kunnen werken zonder dat Microsoft Project hoeft te worden geïnstalleerd.
## Vereisten
Voordat we beginnen, zorg ervoor dat u de volgende vereisten hebt geïnstalleerd en ingesteld:
1. Java Development Kit (JDK): Zorg ervoor dat Java Development Kit op uw systeem is geïnstalleerd. U kunt de nieuwste versie van JDK downloaden en installeren vanaf de Oracle-website.
2.  Aspose.Tasks voor Java: Download en installeer de Aspose.Tasks voor Java-bibliotheek vanuit de[downloadpagina](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
Eerst moet u de benodigde pakketten in uw Java-project importeren:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Stap 1: Lees het bronproject
```java
// Het pad naar de documentenmap.
String dataDir = "Your Data Directory";
// Lees het bronproject
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
In deze stap specificeren we het pad naar het bronprojectbestand (`ResourceUsageView.mpp` ) en gebruik de`Project` klas om het te lezen.
## Stap 2: Definieer SaveOptions met de vereiste tijdschaalinstellingen
```java
// Definieer de SaveOptions met de vereiste TimeScale-instellingen als Dagen
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Hier definiëren we de`SaveOptions` met de vereiste`TimeScale` instellingen. In dit voorbeeld stellen we de`TimeScale` tot Dagen.
## Stap 3: Stel het presentatieformaat in op ResourceUsage
```java
// Stel de presentatie-indeling in op ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 We hebben het presentatieformaat ingesteld op`ResourceUsage`, wat aangeeft dat we de weergave Resourcegebruik willen weergeven.
## Stap 4: Sla het project op
```java
// Sla het project op
project.save(dataDir + days, options);
```
Ten slotte slaan we het project op met de opgegeven opties. In dit voorbeeld wordt het uitvoerbestand opgeslagen als`result_days.pdf`.
## Stap 5: Geef weergaven weer voor andere tijdschaalinstellingen
Herhaal stap 2 tot en met 4 voor het renderen van weergaven met verschillende TimeScale-instellingen (ThirdsOfMonths en Months).
```java
// Stel de tijdschaalinstellingen in op ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Sla het project op
project.save(thirds, options);
// Stel de Tijdschaal-instellingen in op Maanden
options.setTimescale(Timescale.Months);
// Sla het project op
project.save(dataDir + months, options);
```
 Zorg ervoor dat u de`Timescale` instellingen dienovereenkomstig voor elke weergave.

## Conclusie
In deze zelfstudie hebben we onderzocht hoe u Aspose.Tasks voor Java kunt gebruiken om MS Project Resource Usage- en Sheet-weergaven weer te geven. Door de hierboven beschreven stappen te volgen, kunt u deze weergaven efficiënt in PDF-formaat genereren, waardoor een betere visualisatie en analyse van uw projectgegevens mogelijk wordt.
## Veelgestelde vragen
### Kan Aspose.Tasks naast Resourcegebruik en Blad ook andere weergaven weergeven?
Aspose.Tasks ondersteunt het weergeven van verschillende weergaven, zoals onder meer Gantt-diagram, Taakgebruik en Kalenderweergaven.
### Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project-bestanden?
Ja, Aspose.Tasks ondersteunt een breed scala aan Microsoft Project-bestandsindelingen, waaronder MPP-, MPT- en XML-indelingen.
### Kan ik het uiterlijk van gerenderde weergaven aanpassen met Aspose.Tasks?
Absoluut! Aspose.Tasks biedt uitgebreide opties voor het aanpassen van het uiterlijk en de lay-out van gerenderde weergaven zodat deze aan uw specifieke vereisten voldoen.
### Moet voor Aspose.Tasks Microsoft Project op het systeem worden geïnstalleerd?
Nee, Aspose.Tasks is een zelfstandige bibliotheek en vereist geen installatie van Microsoft Project om te kunnen functioneren.
### Is er technische ondersteuning beschikbaar voor Aspose.Tasks-gebruikers?
 Ja, Aspose.Tasks-gebruikers kunnen gebruik maken van technische ondersteuning via de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15).