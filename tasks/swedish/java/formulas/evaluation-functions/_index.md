---
date: 2025-12-09
description: Lär dig hur du skapar ett projektobjekt i Java och stödjer evalueringsfunktioner
  i Aspose.Tasks‑formler med Java. Upptäck hur du skapar ett utökat attribut för uppgifter.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Skapa projektobjekt i Java – Stöd för utvärderingsfunktioner i Aspose.Tasks
url: /sv/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stöd för utvärderingsfunktioner i Aspose.Tasks-formler

## Introduktion
Aspose.Tasks for Java låter dig **create project object java** instanser och utvärdera Microsoft Project-funktioner direkt i din Java‑kod. Genom att bädda in dessa formler kan du köra avancerade beräkningar, generera anpassade rapporter och automatisera projektanalys utan att lämna din utvecklingsmiljö. Denna handledning guidar dig genom hela processen – från att konfigurera projektobjektet till att lägga till ett utökat attribut som kan innehålla anpassade data.

## Snabba svar
- **What does “create project object java” mean?** Det skapar en in‑memory `Project`‑instans som du kan manipulera programatiskt.  
- **Which library is required?** Aspose.Tasks for Java (ladda ner från den officiella webbplatsen).  
- **Do I need a license?** En tillfällig eller fullständig licens krävs för produktionsbruk; en gratis provversion finns tillgänglig.  
- **Can I use custom fields?** Ja – du kan definiera och bifoga utökade attribut till uppgifter.  
- **Is this compatible with all Project file formats?** Aspose.Tasks stödjer MPP-, MPT- och XML‑format.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Environment** – JDK 8+ och en IDE såsom IntelliJ IDEA eller Eclipse.  
2. **Aspose.Tasks for Java Library** – Ladda ner och inkludera biblioteket från [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).

## Importera paket
Lägg till Aspose.Tasks‑namnrymden i din Java‑klass så att du kan arbeta med projekt, uppgifter och utökade attribut:

```java
import com.aspose.tasks.*;
```

## Steg 1: Skapa projektobjekt Java
Instansiera ett nytt `Project`‑objekt. Detta kommer att fungera som behållare för alla uppgifter, resurser och anpassade data du definierar.

```java
Project project = new Project();
```

Raden ovan **creates project object java** som startar tom och är redo för anpassning.

## Steg 2: Hur man skapar ett utökat attribut
Definiera ett utökat attribut som kommer att lagra anpassade numeriska data (t.ex. ett sinusvärde) för varje uppgift.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Här **create extended attribute** av typen `Number` med namnet “Sine” och associerar det med uppgifter.

## Steg 3: Lägg till det utökade attributet i projektet
Registrera attributdefinitionen i projektet så att varje uppgift kan referera till den.

```java
project.getExtendedAttributes().add(attr);
```

## Steg 4: Skapa en ny uppgift
Lägg till en enkel uppgift med namnet “Task” under rotuppgiften i projektet.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Steg 5: Koppla det utökade attributet till uppgiften
Länka det tidigare definierade utökade attributet till den nyss skapade uppgiften.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Nu innehåller uppgiften ett anpassat “Sine”-fält som du kan använda i formler eller beräkningar.

## Varför använda utvärderingsfunktioner?
Att bädda in MS Project‑funktioner i Aspose.Tasks‑formler gör det möjligt att:

- Utföra beräkningar i farten (t.ex. `Sin([Start])`) utan externa verktyg.  
- Hålla all projektlogik i en enda, underhållbar kodbas.  
- Generera dynamiska rapporter som återspeglar realtidsdataförändringar.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Formula returns `NaN`** | Verifiera att den anpassade fälttypen matchar den förväntade numeriska typen. |
| **Extended attribute not visible** | Säkerställ att attributdefinitionen läggs till i projektet **innan** du skapar uppgifter. |
| **License exception** | Installera en tillfällig eller fullständig licens; provläge kan begränsa vissa funktioner. |

## Vanliga frågor

**Q: Kan Aspose.Tasks for Java hantera komplexa MS Project‑formler?**  
A: Ja, Aspose.Tasks for Java stödjer utvärdering av ett brett spektrum av MS Project‑funktioner, vilket möjliggör komplexa beräkningar i Java‑applikationer.

**Q: Är Aspose.Tasks for Java kompatibel med olika versioner av Microsoft Project‑filer?**  
A: Ja, Aspose.Tasks for Java stödjer olika versioner av Microsoft Project‑filer, inklusive MPP-, MPT- och XML‑format.

**Q: Kan jag prova Aspose.Tasks for Java innan jag köper?**  
A: Ja, du kan ladda ner en gratis provversion av Aspose.Tasks for Java från webbplatsen [here](https://purchase.aspose.com/buy).

**Q: Hur får jag support för Aspose.Tasks for Java?**  
A: Du kan få support via Aspose.Tasks‑community‑forumet [here](https://forum.aspose.com/c/tasks/15).

**Q: Finns det en tillfällig licens för Aspose.Tasks for Java?**  
A: Ja, du kan skaffa en tillfällig licens för teständamål från Aspose‑webbplatsen [here](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2025-12-09  
**Testad med:** Aspose.Tasks for Java 24.10  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}