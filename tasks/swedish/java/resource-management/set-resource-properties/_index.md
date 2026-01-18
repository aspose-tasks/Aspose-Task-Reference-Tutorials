---
date: 2026-01-18
description: Lär dig hur du ställer in standardpris och andra resursattribut i MS
  Project med Aspose.Tasks för Java, inklusive hur du lägger till resurser i MS Project
  och hanterar resurser effektivt.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man ställer in standardpris för resurser i Aspose.Tasks
url: /sv/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in standardpris för resurser i Aspose.Tasks

## Introduktion
Om du bygger Java‑applikationer som behöver interagera med Microsoft Project‑filer är **inställning av standardpris** för en resurs en av de vanligaste uppgifterna. I den här handledningen kommer du att lära dig hur du **ställer in standardpris** och andra resurs‑egenskaper med Aspose.Tasks för Java. I slutet av guiden kommer du att kunna skapa ett projektobjekt, lägga till en resurs i en MS Project‑fil och hantera MS Project‑resurser med självförtroende.

## Snabba svar
- **Vilken är den primära klassen för att arbeta med en Project‑fil?** `Project`
- **Vilken metod lägger till en ny resurs?** `project.getResources().add()`
- **Hur ställer du in standardpriset?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Behöver jag en licens för produktion?** Ja, en giltig Aspose.Tasks‑licens krävs.
- **Vilken Java‑version stöds?** Java 8+ (senaste JDK rekommenderas).

## Vad är “set standard rate”?
*set standard rate*-operationen tilldelar en standard timkostnad till en resurs. Projektledare använder detta värde för att beräkna arbetskostnader, generera kostnadsrapporter och prognostisera budgetar.

## Varför sätta priser med Aspose.Tasks?
- **Ingen Microsoft Project‑installation behövs** – manipulera filer direkt från Java.
- **Fullständig noggrannhet** – alla resursfält, inklusive övertids- och kostnadspriser, bevaras.
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS.
- **Automatiseringsvänlig** – idealisk för batch‑bearbetning eller integration med CI‑pipelines.

## Förutsättningar
Innan du börjar, se till att du har följande:

### Java‑utvecklingsmiljöinställning
1. **Installera JDK:** Se till att du har Java Development Kit (JDK) installerat på ditt system. Du kan ladda ner det från [Oracle‑webbplatsen](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. **IDE‑inställning:** Välj en Integrated Development Environment (IDE) såsom IntelliJ IDEA, Eclipse eller NetBeans och konfigurera den på din maskin.

### Aspose.Tasks för Java‑installation
1. **Ladda ner Aspose.Tasks för Java:** Gå till [nedladdningssidan](https://releases.aspose.com/tasks/java/) och hämta den senaste versionen av Aspose.Tasks för Java.
2. **Integrera med projektet:** Inkludera Aspose.Tasks för Java‑biblioteket i ditt Java‑projekt genom att lägga till det som en beroende.

## Importera paket
För att börja måste du importera de nödvändiga paketen från Aspose.Tasks för Java till ditt projekt. Detta steg säkerställer att du har tillgång till de funktioner som krävs.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Steg 1: Skapa ett projektobjekt
Att skapa ett **project object** är det första steget för alla MS Project‑manipulationer. Det representerar hela projektfilen i minnet.

```java
Project project = new Project();
```

## Steg 2: Lägg till en resurs (add resource ms project)
Nu kommer vi att **add resource MS Project** med hjälp av Resources‑samlingen. Resursnamnet kan vara vad som helst som passar ditt schema.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Steg 3: Ställ in resurs‑egenskaper (how to set rates)
Här **ställer vi in standardpriset** och demonstrerar också hur man anger ett övertidspris. Dessa priser lagras som `BigDecimal`‑värden för att bevara precisionen.

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
| Priser visas som 0 i den sparade filen | Använder `int` istället för `BigDecimal`. | Använd alltid `BigDecimal.valueOf()` för monetära värden. |
| Licens hittades inte | Licensfilen laddades inte innan `Project` skapades. | Läs in licensen (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) i början av ditt program. |

## Slutsats
Genom att följa dessa steg har du lärt dig hur du **skapar ett projektobjekt**, **lägger till en resurs MS Project** och **ställer in standardpris** samt andra resurs‑egenskaper. Detta ger dig möjlighet att automatisera kostnadsberäkningar, generera anpassade rapporter och fullt hantera MS Project‑resurser från Java.

## FAQ
### Kan Aspose.Tasks för Java hantera komplexa MS Project‑filer?
Ja, Aspose.Tasks för Java kan hantera ett brett spektrum av MS Project‑filformat, inklusive komplexa med omfattande uppgifts‑hierarkier.

### Finns en gratis provversion av Aspose.Tasks för Java?
Ja, du kan få en gratis provversion av Aspose.Tasks för Java från [here](https://releases.aspose.com/).

### Var kan jag hitta support för Aspose.Tasks för Java?
Du kan söka hjälp och delta i diskussioner om Aspose.Tasks för Java på [supportforumet](https://forum.aspose.com/c/tasks/15).

### Hur kan jag få en tillfällig licens för Aspose.Tasks för Java?
Du kan få en tillfällig licens från [temporary license page](https://purchase.aspose.com/temporary-license/) för utvärderingsändamål.

### Var kan jag köpa en licensierad version av Aspose.Tasks för Java?
Du kan köpa en licensierad version av Aspose.Tasks för Java från [purchase page](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2026-01-18  
**Testat med:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Författare:** Aspose