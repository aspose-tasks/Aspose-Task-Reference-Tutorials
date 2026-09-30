---
date: 2026-09-30
description: Lär dig hur du skapar en utökad uppgiftsattribut med Aspose.Tasks för
  Java, det ledande Java-projektledningsbiblioteket för att lägga till anpassade uppgiftsfält.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Hur man skapar en utökad uppgiftsattribut med Aspose.Tasks Java
og_description: Lär dig hur du skapar en utökad uppgiftsattribut med Aspose.Tasks
  för Java, det ledande Java-projektledningsbiblioteket för att lägga till anpassade
  uppgiftsfält.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Hur man skapar en utökad uppgiftsattribut med Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Hur man skapar en utökad uppgiftsattribut med Aspose.Tasks Java
url: /sv/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur du skapar utökad uppgiftsegenskap med Aspose.Tasks Java

## Introduktion
I den här handledningen kommer du att lära dig hur du **skapar en utökad uppgiftsegenskap** i en Microsoft Project‑fil med hjälp av Aspose.Tasks för Java. Att lägga till anpassade fält låter dig fånga projektspecifik data som inte täcks av de inbyggda kolumnerna, vilket ger dig finare kontroll över rapportering och resursplanering. I slutet av guiden kommer du att kunna lägga till vanlig text, uppslag‑aktiverade och varaktighets‑attribut till vilken uppgift som helst.

## Snabba svar
- **Vad betyder “extended attribute”?** Det är ett anpassat fält som du definierar och fäster på uppgifter, resurser eller tilldelningar.  
- **Vilket bibliotek ger denna funktion?** Aspose.Tasks för Java, ett Java‑projektledningsbibliotek.  
- **Behöver jag en licens för att prova?** Ja – en gratis 30‑dagars provversion finns tillgänglig på Aspose‑webbplatsen.  
- **Kan jag lägga till uppslagsvärden?** Absolut; du kan ange en lista med tillåtna värden för text‑ eller varaktighetsfält.  
- **Är API‑et kompatibelt med Java 8 och senare?** Ja, det stödjer Java 8+ och körs på alla större operativsystem.

## Vad är en utökad uppgiftsegenskap?
En utökad uppgiftsegenskap är en användardefinierad kolumn som lagrar ytterligare information för varje uppgift i en projektfil. Den fungerar som ett inbyggt fält men kan innehålla vilken datatyp du behöver, såsom text, siffror, datum eller varaktigheter.

## Varför använda Aspose.Tasks för Java?
Aspose.Tasks stödjer **över 50 filformat** och kan bearbeta projekt med **över 10 000 uppgifter** utan att Microsoft Project behöver vara installerat. Biblioteket fungerar helt offline, vilket garanterar datasekretess och förutsägbar prestanda för företags‑skala lösningar.

## Förutsättningar
Innan du börjar, se till att du har:

- Grundläggande kunskaper i Java‑programmering.  
- Aspose.Tasks för Java‑biblioteket installerat. Du kan ladda ner det från [webbplatsen](https://releases.aspose.com/tasks/java/).  
- En Java‑IDE (IntelliJ IDEA, Eclipse eller VS Code) installerad på din maskin.

## Importera paket
`import`‑satserna ger dig åtkomst till de kärnklasser du behöver, såsom `Project`, `ExtendedAttributeDefinition` och `ExtendedAttribute`.

`Project` representerar en Microsoft Project‑fil och tillhandahåller metoder för att läsa, ändra och spara den.  
`ExtendedAttributeDefinition` definierar ett anpassat fält som kan fästas på uppgifter, resurser eller tilldelningar.  
`ExtendedAttribute` är en instans av en definition som innehåller det faktiska värdet för en specifik entitet.

## Hur lägger du till ett vanlig‑text utökat attribut till en uppgift?
För att lägga till ett vanlig‑text utökat attribut laddar du först projektet, skapar sedan en definition av typen Text, lägger till den i projektets samling, skapar en uppgift, instansierar attributet från definitionen, sätter dess textvärde, fäster det på uppgiften och sparar slutligen projektet.

### 1. Ange sökvägen till dokumentkatalogen
Ange var dina käll‑ och utdatafiler finns.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Skapa ett nytt projekt
Instansiera ett `Project`‑objekt, eventuellt genom att ladda en befintlig .mpp‑fil.

```java
String dataDir = "Your Document Directory";
```

### 3. Skapa en definition för ett utökat attribut av typen Text1
Definiera det anpassade fältet som en vanlig‑text kolumn med namnet “Text1”.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Lägg till definitionen i projektets samling av utökade attribut
Registrera den nya definitionen så att projektet känner igen den.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Lägg till en uppgift i projektet
Skapa en uppgift som kommer att få det anpassade fältet.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Skapa ett utökat attribut från attributdefinitionen
Generera en instans som du kan binda till en specifik uppgift.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Tilldela ett värde till det genererade utökade attributet
Ange den faktiska text du vill lagra, t.ex. “Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Lägg till det utökade attributet till uppgiften
Fäst attributinstansen till uppgiftens `ExtendedAttributes`‑samling.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Spara projektet
Skriv det uppdaterade projektet tillbaka till disk i önskat format.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Hur lägger du till ett textattribut med en uppslagsalternativ?
När du lägger till ett textattribut med ett uppslag följer du samma steg som för ett vanlig‑text attribut, men innan du lägger till definitionen fyller du dess `LookupValues`‑samling med de tillåtna strängarna. Dessa värden visas som en rullgardinslista i Microsoft Project, vilket säkerställer datakonsistens.

## Hur lägger du till ett varaktighetsattribut med ett uppslagsalternativ?
För att lägga till ett varaktighetsattribut med ett uppslag, ersätt `Text1`‑typen med `Duration2` när du skapar definitionen, fyll sedan `LookupValues`‑samlingen med varaktighetssträngar såsom “1 dag”, “2 dagar” osv. Efter att definitionen har lagts till i projektet, skapa attributinstansen, sätt ett varaktighetsvärde, fäst det till en uppgift och spara filen.

## Vanliga problem och felsökning
- **Uppslagsvärden visas inte** – Se till att du lägger till varje uppslagspost i `LookupValues`‑samlingen *innan* du anropar `project.getExtendedAttributes().add(definition)`.  
- **Attributvärdet sparas inte** – Verifiera att du lägger till `ExtendedAttribute`‑instansen till uppgiften *efter* att du har satt dess värde.  
- **Filstorleken växer oväntat** – När du arbetar med mycket stora projekt, överväg att anropa `project.setSaveOptions(new ProjectSaveOptions())` för att möjliggöra inkrementell sparning.

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks för Java med andra Java‑bibliotek?**  
A: Ja, Aspose.Tasks för Java integreras smidigt med alla Java‑ekosystem, inklusive Spring, Hibernate och Apache POI.

**Q: Är Aspose.Tasks för Java lämplig för storskaliga projektledningsapplikationer?**  
A: Absolut. Biblioteket är konstruerat för att hantera projekt med flera tusen uppgifter och stödjer streaming för att hålla minnesanvändningen låg.

**Q: Finns det några licensieringsaspekter för att använda Aspose.Tasks för Java i ett kommersiellt projekt?**  
A: Ja, du behöver en giltig kommersiell licens. Du kan granska detaljerna på [Aspose.Tasks‑webbplatsen](https://purchase.aspose.com/buy).

**Q: Hur kan jag få support eller hjälp med Aspose.Tasks för Java?**  
A: Besök [Aspose.Tasks‑forumet](https://forum.aspose.com/c/tasks/15) för gemenskapsstöd, eller öppna ett supportärende via ditt Aspose‑konto.

**Q: Kan jag prova Aspose.Tasks för Java innan jag köper?**  
A: Ja, du kan komma åt en gratis provversion på sidan för [Aspose.Tasks‑gratisprov](https://releases.aspose.com/).

---

**Senast uppdaterad:** 2026-09-30  
**Testad med:** Aspose.Tasks for Java 24.10  
**Författare:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Relaterade handledningar

- [Anpassade kolumner och utökade attribut i Java projektledning](/tasks/java/project-management/extended-attributes/)
- [Läs utökade uppgiftsattribut med Aspose.Tasks för Java](/tasks/java/task-properties/extended-task-attributes/)
- [Hur man skapar projekt aspose.tasks – Ställ in nya uppgiftsattribut](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}