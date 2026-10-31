---
date: 2026-10-31
description: Leer hoe u een project opslaat als PDF en de Microsoft Project-database
  leest met Aspose.Tasks for Java, plus verbinding maken met Project Server, het project
  converteren naar HTML en exporteren naar XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Projectgegevens lezen uit Microsoft Project-database in Aspose.Tasks
og_description: Project opslaan als PDF en Microsoft Project-database lezen met Aspose.Tasks
  for Java. Leer verbinding maken met Project Server, exporteren naar HTML, XML en
  CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Project opslaan als PDF en Microsoft Project-database lezen met Aspose.Tasks
  for Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Project opslaan als PDF en Microsoft Project-database lezen met Aspose.Tasks
  for Java
url: /nl/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Project opslaan als PDF en Microsoft Project-database lezen met Aspose.Tasks voor Java

## Introductie
In deze tutorial ontdek je hoe je **Microsoft Project-database** rechtstreeks van een Microsoft Project Server kunt **lezen** en vervolgens **het project als PDF kunt opslaan** met de Aspose.Tasks Java‑API. Of je nu afdrukbare rapporten moet genereren, legacy‑data wilt migreren, of projectinformatie wilt integreren in een aangepast portaal, deze gids leidt je stap voor stap—van het configureren van de JDBC‑verbinding tot het exporteren van het project naar PDF, XML of HTML. Aan het einde heb je een productieklare oplossing die op elke Java‑server draait zonder Microsoft Project te installeren.

## Snelle antwoorden
- **Wat doet Aspose.Tasks?** Het biedt een pure‑Java‑API om Microsoft Project‑bestanden en -databases te lezen, te schrijven en te manipuleren.  
- **Heb ik Microsoft Project geïnstalleerd nodig?** Nee, Aspose.Tasks werkt onafhankelijk van Microsoft Project.  
- **Welke databasetype wordt ondersteund?** Microsoft SQL Server, de backend van Project Server.  
- **Kan ik exporteren naar andere formaten?** Ja—PDF, XML, HTML, CSV, PNG, JPEG en meer.  
- **Wat zijn de belangrijkste vereisten?** JDK 8 of nieuwer, Aspose.Tasks for Java‑bibliotheek, de SQL Server JDBC‑driver en geldige Project Server‑referenties.

## Wat betekent “Microsoft Project-database lezen”?
Het lezen van een Microsoft Project‑database betekent verbinding maken met de SQL‑Server‑repository van Project Server, de opgeslagen projectgegevens extraheren en laden in een `Project`‑object dat Aspose.Tasks kan manipuleren. Deze aanpak is ideaal voor geautomatiseerde rapportage, datamigratie of aangepaste analyses.

## Waarom Aspose.Tasks voor Java gebruiken?
Aspose.Tasks voor Java stelt je in staat met Microsoft Project‑data te werken zonder de desktop‑applicatie, en biedt een pure‑Java‑oplossing die op elk platform draait. Het levert een uitgebreid objectmodel voor taken, resources, kalenders en aangepaste velden, en kan grote enterprise‑projecten efficiënt verwerken, waardoor het ideaal is voor geautomatiseerde rapportage, migratie en integratiescenario's.

- **Geen afhankelijkheid van Microsoft Project** – draait op elke server of CI‑omgeving.  
- **Rijk objectmodel** – toegang tot taken, resources, toewijzingen, kalenders en aangepaste velden via code.  
- **Meerdere exportopties** – Aspose.Tasks ondersteunt export naar **meer dan 20 bestandsformaten**, waaronder PDF, XML, HTML, CSV, PNG en JPEG, met één API‑aanroep.  
- **Hoge prestaties** – de bibliotheek kan projecten met **tot 10.000 taken** in minder dan een minuut verwerken en streamt data om te voorkomen dat het volledige bestand in het geheugen wordt geladen.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:

1. Een werkende Java‑ontwikkelomgeving (JDK 8 of nieuwer).  
2. Aspose.Tasks for Java‑bibliotheek toegevoegd aan de classpath van je project.  
3. Toegangsreferenties voor de Project Server‑SQL‑database (servernaam, poort, databasenaam, gebruikersnaam, wachtwoord) om verbinding te maken met Project Server.  
4. De Microsoft JDBC‑driver voor SQL Server (bijv. `sqljdbc4.jar`).  

## Pakketten importeren
Eerst importeer je de klassen die je nodig hebt. De lijst bevat Aspose.Tasks‑coreklassen en standaard Java‑hulpmiddelen.

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
Een betrouwbare verbinding is de basis voor het lezen van projectdata. Zorg dat de SQL‑Server‑instantie bereikbaar is vanaf je Java‑host en dat de login die je gebruikt **SELECT**‑rechten heeft op het Project Server‑schema. Controleer ook de netwerklatentie en configureer eventuele vereiste SSL‑instellingen voor een veilige communicatie.

## Stap 1: databaseverbinding instellen
De `MspDbSettings`‑klasse omsluit de JDBC‑verbindingdetails die nodig zijn om toegang te krijgen tot een Microsoft Project Server‑database. Maak een `MspDbSettings`‑instantie die de JDBC‑verbindingstring bevat. Vervang de tijdelijke waarden door je eigen serverdetails.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Sla de verbindingstring op in een veilig configuratie‑bestand of omgevingsvariabele in plaats van in de code te hard‑coderen.

## Stap 2: JDBC-driver toevoegen
Laad de Microsoft SQL Server JDBC‑driver tijdens runtime zodat de JVM met de database kan communiceren.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Waarschuwing:** Zorg ervoor dat de driver‑versie overeenkomt met je SQL Server‑versie. Een incompatibele driver kan verbindingsfouten veroorzaken.

## Stap 3: projectgegevens lezen
De `Project`‑klasse vertegenwoordigt een Microsoft Project‑bestand dat in het geheugen is geladen, met toegang tot taken, resources en toewijzingen. Maak een `Project`‑object aan door de `MspDbSettings` door te geven. Aspose.Tasks haalt de projectdata automatisch uit de database.

```java
Project project = new Project(settings);
```

Op dit moment kun je het `project`‑object verkennen—taken, resources opsommen of velden aanpassen naar behoefte.

## Stap 4: project opslaan als PDF
De `SaveFileFormat`‑enumeratie definieert het uitvoerformaat voor de `Project.save`‑methode, zoals PDF, XML of HTML. Exporteer het geladen project naar een bestandsformaat naar keuze. Het voorbeeld hieronder slaat het project op als **PDF**, ideaal voor afdrukbare rapporten. Je kunt ook **project exporteren naar XML** of **project converteren naar HTML** door de `SaveFileFormat`‑enum aan te passen.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Wil je XML, vervang dan `SaveFileFormat.Pdf` door `SaveFileFormat.Xml`. Voor HTML‑output gebruik je `SaveFileFormat.Html`.

## Veelvoorkomende problemen & oplossingen
| Probleem | Typische oorzaak | Oplossing |
|----------|------------------|-----------|
| **Verbindingstime-out** | Verkeerde server/poort of firewall blokkeert | Controleer serveradres, open poort 1433 en test de connectiviteit met een eenvoudig JDBC‑testprogramma. |
| **Authenticatiefout** | Ongeldige gebruikersnaam/wachtwoord of SQL Server niet geconfigureerd voor SQL‑authenticatie | Gebruik een geldige SQL‑login of schakel mixed‑mode authenticatie in op de server. |
| **Driver niet gevonden** | JDBC‑jar niet op het classpath | Zorg ervoor dat `addJDBCDriver` naar het juiste `.jar`‑bestand wijst en dat het pad dubbele backslashes (`\\`) gebruikt. |
| **Leeg project na laden** | Onvoldoende rechten om Project Server‑tabellen te lezen | Geef de login SELECT‑rechten op het schema van de Project Server‑database. |

## Veelgestelde vragen

**Q: Kan Aspose.Tasks worden gebruikt om projectgegevens uit andere databases dan Microsoft Project te lezen?**  
A: Ja, Aspose.Tasks ondersteunt het lezen van projectgegevens uit XML‑bestanden, Primavera‑databases en andere standaard projectformaten.

**Q: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project?**  
A: Ja, de bibliotheek werkt met Microsoft Project 2007 tot en met de nieuwste 2024‑releases, waardoor naadloze integratie over versies heen wordt gegarandeerd.

**Q: Kan ik de projectgegevens bewerken voordat ik ze opsla?**  
A: Absoluut, u kunt taken, resources en aangepaste velden toevoegen, bijwerken of verwijderen met de uitgebreide API voordat u exporteert.

**Q: Ondersteunt Aspose.Tasks meerdere uitvoerformaten?**  
A: Ja, u kunt projecten opslaan als PDF, XML, HTML, CSV, PNG, JPEG en meer — meer dan 20 formaten in totaal.

**Q: Waar kan ik meer ondersteuning of hulp vinden voor Aspose.Tasks?**  
A: Voor extra hulp, bezoek het Aspose.Tasks‑forum of bekijk de documentatie op de website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusie
Door deze stap‑voor‑stap‑gids te volgen, weet je nu hoe je **Microsoft Project‑database kunt lezen**, **het project als PDF kunt opslaan** en naar andere formaten kunt exporteren met Aspose.Tasks voor Java. Deze aanpak verwijdert de afhankelijkheid van Microsoft Project, stroomlijnt geautomatiseerde rapportage en opent de deur naar krachtige aangepaste integraties.

---

**Laatst bijgewerkt:** 2026-10-31  
**Getest met:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe Project opslaan als PDF met Aspose.Tasks – Exportgids](/tasks/java/project-file-operations/save-as-pdf/)
- [Project opslaan als PDF – Taakblad weergeven met Aspose.Tasks voor Java](/tasks/java/task-properties/render-task-sheet/)
- [Project exporteren naar PDF en de ruimte tussen takenlijst en voettekst verkleinen in Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}