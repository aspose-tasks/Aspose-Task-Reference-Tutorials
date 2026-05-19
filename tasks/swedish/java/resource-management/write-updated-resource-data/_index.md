---
date: 2026-01-15
description: Lär dig hur du lägger till resurs i projektet, uppdaterar resursdata
  och sparar projektet som MPP med Aspose.Tasks för Java.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Lägg till resurs till projekt med Aspose.Tasks för Java
url: /sv/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till resurs i projekt med Aspose.Tasks för Java

## Introduktion
I den här praktiska handledningen kommer du att upptäcka **hur man lägger till resurs i projekt** programatiskt med Aspose.Tasks Java API. Vi går igenom hur man laddar en befintlig MS Project XML-fil, infogar en ny resurs, uppdaterar dess egenskaper och slutligen **sparar projektet som MPP**. I slutet har du ett tydligt, återanvändbart mönster som du kan infoga i vilket Java‑baserat rapporterings‑ eller automatiseringsverktyg som helst.

## Snabba svar
- **Vad betyder “add resource to project”?** Det skapar en ny resurspost (personer, utrustning, material) i en Microsoft Project‑fil.  
- **Vilket bibliotek hanterar detta?** Aspose.Tasks for Java – ingen installation av Microsoft Project behövs.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Kan jag konvertera XML till MPP?** Ja – ladda XML‑filen och **spara projektet som MPP** med `project.save(...)`.  
- **Vilken Java‑version krävs?** Java 6 eller senare (Java 8+ rekommenderas).

## Vad är “add resource to project”?
Att lägga till en resurs i ett projekt innebär att infoga en ny rad i resurstabellen i en MS Project‑fil. Denna rad lagrar detaljer såsom namn, kostnadspriser, grupp och anpassade fält som uppgifter senare kan referera till.

## Varför använda Aspose.Tasks för Java?
- **Ingen Microsoft Project‑beroende** – fungerar på alla OS eller CI‑servrar.  
- **Fullständig noggrannhet** – behåller alla inbyggda Project‑funktioner vid konvertering mellan format.  
- **Rik API** – låter dig läsa, skriva och manipulera uppgifter, resurser, kalendrar och mer.

## Förutsättningar
Innan du börjar, se till att du har:

1. Java Development Kit (JDK) 8 eller nyare installerat.  
2. Aspose.Tasks for Java‑bibliotek – ladda ner det från [here](https://releases.aspose.com/tasks/java/).  
3. Grundläggande kunskap om Java‑syntax och Maven/Gradle‑projektuppsättning.

## Importera paket
Lägg till de nödvändiga Aspose.Tasks‑klasserna i din Java‑källfil:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Steg 1: Ställ in din datakatalog
Definiera var käll‑XML‑ och de resulterande MPP‑filerna ska lagras:

```java
String dataDir = "Your Data Directory";
```

## Steg 2: Ange in- och utdatafiler
Peka på XML‑filen du vill konvertera (**convert XML to MPP**) och mål‑MPP‑filen som ska innehålla den nya resursen:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Steg 3: Läs in projektet
Skapa ett `Project`‑objekt från XML‑källan:

```java
Project project = new Project(file);
```

## Steg 4: Lägg till en resurs och ange attribut
Här är där vi **add resource to project** och konfigurerar dess priser och grupp:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*Proffstips:* Du kan upprepa `add`‑anropet i en loop för att **uppdatera flera resurser** i ett enda körning.

## Steg 5: Spara projektet
Slutligen, **save project as MPP** för att spara ändringarna:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Slutsats
Du har just lärt dig **how to add resource to project**, uppdaterat dess egenskaper och **save project as MPP** med Aspose.Tasks för Java. Detta tillvägagångssätt är idealiskt för automatiserade rapporteringspipelines, massimport av resurser eller vilket scenario som helst där du behöver manipulera MS Project‑filer utan skrivbordsapplikationen.

## Vanliga frågor

**Q1: Kan jag uppdatera flera resurser i samma projekt med Aspose.Tasks för Java?**  
A: Ja, iterera över `project.getResources()` eller anropa `add` upprepade gånger, och sätt varje resurs fält efter behov.

**Q2: Stöder Aspose.Tasks andra filformat förutom MS Project?**  
A: Absolut – XML, MPP, MPX, Primavera och fler stöds.

**Q3: Är Aspose.Tasks kompatibelt med olika versioner av Java?**  
A: Biblioteket fungerar med Java 6 och nyare; Java 8+ rekommenderas starkt för bästa prestanda.

**Q4: Kan jag utföra andra operationer på MS Project‑filer med Aspose.Tasks?**  
A: Ja, du kan läsa/skriva uppgifter, kalendrar, tilldelningar, anpassade fält och till och med generera rapporter.

**Q5: Var kan jag hitta ytterligare hjälp eller support för Aspose.Tasks?**  
A: Besök [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för gemenskapsstöd och officiell support.

---

**Senast uppdaterad:** 2026-01-15  
**Testat med:** Aspose.Tasks for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}