---
date: 2025-12-23
description: Lär dig hur du skapar MPP‑sammanfattning och uppdaterar projektförfattare
  med Aspose.Tasks för Java. Ställ in och hämta projektinformation enkelt.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man skapar en MPP‑sammanfattning och uppdaterar projektets författare med
  Aspose.Tasks
url: /sv/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skriv MPP-projektsammanfattning i Aspose.Tasks

## Introduktion
I den här handledningen kommer du att **skapa MPP‑sammanfattning** för en Microsoft Project‑fil och lära dig hur du **uppdaterar projektförfattare**‑uppgifter med hjälp av Aspose.Tasks‑biblioteket för Java. Oavsett om du bygger ett projekt‑hanteringsverktyg eller automatiserar rapportering, sparar det att programatiskt styra sammanfattnings‑egenskaper tid och säkerställer konsekvens i dina projekt.

## Snabba svar
- **Vad betyder “create MPP summary”?** Det betyder att ställa in de övergripande projekt‑egenskaperna (författare, revision, nyckelord osv.) som visas i dialogrutan Projekt‑sammanfattningsinformation i Microsoft Project.  
- **Vilket bibliotek hanterar detta?** Aspose.Tasks för Java tillhandahåller ett flytande API för att läsa och skriva dessa egenskaper.  
- **Behöver jag en licens?** En gratis provversion finns tillgänglig, men en kommersiell licens krävs för produktionsanvändning.  
- **Kan jag också ändra författaren efter att filen har sparats?** Ja – du kan **uppdatera projektförfattare** genom att anropa `project.set(Prj.AUTHOR, "New Author")` och sedan spara filen igen.  
- **Vilka filformat stöds?** Både MPP och XML (SaveFileFormat.Xml) stöds fullt ut.

## Vad är create MPP summary?
Att skapa en MPP‑sammanfattning innebär att fylla i projektets metadata – författare, revisionsnummer, nyckelord, kommentarer, skapelsedatum och utskriftsdatum. Denna metadata lagras i posten Projekt‑sammanfattningsinformation och visas i Microsoft Projects **File → Info**‑avsnitt.

## Varför uppdatera projektförfattare?
Att hålla informationen om **projektförfattare** korrekt är avgörande för revisionsspår, samarbete och rapportering. När flera teammedlemmar bidrar kan du behöva **uppdatera projektförfattare** för att återspegla de senaste ändringarna eller för att korrekt tillskriva arbete.

## Förutsättningar
1. Java Development Kit (JDK) installerat på din maskin.  
2. Aspose.Tasks för Java – ladda ner det från [här](https://releases.aspose.com/tasks/java/).  
3. En IDE såsom IntelliJ IDEA, Eclipse eller NetBeans.

## Importera paket
Firstly, import the necessary packages into your Java class:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Steg 1: Ställ in projekt och definiera sammanfattningsinformation
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
I koden ovan **skapar vi MPP‑sammanfattning**‑fält som författare, revision och nyckelord. Du kan också **uppdatera projektförfattare** senare genom att anropa `project.set(Prj.AUTHOR, "New Name")`.

## Steg 2: Spara projekt‑sammanfattningsinformation
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Att spara projektet lagrar all sammanfattningsdata du just definierade.

## Steg 3: Läs projekt‑sammanfattningsinformation
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Detta kodsnutt visar hur du **läser tillbaka** sammanfattningsinformationen och bekräftar att **create MPP summary**‑operationen lyckades.

## Vanliga problem och lösningar
- **Null‑värden efter läsning:** Säkerställ att projektet sparades korrekt innan det laddas om. Kontrollera filsökvägar och behörigheter.  
- **Datumformatskillnader:** `project.get(Prj.CREATION_DATE)` returnerar ett `java.util.Date`. Använd `SimpleDateFormat` om du behöver ett eget visningsformat.  
- **Licens ej satt:** Utan en giltig licens kör Aspose.Tasks i evalueringsläge och kan infoga ett vattenmärke. Registrera din licens tidigt i koden.

## Vanliga frågor
**Q: Kan jag använda Aspose.Tasks för Java med andra Java‑bibliotek?**  
A: Ja, Aspose.Tasks för Java kan sömlöst integreras med andra Java‑bibliotek för att förbättra dina projekt‑hanteringsmöjligheter.

**Q: Finns det en provversion tillgänglig för Aspose.Tasks för Java?**  
A: Ja, du kan ladda ner en gratis provversion från [här](https://releases.aspose.com/).

**Q: Hur ofta uppdateras Aspose.Tasks för Java?**  
A: Aspose.Tasks för Java uppdateras regelbundet för att säkerställa kompatibilitet med de senaste versionerna av Java och Microsoft Project‑filer.

**Q: Kan jag anpassa projekt‑sammanfattningsinformationen ytterligare?**  
A: Absolut, Aspose.Tasks för Java erbjuder omfattande alternativ för att anpassa projekt‑sammanfattningsinformationen enligt dina specifika krav.

**Q: Var kan jag få support för Aspose.Tasks för Java?**  
A: Du kan få support från Aspose.Tasks‑community‑forumet [här](https://forum.aspose.com/c/tasks/15).

## Slutsats
I den här handledningen har vi visat hur du **skapar MPP‑sammanfattning**‑data, **uppdaterar projektförfattare** och verifierar dessa ändringar med Aspose.Tasks för Java. Genom att automatisera dessa steg får du full kontroll över projekt‑metadata, vilket gör dina applikationer mer robusta och dina projekt‑rapporter mer korrekta.

---

**Senast uppdaterad:** 2025-12-23  
**Testat med:** Aspose.Tasks for Java 24.10  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}