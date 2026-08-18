---
date: 2026-02-18
description: Lär dig hur du sparar projekt som PDF och läser Microsoft Project‑databasen
  med Aspose.Tasks för Java, samt ansluter till Project Server, konverterar projektet
  till HTML och exporterar projektet till XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Spara projekt som PDF och läs projektdatabasen med Aspose.Tasks för Java
url: /sv/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spara projekt som PDF och läs Microsoft Project-databas med Aspose.Tasks för Java

## Introduktion
I den här handledningen kommer du att upptäcka hur du **läser Microsoft Project-databas** direkt från en Microsoft Project Server och sedan **sparar projektet som PDF** med hjälp av Aspose.Tasks Java‑API. Oavsett om du behöver generera rapporter, migrera data eller integrera projektinformation i dina egna applikationer, guidar den här guiden dig genom varje steg—från att konfigurera databasanslutningen till att exportera projektet till PDF, XML eller HTML. I slutet har du en solid, produktionsklar lösning som fungerar utan att installera Microsoft Project på värddatorn.

## Snabba svar
- **Vad gör Aspose.Tasks?** Det tillhandahåller ett rent Java‑API för att läsa, skriva och manipulera Microsoft Project‑filer och databaser.  
- **Behöver jag ha Microsoft Project installerat?** Nej, Aspose.Tasks fungerar oberoende av Microsoft Project.  
- **Vilken databastyp stöds?** Microsoft SQL Server (bakänden för Project Server).  
- **Kan jag exportera till andra format?** Ja, förutom PDF kan du spara till XML, HTML, CSV och mer.  
- **Vad är de viktigaste förutsättningarna?** JDK, Aspose.Tasks för Java‑bibliotek, SQL Server JDBC‑drivrutin och autentiseringsuppgifter för att **ansluta till Project Server**.

## Vad betyder “läsa Microsoft Project-databas”?
Att läsa en Microsoft Project-databas innebär att ansluta till Project Servers SQL Server‑arkiv, extrahera den lagrade projektinformationen och ladda den i ett `Project`‑objekt som Aspose.Tasks kan manipulera. Detta tillvägagångssätt är idealiskt för automatiserad rapportering, datamigrering eller anpassad analys.

## Varför använda Aspose.Tasks för Java?
- **Ingen Microsoft Project‑beroende** – kör på vilken server eller CI‑miljö som helst.  
- **Rik objektmodell** – åtkomst till uppgifter, resurser, tilldelningar, kalendrar och anpassade fält programatiskt.  
- **Flera exportalternativ** – PDF, XML, HTML, PNG osv., med ett enda API‑anrop.  
- **Hög prestanda** – optimerad för stora företagsprojekt.

## Förutsättningar
Innan du börjar, se till att du har:

1. En fungerande Java‑utvecklingsmiljö (JDK 8 eller nyare).  
2. Aspose.Tasks för Java‑biblioteket tillagt i ditt projekts classpath.  
3. Åtkomstuppgifter för Project Server‑SQL‑databasen (servernamn, port, databasnamn, användarnamn, lösenord) **för att ansluta till Project Server**.  
4. Microsoft JDBC‑drivrutin för SQL Server (t.ex. `sqljdbc4.jar`).  

## Importera paket
Först importerar du de klasser du behöver. Listan innehåller Aspose.Tasks‑kärnklasser och standard‑Java‑verktyg.

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

## Hur du ansluter till Project Server
Att etablera en pålitlig anslutning är grunden för att läsa projektdata. Se till att SQL Server‑instansen är nåbar från din Java‑värd och att inloggningen du använder har **SELECT**‑behörighet på Project Server‑schemat.

## Steg 1: Konfigurera databasanslutning
Skapa en `MspDbSettings`‑instans som innehåller JDBC‑anslutningssträngen. Ersätt platshållarvärdena med dina faktiska serverdetaljer.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Spara anslutningssträngen i en säker konfigurationsfil eller miljövariabel istället för att hårdkoda autentiseringsuppgifter.

## Steg 2: Lägg till JDBC‑drivrutin
Läs in Microsoft SQL Server JDBC‑drivrutinen vid körning så att JVM kan kommunicera med databasen.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** Säkerställ att drivrutinsversionen matchar din SQL Server‑version. En inkompatibel drivrutin kan leda till anslutningsfel.

## Steg 3: Läs projektdata
Instansiera ett `Project`‑objekt genom att skicka in `MspDbSettings`. Aspose.Tasks hämtar automatiskt projektdata från databasen.

```java
Project project = new Project(settings);
```

Vid detta tillfälle kan du utforska `project`‑objektet—lista uppgifter, resurser eller ändra fält efter behov.

## Steg 4: Spara projekt som PDF
Exportera det laddade projektet till ett filformat du väljer. Exemplet nedan sparar projektet som **PDF**, vilket är perfekt för utskrivbara rapporter. Du kan också **exportera projektet till XML** eller **konvertera projektet till HTML** genom att ändra `SaveFileFormat`‑enum.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Om du föredrar XML, ersätt helt enkelt `SaveFileFormat.Pdf` med `SaveFileFormat.Xml`. För HTML‑utdata, använd `SaveFileFormat.Html`.

## Vanliga problem & lösningar
| Problem | Typisk orsak | Lösning |
|---------|--------------|---------|
| **Connection timeout** | Fel server/port eller brandvägg blockerar | Verifiera serveradress, öppna port 1433 och testa anslutning med ett enkelt JDBC‑testprogram. |
| **Authentication error** | Ogiltigt användarnamn/lösenord eller SQL Server är inte konfigurerad för SQL‑autentisering | Använd en giltig SQL‑inloggning eller aktivera blandad autentisering på servern. |
| **Driver not found** | JDBC‑jar saknas i classpath | Säkerställ att `addJDBCDriver` pekar på rätt `.jar`‑fil och att sökvägen använder dubbla bakstreck (`\\`). |
| **Empty project after load** | Otillräckliga rättigheter för att läsa Project Server‑tabeller | Tilldela inloggningen SELECT‑rättigheter på Project Server‑databasens schema. |

## Vanliga frågor

**Q: Kan Aspose.Tasks användas för att läsa projektdata från andra databaser än Microsoft Project?**  
A: Ja, Aspose.Tasks stödjer läsning av projektdata från olika källor, inklusive XML‑filer, Primavera och Microsoft Project‑databaser.

**Q: Är Aspose.Tasks kompatibel med olika versioner av Microsoft Project?**  
A: Ja, Aspose.Tasks är designat för att fungera med flera Microsoft Project‑versioner, vilket säkerställer sömlös integration.

**Q: Kan jag manipulera projektdata innan jag sparar den?**  
A: Absolut, Aspose.Tasks erbjuder ett rikt API för att lägga till uppgifter, uppdatera resurser och sätta projektegenskaper innan export.

**Q: Stöder Aspose.Tasks flera utdataformat?**  
A: Ja, du kan spara projekt som PDF, XML, HTML, CSV, PNG, JPEG och mer.

**Q: Var kan jag hitta ytterligare support eller hjälp med Aspose.Tasks?**  
A: För ytterligare hjälp, besök Aspose.Tasks‑forumet eller utforska dokumentationen som finns på webbplatsen [here](https://forum.aspose.com/c/tasks/15).

## Slutsats
Genom att följa den här steg‑för‑steg‑guiden vet du nu hur du **läser Microsoft Project-databas**, **sparar projektet som PDF** och exporterar till andra format med Aspose.Tasks för Java. Detta tillvägagångssätt eliminerar beroendet av Microsoft Project, förenklar automatiserad rapportering och öppnar dörren för kraftfulla anpassade integrationer.

---

**Senast uppdaterad:** 2026-02-18  
**Testad med:** Aspose.Tasks för Java 24.5 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}