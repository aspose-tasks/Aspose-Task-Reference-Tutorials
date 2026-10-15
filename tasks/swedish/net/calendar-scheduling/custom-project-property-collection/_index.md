---
date: 2026-10-15
description: Lär dig hur du lägger till en anpassad egenskap och hanterar anpassade
  projekt‑egenskaper i Aspose.Tasks för .NET, vilket förbättrar din kontroll över
  projektmetadata.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Hantera samling av anpassade projekt‑egenskaper i Aspose.Tasks
og_description: Lägg till en anpassad egenskap i dina projektfiler med Aspose.Tasks
  för .NET. Denna guide visar hur du hanterar anpassade egenskaper, läser dem och
  lägger till booleska eller strängvärden på ett effektivt sätt.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Lägg till en anpassad egenskap med Aspose.Tasks .NET API för projekt
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Hur man lägger till en anpassad egenskap i Aspose.Tasks för .NET
url: /sv/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så lägger du till en anpassad egenskap i Aspose.Tasks för .NET

## Introduktion

Stöd för anpassade egenskaper låter dig lagra projekt‑specifik metadata som de inbyggda fälten inte täcker. I den här handledningen kommer du att lära dig hur du **lägger till en anpassad egenskap**, läser tillbaka den och hanterar hela samlingen av anpassade egenskaper med Aspose.Tasks för .NET. I slutet kommer du att kunna anpassa projektfiler med Boolean, DateTime, Double och String‑värden som passar dina affärsregler.

## Snabba svar
- **Kan jag lägga till en Boolean‑anpassad egenskap?** Ja – använd `CustomPropertyType.Boolean`.
- **Hur många typer av anpassade egenskaper stöds?** Fyra: Boolean, DateTime, Double, String.
- **Är samlingen av anpassade egenskaper skrivskyddad?** Den kan vara skrivskyddad om projektet laddas från en skrivskyddad källa.
- **Behöver jag en licens för att använda den här funktionen?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.
- **Vilka .NET‑versioner är kompatibla?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är en anpassad egenskap?

En anpassad egenskap är ett användardefinierat metadatafält som du fäster på ett Project‑objekt. Den låter dig lagra extra information såsom “Risknivå”, “Kund‑ID” eller någon Boolean‑flagga som inte täcks av de standardiserade MS‑Project‑fälten.

## Varför lägga till en anpassad egenskap i Aspose.Tasks?

Aspose.Tasks stöder **50+ in‑ och utdataformat** och kan hantera projekt med **upp till 10 000 uppgifter** utan att läsa in hela filen i minnet. Att lägga till anpassade egenskaper låter dig bädda in affärskritisk data direkt i projektfilen, vilket eliminerar behovet av externa databaser och säkerställer att data följer med projektet.

## Förutsättningar

- Visual Studio (valfri nyare edition) installerad på din arbetsstation.  
- Aspose.Tasks för .NET – ladda ner den från [download link](https://releases.aspose.com/tasks/net/).  
- Grundläggande kunskap om C#‑syntax och .NET‑projektstruktur.

## Importera namnrymder

Följande namnrymder ger dig åtkomst till kärnmodellen för projektet och API‑erna för anpassade egenskaper.

```csharp
using Aspose.Tasks;
using System;


```

## Så lägger du till en anpassad egenskap i Aspose.Tasks?

För att lägga till en anpassad egenskap, ladda först projektet, skapa sedan ett `CustomProperty`‑objekt, sätt dess namn, typ och värde, och lägg slutligen till det i projektets `CustomProperties`‑samling. Denna operation bäddar in metadata direkt i projektfilen, och ändringarna sparas när du anropar `project.Save(...)`.  

`CustomProperty` representerar ett enskilt användardefinierat fält som är fäst vid ett projekt.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Steg 1: initiera projekt

`Project` är den primära klassen som representerar en projektfil i Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Steg 2: kontrollera att samlingen av anpassade egenskaper är redo

`CustomProperties` är samlingen som innehåller alla anpassade egenskapsobjekt för ett projekt.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Steg 3: lägg till anpassade egenskaper

`Add`‑metoden infogar en ny anpassad egenskap i projektets samling.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Steg 4: åtkomst till anpassade egenskaper

`CustomProperties`‑samlingen implementerar IEnumerable, vilket möjliggör iteration över varje `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Steg 5: hämta ett värde för en anpassad egenskap

`Get`‑metoden returnerar värdet för en anpassad egenskap baserat på dess namn.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Steg 6: iterera över namn på anpassade egenskaper

`Names`‑egenskapen ger en lista med alla namn på anpassade egenskaper i samlingen.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Steg 7: ta bort eller rensa anpassade egenskaper

`Remove`‑metoden tar bort en specifik egenskap, medan `Clear` tömmer hela samlingen.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Vanliga fallgropar och felsökning

- **Skrivskyddad samling** – Om `project.CustomProperties.IsReadOnly` returnerar `true`, säkerställ att källfilen inte är öppnad med exklusiv läsåtkomst eller kopiera den till en skrivbar plats innan du redigerar.  
- **Typmismatch** – Att tilldela ett värde som inte matchar den deklarerade `CustomPropertyType` kastar ett `ArgumentException`. Sätt alltid `Value` efter att du har definierat rätt `Type`.  
- **Spara ändringar** – Efter att ha lagt till eller tagit bort egenskaper, anropa `project.Save("output.mpp")` för att beständigt lagra förändringarna; annars förblir ändringarna bara i minnet.

## Vanliga frågor

**Q: Kan jag lägga till anpassade egenskaper av någon datatyp i mitt projekt med Aspose.Tasks för .NET?**  
A: Ja, du kan lägga till anpassade egenskaper som stöder Boolean, DateTime, Double och String‑typer.

**Q: Är det möjligt att iterera över namn på anpassade egenskaper i Aspose.Tasks för .NET?**  
A: Absolut, du kan iterera över namn på anpassade egenskaper med hjälp av `Names`‑egenskapen.

**Q: Hur kan jag ta bort en specifik anpassad egenskap från mitt projekt?**  
A: Du kan ta bort en anpassad egenskap genom att ange dess namn med `Remove`‑metoden.

**Q: Ger Aspose.Tasks för .NET stöd för tillfälliga licenser?**  
A: Ja, du kan erhålla en tillfällig licens från Aspose‑webbplatsen för utvärderingsändamål.

**Q: Var kan jag hitta support eller ytterligare hjälp angående Aspose.Tasks för .NET?**  
A: Du kan besöka Aspose.Tasks‑forumet [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för frågor eller assistans.

---

**Senast uppdaterad:** 2026-10-15  
**Testad med:** Aspose.Tasks 24.11 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man läser inbyggda projektegenskaper med Aspose.Tasks för .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Hantera MS Project‑attributsamling i Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Aspose.Tasks anpassade fälttyper – Kalender och schemaläggning](/tasks/net/calendar-scheduling/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}