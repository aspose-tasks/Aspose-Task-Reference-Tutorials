---
date: 2026-04-09
description: Lär dig hur du kontrollerar kretsen och validerar integriteten i Microsoft
  Project‑filer med Aspose.Tasks för .NET.
keywords:
- how to check circuit
- check project structure
- validate microsoft project
- project file integrity check
linktitle: Kontrollera krets i Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hur man kontrollerar krets i Aspose.Tasks
url: /sv/net/calendar-scheduling/check-circuit/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man kontrollerar krets i Aspose.Tasks

## Introduktion

I .NET‑utvecklingens värld är det avgörande att hantera uppgifter och projekt på ett effektivt sätt. **Hur man kontrollerar krets** i en projektfil är ett vanligt krav när du behöver säkerställa integriteten i ett Microsoft Project‑schema. Aspose.Tasks för .NET erbjuder ett enkelt API som låter dig validera projektstrukturen och upptäcka brutna uppgiftshierarkier med bara några rader kod.

## Snabba svar
- **Vad gör “check circuit”?** Den skannar uppgiftshierarkin efter cirkulära referenser eller brutna förälder‑barn‑länkar.  
- **Varför är det viktigt?** Det hjälper till att hålla en ren projektfil och förhindrar beräkningsfel i Microsoft Project.  
- **Vilket bibliotek används?** Aspose.Tasks för .NET.  
- **Behöver jag en licens?** En tillfällig licens krävs för produktion; en gratis provversion fungerar för testning.  
- **Stödda plattformar?** .NET Framework, .NET Core och .NET 5/6+.

## Vad är en projektkretskontroll?

En kretskontroll (ibland kallad en “strukturvalidering”) går igenom varje uppgift från rotuppgiften och verifierar att varje barn pekar tillbaka på en giltig förälder. Om en slinga eller en föräldralös uppgift hittas kastar biblioteket ett `TasksException`, vilket låter dig hantera problemet programatiskt.

## Varför validera Microsoft Project‑filer?

- **Förhindra beräkningsfel:** Cirkulära referenser kan förstöra schemaläggningsberäkningar.  
- **Behålla dataintegritet:** Säkerställer att varje uppgift tillhör en korrekt hierarki.  
- **Automatisera kvalitetskontroller:** Användbart i CI‑pipelines där projektfiler genereras eller modifieras automatiskt.  
- **Spara tid:** Upptäck problem tidigt istället för att felsöka ett trasigt schema i Microsoft Project.

## Förutsättningar

Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:

1. Visual Studio: Se till att du har Visual Studio installerat på ditt system.  
2. Aspose.Tasks för .NET: Ladda ner och installera Aspose.Tasks för .NET‑biblioteket från [here](https://releases.aspose.com/tasks/net/).  
3. Grundläggande C#‑kunskaper: Bekantskap med C#‑programmeringsspråket är nödvändigt för att följa exemplen.

## Importera namnrymder

I ditt C#‑projekt, inkludera följande namnrymder för att få åtkomst till de nödvändiga klasserna och metoderna:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

## Steg 1: Ladda projektfilen

Börja med att ladda Microsoft Project‑filen (.mpp) som du vill kontrollera för en trasig struktur. Använd `Project`‑klassen för att ladda filen.

```csharp
var project = new Project(DataDir + "ParentChildTasks.mpp");
```

## Steg 2: Kontrollera projektstrukturen

För att upptäcka eventuell trasig struktur i projektet använder vi `CheckCircuit`‑klassen tillsammans med `TaskUtils.Apply`‑metoden. Detta steg **kontrollerar projektstrukturen** och kommer att kasta ett undantag om en krets hittas.

```csharp
try
{
    TaskUtils.Apply(project.RootTask, new CheckCircuit(), 0);
}
catch (TasksException ex)
{
    Console.WriteLine(ex);
}
```

## Vanliga fallgropar och tips

- **Fallgrop:** Glömmer du att omsluta anropet i en `try/catch`. `CheckCircuit`‑operationen kastar ett `TasksException` när den hittar ett problem, så hantera det alltid på ett smidigt sätt.  
- **Tips:** Använd `project.RootTask` som startpunkt; att skicka någon annan uppgift kan missa problem längre upp i hierarkin.  
- **Tips:** Efter att ha åtgärdat kretsen kan du köra kontrollen igen för att bekräfta projektfilens integritet.

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks för .NET med andra .NET‑ramverk?**  
A: Ja, Aspose.Tasks för .NET är kompatibel med olika .NET‑ramverk, inklusive .NET Core och .NET Framework.

**Q: Finns det en provversion tillgänglig innan köp?**  
A: Ja, du kan få en gratis provversion av Aspose.Tasks för .NET från [here](https://releases.aspose.com/).

**Q: Hur kan jag få support för Aspose.Tasks för .NET?**  
A: Du kan söka hjälp i Aspose.Tasks community‑forum [here](https://forum.aspose.com/c/tasks/15).

**Q: Behöver jag en tillfällig licens för teständamål?**  
A: Ja, du kan skaffa en tillfällig licens från [here](https://purchase.aspose.com/temporary-license/) för testning.

**Q: Var kan jag köpa Aspose.Tasks för .NET?**  
A: Du kan köpa den fullständiga versionen av Aspose.Tasks för .NET från [here](https://purchase.aspose.com/buy).

## Slutsats

Genom att följa den här guiden har du lärt dig **hur man kontrollerar krets** i ett Aspose.Tasks‑projekt, vilket effektivt validerar projektfilens integritet och säkerställer en ren uppgiftshierarki. Att integrera denna kontroll i din bygg‑ eller importprocess kan spara timmar av manuell felsökning och hålla dina scheman pålitliga.

---

**Senast uppdaterad:** 2026-04-09  
**Testad med:** Aspose.Tasks för .NET (senaste versionen)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}