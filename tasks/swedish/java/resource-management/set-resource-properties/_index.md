---
date: 2026-08-24
description: Lär dig hur du lägger till resurs ms project, anger standard rate och
  andra resource properties i MS Project med Aspose.Tasks för Java, och hanterar resurser
  effektivt.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Ställ in Resource Properties i Aspose.Tasks
og_description: Lägg till resurs ms project och ange standard rate med Aspose.Tasks
  för Java. Lär dig förutsättningar, steg‑för‑steg kod, och felsökning i denna koncisa
  guide.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Lägg till resurs ms project och ange rate med Aspose.Tasks (Java)
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Hur man lägger till resurs ms project med Aspose.Tasks
url: /sv/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till resurs ms project och ange taxa i Aspose.Tasks

## Introduktion
Om du utvecklar Java‑applikationer som behöver läsa eller skriva Microsoft Project‑filer, **lägga till en resurs ms project** och konfigurera dess standardtaxa är en rutinmässig men viktig uppgift. I den här guiden kommer du att se hur du skapar ett `Project`‑objekt, lägger till en resurs och anger både standard‑ och övertidstaxor med Aspose.Tasks för Java. När du är klar kan du automatisera kostnadsberäkningar och hålla dina projektscheman uppdaterade utan att behöva ha Microsoft Project installerat.

## Snabba svar
- **Vilken klass representerar en Project‑fil?** `Project`
- **Vilket anrop lägger till en ny resurs?** `project.getResources().add()`
- **Hur anger du standardtaxan?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Krävs en licens för produktionsbruk?** Ja, du måste ladda en giltig Aspose.Tasks‑licens.
- **Vilka Java‑versioner stöds?** Java 8 och senare (Java 17+ rekommenderas).

## Vad är “set standard rate”?
Operationen *set standard rate* tilldelar en standard timkostnad till en resurs. Denna taxa används av projektledare för att beräkna arbetskostnader, generera kostnadsrapporter och prognostisera budgetar, vilket säkerställer att kostnadsberäkningarna återspeglar det förväntade priset för arbete som utförs av varje resurs under hela projektets livscykel.

## Varför ange taxor med Aspose.Tasks?
Aspose.Tasks kan bearbeta **över 50 in‑ och utdataformat**, inklusive MPP, MPX, XML och Primavera‑filer, och hanterar projekt med hundratals sidor utan att ladda hela filen i minnet. Detta möjliggör hög‑genomströmning batch‑bearbetning på Windows, Linux eller macOS‑servrar, vilket minskar manuellt arbete med upp till 90 % i typiska automatiseringsscenario.

## Förutsättningar
Innan du börjar, se till att följande är klara:

### Inställning av Java‑utvecklingsmiljö
1. Installera JDK 8 eller nyare. Du kan ladda ner den från den [Oracle‑webbplatsen](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Välj en IDE som IntelliJ IDEA, Eclipse eller NetBeans och konfigurera den för Java‑utveckling.

### Installation av Aspose.Tasks för Java
1. Ladda ner det senaste Aspose.Tasks‑paketet för Java från den [nedladdningssidan](https://releases.aspose.com/tasks/java/).  
2. Lägg till JAR‑filerna i ditt projekts classpath eller deklarera Maven/Gradle‑beroendet enligt produktdokumentationen.

## Importera paket
Importera de grundläggande Aspose.Tasks‑klasserna du behöver. Detta steg ger dig åtkomst till typerna `Project`, `Resource` och `Rsc` som används senare.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Steg 1: skapa ett projektobjekt
`Project`‑klassen är det översta objektet som representerar en hel MS Project‑fil i minnet. Att instansiera den skapar ett tomt projekt som du kan fylla med uppgifter, resurser och annan data.

```java
Project project = new Project();
```

## Steg 2: lägg till en resurs (add resource ms project)
`Resource`‑klassen modellerar en enskild projektresurs, såsom en person, utrustning eller material. Att lägga till en resurs via `project.getResources().add()` returnerar en icke‑null `Resource`‑instans som är klar för egenskapskonfiguration.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Steg 3: ange resursens egenskaper (how to set rates)
`Rsc`‑enumet innehåller konstanter för resursfält såsom `STANDARD_RATE` och `OVERTIME_RATE`.  
Du anger standard‑ och övertidstaxor genom att anropa `set` på `Resource`‑objektet med lämpliga `Rsc`‑enum‑värden. Taxorna lagras som `BigDecimal` för att bevara monetär precision.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|---------|-------------------|--------|
| `NullPointerException` när `set` anropas | Resursen lades inte till korrekt. | Säkerställ att `project.getResources().add()` returnerar en icke‑null `Resource`. |
| Taxor visas som 0 i den sparade filen | Använder `int` istället för `BigDecimal`. | Använd alltid `BigDecimal.valueOf()` för monetära värden. |
| Licens hittades inte | Licensfilen har inte laddats innan `Project` skapas. | Läs in licensen (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) vid programmets start. |

## Slutsats
Du vet nu hur du **lägger till resurs ms project**, skapar ett `Project`‑objekt och **anger standard‑ och övertidstaxor** med Aspose.Tasks för Java. Denna funktionalitet låter dig automatisera kostnadsberäkningar, generera anpassade rapporter och fullt hantera MS Project‑resurser från vilken Java‑applikation som helst.

## Vanliga frågor
**Q: Kan Aspose.Tasks för Java hantera komplexa MS Project‑filer?**  
A: Ja, den stöder alla större Project‑format, inklusive stora filer med tusentals uppgifter och resurser, och bevarar varje fält utan dataförlust.

**Q: Finns en gratis provversion tillgänglig?**  
A: Ja, du kan få en gratis provversion av Aspose.Tasks för Java från den [Aspose.Tasks gratis provversionssida](https://releases.aspose.com/).

**Q: Var kan jag få support för Aspose.Tasks för Java?**  
A: Du kan söka hjälp på [supportforumet](https://forum.aspose.com/c/tasks/15).

**Q: Hur får jag en tillfällig licens för utvärdering?**  
A: En tillfällig licens finns tillgänglig på [tillfällig licens‑sida](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag köpa en licensierad version?**  
A: Köp en full licens från [köpsidan](https://purchase.aspose.com/buy).

---

**Senast uppdaterad:** 2026-08-24  
**Testad med:** Aspose.Tasks för Java 24.12 (senaste vid skrivtillfället)  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skapar resurser – Resurshantering med Aspose.Tasks för Java](/tasks/java/resource-management/)
- [Lägg till resurs i projekt med Aspose.Tasks för Java](/tasks/java/resource-management/create-resources/)
- [Hur man lägger till resurs i projekt och hanterar nivåfördröjningsegenskaper i Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}