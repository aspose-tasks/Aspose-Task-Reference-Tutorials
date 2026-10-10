---
date: 2026-10-10
description: Lär dig hur du lägger till extended attribute i Aspose.Tasks, använder
  evaluation functions och genererar projektrapporter med detta Java-projektledningsbibliotek.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Stöd för Evaluation Functions i Aspose.Tasks-formler
og_description: Lär dig hur du lägger till extended attribute i Aspose.Tasks, använder
  evaluation functions och genererar projektrapporter med detta Java-projektledningsbibliotek.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Hur man lägger till extended attribute i Aspose.Tasks-formler
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Hur man lägger till extended attribute i Aspose.Tasks-formler
url: /sv/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till utökad attribut i Aspose.Tasks-formler

## Introduktion
Aspose.Tasks for Java är ett **Java projektledningsbibliotek** som låter dig generera projektrapporter genom att skapa ett `Project`-objekt i Java och utvärdera Microsoft Project-funktioner direkt i din kod. Genom att bädda in dessa formler kan du köra avancerade beräkningar, skapa anpassade rapporter och automatisera projektanalys utan att lämna din utvecklingsmiljö. I den här handledningen går vi igenom hur man skapar ett projektobjekt, lägger till ett utökat attribut och använder utvärderingsfunktioner för att **add custom field task** data.

## Snabba svar
- **What does “create project object java” mean?** Det skapar en in‑memory `Project`-instans som du kan manipulera programmässigt.  
- **Which library is required?** Aspose.Tasks for Java (download from the official site).  
- **Do I need a license?** En tillfällig eller fullständig Aspose.Tasks-licens krävs för produktionsanvändning; en gratis provversion finns tillgänglig.  
- **Can I use custom fields?** Ja – du kan **add extended attribute** till uppgifter och behandla dem som anpassade fält.  
- **Is this compatible with all Project file formats?** Aspose.Tasks stöder 3 huvudformat (MPP, MPT, XML) och över 50 ytterligare in‑/utmatningsformat.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Environment** – JDK 8+ och en IDE såsom IntelliJ IDEA eller Eclipse.  
2. **Aspose.Tasks for Java Library** – Ladda ner och inkludera biblioteket från [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).

## Importera paket
Lägg till Aspose.Tasks‑namnutrymmet i din Java‑klass så att du kan arbeta med projekt, uppgifter och utökade attribut:

```java
import com.aspose.tasks.*;
```

## Generera projektrapport – create project object java
`Project`‑klassen representerar en Microsoft Project‑fil i minnet och exponerar uppgifter, resurser och anpassade data. Att instansiera denna klass ger dig en behållare för alla projekteelement du kommer att definiera.

```java
Project project = new Project();
```

Raden ovan **creates project object java** som börjar tom och är redo för anpassning.

## Hur man lägger till utökat attribut
`ExtendedAttributeDefinition`‑klassen definierar ett anpassat fält som kan kopplas till uppgifter. För att lägga till ett utökat attribut, skapa en instans av denna klass med typen `Number`, ge den ett alias som “Sine”, lägg till den i projektets `ExtendedAttributes`‑samling och länka den sedan till varje uppgift som kräver det anpassade fältet.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Här **add extended attribute** av typen `Number` med namnet “Sine” och associerar den med uppgifter.

## Lägg till det utökade attributet i projektet
Registrera attributdefinitionen i projektet så att varje uppgift kan referera till den.

```java
project.getExtendedAttributes().add(attr);
```

## Skapa en ny uppgift
`Task` representerar ett arbetsobjekt i projektet och kan innehålla anpassade fält.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Lägg till anpassat fältuppgift i projektet
Koppla det tidigare definierade utökade attributet till den nyss skapade uppgiften, vilket ger uppgiften ett anpassat “Sine”-fält som du kan använda i formler eller beräkningar.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Nu innehåller uppgiften ett anpassat “Sine”-fält som du kan använda i formler eller beräkningar. Detta är också hur du **add custom field task** data programatiskt.

## Varför använda utvärderingsfunktioner?
Utvärderingsfunktioner låter dig bädda in inhemska Microsoft Project‑formler (t.ex. `Sin([Start])`) direkt i Aspose.Tasks, vilket möjliggör beräkningar i farten utan extern bearbetning. Detta håller all projektlogik på ett ställe, minskar data‑synkroniseringsfel och snabbar upp rapportgenerering. Aspose.Tasks stöder utvärdering av över 100 MS Project‑funktioner och erbjuder en omfattande beräkningsmotor i Java.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Formula returns `NaN`** | Verifiera att den anpassade fälttypen matchar den förväntade numeriska typen. |
| **Extended attribute not visible** | Säkerställ att attributdefinitionen läggs till i projektet **before** uppgifter skapas. |
| **License exception** | Installera en tillfällig eller fullständig **Aspose.Tasks license**; provläge kan begränsa vissa funktioner. |
| **Missing temporary license** | Skaffa en **temporary Aspose license** från Aspose‑webbplatsen. |

## Vanliga frågor

**Q: Kan Aspose.Tasks for Java hantera komplexa MS Project‑formler?**  
A: Ja, Aspose.Tasks for Java stöder utvärdering av ett brett spektrum av MS Project‑funktioner, vilket möjliggör komplexa beräkningar inom Java‑applikationer.

**Q: Är Aspose.Tasks for Java kompatibel med olika versioner av Microsoft Project‑filer?**  
A: Ja, Aspose.Tasks for Java stöder olika versioner av Microsoft Project‑filer, inklusive MPP, MPT och XML‑format.

**Q: Kan jag prova Aspose.Tasks for Java innan jag köper?**  
A: Ja, du kan ladda ner en gratis provversion av Aspose.Tasks for Java från webbplatsen [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).

**Q: Hur får jag support för Aspose.Tasks for Java?**  
A: Du kan få support via Aspose.Tasks‑community‑forum [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Finns det en tillfällig licens för Aspose.Tasks for Java?**  
A: Ja, du kan skaffa en tillfällig licens för teständamål från Aspose‑webbplatsen [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

## Slutsats
Genom att följa dessa steg har du lärt dig hur man **create project object**, **add extended attribute**, och utnyttjar utvärderingsfunktioner för att **generate project report** automatiskt. Du kan nu bygga vidare på detta för att skapa rikare projektanalys, anpassade instrumentpaneler eller automatiserade schemaläggningsverktyg – allt drivet av Aspose.Tasks for Java.

---

**Last Updated:** 2026-10-10  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose

## Relaterade handledningar

- [Anpassade kolumner och utökade attribut i Java projektledning](/tasks/java/project-management/extended-attributes/)
- [Läs utökade uppgiftsattribut med Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [Hur man använder Aspose.Tasks for Java – Lägg till utökade attribut till resursuppdrag](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}