---
date: 2026-03-27
description: Lär dig hur du exporterar MPP till SVG i Java med Aspose.Tasks. Steg‑för‑steg‑guide,
  kodexempel och tips för att snabbt spara ett projekt som SVG.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man exporterar MPP till SVG i Java med Aspose.Tasks
url: /sv/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så exporterar du MPP till SVG i Java

## Export MPP till SVG – Introduktion
I den här handledningen lär du dig hur du **exporterar MPP till SVG**‑filer med Aspose.Tasks för Java. Att konvertera en Microsoft Project‑fil (MPP) till en Scalable Vector Graphics (SVG)‑bild låter dig bädda in högkvalitativa, upplösningsoberoende diagram direkt i webbsidor, rapporter eller instrumentpaneler. Vi går igenom den nödvändiga konfigurationen, visar exakt den kod du behöver och förklarar varje steg så att du tryggt kan **spara projekt som SVG** i dina egna applikationer.

## Snabba svar
- **Vad betyder “export MPP till SVG”?**  
  Det konverterar en Microsoft Project‑fil (.mpp) till en SVG‑bild som kan visas i vilken webbläsare som helst utan kvalitetsförlust.  
- **Vilket bibliotek hanterar konverteringen?**  
  Aspose.Tasks för Java tillhandahåller en enradig `save`‑metod för att utföra konverteringen.  
- **Behöver jag en licens?**  
  En tillfällig licens krävs för kommersiell användning; en gratis provversion finns tillgänglig.  
- **Vilka förutsättningar finns?**  
  Java JDK 8+ och Aspose.Tasks för Java‑JAR‑filen.  
- **Hur lång tid tar konverteringen?**  
  Vanligtvis mindre än en sekund för standardprojektfiler.

## Vad är “export MPP till SVG”?
Att exportera MPP till SVG innebär att ta den visuella representationen av ett projektschema – uppgifter, tidslinjer och resurser – och skriva ut den som en SVG‑fil. SVG är XML‑baserat, lättviktigt och skalas perfekt på högupplösta skärmar.

## Varför exportera MPP till SVG med Aspose.Tasks?
- **Ingen Microsoft Project‑installation krävs** – biblioteket fungerar oberoende.  
- **Fullständig trohet** – diagram, Gantt‑staplar och milstolpar behåller sina stilar.  
- **Plattformsoberoende** – kör koden på Windows, Linux eller macOS.  
- **Enradigt API** – ett enda anrop sparar projektet som SVG och passar naturligt in i befintliga Java‑pipelines.

## Förutsättningar
- **Java Development Kit (JDK)** – version 8 eller senare. Ladda ner från Oracles webbplats.  
- **Aspose.Tasks för Java** – hämta biblioteket från den officiella nedladdningssidan **[här](https://releases.aspose.com/tasks/java/)**.  

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

> **Pro tip:** Använd en absolut sökväg eller en sökväg relativ till ditt projekts resurser‑mapp för att undvika `FileNotFoundException`.

## Steg 2: Läs in MPP‑filen
Skapa en `Project`‑instans genom att läsa in den befintliga Microsoft Project‑filen.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Den här raden läser *HomeMovePlan.mpp* från den katalog du definierade tidigare.

## Steg 3: Spara projektet som SVG
Nu kan du **exportera MPP till SVG** med ett enda kommando.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Metoden skriver `project5.svg` till samma katalog. Den resulterande SVG‑filen kan öppnas i vilken modern webbläsare som helst eller bäddas in direkt i HTML.

## Vanliga användningsområden
- **Projekt‑instrumentpaneler** – bädda in levande Gantt‑diagram i webbportaler utan att klienten behöver installera Microsoft Project.  
- **Automatiserad rapportering** – generera SVG‑bilder i farten för PDF‑ eller HTML‑rapporter.  
- **Samarbete över team** – dela ett visuellt schema med intressenter som bara behöver en webbläsare för att visa det.

## Vanliga problem och lösningar
| Problem | Orsak | Åtgärd |
|-------|--------|-----|
| **Fil ej hittad** | Felaktig `dataDir`‑sökväg | Kontrollera att katalogsträngen avslutas med en separator (`/` eller `\\`). |
| **Tom SVG‑utdata** | Projektet laddades utan vyer | Säkerställ att MPP‑filen innehåller en Gantt‑vy innan du sparar. |
| **Licensundantag** | Ingen giltig licens tillämpad | Tillämpa en tillfällig licens med `License.setLicense("path/to/license.xml")` innan du anropar `save`. |

## Vanliga frågor

**Q: Är Aspose.Tasks för Java kompatibel med alla versioner av Microsoft Project‑filer?**  
A: Ja, den stödjer MPP, MPT och XML‑format från äldre till de senaste Project‑utgåvorna.

**Q: Kan jag anpassa utseendet på SVG‑utdata?**  
A: Absolut. Använd `SvgOptions` för att ställa in teckensnitt, färger och layoutalternativ innan du anropar `save`.

**Q: Kräver Aspose.Tasks för Java en licens för kommersiell användning?**  
A: Ja, en giltig licens krävs för produktion. Du kan skaffa en tillfällig licens **[här](https://purchase.aspose.com/temporary-license/)**.

**Q: Kan jag prova Aspose.Tasks för Java innan jag köper?**  
A: Ja, en gratis provversion finns **[här](https://purchase.aspose.com/buy)**.

**Q: Var kan jag få support för Aspose.Tasks för Java?**  
A: Besök community‑forumet **[här](https://forum.aspose.com/c/tasks/15)** för att ställa frågor och dela feedback.

## Slutsats
Du vet nu hur du **exporterar MPP till SVG** i Java och effektivt **sparar projekt som SVG** med Aspose.Tasks. Denna funktion låter dig integrera rika projektdiagram i webbportaler, rapport‑instrumentpaneler eller var som helst där skalbara grafik­bilder behövs. Experimentera med `SvgOptions` för att finjustera utdata, så har du ett kraftfullt verktyg i din utvecklingsverktygslåda.

---

**Senast uppdaterad:** 2026-03-27  
**Testad med:** Aspose.Tasks för Java 24.10  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}