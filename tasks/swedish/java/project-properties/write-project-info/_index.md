---
date: 2025-12-31
description: Lär dig hur du ställer in projektets startdatum, skriver projektinformation
  och sparar projektet som XML med Aspose.Tasks för Java.
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ange projektets startdatum i MS Project med Aspose.Tasks för Java
url: /sv/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in projektets startdatum i MS Project med Aspose.Tasks för Java

## Introduktion
I den här handledningen kommer du att upptäcka hur du **ställer in projektets startdatum** och skriver ytterligare MS Project‑information med Aspose.Tasks för Java. Oavsett om du automatiserar projektscheman, genererar rapporter eller integrerar projektdata i ett större system, ger programmatisk kontroll av startdatumet dig exakt styrning över dina tidslinjer. Vi går igenom varje steg—från att konfigurera miljön till att spara det uppdaterade projektet som en XML‑fil—så att du kan börja använda dessa tekniker omedelbart.

## Snabba svar
- **Vad är den primära klassen för att manipulera ett projekt?** `Project` från Aspose.Tasks‑biblioteket.  
- **Hur ställer jag in projektets startdatum?** Använd `project.set(Prj.START_DATE, <date>)`.  
- **Kan jag också sätta statusdatum?** Ja, med `project.set(Prj.STATUS_DATE, <date>)`.  
- **Vilket format ska jag använda för att exportera projektet?** Spara som XML med `SaveFileFormat.Xml`.  
- **Behöver jag en licens för produktionsanvändning?** En giltig Aspose.Tasks‑licens krävs för full funktionalitet.

## Vad är **set project start date**?
Att sätta projektets startdatum definierar kalenderdagen då alla schemalagda uppgifter börjar. Det är ankarnpunkten för beräkningar som uppgiftens varaktighet, beroenden och kritiska vägar. Genom att programatiskt sätta detta datum säkerställer du konsistens över flera projektfiler och eliminerar manuella inmatningsfel.

## Varför använda Aspose.Tasks för Java för att skriva projektinformation?
- **Full API-täckning:** Läs, ändra och skriv varje projekt‑egenskap utan att behöva Microsoft Project installerat.  
- **Plattformsoberoende:** Fungerar på Windows, Linux och macOS.  
- **Automationsklar:** Idealisk för batch‑bearbetning, CI‑pipelines eller backend‑tjänster som genererar projektscheman i realtid.  

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Kit (JDK)** – någon aktuell version (8+ rekommenderas).  
2. **Aspose.Tasks for Java‑biblioteket** – ladda ner det från [here](https://releases.aspose.com/tasks/java/).  
3. **En IDE** – IntelliJ IDEA, Eclipse eller din favoriteditor för Java.  

## Importera paket
Först, importera de nödvändiga paketen i ditt Java‑projekt:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Steg 1: Ställ in datakatalog
Definiera katalogen där dina projektdata kommer att lagras.
```java
String dataDir = "Your Data Directory";
```

## Steg 2: Skapa projektinstans
Initiera en ny projektinstans.
```java
Project project = new Project();
```

## Steg 3: Ställ in projektinformationsegenskaper
Här sätter vi **project start date**, schedule from start och status date—som täcker de primära och sekundära nyckelorden *write project information* och *how to set status*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Steg 4: Spara projekt som XML
Slutligen, spara den uppdaterade projektfilen. Detta demonstrerar det sekundära nyckelordet **save project as xml**.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|--------|-----|
| **Fel startdatum** | Kalendermånaden är nollbaserad i Java. | Använd `Calendar.JULY` (eller lägg till 1 till månadsindex) som visas. |
| **Filen sparas inte** | `dataDir` finns inte eller saknar skrivbehörighet. | Skapa katalogen i förväg eller välj en skrivbar sökväg. |
| **Licensvarning** | Körning utan licens lägger till ett vattenmärke. | Applicera en giltig Aspose.Tasks‑licens innan du skapar `Project`‑objektet. |

## Vanliga frågor
### Q: Kan jag använda Aspose.Tasks för Java för att läsa MS Project‑filer?
A: Ja, Aspose.Tasks för Java erbjuder robusta funktioner för både läsning och skrivning av MS Project‑filer.  
### Q: Är Aspose.Tasks för Java kompatibel med olika versioner av MS Project?
A: Absolut, Aspose.Tasks för Java stödjer olika versioner av MS Project och säkerställer kompatibilitet över olika filformat.  
### Q: Finns det några begränsningar i provversionen av Aspose.Tasks för Java?
A: Även om provversionen låter dig utforska bibliotekets funktioner, har den vissa begränsningar som vattenmärken på utdatafiler.  
### Q: Hur kan jag få support för Aspose.Tasks för Java?
A: Du kan söka hjälp i Aspose.Tasks‑community‑forum [here](https://forum.aspose.com/c/tasks/15).  
### Q: Kan jag köpa en tillfällig licens för Aspose.Tasks för Java?
A: Ja, tillfälliga licenser finns tillgängliga för korttidsanvändning. Du kan skaffa en från [here](https://purchase.aspose.com/temporary-license/).  

## Slutsats
Du har nu lärt dig hur du **ställer in projektets startdatum**, skriver viktig projektinformation och **sparar projekt som XML** med Aspose.Tasks för Java. Dessa byggstenar ger dig möjlighet att automatisera projektledningsarbetsflöden, generera konsekventa scheman och integrera MS Project‑data i dina Java‑applikationer.

---

**Senast uppdaterad:** 2025-12-31  
**Testat med:** Aspose.Tasks for Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}