---
date: 2026-03-29
description: Lär dig hur du anger nyckelord och ställer in skapelsedatum i ett MPP‑projekt
  med Aspose.Tasks för Java. Steg‑för‑steg‑guide med kodexempel.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man anger nyckelord i MPP-projektsammanfattning med Aspose.Tasks
url: /sv/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man anger nyckelord i MPP-projektsammanfattning med Aspose.Tasks

## Introduktion
I den här handledningen kommer du att upptäcka **hur man anger nyckelord** och annan sammanfattningsinformation för en MPP‑projektfil genom att använda Aspose.Tasks for Java. Oavsett om du behöver bädda in författarinformation, revisionsnummer eller ett anpassat skapandedatum, guidar den här artikeln dig genom de exakta stegen, komplett med färdig‑att‑köra kod. I slutet kommer du att kunna ange nyckelord, ange skapandedatum java och hämta tillbaka data från filen.

## Snabba svar
- **Vilket bibliotek används?** Aspose.Tasks for Java  
- **Primärt syfte?** Ange nyckelord, författarinformation och skapandedatum i en MPP‑fil  
- **Hur många kodsteg?** Tre enkla kodblock (initiera, spara, läs)  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion  
- **Stödd Java-version?** Java 8 och högre  

## Vad är “hur man anger nyckelord” i en MPP‑fil?
Nyckelord är metadatafält som lagras inuti en Microsoft Project‑fil (MPP). De hjälper till att kategorisera projekt, möjliggör snabb sökning och ger kontextuell information för efterföljande verktyg. Aspose.Tasks exponerar egenskapen `Prj.KEYWORDS`, vilket gör det enkelt att skriva eller uppdatera detta värde programmässigt.

## Varför använda Aspose.Tasks for Java för att ange nyckelord och skapandedatum?
* **Full .MPP-kompatibilitet** – fungerar med alla Project 2007‑2023-format.  
* **Ingen COM- eller Office‑installation krävs** – ren Java, perfekt för server‑miljöer.  
* **Rik API** – förutom nyckelord kan du ange författare, revision, kommentarer och datum i ett enda anrop.  
* **Prestandaoptimerad** – snabb läsning/skrivning även för stora projektfiler.

## Förutsättningar
1. **Java Development Kit (JDK)** – JDK 8 eller nyare installerat.  
2. **Aspose.Tasks for Java** – ladda ner den senaste JAR‑filen från [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans eller någon editor du föredrar.

## Importera paket
Först importerar du de klasser du kommer att behöva. Dessa importeringar ger dig åtkomst till `Project`‑objektet, `Prj`‑enumerationen för sammanfattningsfält och `SaveFileFormat`‑enum för sparning.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Steg 1: Ställ in projekt och definiera sammanfattningsinformation
Skapa en `Project`‑instans och använd sedan `set`‑metoden för att skriva den önskade metadata. Lägg märke till hur vi **anger nyckelorden** och **anger skapandedatum java** med ett `Calendar`‑objekt.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Steg 2: Spara projektsammanfattningsinformation
Efter att fälten har fyllts i, persistera ändringarna. Här sparar vi projektet som XML för enkel inspektion, men du kan också spara tillbaka till MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Steg 3: Läs projektsammanfattningsinformation
För att verifiera att metadata har skrivits korrekt, läs in filen igen och läs tillbaka varje egenskap. Detta steg demonstrerar att **hur man anger nyckelord** verkligen fungerar från början till slut.

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
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **NullPointerException on `project.get(Prj.CREATION_DATE)`** | Kalendern sattes aldrig innan sparning. | Se till att du anropar `project.set(Prj.CREATION_DATE, cal.getTime())` innan `save()`. |
| **Keywords not appearing in Microsoft Project UI** | Filen sparades som XML och öppnades direkt i Project. | Spara tillbaka till MPP (`SaveFileFormat.MPP`) eller öppna XML‑filen via *Import* i Project. |
| **Date values shifted by timezone** | Java `Date` innehåller tidszonsinformation. | Använd `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` om du behöver UTC‑datum. |

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks for Java med andra Java‑bibliotek?**  
A: Ja, Aspose.Tasks for Java kan sömlöst integreras med andra Java‑bibliotek för att förbättra dina projektledningsmöjligheter.

**Q: Finns det en provversion tillgänglig för Aspose.Tasks for Java?**  
A: Ja, du kan ladda ner en gratis provversion från [here](https://releases.aspose.com/).

**Q: Hur ofta uppdateras Aspose.Tasks for Java?**  
A: Aspose.Tasks for Java uppdateras regelbundet för att säkerställa kompatibilitet med de senaste versionerna av Java och Microsoft Project‑filer.

**Q: Kan jag anpassa projektsammanfattningsinformationen ytterligare?**  
A: Absolut, Aspose.Tasks for Java erbjuder omfattande alternativ för att anpassa projektsammanfattningsinformationen enligt dina specifika krav.

**Q: Var kan jag få support för Aspose.Tasks for Java?**  
A: Du kan få support från Aspose.Tasks‑community‑forum [here](https://forum.aspose.com/c/tasks/15).

---

**Senast uppdaterad:** 2026-03-29  
**Testat med:** Aspose.Tasks for Java 24.11 (senaste vid skrivande tidpunkt)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}