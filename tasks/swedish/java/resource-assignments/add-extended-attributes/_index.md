---
date: 2026-01-05
description: Lär dig hur du ställer in projektets startdatum och sparar MS Project
  XML med Aspose.Tasks för Java. Steg‑för‑steg‑guide för Java‑utvecklare.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ange projektets startdatum med Aspose.Tasks för Java
url: /sv/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ange projektets startdatum med Aspose.Tasks för Java

## Introduction
I den här handledningen kommer du att lära dig **hur du anger projektets startdatum** i en Microsoft Project‑fil och sedan **spara MS Project XML** med hjälp av Aspose.Tasks‑biblioteket för Java. Oavsett om du automatiserar en rapporteringspipeline eller bygger ett anpassat projekt‑hanteringsverktyg, kommer behärskning av denna uppgift att spara tid och eliminera manuella fel.

## Quick Answers
- **Vad är den primära metoden för att ange ett startdatum?** Använd `project.set(Prj.START_DATE, …)`.
- **Vilket format ska jag använda för att exportera filen?** Spara den som XML med `SaveFileFormat.Xml`.
- **Behöver jag en licens för denna operation?** En provversion fungerar, men en full licens tar bort vattenstämplar.
- **Kan jag ändra startdatumet efter att ha skapat uppgifter?** Ja, uppdatera projektegenskapen innan du lägger till uppgifter.
- **Är detta kompatibelt med alla MS Project‑versioner?** Aspose.Tasks stödjer XML, MPP och mer.

## What is “Set Project Start Date”?
Att ange projektets startdatum definierar den grundläggande kalendern som alla schemaläggningsberäkningar för uppgifter utgår från. Det är det första steget i att programatiskt bygga ett pålitligt projektschema.

## Why use Aspose.Tasks for Java?
Aspose.Tasks erbjuder ett rent Java‑API som fungerar på alla plattformar utan att Microsoft Project måste vara installerat. Det låter dig skapa, modifiera och exportera projektdata snabbt, vilket gör det idealiskt för server‑sidig automatisering.

## Prerequisites
1. **Java Development Kit (JDK)** – någon nyligen version av JDK.
2. **Aspose.Tasks for Java** – ladda ner från [here](https://releases.aspose.com/tasks/java/).
3. **IDE** – IntelliJ IDEA, Eclipse eller din föredragna Java‑IDE.

## Import Packages
Först importera de nödvändiga klasserna:

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

### Step 1: Set Up Data Directory
Definiera var de genererade filerna ska lagras.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Create a Project Instance
Instansiera ett nytt, tomt projekt.

```java
Project project = new Project();
```

### Step 3: Set Project Information Properties
Här **anger vi projektets startdatum** och relaterade schemaläggningsegenskaper.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Step 4: Save MS Project XML
Exportera det konfigurerade projektet till en XML‑fil.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
- **Felaktigt datumformat:** Säkerställ att du använder `java.util.Calendar` och anropar `getTime()` innan du tilldelar.
- **Filen sparas inte:** Verifiera att `dataDir` pekar på en befintlig, skrivbar mapp.
- **Licensvarningar:** En provversion lägger till vattenstämplar; applicera en giltig licens för att ta bort dem.

## Frequently Asked Questions

### Q: Kan jag använda Aspose.Tasks för Java för att läsa MS Project‑filer?  
**A:** Ja, Aspose.Tasks för Java erbjuder robusta funktioner för både läsning och skrivning av MS Project‑filer.

### Q: Är Aspose.Tasks för Java kompatibel med olika versioner av MS Project?  
**A:** Absolut, Aspose.Tasks för Java stödjer olika MS Project‑format, vilket säkerställer bred kompatibilitet.

### Q: Finns det några begränsningar i provversionen av Aspose.Tasks för Java?  
**A:** Provversionen låter dig utforska biblioteket men lägger till vattenstämplar i utdatafiler.

### Q: Hur kan jag få support för Aspose.Tasks för Java?  
**A:** Du kan söka hjälp i Aspose.Tasks‑community‑forum [here](https://forum.aspose.com/c/tasks/15).

### Q: Kan jag köpa en tillfällig licens för Aspose.Tasks för Java?  
**A:** Ja, tillfälliga licenser finns tillgängliga för korttidsbruk. Skaffa en [here](https://purchase.aspose.com/temporary-license/).

### Q: Bevarar sparande som XML anpassade fält?  
**A:** Ja, när du sparar med `SaveFileFormat.Xml` behålls alla anpassade attribut och utökade fält.

### Q: Kan jag ändra startdatumet efter att ha lagt till uppgifter?  
**A:** Du kan uppdatera startdatumet när som helst innan du sparar; anropa bara `project.set(Prj.START_DATE, …)` igen.

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}