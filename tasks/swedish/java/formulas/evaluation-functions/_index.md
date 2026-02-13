---
date: 2026-02-13
description: Lär dig hur du genererar projektrapport genom att skapa ett projektobjekt
  i Java, lägga till utökade attribut och använda utvärderingsfunktioner med Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Generera projektrapport – Skapa projektobjekt Java
url: /sv/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stöd för utvärderingsfunktioner i Aspose.Tasks-formler

## Introduktion
Aspose.Tasks for Java låter dig **generate project report** genom att skapa ett **project object** i Java och utvärdera Microsoft Project-funktioner direkt i din kod. Genom att bädda in dessa formler kan du köra avancerade beräkningar, skapa anpassade rapporter och automatisera projektanalys utan att lämna din utvecklingsmiljö. I den här handledningen går vi igenom hur du skapar ett projektobjekt, lägger till ett utökat attribut och använder utvärderingsfunktioner för att **add custom field task** data.

## Snabba svar
- **Vad betyder “create project object java”?** Det skapar en `Project`‑instans i minnet som du kan manipulera programmässigt.  
- **Vilket bibliotek krävs?** Aspose.Tasks for Java (ladda ner från den officiella webbplatsen).  
- **Behöver jag en licens?** En tillfällig eller fullständig Aspose.Tasks‑licens krävs för produktionsanvändning; en gratis provversion finns tillgänglig.  
- **Kan jag använda anpassade fält?** Ja – du kan **add extended attribute** till uppgifter och behandla dem som anpassade fält.  
- **Är detta kompatibelt med alla Project‑filformat?** Aspose.Tasks stödjer MPP-, MPT- och XML‑format.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java‑utvecklingsmiljö** – JDK 8+ och en IDE som IntelliJ IDEA eller Eclipse.  
2. **Aspose.Tasks for Java‑bibliotek** – Ladda ner och inkludera biblioteket från den [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).

## Importera paket
Lägg till Aspose.Tasks‑namnutrymmet i din Java‑klass så att du kan arbeta med projekt, uppgifter och utökade attribut:

```java
import com.aspose.tasks.*;
```

## Generera projektrapport – Create Project Object Java
Instansiera ett nytt `Project`‑objekt. Detta fungerar som behållare för alla uppgifter, resurser och anpassade data du kommer att definiera.

```java
Project project = new Project();
```

Raden ovan **creates project object java** som startar tom och är redo för anpassning.

## Hur man lägger till ett utökat attribut
Definiera ett utökat attribut som kommer att lagra anpassade numeriska data (t.ex. ett sinusvärde) för varje uppgift.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Här **add extended attribute** av typen `Number` med namnet “Sine” och associerar det med uppgifter.

## Lägg till det utökade attributet i projektet
Registrera attributdefinitionen i projektet så att varje uppgift kan referera till den.

```java
project.getExtendedAttributes().add(attr);
```

## Skapa en ny uppgift
Lägg till en enkel uppgift med namnet “Task” under rotuppgiften i projektet.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Koppla det utökade attributet till uppgiften
Koppla det tidigare definierade utökade attributet till den nyss skapade uppgiften.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Nu innehåller uppgiften ett anpassat “Sine”-fält som du kan använda i formler eller beräkningar. Detta är också hur du **add custom field task** data programatiskt.

## Varför använda utvärderingsfunktioner?
- Utför beräkningar i farten (t.ex. `Sin([Start])`) utan externa verktyg.  
- Behåll all projektlogik i en enda, underhållbar kodbas.  
- Generera dynamiska rapporter som återspeglar realtidsdatabearbetningar, vilket hjälper dig att **generate project report** automatiskt.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Formula returns `NaN`** | Verifiera att den anpassade fälttypen matchar den förväntade numeriska typen. |
| **Extended attribute not visible** | Säkerställ att attributdefinitionen läggs till i projektet **before** skapa uppgifter. |
| **License exception** | Installera en tillfällig eller fullständig **Aspose.Tasks license**; provläget kan begränsa vissa funktioner. |
| **Missing temporary license** | Skaffa en **temporary Aspose license** från Aspose‑webbplatsen. |

## Vanliga frågor

**Q: Kan Aspose.Tasks for Java hantera komplexa MS Project‑formler?**  
A: Ja, Aspose.Tasks for Java stödjer utvärdering av ett brett spektrum av MS Project‑funktioner, vilket möjliggör komplexa beräkningar i Java‑applikationer.

**Q: Är Aspose.Tasks for Java kompatibel med olika versioner av Microsoft Project‑filer?**  
A: Ja, Aspose.Tasks for Java stödjer olika versioner av Microsoft Project‑filer, inklusive MPP-, MPT- och XML‑format.

**Q: Kan jag prova Aspose.Tasks for Java innan jag köper?**  
A: Ja, du kan ladda ner en gratis provversion av Aspose.Tasks for Java från webbplatsen [here](https://purchase.aspose.com/buy).

**Q: Hur kan jag få support för Aspose.Tasks for Java?**  
A: Du kan få support via Aspose.Tasks‑community‑forumet [here](https://forum.aspose.com/c/tasks/15).

**Q: Finns det en tillfällig licens tillgänglig för Aspose.Tasks for Java?**  
A: Ja, du kan skaffa en tillfällig licens för teständamål från Aspose‑webbplatsen [here](https://purchase.aspose.com/temporary-license/).

## Slutsats
Genom att följa dessa steg har du lärt dig hur du **create project object**, **add extended attribute**, och utnyttjar utvärderingsfunktioner för att **generate project report** automatiskt. Du kan nu bygga vidare på detta fundament för att skapa mer avancerad projektanalys, anpassade instrumentpaneler eller automatiserade schemaläggningsverktyg – allt drivet av Aspose.Tasks for Java.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}