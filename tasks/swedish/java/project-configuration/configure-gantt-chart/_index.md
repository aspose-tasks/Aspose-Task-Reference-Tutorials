---
date: 2026-02-13
description: Lär dig hur du skapar en ny aktivitet, ställer in datakatalogen och sparar
  projektet som MPP i Aspose.Tasks Java. Denna steg‑för‑steg‑guide täcker också anpassning
  av tabellfält.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man skapar ny aktivitet och ställer in datakatalog för Aspose.Tasks
url: /sv/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar ny aktivitet & anger datakatalog Aspose.Tasks

## Introduktion
I den här handledningen kommer du att lära dig **hur man anger datakatalog**, hur man **skapar ny aktivitet**, och hur man **sparar projekt som MPP** samtidigt som du konfigurerar Gantt MS Project Chart View i Aspose.Tasks-projekt med Java. Aspose.Tasks är ett robust Java‑API som låter dig manipulera Microsoft Project‑filer programatiskt. I slutet av guiden kommer du att kunna **anpassa tabellfält**, justera datakatalogen och visualisera ditt projekt exakt på det sätt du behöver det.

## Snabba svar
- **Vad är första steget?** Ange sökvägen till datakatalogen där dina projektfiler finns.  
- **Vilket bibliotek krävs?** Aspose.Tasks för Java (nedladdningsbart från den officiella webbplatsen).  
- **Kan jag lägga till anpassade attribut?** Ja – du kan definiera utökade attribut och visa dem i Gantt‑diagrammet.  
- **Behöver jag en licens för testning?** En tillfällig licens finns tillgänglig för utvärderingsändamål.  
- **Vilken IDE fungerar bäst?** Alla Java‑IDE (IntelliJ IDEA, Eclipse, NetBeans) fungerar.

## Vad är “set data directory” och varför är det viktigt?
Att ange datakatalogen talar om för Aspose.Tasks var den ska läsa och skriva projektfiler. Utan en korrekt sökväg kan API:et inte hitta dina `.mpp`‑filer, vilket leder till FileNotFound‑fel. Att definiera denna katalog i början av din kod gör resten av arbetsflödet rent och repeterbart.

## Varför anpassa tabellfält i ett Gantt‑diagram?
Anpassade tabellfält låter dig visa ytterligare information—såsom anpassade attribut, resursdata eller projektspecifika anteckningar—direkt i Gantt‑vyn. Detta gör diagrammet mer informativt för intressenter och minskar behovet av att växla mellan flera rapporter.

## Hur man skapar ny aktivitet?
Att skapa en ny aktivitet (uppgift) är en av de grundläggande operationerna när du bygger eller uppdaterar ett projektschema. Genom att lägga till uppgifter programatiskt kan du automatisera genereringen av komplexa projektplaner, integrera data från andra system eller tillämpa massändringar utan manuell redigering.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Kit (JDK)** – någon nyare version (8+).  
2. **Aspose.Tasks Library** – ladda ner den från [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse eller någon Java‑kompatibel editor du föredrar.

## Importera paket
Först, importera Aspose.Tasks‑namnutrymmet så att du kan arbeta med dess klasser:

```java
import com.aspose.tasks.*;
```

## Steg‑för‑steg guide

### Steg 1: Ställ in datakatalog
Definiera mappen som innehåller dina projektfiler. Detta är steget **set data directory** som handledningen fokuserar på.

```java
String dataDir = "Your Data Directory";
```

Byt ut `"Your Data Directory"` mot den absoluta sökvägen till mappen där `project.mpp` lagras.

### Steg 2: Ladda projektfil
Skapa en `Project`‑instans genom att ladda en befintlig Microsoft Project‑fil.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Steg 3: Lägg till ny aktivitet
Infoga en ny uppgift (aktivitet) i projektets rot. Detta demonstrerar **how to create new activity** programatiskt.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Steg 4: Definiera anpassat attribut
Skapa en definition för ett anpassat attribut som du senare kan fästa på uppgifter.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Steg 5: Lägg till anpassat attribut till uppgift
Tilldela det nydefinierade attributet till den uppgift du skapade.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Steg 6: Anpassa tabell – **customize table fields**
Lägg till det anpassade attributet som en kolumn i Gantt‑diagrammets tabell, ange bredd, titel och justering.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Steg 7: Spara projekt
Spara ändringarna till en ny fil som kan öppnas i Microsoft Project. Detta steg **saves the project as MPP**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **FileNotFoundException** när projektet laddas | Sökvägen **set data directory** är felaktig eller saknar ett avslutande snedstreck. | Verifiera att `dataDir` pekar på exakt rätt mapp och inkludera rätt filseparator (`/` eller `\\`). |
| Anpassat attribut syns inte i Gantt‑vyn | Tabellfältet lades till på fel index eller kolumnbredden är för liten. | Se till att `table.getTableFields().add(3, attrField);` använder ett giltigt index och justera `setWidth` vid behov. |
| LicenseException vid sparning | Ingen giltig licens har tillämpats för produktionsbruk. | Applicera en tillfällig eller permanent licens innan du anropar `project.save()`. |

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks med andra programmeringsspråk?**  
A: Ja, Aspose.Tasks finns tillgängligt för flera programmeringsspråk inklusive .NET, Java och C++.

**Q: Finns det en gratis provversion av Aspose.Tasks?**  
A: Ja, du kan ladda ner en gratis provversion från [here](https://releases.aspose.com/).

**Q: Var kan jag hitta support för Aspose.Tasks?**  
A: Du kan hitta support och ställa frågor på [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Hur kan jag köpa en licens för Aspose.Tasks?**  
A: Du kan köpa en licens från [here](https://purchase.aspose.com/buy).

**Q: Behöver jag en tillfällig licens för teständamål?**  
A: Ja, du kan skaffa en tillfällig licens från [here](https://purchase.aspose.com/temporary-license/).

## Slutsats
Du har nu lärt dig hur man **set data directory**, **create new activity**, definierar och bifogar ett anpassat attribut, och **save project as MPP** medan du **customizing table fields** i en Gantt‑diagramvy med Aspose.Tasks för Java. Dessa steg ger dig full kontroll över hur projektdata visas, vilket gör dina Gantt‑diagram mer informativa och anpassade efter dina intressenters behov.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}