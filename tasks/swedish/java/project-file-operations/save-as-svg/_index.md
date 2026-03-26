---
date: 2025-12-21
description: Lär dig hur du skapar SVG från MPP‑filer i Java och sparar projektet
  som SVG med Aspose.Tasks‑biblioteket. Steg‑för‑steg‑guide med kodexempel.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man skapar SVG från MPP i Java med Aspose.Tasks
url: /sv/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar SVG från MPP i Java

## Introduktion
I den här handledningen kommer du att lära dig hur du **skapar SVG från MPP**‑filer med Aspose.Tasks for Java. Att konvertera en Microsoft Project‑fil (MPP) till skalbara vektorgrafik‑format (SVG) låter dig bädda in högkvalitativa, upplösningsoberoende diagram direkt i webbsidor, rapporter eller instrumentpaneler. Vi går igenom den nödvändiga konfigurationen, visar exakt den kod du behöver och förklarar varje steg så att du tryggt kan **spara projekt som SVG** i dina egna applikationer.

## Snabba svar
- **Vad betyder “create SVG from MPP”?**  
  Det konverterar en Microsoft Project‑fil (.mpp) till en SVG‑bild som kan visas i vilken webbläsare som helst utan kvalitetsförlust.  
- **Vilket bibliotek hanterar konverteringen?**  
  Aspose.Tasks for Java tillhandahåller en en‑rad `save`‑metod för att utföra konverteringen.  
- **Behöver jag en licens?**  
  En tillfällig licens krävs för kommersiell användning; en gratis provperiod finns tillgänglig.  
- **Vad är förutsättningarna?**  
  Java JDK 8+ och Aspose.Tasks for Java‑JAR‑filen.  
- **Hur lång tid tar konverteringen?**  
  Vanligtvis mindre än en sekund för standardprojektfiler.

## Vad är “create SVG from MPP”?
Att skapa en SVG från en MPP‑fil innebär att exportera den visuella representationen av ett projektschema — uppgifter, tidslinjer och resurser — till Scalable Vector Graphics‑formatet. SVG är XML‑baserat, lättviktigt och skalar perfekt på högupplösta skärmar.

## Varför använda Aspose.Tasks för att spara projekt som SVG?
- **Ingen Microsoft Project‑installation krävs** – biblioteket fungerar oberoende.  
- **Fullständig trohet** – diagram, Gantt‑staplar och milstolpar behåller sina stilar.  
- **Plattformsoberoende** – kör koden på Windows, Linux eller macOS.  
- **Enkel integration** – ett‑rad API‑anrop passar naturligt in i befintliga Java‑pipelines.

## Förutsättningar
- **Java Development Kit (JDK)** – version 8 eller senare. Ladda ner från Oracles webbplats.  
- **Aspose.Tasks for Java** – hämta biblioteket från den officiella nedladdningssidan **[here](https://releases.aspose.com/tasks/java/)**.  

## Importera paket
Först importerar du de klasser du behöver. Importblocket förblir oförändrat.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Steg 1: Definiera datakatalogen
Ange var din käll‑MPP‑fil finns och var SVG‑filen ska skrivas.

```java
String dataDir = "Your Data Directory";
```

> **Proffstips:** Använd en absolut sökväg eller en sökväg relativ till ditt projekts resurser‑mapp för att undvika `FileNotFoundException`.

## Steg 2: Ladda MPP‑filen
Skapa en `Project`‑instans genom att läsa in den befintliga Microsoft Project‑filen.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Den här raden läser *HomeMovePlan.mpp* från den mapp du definierade tidigare.

## Steg 3: Spara projektet som SVG
Nu kan du **spara projekt som SVG** med ett enda kommando.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Metoden skriver `project5.svg` till samma katalog. Den resulterande SVG‑filen kan öppnas i vilken modern webbläsare som helst eller bäddas in direkt i HTML.

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|---------|-------|---------|
| **Fil ej hittad** | Felaktig `dataDir`‑sökväg | Verifiera att katalogsträngen avslutas med en separator (`/` eller `\\`). |
| **Tom SVG‑utdata** | Projektet laddades utan vyer | Se till att MPP‑filen innehåller en Gantt‑diagramvy innan du sparar. |
| **Licensundantag** | Ingen giltig licens har använts | Applicera en tillfällig licens med `License.setLicense("path/to/license.xml")` innan du anropar `save`. |

## Vanliga frågor

**Q: Är Aspose.Tasks for Java kompatibel med alla versioner av Microsoft Project‑filer?**  
A: Ja, det stödjer MPP, MPT och XML‑format från äldre till de senaste Project‑utgåvorna.

**Q: Kan jag anpassa utseendet på SVG‑utdata?**  
A: Absolut. Använd `SvgOptions` för att ställa in teckensnitt, färger och layoutalternativ innan du anropar `save`.

**Q: Kräver Aspose.Tasks for Java en licens för kommersiell användning?**  
A: Ja, en giltig licens krävs för produktion. Du kan skaffa en tillfällig licens **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Kan jag prova Aspose.Tasks for Java innan jag köper?**  
A: Ja, en gratis provperiod finns tillgänglig **[here](https://purchase.aspose.com/buy)**.

**Q: Var kan jag få support för Aspose.Tasks for Java?**  
A: Besök community‑forumet **[here](https://forum.aspose.com/c/tasks/15)** för att ställa frågor och dela feedback.

## Slutsats
Du vet nu hur du **skapar SVG från MPP**‑filer i Java och effektivt **sparar projekt som SVG** med Aspose.Tasks. Denna funktion låter dig integrera rika projektvisualiseringar i webbportaler, rapporteringsinstrumentpaneler eller var som helst där skalbara grafik behövs. Experimentera med `SvgOptions` för att finjustera utdata, så har du ett kraftfullt verktyg i din utvecklingsverktygslåda.

---

**Senast uppdaterad:** 2025-12-21  
**Testad med:** Aspose.Tasks for Java 24.10  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}