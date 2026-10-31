---
date: 2026-10-31
description: Lär dig hur du sparar projekt som PDF och läser Microsoft Project-databas
  med Aspose.Tasks för Java, samt ansluter till Project Server, konverterar projekt
  till HTML och exporterar projekt till XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Läsa projektdata från Microsoft Project-databas i Aspose.Tasks
og_description: Spara projekt som PDF och läs Microsoft Project-databas med Aspose.Tasks
  för Java. Lär dig att ansluta till Project Server, exportera till HTML, XML och
  CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Spara projekt som PDF och läs Microsoft Project-databas med Aspose.Tasks
  för Java
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
title: Spara projekt som PDF och läs Microsoft Project-databas med Aspose.Tasks för
  Java
url: /sv/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spara projekt som PDF och läs Microsoft Project-databas med Aspose.Tasks för Java

## Introduktion
I den här handledningen kommer du att upptäcka hur du **läser Microsoft Project-databas** direkt från en Microsoft Project Server och sedan **sparar projektet som PDF** med hjälp av Aspose.Tasks Java‑API. Oavsett om du behöver generera utskrivbara rapporter, migrera äldre data eller bädda in projektinformation i en anpassad portal, guidar den här artikeln dig genom varje steg – från att konfigurera JDBC‑anslutningen till att exportera projektet till PDF, XML eller HTML. I slutet har du en produktionsklar lösning som körs på vilken Java‑server som helst utan att installera Microsoft Project.

## Snabba svar
- **Vad gör Aspose.Tasks?** Det tillhandahåller ett rent Java‑API för att läsa, skriva och manipulera Microsoft Project‑filer och databaser.  
- **Behöver jag ha Microsoft Project installerat?** Nej, Aspose.Tasks fungerar oberoende av Microsoft Project.  
- **Vilken databastyp stöds?** Microsoft SQL Server, backend för Project Server.  
- **Kan jag exportera till andra format?** Ja – PDF, XML, HTML, CSV, PNG, JPEG och mer.  
- **Vad är de viktigaste förutsättningarna?** JDK 8 eller nyare, Aspose.Tasks för Java‑biblioteket, SQL Server JDBC‑drivrutin och giltiga Project Server‑uppgifter.

## Vad betyder “read Microsoft Project database”?
Att läsa en Microsoft Project‑databas innebär att ansluta till Project Servers SQL‑Server‑arkiv, extrahera de lagrade projektdata och ladda dem i ett `Project`‑objekt som Aspose.Tasks kan manipulera. Detta tillvägagångssätt är idealiskt för automatiserad rapportering, datamigrering eller anpassad analys.

## Varför använda Aspose.Tasks för Java?
Aspose.Tasks för Java låter dig arbeta med Microsoft Project‑data utan att behöva skrivbordsapplikationen, vilket ger en ren Java‑lösning som körs på vilken plattform som helst. Det erbjuder en omfattande objektmodell för uppgifter, resurser, kalendrar och anpassade fält och kan hantera stora företagsprojekt effektivt, vilket gör det idealiskt för automatiserad rapportering, migrering och integrationsscenarier.

- **Ingen Microsoft Project‑beroende** – kör på vilken server eller CI‑miljö som helst.  
- **Rik objektmodell** – få programmatisk åtkomst till uppgifter, resurser, tilldelningar, kalendrar och anpassade fält.  
- **Flera exportalternativ** – Aspose.Tasks stöder export till **över 20 filformat**, inklusive PDF, XML, HTML, CSV, PNG och JPEG, med ett enda API‑anrop.  
- **Hög prestanda** – biblioteket kan bearbeta projekt med **upp till 10 000 uppgifter** på under en minut och strömmar data för att undvika att hela filen laddas in i minnet.

## Förutsättningar
Innan du börjar, se till att du har:

1. En fungerande Java‑utvecklingsmiljö (JDK 8 eller nyare).  
2. Aspose.Tasks för Java‑biblioteket tillagt i projektets classpath.  
3. Åtkomstuppgifter för Project Server SQL‑databasen (servernamn, port, databasenamn, användarnamn, lösenord) för att ansluta till Project Server.  
4. Microsoft JDBC‑drivrutin för SQL Server (t.ex. `sqljdbc4.jar`).  

## Importera paket
Först importerar du de klasser du behöver. Listan inkluderar Aspose.Tasks‑kärnklasser och vanliga Java‑verktyg.

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

## Så ansluter du till Project Server
Att etablera en pålitlig anslutning är grunden för att läsa projektdata. Se till att SQL Server‑instansen är nåbar från din Java‑värd och att inloggningen du använder har **SELECT**‑behörighet på Project Server‑schemat. Du bör också verifiera nätverkslatens och konfigurera eventuella SSL‑inställningar för att säkerställa säker kommunikation.

## Steg 1: konfigurera databasanslutning
Klassen `MspDbSettings` kapslar in JDBC‑anslutningsdetaljerna som krävs för att komma åt en Microsoft Project Server‑databas. Skapa en `MspDbSettings`‑instans som innehåller JDBC‑anslutningssträngen. Ersätt platshållarvärdena med dina faktiska serveruppgifter.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Förvara anslutningssträngen i en säker konfigurationsfil eller miljövariabel istället för att hårdkoda autentiseringsuppgifter.

## Steg 2: lägg till JDBC‑drivrutin
Läs in Microsoft SQL Server JDBC‑drivrutinen vid körning så att JVM kan kommunicera med databasen.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** Säkerställ att drivrutinsversionen matchar din SQL Server‑version. En inkompatibel drivrutin kan leda till anslutningsfel.

## Steg 3: läs projektdata
Klassen `Project` representerar en Microsoft Project‑fil som laddats in i minnet och exponerar uppgifter, resurser och tilldelningar. Skapa ett `Project`‑objekt genom att skicka in `MspDbSettings`. Aspose.Tasks hämtar automatiskt projektdata från databasen.

```java
Project project = new Project(settings);
```

Vid detta tillfälle kan du utforska `project`‑objektet – lista uppgifter, resurser eller ändra fält efter behov.

## Steg 4: spara projekt som PDF
Enumen `SaveFileFormat` definierar utdataformatet för `Project.save`‑metoden, såsom PDF, XML eller HTML. Exportera det inlästa projektet till det format du föredrar. Exemplet nedan sparar projektet som **PDF**, vilket är perfekt för utskrivbara rapporter. Du kan också **exportera projektet till XML** eller **konvertera projektet till HTML** genom att ändra `SaveFileFormat`‑enum.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Om du föredrar XML, ersätt helt enkelt `SaveFileFormat.Pdf` med `SaveFileFormat.Xml`. För HTML‑utdata, använd `SaveFileFormat.Html`.

## Vanliga problem & lösningar
| Problem | Typisk orsak | Lösning |
|-------|---------------|-----|
| **Connection timeout** | Fel server/port eller brandvägg blockerar | Verifiera serveradressen, öppna port 1433 och testa anslutning med ett enkelt JDBC‑testprogram. |
| **Authentication error** | Ogiltigt användarnamn/lösenord eller SQL Server är inte konfigurerad för SQL‑autentisering | Använd en giltig SQL‑inloggning eller aktivera blandad autentisering på servern. |
| **Driver not found** | JDBC‑jar saknas i classpath | Säkerställ att `addJDBCDriver` pekar på rätt `.jar`‑fil och att sökvägen använder dubbla bakstreck (`\\`). |
| **Empty project after load** | Otillräckliga behörigheter för att läsa Project Server‑tabeller | Tilldela inloggningen SELECT‑rättigheter på Project Server‑databasens schema. |

## Vanliga frågor

**Q: Kan Aspose.Tasks användas för att läsa projektdata från andra databaser än Microsoft Project?**  
A: Ja, Aspose.Tasks stöder läsning av projektdata från XML‑filer, Primavera‑databaser och andra standardprojektformat.

**Q: Är Aspose.Tasks kompatibel med olika versioner av Microsoft Project?**  
A: Ja, biblioteket fungerar med Microsoft Project 2007 upp till de senaste 2024‑utgåvorna, vilket säkerställer sömlös integration över versioner.

**Q: Kan jag manipulera projektdata innan jag sparar den?**  
A: Absolut, du kan lägga till, uppdatera eller ta bort uppgifter, resurser och anpassade fält med det rika API‑et innan du exporterar.

**Q: Stöder Aspose.Tasks flera utdataformat?**  
A: Ja, du kan spara projekt som PDF, XML, HTML, CSV, PNG, JPEG och mer – över 20 format totalt.

**Q: Var kan jag hitta ytterligare support eller hjälp med Aspose.Tasks?**  
A: För ytterligare hjälp, besök Aspose.Tasks‑forumet eller utforska dokumentationen på webbplatsen [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Slutsats
Genom att följa den här steg‑för‑steg‑guiden vet du nu hur du **läser Microsoft Project‑databas**, **sparar projektet som PDF** och exporterar till andra format med Aspose.Tasks för Java. Detta tillvägagångssätt eliminerar beroendet av Microsoft Project, förenklar automatiserad rapportering och öppnar dörren för kraftfulla anpassade integrationer.

---

**Last Updated:** 2026-10-31  
**Testad med:** Aspose.Tasks för Java 24.5 (senaste vid skrivande)  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man sparar projekt som PDF med Aspose.Tasks – Exportguide](/tasks/java/project-file-operations/save-as-pdf/)
- [Spara projekt som PDF – Rendera uppgiftssblad med Aspose.Tasks för Java](/tasks/java/task-properties/render-task-sheet/)
- [Exportera projekt till PDF och minska gapet mellan uppgiftslistan och sidfoten i Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}