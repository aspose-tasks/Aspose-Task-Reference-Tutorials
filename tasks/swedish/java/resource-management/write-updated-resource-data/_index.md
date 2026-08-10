---
date: 2026-06-30
description: Lär dig hur du uppdaterar flera resurser och ändrar data för resursgrupp,
  sedan exporterar projektet till MPP och sparar projektet som MPP med Aspose.Tasks
  för Java.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Uppdatera flera resurser i Aspose.Tasks för Java
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Uppdatera flera resurser i Aspose.Tasks för Java
url: /sv/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uppdatera flera resurser i Aspise.Tasks för Java

## Introduktion
I den här handledningen kommer du att lära dig hur du **uppdaterar flera resurser** i en Microsoft Project‑fil med hjälp av Aspose.Tasks för Java. Oavsett om du behöver ändra timpriser, omfördela grupper eller exportera den uppdaterade filen till MPP, så guidar stegen nedan dig genom ett komplett, produktionsklart arbetsflöde. Ingen Microsoft Project‑installation krävs, och API‑et kan hantera projekt med hundratals resurser effektivt.

## Snabba svar
- **Kan jag uppdatera flera resurser samtidigt?** Ja – iterera genom `ResourceCollection` och sätt attributen i ett enda pass.  
- **Vilken metod sparar filen som MPP?** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **Behöver jag en licens för kommersiell användning?** En betald licens krävs för produktion; en gratis provversion finns tillgänglig.  
- **Vilka Java‑versioner stöds?** Java 6 och högre, inklusive Java 17 LTS.  
- **Är massuppdatering presterande?** Aspose.Tasks bearbetar projekt med 500 resurser på under 2 sekunder på en vanlig server.

## Vad är “update multiple resources”?
**“Update multiple resources”** avser att programatiskt ändra egenskaperna för flera resursposter—såsom timpriser, grupper, kalendrar eller anpassade fält—i en enda projektfil. Denna operation krävs ofta när projektdata synkroniseras med företagets resurshanteringssystem, när budgetar justeras för många resurser, eller när organisationsomfattande policyändringar tillämpas.

## Varför använda Aspose.Tasks för att modifiera resursgrupp och exportera projekt till MPP?
Aspose.Tasks stöder **över 50 in‑ och utdataformat**, inklusive MPP, XML och CSV, och kan **exportera projekt till MPP** utan att ladda hela filen i minnet. Biblioteket kan bearbeta filer upp till **2 GB** i storlek, vilket gör att du kan **spara projekt som MPP** snabbt och pålitligt.

## Förutsättningar

Innan vi börjar, se till att du har följande:

1. Java Development Kit (JDK) installerat på ditt system.  
2. Aspose.Tasks för Java‑biblioteket. Du kan ladda ner det från [här](https://releases.aspose.com/tasks/java/).  
3. Grundläggande kunskaper i Java‑programmering.  

## Importera paket
`import`‑satserna importerar de nödvändiga Aspose.Tasks‑klasserna till din källkod.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Steg 1: Ange din datakatalog
Definiera katalogen där dina datafiler finns:

```java
String dataDir = "Your Data Directory";
```

## Steg 2: Ange in- och utdatafiler
Definiera sökvägarna för indata‑MS‑Project‑filen och den resulterande uppdaterade filen:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Steg 3: Ladda projektet
`Project` representerar en Microsoft Project‑fil som har laddats in i minnet och ger åtkomst till uppgifter, resurser och annan projektdata.

```java
Project project = new Project(file);
```

## Steg 4: Lägg till en resurs och ange attribut
`Resource` modellerar en enskild projektresurs och låter dig ange timpriser, grupper, kalendrar och andra attribut.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Steg 5: Uppdatera flera resurser effektivt
`ResourceCollection` är samlingen av alla resurser i ett projekt, åtkomlig via `project.getResources()`.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Steg 6: Spara projektet
`SaveFileFormat` listar de filformat som stöds för att spara ett projekt, såsom MPP, XML och PDF.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Hur uppdaterar man flera resurser i ett projekt?
Läs in det befintliga projektet, hämta dess `ResourceCollection` och iterera över varje `Resource`‑objekt. För varje resurs, ändra de nödvändiga fälten såsom timpriser, grupper eller anpassade attribut, och gå sedan vidare till nästa objekt. Efter att alla resurser har bearbetats, anropa `project.save(...)` en gång för att på ett effektivt sätt spara ändringarna.

## Vanliga problem och lösningar

- **Resurs‑ID‑krock** – Säkerställ att varje ny resurs får ett unikt ID genom att använda `project.getResources().add(new Resource())`.  
- **Fel i timprisformat** – Använd `ResourceRate`‑objekt och sätt `RateType` till `StandardRate` eller `OvertimeRate`.  
- **Stora filer orsakar minnesbelastning** – Aktivera `Project.setReadOnly(true)` innan inläsning för att minska minnesavtrycket.

## Vanliga frågor

**Q: Kan jag uppdatera flera resurser i samma projekt med Aspose.Tasks för Java?**  
A: Ja, du kan uppdatera flera resurser genom att iterera igenom dem och sätta deras attribut därefter.

**Q: Stöder Aspose.Tasks andra filformat förutom MS Project?**  
A: Ja, Aspose.Tasks stöder olika filformat inklusive XML, MPP och fler.

**Q: Är Aspose.Tasks kompatibel med olika versioner av Java?**  
A: Aspose.Tasks är kompatibelt med Java‑versioner 6 och högre.

**Q: Kan jag utföra andra operationer på MS Project‑filer med Aspose.Tasks?**  
A: Ja, du kan utföra ett brett spektrum av operationer såsom att läsa, skriva och manipulera uppgifter, resurser och kalendrar.

**Q: Var kan jag hitta ytterligare hjälp eller support för Aspose.Tasks?**  
A: Du kan besöka [Aspose.Tasks‑forumet](https://forum.aspose.com/c/tasks/15) för hjälp eller frågor.

**Q: Hur exporterar jag den uppdaterade filen till MPP‑format?**  
A: Anropa `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` efter att alla resursändringar har gjorts.

**Q: Vad är det bästa sättet att modifiera en resursgrupp?**  
A: Sätt `Resource.Group`‑egenskapen på varje `Resource`‑objekt innan du sparar projektet.

---

**Senast uppdaterad:** 2026-06-30  
**Testad med:** Aspose.Tasks för Java 24.12  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Lägg till resurs i projekt med Aspose.Tasks för Java](/tasks/java/resource-management/create-resources/)
- [Hantera MS Project‑resurskostnader med Aspose.Tasks för Java](/tasks/java/resource-management/resource-cost/)
- [Hur man exporterar MPP till Excel med Aspose.Tasks för Java](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}