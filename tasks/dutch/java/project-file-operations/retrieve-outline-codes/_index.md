---
date: 2026-03-27
description: Leer hoe u outline‑codes van MS Project programmatically kunt ophalen
  met Aspose.Tasks voor Java. Verbeter uw projectmanagementvaardigheden.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ophalen van MS Project Outline-codes in Aspose.Tasks
url: /nl/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ophalen van MS Project Outline Codes in Aspose.Tasks

## Inleiding
In deze tutorial ontdek je **hoe je ms project outline codes kunt ophalen** met Aspose.Tasks voor Java. Outline codes in MS Project bieden een krachtige manier om taken, resources en toewijzingen te categoriseren, en ze programmatisch benaderen stelt je in staat aangepaste rapportage, automatisering of integratieoplossingen te bouwen. We lopen een volledig, stap‑voor‑stap voorbeeld door dat je kunt kopiëren naar je eigen project.

## Snelle antwoorden
- **Wat doet de code?** Hij laadt een Project‑bestand en drukt elke outline‑code‑definitie, de maskers en de waarden af.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (een recente versie).  
- **Heb ik een licentie nodig?** Een proefversie werkt voor ontwikkeling; een volledige licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger.  
- **Kan ik de codes aanpassen nadat ik ze heb opgehaald?** Ja – dezelfde API laat je outline‑codes toevoegen, bewerken of verwijderen.

## Wat zijn ms project outline codes?
Outline codes zijn aangepaste velden die projectmanagers in staat stellen taken te groeperen en te filteren buiten de standaard hiërarchie. Ze kunnen eenvoudige numerieke waarden, strings of zelfs enterprise‑brede aangepaste codes zijn die op organisatieniveau zijn gedefinieerd. Door deze codes te lezen kun je dashboards aansturen, gegevens exporteren of automatisch naamgevingsconventies afdwingen.

## Waarom ms project outline codes ophalen met Aspose.Tasks?
- **Automatisering:** Genereer rapporten of activeer workflows zonder handmatige export.  
- **Integratie:** Synchroniseer outline codes met ERP-, PPM- of BI‑tools.  
- **Aanpassing:** Pas bedrijfsregels toe op basis van code‑waarden (bijv. kostenallocatie).  
- **Cross‑platform:** Werkt op Windows, Linux en macOS, onafhankelijk van de Microsoft Project‑UI.

## Hoe MPP‑bestanden lezen voor outline codes?
Het lezen van een MPP‑ (Microsoft Project) bestand is de eerste stap naar het extraheren van outline codes. Aspose.Tasks abstraheert het bestandsformaat, zodat je de binaire structuur niet zelf hoeft te parseren. De `Project`‑klasse doet het zware werk, zodat jij je kunt concentreren op de gegevens die je echt nodig hebt.

## Aangepaste velden in MS Project
Outline codes zijn een type **aangepaste velden** in MS Project. Terwijl standaardvelden data zoals datums, duur en resources bevatten, laten aangepaste velden je organisatiespecifieke informatie opslaan. Toegang via Aspose.Tasks biedt dezelfde flexibiliteit programmatically.

## Voorvereisten
Voordat we beginnen, zorg dat je de volgende voorvereisten hebt ingesteld:

### 1. Java‑ontwikkelomgeving
Zorg ervoor dat je Java Development Kit (JDK) op je systeem geïnstalleerd hebt. Je kunt de JDK downloaden en installeren vanaf de Oracle‑website.

### 2. Aspose.Tasks‑bibliotheek
Download en voeg de Aspose.Tasks‑bibliotheek toe aan je Java‑project. Je kunt de bibliotheek downloaden van de [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
Eerst importeer je de benodigde pakketten van Aspose.Tasks in je Java‑code:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Laten we nu de meegeleverde voorbeeldcode opsplitsen in meerdere stappen:

## Stap 1: Het project laden
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
In deze stap laden we het Microsoft Project‑bestand in een `Project`‑object met behulp van de opgegeven bestandsnaam.

## Stap 2: Outline codes ophalen
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
We itereren door elke outline‑code‑definitie in het project.

## Stap 3: Toegang tot outline‑code‑eigenschappen
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
We halen verschillende eigenschappen van de outline‑code‑definitie op en drukken ze af, zoals Alias, Field ID en Field Name.

## Stap 4: Controleren op enterprise‑custom code
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
We controleren of de outline‑code een enterprise‑custom code is en geven het resultaat overeenkomstig weer.

## Stap 5: Outline‑code‑maskers weergeven
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
We itereren door elk masker dat aan de outline‑code is gekoppeld en drukken het niveau en de maskerwaarde af.

## Stap 6: Outline‑code‑waarden weergeven
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
We itereren door elke outline‑code‑waarde en drukken de beschrijving, value ID, waarde en type af.

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Geen output** | Pad naar projectbestand onjuist | Controleer of `projectName` naar een geldig `.mpp`‑bestand wijst. |
| **Null‑waarden** | Outline code niet gedefinieerd in het bestand | Zorg ervoor dat het Project‑bestand daadwerkelijk outline codes bevat (controleer in de MS Project‑UI). |
| **LicenseException** | Proefversie zonder juiste activering | Pas een tijdelijke of volledige licentie toe via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks voor Java gebruiken om outline codes in een Project‑bestand te wijzigen?**  
A: Ja, Aspose.Tasks voor Java biedt API’s om outline codes programmatisch te wijzigen. Je kunt definities toevoegen, bewerken of verwijderen met hetzelfde `Project`‑object.

**Q: Is er een proefversie beschikbaar voor Aspose.Tasks voor Java?**  
A: Ja, je kunt een gratis proefversie van Aspose.Tasks voor Java downloaden via de [Aspose.Tasks website](https://releases.aspose.com/).

**Q: Hoe kan ik technische ondersteuning krijgen voor Aspose.Tasks voor Java?**  
A: Je kunt technische ondersteuning krijgen door het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) te bezoeken en je vragen daar te plaatsen.

**Q: Kan ik een tijdelijke licentie aanschaffen voor Aspose.Tasks voor Java?**  
A: Ja, je kunt een tijdelijke licentie voor Aspose.Tasks voor Java aanschaffen via de [aankooppagina](https://purchase.aspose.com/temporary-license/).

**Q: Waar vind ik de volledige documentatie voor Aspose.Tasks voor Java?**  
A: Je kunt de [documentatie](https://reference.aspose.com/tasks/java/) raadplegen voor gedetailleerde informatie over het gebruik van Aspose.Tasks voor Java.

## Conclusie
In deze tutorial hebben we geleerd hoe we **ms project outline codes** kunnen ophalen met Aspose.Tasks voor Java. Door de gegeven stappen te volgen kun je effectief toegang krijgen tot en manipuleren van outline codes in je Java‑applicaties, waardoor geavanceerde projectmanagementmogelijkheden zoals aangepaste rapportage, automatisering en integratie met andere enterprise‑systemen mogelijk worden.

---

**Laatst bijgewerkt:** 2026-03-27  
**Getest met:** Aspose.Tasks voor Java (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}