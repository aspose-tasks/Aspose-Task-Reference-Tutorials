---
date: 2026-03-14
description: Leer hoe je het databaseschema voor een Microsoft Project-database specificeert
  met Aspose.Tasks, en hoe je projectgegevens importeert in .NET-toepassingen.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Specificeer databaseschema voor Project DB met Aspose.Tasks
url: /nl/net/advanced-concepts/msp-database-settings/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Instellingen voor Microsoft Project-database in Aspose.Tasks

## Introductie

Als je werkt met Microsoft Project-databases in je .NET-toepassingen met behulp van Aspose.Tasks, moet je **database‑schema specificeren** en de benodigde instellingen configureren om **project**‑gegevens naadloos te importeren. Deze tutorial leidt je stap voor stap door het proces en laat je zien **hoe je verbindingsdetails configureert**, **een .NET‑verbindingstring maakt**, en uiteindelijk **het project opslaat als MPP**.

## Snelle antwoorden
- **Wat is het primaire doel?** Om het database‑schema te specificeren en een Project‑database te importeren in een .NET‑app.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor .NET.  
- **Hoe maak ik verbinding met Project Server?** Door een juiste SQL‑verbindingstring te bouwen en `MspDbSettings` te gebruiken.  
- **Welk bestandsformaat wordt geproduceerd?** Een MPP‑bestand opgeslagen met `SaveFileFormat.Mpp`.  
- **Kan ik de schemanaam wijzigen?** Ja, stel de `Schema`‑eigenschap in op `MspDbSettings`.

## Hoe database‑schema specificeren voor Project‑DB

Begrijpen waarom je mogelijk **database‑schema moet specificeren** is essentieel. In veel bedrijfsomgevingen bevindt de Project Server-database zich onder een aangepast schema (bijv. `dbo`, `psdata`). Door het schema expliciet in te stellen, zorg je ervoor dat Aspose.Tasks de juiste tabellen raadpleegt, waardoor runtime‑fouten worden voorkomen en een nauwkeurige gegevensimport wordt gegarandeerd.

## Voorvereisten

Zorg ervoor dat je het volgende hebt voordat je begint:

1. Aspose.Tasks voor .NET: Download en installeer de Aspose.Tasks‑bibliotheek van [hier](https://releases.aspose.com/tasks/net/).  
2. Toegang tot een Microsoft Project-database: Je moet toegang hebben tot een Microsoft Project-database om gegevens vanuit te importeren.  

## Namespaces importeren

Zorg er eerst voor dat je de benodigde namespaces in je project importeert:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Stap 1: Verbindingstring maken

Stel de verbindingstring samen voor je Microsoft Project-database. Hier **maak je een .NET‑verbindingstring** en definieer je ook hoe je **verbinding maakt met Project Server**.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **Pro tip:** Controleer de waarden van `DataSource` en `InitialCatalog` nogmaals; ze moeten overeenkomen met het adres van je server en de naam van de gepubliceerde database.

## Stap 2: MspDbSettings configureren

Maak een instantie van `MspDbSettings`, geef de verbindingstring door, en **specificeer het database‑schema** door de `Schema`‑eigenschap in te stellen. Dit vertelt Aspose.Tasks welk schema moet worden geraadpleegd.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Hier geven we ook de project‑GUID op die het specifieke project identificeert dat je wilt laden.

## Stap 3: Projectgegevens laden

Instantieer een `Project`‑object met behulp van de geconfigureerde instellingen. Deze stap laat effectief zien **hoe je project**‑gegevens uit de database in een .NET‑object importeert.

```csharp
var project = new Project(settings);
```

## Stap 4: Projectgegevens opslaan

Sla tenslotte het geladen project op als een MPP‑bestand op schijf. Dit toont **project opslaan als MPP** met behulp van de Aspose.Tasks‑API.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Na het uitvoeren van de code vind je het bestand `ImportProjectDataFromDatabase_out.mpp` in de output‑directory, klaar om te worden geopend in Microsoft Project.

## Conclusie

In deze tutorial heb je geleerd hoe je **database‑schema specificeert** voor een Microsoft Project-database, **de verbinding configureert**, **project**‑gegevens importeert, en **het project opslaat als MPP** met Aspose.Tasks voor .NET. Deze stappen maken een naadloze integratie van Project Server‑gegevens in je aangepaste toepassingen mogelijk, waardoor je robuuste project‑managementoplossingen kunt bouwen.

## Veelgestelde vragen

### Q1: Kan ik Aspose.Tasks gebruiken met verschillende versies van Microsoft Project-databases?
A1: Ja, Aspose.Tasks ondersteunt verschillende versies van Microsoft Project-databases, wat flexibiliteit in integratie biedt.

### Q2: Hoe kan ik verbindingsproblemen met de database oplossen?
A2: Zorg ervoor dat je verbindingstring correct is geconfigureerd met de juiste inloggegevens en database‑details. Je kunt ook de documentatie raadplegen of ondersteuning zoeken via het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15).

### Q3: Is er een proefversie beschikbaar voor Aspose.Tasks?
A3: Ja, je kunt een gratis proefversie verkrijgen via [hier](https://releases.aspose.com/).

### Q4: Kan ik het schema aanpassen voor database‑interactie?
A4: Ja, je kunt het schema voor het `MspDbSettings`‑object opgeven volgens de structuur van je database.

### Q5: Waar kan ik meer gedetailleerde documentatie vinden over het gebruik van Aspose.Tasks?
A5: Je kunt de uitgebreide documentatie bekijken [hier](https://reference.aspose.com/tasks/net/) voor gedetailleerd inzicht in de functionaliteiten van Aspose.Tasks.

**Q: Werkt deze aanpak met Azure SQL-databases?**  
A: Absoluut. Pas gewoon de `DataSource` aan naar de naam van je Azure‑server en zorg ervoor dat TLS/SSL‑instellingen zijn ingeschakeld.

**Q: Hoe ga ik om met grote Project-databases zonder time‑out?**  
A: Verhoog de `ConnectTimeout`‑waarde in de verbindingstring en overweeg om projecten in batches te laden indien nodig.

---

**Laatst bijgewerkt:** 2026-03-14  
**Getest met:** Aspose.Tasks 24.12 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}