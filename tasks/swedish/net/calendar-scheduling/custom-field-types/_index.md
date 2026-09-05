---
date: 2026-07-19
description: Lär dig hur du lägger till anpassade fälttyper i Aspose.Tasks för .NET
  med steg‑för‑steg‑kod, förutsättningar och vanliga frågor.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Anpassade fälttyper i Aspose.Tasks
og_description: Lär dig hur du lägger till anpassade fälttyper i Aspose.Tasks för
  .NET. Följ denna steg‑för‑steg‑guide för att skapa, definiera och använda utökade
  attribut effektivt.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Hur man lägger till anpassade fälttyper i Aspose.Tasks för .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Hur man lägger till anpassade fälttyper i Aspose.Tasks för .NET
url: /sv/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till anpassade fälttyper i Aspose.Tasks

## Introduktion

I den här handledningen kommer du att upptäcka **hur man lägger till anpassade fält** i en Microsoft Project‑fil med Aspose.Tasks för .NET. Anpassade fält låter dig lagra ytterligare information—som riskpoäng, avdelningskoder eller anpassade anteckningar—direkt på uppgifter, resurser eller själva projektet. Vi går igenom hela processen, från att sätta upp miljön till att definiera, lägga till och verifiera ett anpassat textfält.

## Snabba svar
- **Vad är ett anpassat fält?** En användardefinierad kolumn som kan innehålla text, siffror, datum eller flaggor på uppgifter/ resurser.  
- **Vilken klass definierar ett anpassat fält?** `ExtendedAttributeDefinition`.  
- **Kan jag lägga till ett anpassat fält i ett befintligt projekt?** Ja—ladda projektet, skapa definitionen, och lägg sedan till den i samlingen.  
- **Behöver jag en licens för Aspose.Tasks?** En licens krävs för produktion; en gratis provversion fungerar för utvärdering.  
- **Stödda .NET‑versioner?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är “how to add custom field” i Aspose.Tasks?
**How to add custom field** avser processen att skapa en `ExtendedAttributeDefinition` och fästa den till ett projekts `ExtendedAttributes`‑samling. Detta gör det möjligt att lagra extra metadata som inte ingår i standard‑Project‑schemat. Den kan användas för uppgifter, resurser eller själva projektet, vilket låter dig fånga information såsom risknivåer, avdelningskoder eller anpassade anteckningar som inte finns i standardfälten.

## Varför använda anpassade fält i projektledning?
Aspose.Tasks stödjer **50+ inbyggda utökade attributtyper** och låter dig definiera **valfritt antal anpassade fält** utan att påverka filstorleken avsevärt. Genom att använda anpassade fält kan du:  
Dessa fält visas som extra kolumner i Microsoft Project och kan refereras i formler, rapporter och filter. De lagras i projektfilen och följer med den, vilket säkerställer att efterföljande verktyg behåller den anpassade datan.

## Förutsättningar

### 1. Visual Studio installerat
Se till att Visual Studio (2019 eller senare) är installerat på din maskin. Du kan ladda ner det från Microsofts webbplats.

### 2. Aspose.Tasks för .NET
Lägg till Aspose.Tasks NuGet‑paketet i ditt projekt. Ladda ner den senaste versionen från [here](https://releases.aspose.com/tasks/net/).

### 3. Grundläggande C#‑kunskaper
Du bör vara bekväm med C#‑syntax, klasser och .NET‑projektstruktur.

## Importera namnrymder

Klasserna `Project`, `ExtendedAttributeDefinition` och relaterade uppräkningar finns i namnrymden `Aspose.Tasks`. Importera den högst upp i din fil:

Namnrymden `Aspose.Tasks` tillhandahåller alla kärntyper för att hantera Microsoft Project‑filer.

```csharp

```

## Hur man lägger till ett anpassat fält i ett projekt?

Läs in det befintliga projektet, skapa en definition för ett anpassat fält och lägg till det i projektets samling av utökade attribut—allt i tre koncisa steg. Detta mönster fungerar för uppgifter, resurser och själva projektet, och det säkerställer att det anpassade fältet sparas när du sparar filen.

### Steg 1: Skapa projektobjekt
`Project` är Aspose.Tasks översta objekt som representerar en enskild Project‑fil i minnet. Att instansiera den läser in filen och ger dig åtkomst till uppgifter, resurser och utökade attribut.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Steg 2: Definiera anpassat fält
`ExtendedAttributeDefinition` beskriver en ny kolumn. I detta exempel skapar vi ett **Text**‑typ anpassat fält för uppgifter och ger det aliaset “MyText”. Enum‑värdet `ExtendedAttributeTask.Text1` talar om för Aspose.Tasks var värdet ska lagras.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Steg 3: Lägg till definition av anpassat fält i projektet
Projektets `ExtendedAttributes`‑samling innehåller alla definitioner av anpassade fält. Att lägga till definitionen gör den tillgänglig för varje uppgift i projektet.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Vanliga problem och lösningar
- **Fältet visas inte i MS Project‑gränssnittet** – Se till att du sätter `Alias`‑egenskapen; MS Project visar aliaset som kolumnrubrik.  
- **Sparande kastar ett undantag** – Verifiera att projektfilen inte är skrivskyddad och att du har en giltig licens.  
- **Anpassade fältvärden försvinner efter omläsning** – Se till att du anropar `project.Save("output.mpp")` efter att ha tilldelat värden till uppgifter.

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks med andra .NET‑ramverk?**  
A: Ja, Aspose.Tasks fungerar med .NET Framework, .NET Core och .NET 5/6/7.

**Q: Är Aspose.Tasks lämplig för företagsapplikationer?**  
A: Absolut. Den stödjer bearbetning av projekt med **upp till 10 000 uppgifter** och kan köras i flertrådade servermiljöer.

**Q: Stöder Aspose.Tasks flera projektfilformat?**  
A: Ja—Aspose.Tasks läser och skriver MPP, XML, HTML och CSV‑format, vilket täcker **alla större Microsoft Project‑versioner**.

**Q: Kan jag manipulera resurser med Aspose.Tasks?**  
A: Ja, du kan lägga till, uppdatera och ta bort resurser, samt tilldela anpassade fält till dem.

**Q: Finns det ett community‑forum för Aspose.Tasks‑användare?**  
A: Ja, du kan besöka [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för att interagera med andra användare och få support från Aspose‑teamet.

---

**Senast uppdaterad:** 2026-07-19  
**Testad med:** Aspose.Tasks 24.12 för .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Behärska definitioner av utökade attribut i MS Project med Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Manipulera utökade attribut i MS Project med Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Fält‑hjälp MS Project‑integration i Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}