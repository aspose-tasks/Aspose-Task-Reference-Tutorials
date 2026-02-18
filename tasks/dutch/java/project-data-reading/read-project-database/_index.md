---
date: 2026-02-18
description: Leer hoe u een project als PDF opslaat en de Microsoft Project-database
  leest met Aspose.Tasks voor Java, plus verbinding maakt met Project Server, een
  project naar HTML converteert en een project naar XML exporteert.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Project opslaan als PDF en Project DB lezen met Aspose.Tasks voor Java
url: /nl/java/project-data-reading/read-project-database/
weight: 12
---

 a backtop button shortcode unchanged.

Make sure to keep markdown formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Project opslaan als PDF en Microsoft Project-database lezen met Aspose.Tasks voor Java

## Inleiding
In deze tutorial ontdek je hoe je **Microsoft Project-database** rechtstreeks kunt **lezen** vanaf een Microsoft Project Server en vervolgens **het project als PDF** kunt opslaan met de Aspose.Tasks Java‑API. Of je nu rapporten moet genereren, gegevens wilt migreren of projectinformatie in je eigen applicaties wilt integreren, deze gids leidt je stap voor stap – van het instellen van de databaseverbinding tot het exporteren van het project naar PDF, XML of HTML. Aan het einde heb je een solide, productie‑klare oplossing die werkt zonder Microsoft Project op de hostmachine te installeren.

## Snelle antwoorden
- **Wat doet Aspose.Tasks?** Het biedt een pure‑Java API om Microsoft Project‑bestanden en -databases te lezen, te schrijven en te manipuleren.  
- **Heb ik Microsoft Project geïnstalleerd nodig?** Nee, Aspose.Tasks werkt onafhankelijk van Microsoft Project.  
- **Welke databasetype wordt ondersteund?** Microsoft SQL Server (de backend van Project Server).  
- **Kan ik exporteren naar andere formaten?** Ja, naast PDF kun je opslaan als XML, HTML, CSV en meer.  
- **Wat zijn de belangrijkste vereisten?** JDK, Aspose.Tasks for Java‑bibliotheek, de SQL Server JDBC‑driver en inloggegevens om **verbinding te maken met Project Server**.

## Wat betekent “Microsoft Project-database lezen”?
Een Microsoft Project‑database lezen betekent verbinding maken met de SQL‑Server‑repository van Project Server, de opgeslagen projectgegevens extraheren en laden in een `Project`‑object dat Aspose.Tasks kan manipuleren. Deze aanpak is ideaal voor geautomatiseerde rapportage, datamigratie of aangepaste analyses.

## Waarom Aspose.Tasks voor Java gebruiken?
- **Geen afhankelijkheid van Microsoft Project** – draait op elke server of CI‑omgeving.  
- **Rijk objectmodel** – toegang tot taken, resources, toewijzingen, agenda’s en aangepaste velden via code.  
- **Meerdere exportopties** – PDF, XML, HTML, PNG, enz., met één API‑aanroep.  
- **Hoge prestaties** – geoptimaliseerd voor grote enterprise‑projecten.

## Prerequisites
Voordat je begint, zorg dat je het volgende hebt:

1. Een werkende Java‑ontwikkelomgeving (JDK 8 of nieuwer).  
2. Aspose.Tasks for Java‑bibliotheek toegevoegd aan de classpath van je project.  
3. Toegangs‑inloggegevens voor de Project Server‑SQL‑database (servernaam, poort, databasenaam, gebruikersnaam, wachtwoord) **om verbinding te maken met Project Server**.  
4. De Microsoft JDBC‑driver voor SQL Server (bijv. `sqljdbc4.jar`).  

## Pakketten importeren
Eerst importeer je de klassen die je nodig hebt. De lijst bevat Aspose.Tasks‑coreklassen en standaard Java‑utilities.

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## Hoe verbinding te maken met Project Server
Een betrouwbare verbinding is de basis voor het lezen van projectgegevens. Zorg ervoor dat de SQL‑Server‑instantie bereikbaar is vanaf je Java‑host en dat de login die je gebruikt **SELECT**‑rechten heeft op het Project Server‑schema.

## Stap 1: Databaseverbinding instellen
Maak een `MspDbSettings`‑instantie aan die de JDBC‑verbindingstring bevat. Vervang de placeholder‑waarden door je eigen serverdetails.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Bewaar de verbindingstring in een veilig configuratie‑bestand of een omgevingsvariabele in plaats van in de code te hard‑coderen.

## Stap 2: JDBC-driver toevoegen
Laad de Microsoft SQL Server JDBC‑driver tijdens runtime zodat de JVM met de database kan communiceren.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** Zorg ervoor dat de driver‑versie overeenkomt met je SQL Server‑versie. Het gebruik van een incompatibele driver kan verbindingsfouten veroorzaken.

## Stap 3: Projectgegevens lezen
Instantieer een `Project`‑object door de `MspDbSettings` door te geven. Aspose.Tasks haalt de projectgegevens automatisch uit de database.

```java
Project project = new Project(settings);
```

Op dit moment kun je het `project`‑object verkennen – taken, resources opsommen of velden aanpassen naar behoefte.

## Stap 4: Project opslaan als PDF
Exporteer het geladen project naar een bestandsformaat naar keuze. Het voorbeeld hieronder slaat het project op als **PDF**, ideaal voor afdrukbare rapporten. Je kunt ook **project exporteren naar XML** of **project converteren naar HTML** door de `SaveFileFormat`‑enum aan te passen.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Als je XML wilt, vervang je `SaveFileFormat.Pdf` door `SaveFileFormat.Xml`. Voor HTML‑output gebruik je `SaveFileFormat.Html`.

## Veelvoorkomende problemen & oplossingen
| Probleem | Typische oorzaak | Oplossing |
|----------|-------------------|-----------|
| **Verbindingstime-out** | Verkeerde server/poort of firewall blokkeert | Controleer het serveradres, open poort 1433 en test de connectiviteit met een eenvoudig JDBC‑testprogramma. |
| **Authenticatiefout** | Ongeldige gebruikersnaam/wachtwoord of SQL Server niet geconfigureerd voor SQL‑authenticatie | Gebruik een geldige SQL‑login of schakel mixed‑mode authenticatie in op de server. |
| **Driver niet gevonden** | JDBC‑jar niet in classpath | Zorg ervoor dat `addJDBCDriver` naar het juiste `.jar`‑bestand wijst en dat het pad dubbele backslashes (`\\`) gebruikt. |
| **Leeg project na laden** | Onvoldoende rechten om Project Server‑tabellen te lezen | Geef de login SELECT‑rechten op het Project Server‑databaseschema. |

## Veelgestelde vragen

**Q: Kan Aspose.Tasks worden gebruikt om projectgegevens te lezen uit andere databases dan Microsoft Project?**  
A: Ja, Aspose.Tasks ondersteunt het lezen van projectgegevens uit diverse bronnen, waaronder XML‑bestanden, Primavera en Microsoft Project‑databases.

**Q: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project?**  
A: Ja, Aspose.Tasks is ontworpen om met meerdere Microsoft Project‑versies te werken, waardoor naadloze integratie wordt gegarandeerd.

**Q: Kan ik de projectgegevens bewerken voordat ik ze opsla?**  
A: Absoluut, Aspose.Tasks biedt een rijk API voor het toevoegen van taken, bijwerken van resources en instellen van projecteigenschappen vóór export.

**Q: Ondersteunt Aspose.Tasks meerdere uitvoerformaten?**  
A: Ja, je kunt projecten opslaan als PDF, XML, HTML, CSV, PNG, JPEG en meer.

**Q: Waar vind ik verdere ondersteuning of hulp bij Aspose.Tasks?**  
A: Voor extra hulp kun je het Aspose.Tasks‑forum bezoeken of de documentatie raadplegen die beschikbaar is op de website [here](https://forum.aspose.com/c/tasks/15).

## Conclusie
Door deze stap‑voor‑stap‑gids te volgen, weet je nu hoe je **Microsoft Project-database** kunt **lezen**, **het project als PDF** kunt **opslaan** en naar andere formaten kunt exporteren met Aspose.Tasks voor Java. Deze aanpak verwijdert de afhankelijkheid van Microsoft Project, stroomlijnt geautomatiseerde rapportage en opent de deur naar krachtige, aangepaste integraties.

---

**Laatste update:** 2026-02-18  
**Getest met:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}