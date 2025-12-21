---
date: 2025-12-21
description: Lär dig hur du sparar projekt som mall, exporterar MPP till CSV och konverterar
  MPP till text med Aspose.Tasks för Java.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Spara projekt som mall, CSV och text med Aspose.Tasks för Java
url: /sv/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spara projekt som mall, CSV och text med Aspose.Tasks

## Introduktion
I den här handledningen kommer du att upptäcka **hur man sparar projekt som mall** och även hur du exporterar dina Microsoft Project (MPP)-filer till CSV‑ och ren‑text‑format med Aspose.Tasks‑biblioteket för Java. Oavsett om du behöver skapa en återanvändbar projektmall, generera CSV‑rapporter för analys eller producera enkla textutdrag för integration, så guidar dessa steg dig snabbt och effektivt genom processen.

## Snabba svar
- **Kan jag exportera MPP till CSV?** Ja – använd `project.save(..., SaveFileFormat.CSV)`.  
- **Hur exporterar jag text?** Spara med `SaveFileFormat.TEXT`.  
- **Vad innebär “save project as template”?** Det skapar en `.mpt`‑fil som tar bort faktiska och baslinjevärden, klar för återanvändning.  
- **Behöver jag en licens?** En provversion finns tillgänglig; en kommersiell licens krävs för produktion.  
- **Vilken Java‑version krävs?** Java 8+ stöds.

## Vad innebär “save project as template”?
Att spara ett projekt som en mall (`.mpt`) fångar strukturen, uppgiftshierarkin och resursallokeringarna samtidigt som faktiska start/slut‑datum och baslinjedata tas bort. Detta gör mallen idealisk för att återanvända en standardprojektlayout i flera nya projekt.

## Varför använda Aspose.Tasks för Java?
Aspose.Tasks låter dig manipulera Microsoft Project‑filer utan att installera Microsoft Project själv. Det stöder **hur man exporterar MPP**, **hur man exporterar text** och **konverterar MPP till CSV**, allt från ren Java‑kod, vilket är perfekt för server‑sidig automatisering, CI‑pipelines eller skrivbordsverktyg.

## Förutsättningar
Innan vi börjar, se till att du har:

1. Java Development Kit (JDK) 8 eller högre installerat.  
2. Aspose.Tasks för Java‑biblioteket tillagt i ditt projekt. Ladda ner det från [here](https://releases.aspose.com/tasks/java/).  
3. Grundläggande kunskap om Java‑syntax och Maven/Gradle‑projektuppsättning.

## Importera paket
Först, importera de nödvändiga klasserna i din Java‑källfil:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Spara projekt som CSV (Exportera MPP till CSV)
Att exportera en MPP‑fil till CSV är användbart för dataanalys i Excel eller BI‑verktyg.

### Steg 1: Läs in projektet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Steg 2: Spara som CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Spara projekt som text (Hur man exporterar text)
Om du behöver en ren‑text‑representation av uppgifter, resurser eller allokeringar, spara projektet som en textfil.

### Steg 1: Läs in projektet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Steg 2: Spara som text
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Spara projekt som mall (Skapa projektmall i Java)
Att skapa en återanvändbar mall tar bort faktiska datum och baslinjer, vilket lämnar ett rent skelett för nya projekt.

### Steg 1: Läs in projektet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Steg 2: Ställ in mallalternativ
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Steg 3: Spara som mall
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Vanliga problem och tips
- **File Not Found:** Se till att sökvägen till `YourProject.mpp` är korrekt eller använd en absolut sökväg.  
- **License Exceptions:** Utan en giltig licens körs biblioteket i utvärderingsläge och kan lägga till vattenstämplar. Applicera din licens tidigt i koden (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Large Projects:** För mycket stora MPP‑filer, överväg att öka JVM‑heap‑storleken (`-Xmx2g`) för att undvika `OutOfMemoryError`.

## Slutsats
Vi har gått igenom **hur man sparar projekt som mall**, samt hur man **exporterar MPP till CSV** och **konverterar MPP till text** med Aspose.Tasks för Java. Dessa möjligheter låter dig automatisera hantering av projektdata, skapa återanvändbara mallar och integrera projektinformation i andra system – utan att behöva Microsoft Project installerat.

## Vanliga frågor
### Q: Kan Aspose.Tasks för Java hantera komplexa projektfiler?
A: Absolut! Aspose.Tasks för Java kan hantera projekt av varierande komplexitet med lätthet och erbjuder omfattande stöd för Microsoft Project‑filformat.  
### Q: Finns det en provversion av Aspose.Tasks för Java?
A: Ja, du kan få en gratis provversion av Aspose.Tasks för Java från [here](https://releases.aspose.com/).  
### Q: Var kan jag hitta support för Aspose.Tasks för Java?
A: Du kan besöka [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för hjälp eller frågor kring Aspose.Tasks för Java.  
### Q: Kan jag köpa en tillfällig licens för Aspose.Tasks för Java?
A: Ja, du kan köpa en tillfällig licens från [here](https://purchase.aspose.com/temporary-license/), vilket låter dig utvärdera bibliotekets fulla potential.  
### Q: Är Aspose.Tasks för Java kompatibel med olika operativsystem?
A: Ja, Aspose.Tasks för Java är kompatibel med olika operativsystem, inklusive Windows, macOS och Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2025-12-21  
**Testat med:** Aspose.Tasks for Java 24.12 (senaste)  
**Författare:** Aspose  

---