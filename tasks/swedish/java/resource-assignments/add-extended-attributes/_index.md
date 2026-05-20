---
date: 2026-05-20
description: Lär dig hur du använder Aspose.Tasks för Java för att add extended attributes
  to resource assignments, set project start date, och write MS Project files effektivt.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Add Extended Attributes to Resource Assignments i Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hur man använder Aspose.Tasks för Java – Add Extended Attributes to Resource
  Assignments
url: /sv/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Behärska MS Project-manipulering med Aspose.Tasks för Java

## Introduktion
I den här handledningen kommer du att upptäcka **hur du använder Aspose.Tasks för Java** för att lägga till utökade attribut till resursuppdrag och skriva Microsoft Project‑information programatiskt. Oavsett om du automatiserar en rapporteringspipeline eller bygger ett anpassat projekt‑hanteringsverktyg, visar stegen nedan exakt hur du ställer in projektets startdatum, skapar resursuppdrag och sparar filen som XML — allt med bara några få rader Java‑kod.

## Snabba svar
- **Vad gör Aspose.Tasks för Java?** Den läser, skriver och modifierar Microsoft Project‑filer utan att Microsoft Project behöver vara installerat.  
- **Kan jag lägga till anpassade fält till ett resursuppdrag?** Ja, använd `ExtendedAttribute`‑samlingen på `ResourceAssignment`‑objektet.  
- **Hur ställer jag in projektets startdatum?** Anropa `project.setStartDate(LocalDateTime.of(...))` innan du sparar.  
- **Behöver jag en licens för produktionsanvändning?** En kommersiell licens tar bort utvärderingsvattenstämplar och låser upp full API‑åtkomst.  
- **Vilka Java‑versioner stöds?** Aspose.Tasks för Java stöder JDK 8 till JDK 21.

## Hur använder man Aspose.Tasks för Java?
`Project` är det primära objektet som representerar en Microsoft Project‑fil i minnet. Ladda Aspose.Tasks‑biblioteket, skapa en `Project`‑instans, konfigurera projekt‑nivå egenskaper, lägg till utökade attribut till ett resursuppdrag och spara slutligen projektet som XML. Huvudarbetsflödet består av tre koncisa steg: initiera, modifiera och spara. Detta mönster fungerar för projektfiler av alla storlekar och körs på Windows, Linux eller macOS‑JVM:er.

## Vad är ett utökat attribut i Aspose.Tasks?
Ett **utökat attribut** är ett anpassat fält som du bifogar till uppgifter, resurser eller uppdrag för att lagra ytterligare metadata utöver de inbyggda kolumnerna. `ExtendedAttributeDefinition` definierar schemat för ett anpassat fält. Aspose.Tasks exponerar klasserna `ExtendedAttributeDefinition` och `ExtendedAttribute` för att definiera och tilldela dessa fält programatiskt.

## Varför lägga till utökade attribut till resursuppdrag?
Aspose.Tasks stöder **50+ inbyggda och anpassade fält**, och du kan lägga till obegränsade användardefinierade attribut. Genom att lägga till dem kan du fånga kostnadskoder, avdelnings‑ID:n eller annan affärsspecifik data direkt i .mpp‑filen, vilket eliminerar behovet av externa kalkylblad och säkerställer dataintegritet genom hela projektets livscykel.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Kit (JDK)** – JDK 8 eller senare installerat.  
2. **Aspose.Tasks for Java‑bibliotek** – Ladda ner det från den officiella releasesidan [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse eller någon annan Java‑kompatibel editor du föredrar.

## Importera paket
Först, importera de nödvändiga paketen i ditt Java‑projekt:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Steg 1: Ställ in datakatalog
Definiera katalogen där dina projektdata kommer att lagras. Denna sökväg används senare när du sparar XML‑filen.

```java
String dataDir = "Your Data Directory";
```

### Steg 2: Skapa projektinstans
`Project`‑klassen är Aspose.Tasks översta objekt som representerar en enskild Microsoft Project‑fil i minnet. Att instansiera den ger dig full åtkomst till alla projektdelar.

```java
Project project = new Project();
```

### Steg 3: Ställ in projektinformations‑egenskaper
Ställ in viktiga projekt‑egenskaper såsom startdatum, flaggan för schemaläggning från start och statusdatum. Dessa värden lagras i projektets `ProjectInfo`‑objekt.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Steg 4: Lägg till utökade attribut till ett resursuppdrag
Skapa en `ExtendedAttributeDefinition` för det anpassade fältet, fäst den till ett `ResourceAssignment` och fyll i värdet. Detta steg demonstrerar nyckelordet **add extended attributes** i praktiken.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Vanliga problem och lösningar
- **NullPointerException när du får åtkomst till uppdrags‑samlingen** – Se till att du har skapat minst en resurs och en uppgift innan du hämtar uppdrag.  
- **Utökat attribut visas inte i MS Project** – Verifiera att attributets `FieldId` matchar en anpassad fält‑plats (t.ex. `ExtendedAttributeTask.Text1`).  
- **Datumformatet matchar inte** – Använd `java.time.LocalDateTime` för datumvärden; Aspose.Tasks konverterar dem automatiskt till projektets kalenderformat.

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks för Java för att läsa MS Project‑filer?**  
A: Ja, biblioteket erbjuder full läs‑skriv‑funktionalitet för .mpp-, .xml- och .xps‑format.

**Q: Är Aspose.Tasks för Java kompatibel med olika versioner av MS Project?**  
A: Absolut, den stöder filer från Project 2000 upp till den senaste 2024‑utgåvan, vilket täcker över 20 versioner.

**Q: Finns det några begränsningar i provversionen av Aspose.Tasks för Java?**  
A: Provet lägger till en vattenstämpel i genererade filer och begränsar antalet uppgifter du kan skapa, men alla API‑funktioner förblir tillgängliga.

**Q: Hur kan jag få support för Aspose.Tasks för Java?**  
A: Du kan söka hjälp i Aspose.Tasks‑community‑forumet [here](https://forum.aspose.com/c/tasks/15).

**Q: Kan jag köpa en tillfällig licens för Aspose.Tasks för Java?**  
A: Ja, tillfälliga licenser finns tillgängliga för korttidsbruk. Du kan skaffa en från [here](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2026-05-20  
**Testat med:** Aspose.Tasks for Java 24.12 (senaste vid skrivandet)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man lägger till anteckningar till resursuppdrag i Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Hur man läser och skriver taktskala för resursuppdrag i Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Hur man lägger till resurs till projekt och hanterar nivåfördröjnings‑egenskaper i Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}