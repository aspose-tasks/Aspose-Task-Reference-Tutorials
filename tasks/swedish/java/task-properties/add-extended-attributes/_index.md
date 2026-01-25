---
date: 2026-01-25
description: Lär dig hur du lägger till attribut till uppgifter med Aspose.Tasks för
  Java, anpassar Microsoft Project‑filer med utökade attribut för bättre projektstyrning.
linktitle: Add Extended Attributes to Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man lägger till attribut – Lägg till utökade attribut till uppgifter i
  Aspose.Tasks
url: /sv/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till attribut – Lägg till utökade attribut till uppgifter i Aspose.Tasks

## Introduktion
Att förbättra dina projektledningsmöjligheter är avgörande för effektiv uppgiftsspårning och resursförvaltning. I den här handledningen **kommer du att lära dig hur du lägger till attribut** till uppgifter med Aspose.Tasks för Java, vilket ger dig flexibiliteten att anpassa Microsoft Project‑filer efter din organisations specifika behov. Vi går igenom hela processen steg för steg, från att sätta upp miljön till att spara den uppdaterade projektfilen.

## Snabba svar
- **Vad är huvudsyftet?** Att lägga till anpassade (utökade) attribut till uppgifter i en Microsoft Project‑fil.  
- **Vilket bibliotek krävs?** Aspose.Tasks för Java.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens behövs för produktion.  
- **Kan jag lägga till uppslagsvärden?** Ja – du kan skapa text‑ eller varaktighetsattribut med fördefinierade uppslagslistor.  
- **Vilka filformat stöds för sparande?** MPP, XML och andra format som stöds av Aspose.Tasks.

## Förutsättningar
Innan du dyker ner i handledningen, se till att du har följande förutsättningar:
- Grundläggande kunskaper i Java‑programmering.  
- Aspose.Tasks för Java‑biblioteket installerat. Du kan ladda ner det från [webbplatsen](https://releases.aspose.com/tasks/java/).  
- En Java‑integrerad utvecklingsmiljö (IDE) installerad på ditt system.

## Importera paket
I ditt Java‑projekt importerar du de nödvändiga paketen för att få åtkomst till Aspose.Tasks‑funktionerna:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```

Nu bryter vi ner varje exempel i flera steg:

## Hur man lägger till attribut till en uppgift (vanligt textexempel)
### 1. Ange dokumentkatalogen
Definiera först mappen som innehåller din källprojektfil:
```java
String dataDir = "Your Document Directory";
```

### 2. Ladda projektet
Skapa en `Project`‑instans som pekar på en befintlig `.mpp`‑fil:
```java
Project project = new Project(dataDir + "project.mpp");
```

### 3. Definiera ett vanligt text‑utökat attribut
Skapa en attributdefinition av typen **Text1** – detta kommer att hålla stadens namn för varje uppgift:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 4. Lägg till definitionen i projektet
Registrera den nya definitionen i projektets samling av utökade attribut:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 5. Skapa en ny uppgift
Lägg till en underuppgift under rotuppgiften:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 6. Instansiera det utökade attributet
Generera en faktisk attributinstans från den definition du skapade tidigare:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 7. Tilldela ett värde
Ange det konkreta värdet (t.ex. staden “London”) för denna uppgifts utökade attribut:
```java
taskExtendedAttributeText1.setTextValue("London");
```

### 8. Fäst attributet på uppgiften
Lägg till det ifyllda attributet i uppgiftens samling:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

### 9. Spara det uppdaterade projektet
Spara slutligen ändringarna till en ny fil så att du kan verifiera resultatet i Microsoft Project:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Lägga till textattribut med uppslagsalternativ
För att skapa ett textattribut som erbjuder en fördefinierad lista med värden (uppslag), upprepa stegen ovan men ersätt `ExtendedAttributeTask.Text1` med `ExtendedAttributeTask.Text2` och fyll i uppslagstabellen med `taskExtendedAttributeText2Definition.getLookupValues().add(...)`. Detta gör det möjligt för användare att välja från ett fast antal alternativ när de redigerar uppgiften.

## Lägga till varaktighetsattribut med uppslagsalternativ
På samma sätt, för ett varaktighetsbaserat attribut, använd `CustomFieldType.Duration` och `ExtendedAttributeTask.Duration2`. Fyll i uppslagsvärdena med specifika tidsintervall (t.ex. “1 dag”, “2 veckor”) för att standardisera varaktighetsinmatningar i hela projektet.

## Varför använda utökade attribut?
- **Flexibilitet:** Lagra all anpassad data som inte täcks av standardfält i Project.  
- **Standardisering:** Uppslagstabeller säkerställer konsekvent datainmatning.  
- **Rapportering:** Anpassade fält kan inkluderas i rapporter och filter, vilket ger djupare insikter.

## Vanliga problem & felsökning
- **Ogiltig sökväg:** Se till att `dataDir` avslutas med en filseparator (`/` eller `\\`) som passar ditt operativsystem.  
- **Licensundantag:** Utan en giltig licens körs biblioteket i evalueringsläge och kan lägga till vattenstämplar.  
- **Uppslag visas inte:** Efter att ha definierat uppslagsvärden, lägg alltid till definitionen i projektet innan du skapar uppgiftsattribut.

## Vanliga frågor
### Q: Kan jag använda Aspose.Tasks för Java med andra Java‑bibliotek?
A: Ja, Aspose.Tasks för Java kan sömlöst integreras i dina Java‑projekt och fungerar bra med andra Java‑bibliotek.

### Q: Är Aspose.Tasks för Java lämpligt för storskaliga projektledningsapplikationer?
A: Absolut, Aspose.Tasks för Java är designat för att hantera projekt av olika storlekar, inklusive storskaliga applikationer.

### Q: Finns det licensaspekter att beakta när man använder Aspose.Tasks för Java i ett kommersiellt projekt?
A: Ja, se till att granska licensinformationen som finns på [Aspose.Tasks‑webbplatsen](https://purchase.aspose.com/buy).

### Q: Hur får jag support eller hjälp med Aspose.Tasks för Java?
A: Besök [Aspose.Tasks‑forumet](https://forum.aspose.com/c/tasks/15) för community‑support och diskussioner.

### Q: Kan jag prova Aspose.Tasks för Java innan jag köper?
A: Ja, du kan komma åt en gratis provversion [här](https://releases.aspose.com/).

**Ytterligare Q&A**

**Q: Kan jag lägga till flera utökade attribut till en enda uppgift?**  
A: Ja, skapa helt enkelt ytterligare `ExtendedAttribute`‑instanser och lägg till var och en i uppgiftens `ExtendedAttributes`‑samling.

**Q: Stöder uppslagsvärden lokalisering?**  
A: Uppslagsvärden lagras som vanliga strängar, så du kan tillhandahålla lokalanpassad text för varje post vid behov.

## Slutsats
Genom att följa den här steg‑för‑steg‑guiden **har du lärt dig hur du lägger till attribut** till uppgifter i Microsoft Project‑filer med Aspose.Tasks för Java. Denna kraftfulla anpassning låter dig fånga projektspecifik data, förbättra rapportering och upprätthålla konsistens i hela din organisations scheman.

---

**Senast uppdaterad:** 2026-01-25  
**Testat med:** Aspose.Tasks för Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}