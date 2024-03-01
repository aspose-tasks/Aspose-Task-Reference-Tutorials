---
title: Lees valuta-eigenschappen in Aspose.Tasks-projecten
linktitle: Lees valuta-eigenschappen in Aspose.Tasks-projecten
second_title: Aspose.Tasks Java-API
description: Leer hoe u valuta-informatie uit MS Project-bestanden kunt extraheren met Aspose.Tasks voor Java. Stap-voor-stap handleiding meegeleverd.
type: docs
weight: 10
url: /nl/java/currency-properties/read-properties/
---
## Invoering
In deze zelfstudie leren we hoe u Aspose.Tasks voor Java kunt gebruiken om valuta-eigenschappen uit Microsoft Project-bestanden te lezen. Aspose.Tasks is een krachtige Java API waarmee ontwikkelaars Microsoft Project-documenten kunnen manipuleren zonder dat Microsoft Project hoeft te worden geïnstalleerd. Door de onderstaande stappen te volgen, kunt u moeiteloos valutagerelateerde informatie extraheren.
## Vereisten
Voordat u doorgaat met deze zelfstudie, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor Java JAR: Download de Aspose.Tasks voor Java-bibliotheek van[hier](https://releases.aspose.com/tasks/java/) en neem het op in uw Java-project.
## Pakketten importeren
Begin met het importeren van de benodigde pakketten in uw Java-klasse:
```java
import com.aspose.tasks.*;
```
## Stap 1: Stel uw projectdirectory in
Stel eerst uw projectmap in waar uw Microsoft Project-bestand zich bevindt. U kunt dit mappad als volgt definiëren:
```java
String dataDir = "Your Data Directory";
```
 Vervangen`"Your Data Directory"` met het daadwerkelijke pad naar uw projectmap.
## Stap 2: Maak een Project Reader-instantie
 Instantieer een`Project` object door het pad naar uw Microsoft Project-bestand op te geven:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Zorg ervoor dat u deze vervangt`"project.mpp"` met de naam van uw MS Project-bestand.
## Stap 3: Geef valuta-eigenschappen weer
Valuta-eigenschappen uit het projectbestand ophalen en weergeven:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Dit codesegment haalt informatie zoals valutacode, cijfers, symbool en symboolpositie op uit het MS Project-bestand en drukt deze af naar de console.
## Stap 4: Voltooiing van het proces
Druk ten slotte een bericht af dat de succesvolle voltooiing van het proces aangeeft:
```java
System.out.println("Process completed Successfully");
```
## Conclusie
In deze zelfstudie hebben we onderzocht hoe u valuta-eigenschappen uit Microsoft Project-bestanden kunt lezen met Aspose.Tasks voor Java. Door de beschreven stappen te volgen, kunt u moeiteloos valutagerelateerde informatie programmatisch uit uw projectbestanden extraheren, waardoor een naadloze integratie in uw Java-applicaties mogelijk wordt.
## Veelgestelde vragen
### Vraag: Is Aspose.Tasks compatibel met alle versies van Microsoft Project?
A: Aspose.Tasks ondersteunt verschillende versies van Microsoft Project, inclusief MPP-bestanden gegenereerd door MS Project 2003-2021.
### Vraag: Kan ik valuta-eigenschappen wijzigen met Aspose.Tasks?
A: Ja, met Aspose.Tasks kunt u valuta-eigenschappen in MS Project-bestanden programmatisch lezen en wijzigen.
### Vraag: Is Aspose.Tasks geschikt voor commercieel gebruik?
 A: Ja, Aspose.Tasks is een commerciële bibliotheek ontworpen voor professioneel gebruik. U kunt een licentie kopen[hier](https://purchase.aspose.com/buy).
### Vraag: Biedt Aspose.Tasks een gratis proefperiode?
 A: Ja, u kunt profiteren van een gratis proefperiode van Aspose.Tasks vanaf[hier](https://releases.aspose.com/).
### Vraag: Waar kan ik hulp of ondersteuning zoeken voor Aspose.Tasks?
 A: U kunt het Aspose.Tasks-forum bezoeken[hier](https://forum.aspose.com/c/tasks/15) voor eventuele hulp of vragen.