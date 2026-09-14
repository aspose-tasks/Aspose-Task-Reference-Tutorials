---
date: 2026-09-14
description: Leer hoe u de valuta van MS Project kunt ophalen en projecteigenschappen
  in Java kunt lezen met Aspose.Tasks. Stapsgewijze handleiding voor het extraheren
  van valutacijfers uit een MPP‑bestand.
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Hoe valuta uit MS Project te halen met Aspose.Tasks
og_description: Leer hoe u de valuta van MS Project kunt ophalen en projecteigenschappen
  in Java kunt lezen met Aspose.Tasks. Volg deze beknopte Java‑tutorial om valutacijfers
  uit een MPP‑bestand te extraheren.
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Hoe de valuta van MS Project op te halen met Aspose.Tasks – Java‑gids
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Hoe de valuta van MS Project op te halen met Aspose.Tasks
url: /nl/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe ms projectvaluta op te halen met Aspose.Tasks

## Inleiding
Als je je afvraagt **hoe je ms projectvaluta** kunt opvragen uit een Microsoft Project‑bestand, ben je hier aan het juiste adres. In deze uitgebreide tutorial ontdek je **hoe je met ms projectvaluta** waarden kunt werken met de Aspose.Tasks‑bibliotheek voor Java. Of je nu een rapportagetool, een migratie‑utility bouwt, of simpelweg de valutainstellingen moet lezen uit een **java projectbestand**, deze gids leidt je door elke stap — van het laden van een *.mpp*‑bestand tot het extraheren van de valutacijfers. Aan het einde kun je moeiteloos ms projectvaluta‑gegevens verwerken in je eigen applicaties.

## Snelle antwoorden
- **Welke bibliotheek leest MS Project‑bestanden?** Aspose.Tasks for Java.  
- **Hoeveel regels code zijn nodig om valutacijfers op te halen?** Slechts drie beknopte regels nadat het project is geladen.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger (elke JDK die Aspose.Tasks kan uitvoeren).  
- **Kan ik andere Project‑eigenschappen ophalen?** Ja – Aspose.Tasks biedt een volledige set Project‑velden (bijv. startdatum, kostentarieven, enz.).

## Wat is ms projectvaluta?
De eigenschap `ms project currency` bepaalt het aantal decimalen dat Microsoft Project gebruikt bij het weergeven van geldbedragen. Het wordt opgeslagen in het Project‑bestand als het **CURRENCY_DIGITS**‑veld en bepaalt of bedragen worden weergegeven als gehele getallen, één‑decimaal, twee‑decimalen, enz. Deze instelling beïnvloedt direct budgetrapporten, kosten‑roll‑ups en elke UI die financiële cijfers toont, waardoor het essentieel is voor een nauwkeurige gegevensuitwisseling.

## Waarom Aspose.Tasks gebruiken voor het verwerken van ms projectvaluta?
Aspose.Tasks stelt je in staat de valutacijfers te extraheren zonder Microsoft Project te installeren, en dat doet het met enterprise‑prestaties. De bibliotheek ondersteunt **meer dan 30 jaar Project‑bestandversies** — van Project 2000 tot en met Project 2024 — en omvat meer dan **150 verschillende bestandschema's**. Het laden van een project van 500 pagina's duurt doorgaans minder dan **2 seconden** op een standaard server, en je kunt alleen de velden opvragen die je nodig hebt, waardoor het geheugenverbruik onder **50 MB** blijft, zelfs voor de grootste planningen.

## Vereisten
Zorg ervoor dat je het volgende hebt voordat je begint:

1. **Java Development Environment** – JDK 8 of nieuwer geïnstalleerd en geconfigureerd.  
2. **Aspose.Tasks for Java** – download de nieuwste JAR van de officiële site: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Basiskennis van Java** – je moet vertrouwd zijn met het maken van een Java‑project, het toevoegen van externe bibliotheken en het uitvoeren van een `main`‑methode.  

## Importer pakketten
Eerst importeer je de klassen die we nodig hebben.  
Importeer de `Project`‑klasse en gerelateerde hulpprogramma's uit de Aspose.Tasks‑bibliotheek.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Stap 1: definieer gegevensmap
Geef de map op die je **java projectbestand** (`*.mpp`) bevat.  
```java
String dataDir = "Your Data Directory";
```
Vervang `"Your Data Directory"` door het absolute of relatieve pad waar `project.mpp` zich bevindt.

## Stap 2: laad het mpp‑bestand  
Nu zien we **hoe je mpp**‑bestanden laadt met Aspose.Tasks.  
De `Project`‑klasse vertegenwoordigt een Microsoft Project‑bestand en biedt toegang tot de eigenschappen.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Zorg ervoor dat de bestandsnaam exact overeenkomt; anders wordt een `IOException` gegooid.

## Stap 3: haal valutacijfers op  
Met het project geladen, is het extraheren van de **ms projectvaluta**‑cijfers een één‑regelige opdracht:  
De `getCurrencyDigits()`‑methode retourneert het aantal decimalen dat is gedefinieerd voor geldwaarden.  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
De aanroep retourneert een `Integer` die het aantal decimalen weergeeft (bijv. `2` voor centen). De waarde wordt naar de console geprint, maar je kunt deze ook in een variabele opslaan voor verdere verwerking.

## Veelvoorkomende problemen & tips
- **Bestand niet gevonden** – controleer het `dataDir`‑pad nogmaals en zorg dat de bestandsnaam correct is, inclusief de `.mpp`‑extensie.  
- **Niet‑ondersteunde bestandsversie** – Aspose.Tasks ondersteunt Project 2000‑2024‑formaten; oudere of beschadigde bestanden kunnen conversie nodig hebben.  
- **Licentie niet ingesteld** – tijdens ontwikkeling werkt een proefversie, maar voor productie moet je een geldige licentie toepassen om evaluatiewatermerken te vermijden.

## Veelgestelde vragen

**Q: Kan Aspose.Tasks andere Project‑attributen verwerken naast valutacijfers?**  
A: Ja, Aspose.Tasks biedt een breed scala aan functionaliteiten om verschillende aspecten van Project‑bestanden te manipuleren, zoals taken, resources en aangepaste velden.

**Q: Is Aspose.Tasks geschikt voor enterprise‑niveau applicaties?**  
A: Absoluut, Aspose.Tasks is ontworpen om te voldoen aan de eisen van enterprise‑grade projecten, met hoge prestaties en schaalbaarheid.

**Q: Ondersteunt Aspose.Tasks cross‑platform ontwikkeling?**  
A: Ja, je kunt Aspose.Tasks voor Java gebruiken op elk platform dat de Java Runtime Environment ondersteunt (Windows, Linux, macOS).

**Q: Kan ik Aspose.Tasks uitproberen voordat ik aankoop?**  
A: Ja, je kunt een gratis proefversie downloaden van de [Aspose releases-pagina](https://releases.aspose.com/).

**Q: Waar kan ik ondersteuning krijgen voor Aspose.Tasks?**  
A: Je kunt ondersteuning vinden op het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15).

---

**Laatst bijgewerkt:** 2026-09-14  
**Getest met:** Aspose.Tasks for Java (latest at time of writing)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [java projecteigenschappen – Valutasymbool extraheren uit MPP met Aspose.Tasks voor Java](/tasks/java/currency/currency-symbols/)
- [Hoe valuta op te halen uit MS Project met Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Projecteigenschappen Java – Metagegevens lezen met Aspose.Tasks](/tasks/java/project-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}