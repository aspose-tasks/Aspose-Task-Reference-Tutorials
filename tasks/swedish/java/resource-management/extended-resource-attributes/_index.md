---
date: 2026-01-13
description: Lär dig hur du skapar ett anpassat attribut, laddar en Microsoft Project‑fil,
  anger ett numeriskt värde i Java och sparar projektet som XML med Aspose.Tasks för
  Java.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man skapar ett anpassat attribut i MS Project med Aspose.Tasks
url: /sv/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar ett anpassat attribut i MS Project med Aspose.Tasks

## Introduktion
I den här handledningen **kommer du att lära dig hur man skapar ett anpassat attribut** för resurser i en Microsoft Project‑fil med Aspose.Tasks för Java. Vi går igenom att läsa in en Microsoft Project‑fil, definiera ett nytt numeriskt attribut, tilldela ett värde och slutligen spara projektet som XML. I slutet har du ett tydligt, praktiskt exempel som du kan anpassa till dina egna projekt‑hanteringslösningar.

## Snabba svar
- **Vad betyder “custom attribute”?**  
  Ett användardefinierat fält som lagrar extra information (t.ex. Age, Skill Level) för en resurs eller uppgift.  
- **Vilket bibliotek hanterar detta?**  
  Aspose.Tasks for Java tillhandahåller ett flytande API för att skapa och hantera anpassade attribut.  
- **Behöver jag en licens?**  
  En gratis tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Kan jag ange numeriska värden?**  
  Ja – använd `setNumericValue` med en `BigDecimal` (t.ex. `30.5345`).  
- **Hur sparas projektet?**  
  Den modifierade filen kan sparas som XML med `SaveFileFormat.Xml`.

## Vad är ett anpassat attribut?
Ett **custom attribute** (även kallat ett extended attribute) är en extra kolumn som du kan lägga till resurser eller uppgifter i Microsoft Project. Det låter dig samla in data som inte täcks av de inbyggda fälten, såsom anställdas ålder, certifieringsnivå eller någon affärsspecifik mätning.

## Varför skapa ett anpassat attribut i MS Project?
- **Skräddarsy projektdata** efter din organisations behov.  
- **Möjliggör avancerad rapportering** genom att lagra värden som kan frågas senare.  
- **Behåll konsistens** över flera projekt genom att programatiskt tillämpa samma attributdefinition.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Environment** – JDK 8 eller högre installerat.  
2. **Aspose.Tasks for Java** – Ladda ner den senaste versionen från [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA eller någon Java‑kompatibel IDE.  

## Steg‑för‑steg‑guide

### Importera paket
Först importerar du de Aspose.Tasks‑klasser du behöver. Dessa tillhandahåller kärnfunktionaliteten för att hantera projekt, resurser och extended attributes.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### Steg 1: Definiera datakatalog
Ange mappen där din källprojektfil finns och där utdata ska skrivas.

```java
String dataDir = "Your Data Directory";
```

### Steg 2: Läs in Microsoft Project‑fil
Skapa en `Project`‑instans genom att läsa in den befintliga filen. Detta är steget **load Microsoft project file** som ger dig full åtkomst till dess innehåll.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Steg 3: Definiera det anpassade attributet
Vi kommer att definiera ett nytt numeriskt attribut som heter **Age**. API‑et kontrollerar om definitionen redan finns; om den inte finns skapas den.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Steg 4: Ange numeriskt värde i Java
Skapa en instans av attributet för en specifik resurs och tilldela ett numeriskt värde med `setNumericValue`. Detta demonstrerar **set numeric value java** i praktiken.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Steg 5: Lägg till resurs och fäst det anpassade attributet
Lägg till en ny resurs med namnet **R1** och fäst det tidigare skapade anpassade attributet på den.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Steg 6: Spara projekt som XML
Slutligen, beständiga förändringarna genom att spara projektet. Detta är steget **save project as xml**, som producerar en ren XML‑representation av den uppdaterade filen.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Steg 7: Visa resultat
Skriv ut en vänlig bekräftelse så att du vet att processen slutfördes utan fel.

```java
System.out.println("Process completed Successfully");
```

Genom att följa dessa steg har du framgångsrikt **skapat ett anpassat attribut**, läst in en Microsoft Project‑fil, angett ett numeriskt värde med Java och sparat projektet som XML.

## Vanliga fallgropar & tips
- **Attribute ID conflicts:** Kontrollera alltid `getById` innan du skapar en ny definition för att undvika dubbla ID:n.  
- **Precision handling:** `BigDecimal` bevarar decimalprecision; undvik att använda `float` eller `double` för exakta värden.  
- **File paths:** Använd absoluta sökvägar eller konfigurera din IDE:s arbetskatalog för att förhindra `FileNotFoundException`.  

## Vanliga frågor

**Q: Kan jag skapa anpassade attribut för uppgifter såväl som resurser?**  
A: Ja – använd `ExtendedAttributeTask` istället för `ExtendedAttributeResource` när du definierar attributet.

**Q: Är det möjligt att lägga till flera anpassade attribut på en gång?**  
A: Absolut. Skapa separata `ExtendedAttributeDefinition`‑objekt för varje attribut och fäst dem på de önskade resurserna eller uppgifterna.

**Q: Vilka format kan jag spara projektet i?**  
A: Aspose.Tasks stödjer XML, MPP och flera andra format som PDF och HTML. I detta exempel använde vi `SaveFileFormat.Xml`.

**Q: Behöver jag licensiera Aspose.Tasks för utvecklingsbyggen?**  
A: En tillfällig licens räcker för utvärdering. För produktionsdistributioner krävs en full licens.

**Q: Hur läser jag tillbaka de anpassade attributvärdena senare?**  
A: Använd `resource.getExtendedAttributes()` för att iterera över fästa attribut och hämta deras värden med `getNumericValue()` eller `getTextValue()`.

## Slutsats
Att skapa ett **custom attribute** i Microsoft Project med Aspose.Tasks för Java är enkelt när du förstår arbetsflödet: läs in projektet, definiera attributet, ange dess värde, fäst det på en resurs och spara filen. Detta tillvägagångssätt ger dig möjlighet att programatiskt utöka projektdatamodeller, vilket möjliggör rikare rapportering och tätare integration med dina affärsprocesser.

---

**Senast uppdaterad:** 2026-01-13  
**Testat med:** Aspose.Tasks for Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}