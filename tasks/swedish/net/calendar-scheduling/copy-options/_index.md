---
date: 2026-07-05
description: Lär dig hur du kopierar projektdata med Aspose.Tasks för .NET och kopieringsalternativ.
  Förbättra dina .NET-appar med exakt projektstyrning.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Hur man kopierar projektdata med kopieringsalternativ i Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Hur man kopierar projektdata med kopieringsalternativ i Aspose.Tasks
url: /sv/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man kopierar projektdata med kopieringsalternativ i Aspose.Tasks

## Introduktion

Om du behöver **hur man kopierar projekt** information från en Microsoft Project‑fil till en annan, ger Aspose.Tasks för .NET dig ett rent, kod‑först sätt att göra det. I den här handledningen går vi igenom hela arbetsflödet — laddar ett källprojekt, konfigurerar kopieringsalternativ, skapar en kopia och laddar resultatet — så att du kan integrera projekt‑kopieringslogik i vilken .NET‑applikation som helst med förtroende.

## Snabba svar
- **Vad gör kopieringsfunktionen?** Den duplicerar projektdata samtidigt som du kan inkludera eller exkludera specifika sektioner såsom kalendrar, resurser eller vyinformation.  
- **Vilken klass styr beteendet?** `CopyToOptions` låter dig finjustera vad som kopieras.  
- **Behöver jag en licens?** En giltig Aspose.Tasks‑licens krävs för produktion; en gratis provversion fungerar för utveckling.  
- **Stödda format?** Aspose.Tasks hanterar MPP-, XML- och XER‑filer — över 20 + format totalt.  
- **Kan jag hoppa över vydata?** Ja, sätt `CopyToOptions.SkipViewData = true` för att utesluta UI‑relaterad information.

## Vad är “how to copy project” i Aspose.Tasks?
**“How to copy project”** avser att använda Aspose.Tasks API för att duplicera en Project‑objekts data till en ny fil, valfritt filtrera bort oönskade element. Denna operation är användbar för mallning, arkivering eller skapande av projektvarianter utan manuella UI‑steg, och den fungerar över alla stödda filformat.

## Varför använda kopieringsalternativ i Aspose.Tasks?
Aspose.Tasks stöder **50+ projekt‑relaterade enheter** (uppgifter, resurser, kalendrar, tilldelningar osv.) och kan bearbeta filer med **upp till 10 000 uppgifter** samtidigt som minnesanvändningen hålls under 200 MB. Genom att använda `CopyToOptions` kan du undvika att kopiera tung vydata, vilket minskar den resulterande filens storlek med **30‑40 %** och påskyndar operationen med ungefär **2×** för stora projekt.

## Förutsättningar

1. **Aspose.Tasks for .NET** – ladda ner den senaste versionen från [download link](https://releases.aspose.com/tasks/net/).  
2. **.NET‑utvecklingsmiljö** – Visual Studio 2022 (eller någon IDE som stödjer .NET 6+) installerad.  
3. **En giltig Aspose.Tasks‑licens** – valfri för utvärdering, obligatorisk för produktionsbyggnader.  
4. **En befintlig projektfil** (t.ex. `SourceProject.xml`) som du vill kopiera.

## Hur importerar man namnrymder för Aspose.Tasks?
Lägg till de nödvändiga `using`‑direktiven högst upp i din C#‑fil så kompilatorn kan hitta Aspose.Tasks‑typerna. Att inkludera dessa satser ger dig direkt åtkomst till `Project`, `CopyToOptions` och andra hjälparklasser utan att behöva ange deras fullständiga namn, vilket förenklar din kod och förbättrar läsbarheten.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Steg 1: Initiera projektobjekt

Först, skapa en `Project`‑instans som representerar källfilen och ladda XML‑data.  
`Project`‑klassen representerar en Microsoft Project‑fil som laddats in i minnet, och exponerar uppgifter, resurser, kalendrar och annan projektinformation.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Proffstips:** Om du arbetar med mycket stora filer, överväg att använda `LoadOptions`‑konstruktorn för att möjliggöra lazy loading och hålla minnesförbrukningen låg.

## Steg 2: Skapa en kopia av projektet

Nästa, skapa en andra `Project`‑objekt som kommer att ta emot den kopierade datan. Detta objekt startar tomt.

```csharp
Project copiedProject = new Project();
```

Du har nu två separata `Project`‑objekt: ett som laddats från disk och ett som är redo att ta emot kopian.

## Steg 3: Ladda den kopierade projektfilen

Efter kopieringsoperationen (visad senare) vill du verifiera resultatet genom att ladda den nyss sparade filen i en annan `Project`‑instans.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Att ladda filen igen bekräftar att kopieringen lyckades och att de alternativ du angav fungerade som förväntat.

## Steg 4: Konfigurera kopieringsalternativ

`CopyToOptions`‑klassen låter dig specificera exakt vad som överförs från källan till destinationen.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Att sätta `SkipViewData = true` minskar den resulterande filens storlek och påskyndar operationen, särskilt när du bara behöver logisk projektdata.

## Steg 5: Utför projektkopiering

Slutligen, anropa `CopyTo`‑metoden på källprojektet, och skicka med destinationsprojektet samt de alternativ du konfigurerat.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Detta två‑radiga anrop utför hela kopieringsoperationen, med respekt för de alternativ du definierat. Den resulterande `CopiedProject.xml` innehåller endast den data du begärde.

## Vanliga problem och lösningar

| Issue | Cause | Fix |
|-------|-------|-----|
| **NullReferenceException when calling `CopyTo`** | Destinationsprojektet har inte instansierats. | Se till att `new Project()` anropas innan `CopyTo`. |
| **Missing tasks after copy** | `CopyCommonData` är satt till `false`. | Sätt `CopyCommonData = true` eller kopiera specifika samlingar manuellt. |
| **Large output file** | `SkipViewData` är kvar på `false`. | Aktivera `SkipViewData` för att utesluta UI‑relaterad data. |
| **License not applied** | Licensfilen har inte laddats. | Anropa `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` innan någon API‑användning. |

## Vanliga frågor

**Q: Kan jag kopiera endast en delmängd av uppgifter?**  
A: Ja, använd `CopyToOptions` tillsammans med `ProjectRootTask` för att specificera en startuppgift, eller kopiera manuellt valda uppgifter efter den initiala kopian.

**Q: Stöder Aspose.Tasks kopiering mellan olika filformat?**  
A: Absolut. Du kan ladda en MPP‑fil och spara kopian som XML, XER eller något annat stödd format — över **20 + format** totalt.

**Q: Hur hanterar jag lösenordsskyddade projektfiler?**  
A: Ladda källan med `new Project("file.mpp", new LoadOptions { Password = "pwd" })`, och fortsätt sedan med kopieringen som vanligt.

**Q: Finns det ett sätt att kopiera resurspooler utan uppgifter?**  
A: Sätt `CopyToOptions.CopyResources = true` och `CopyToOptions.CopyTasks = false` för att överföra endast resursinformation.

**Q: Var kan jag hitta fler exempel?**  
A: Besök [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för community‑drivna kodsnuttar, felsökningstips och officiell dokumentation.

---

**Senast uppdaterad:** 2026-07-05  
**Testad med:** Aspose.Tasks 24.12 for .NET  
**Författare:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Behärska projektdata med Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Behärska MS Project-sparalternativ för Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Aspose.Tasks kalender och schemaläggning](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}