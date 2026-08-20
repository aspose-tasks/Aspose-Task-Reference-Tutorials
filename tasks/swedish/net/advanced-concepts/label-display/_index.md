---
date: 2026-03-08
description: Lär dig hur du ställer in etikettvisning och anpassar dagsetiketten i
  projektledning med Aspose.Tasks för .NET, vilket förbättrar läsbarhet och tydlighet.
linktitle: Displaying Labels in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hur man ställer in etikettvisning i Aspose.Tasks för .NET
url: /sv/net/advanced-concepts/label-display/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in etikettvisning i Aspose.Tasks för .NET

## Introduktion

När du bygger en projekt‑hanteringslösning med **Aspose.Tasks for .NET**, är det viktigt att kunna **hur man ställer in etikett**‑alternativ för att göra scheman lätta att läsa. Oavsett om du behöver minut‑för‑minut‑precision eller en hög‑nivå årsöversikt, låter anpassning av etikettvisningen dig presentera tidslinjen exakt på det sätt dina intressenter förväntar sig. I den här handledningen går vi igenom steg‑för‑steg‑processen för att ställa in etikettvisningar för minuter, timmar, dagar, veckor, månader och år, och vi visar också hur du **anpassar dagsetikett**‑formatering för maximal tydlighet.

## Snabba svar
- **Vad betyder “hur man ställer in etikett”?** Det avser konfiguration av `DisplayOptions`‑egenskaperna som styr hur tidsenheter visas i en projektfil.  
- **Vilken etikett kan jag ändra?** Minuter, timmar, dagar, veckor, månader och år kan alla konfigureras.  
- **Behöver jag en licens?** En giltig Aspose.Tasks‑licens krävs för produktionsanvändning; en gratis provversion fungerar för testning.  
- **Stöds detta på .NET Core?** Ja, API‑et fungerar med .NET Core, .NET 5/6 och hela .NET Framework.  
- **Kan jag ändra etiketten vid körning?** Absolut – du kan modifiera visningsalternativen när som helst innan projektet sparas.

## Vad är etikettvisning i Aspose.Tasks?

Etikettvisning bestämmer den textuella representationen av tidsenheter (minut, timme, dag osv.) på Gantt‑diagrammet och tidslinjen. Genom att sätta rätt `DisplayOptions`‑egenskap instruerar du Aspose.Tasks hur dessa enheter ska renderas, vilket kan förbättra projektets läsbarhet avsevärt.

## Varför anpassa etikettvisningar?

- **Förbättrad läsbarhet:** Intressenter kan omedelbart förstå schemats granularitet.  
- **Enhetlig rapportering:** Analyserar den visuella utdata med företagets standarder (t.ex. “Mo” för månader).  
- **Flexibilitet:** Växla mellan detaljerade och övergripande vyer utan att ändra den underliggande schemadatan.

## Förutsättningar

1. **C#‑kunskaper** – grundläggande förståelse för C#‑syntax och .NET‑projektstruktur.  
2. **Aspose.Tasks for .NET** – ladda ner och installera biblioteket från [here](https://releases.aspose.com/tasks/net/).  
3. **Utvecklingsmiljö** – Visual Studio, VS Code eller någon IDE som stödjer .NET‑utveckling.

## Importera namnrymder

Innan du börjar, importera de nödvändiga namnrymderna:

```csharp
using Aspose.Tasks;
using Aspose.Tasks;
```

## Hur man ställer in etikettvisning för minuter

### 1. Visa minutetiketter

För att ange minutetiketten, använd egenskapen `MinuteLabel`:

```csharp
public void WorkWithMinuteLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the minute label is displayed
    project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.M;
}
```

## Hur man ställer in etikettvisning för timmar

### 2. Visa timmetiketter

```csharp
public void WorkWithHourLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the hour label is displayed
    project.DisplayOptions.HourLabel = HourLabelDisplay.H;
}
```

## Anpassa dagsetikettvisning

### 3. Visa dagetiketter

```csharp
public void WorkWithDayLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the day label is displayed
    project.DisplayOptions.DayLabel = DayLabelDisplay.D;
}
```

## Hur man ställer in etikettvisning för veckor

### 4. Visa veckoetiketter

```csharp
public void WorkWithWeekLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the week label is displayed
    project.DisplayOptions.WeekLabel = WeekLabelDisplay.W;
}
```

## Hur man ställer in etikettvisning för månader

### 5. Visa månadsetiketter

```csharp
public void WorkWithMonthLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the month label is displayed
    project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mo;
}
```

## Hur man ställer in etikettvisning för år

### 6. Visa årsetiketter

```csharp
public void WorkWithYearLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the year label is displayed
    project.DisplayOptions.YearLabel = YearLabelDisplay.Y;
}
```

## Vanliga fallgropar & tips

- **Tips:** Sätt alltid etikettvisningen *innan* du sparar projektet; ändringar som görs efter sparning kommer inte att återspeglas i filen.  
- **Fallgrop:** Att använda ett ej‑stött enum‑värde kastar ett `ArgumentException`. Håll dig till de medföljande `*LabelDisplay`‑enum‑värdena.  
- **Tips:** Om du behöver olika etikettstilar för separata vyer, skapa separata `Project`‑instanser eller klona `DisplayOptions`‑objektet.

## Slutsats

Genom att behärska **hur man ställer in etikett**‑alternativ i Aspose.Tasks får du fin‑granulerad kontroll över den visuella presentationen av dina projektscheman. Oavsett om du anpassar dagsetiketten för en daglig scrum‑tavla eller justerar årsetiketten för en flerårs‑färdplan, hjälper dessa inställningar dig att leverera tydligare och mer professionell projektdokumentation.

## Vanliga frågor

### Q1: Kan jag anpassa etikettvisningar för specifika sektioner i ett projekt?

A1: Ja, Aspose.Tasks for .NET möjliggör detaljerad kontroll över etikettvisningar, vilket gör det möjligt att anpassa specifika projektsektioner vid behov.

### Q2: Är Aspose.Tasks kompatibel med populära .NET‑ramverk?

A2: Ja, Aspose.Tasks for .NET är kompatibel med olika .NET‑ramverk, inklusive .NET Core och .NET Framework.

### Q3: Kan jag dynamiskt ändra etikettvisningar baserat på projektkrav?

A3: Absolut, flexibiliteten i Aspose.Tasks for .NET tillåter dynamiska justeringar av etikettvisningar baserat på föränderliga projektkrav.

### Q4: Finns det några begränsningar för anpassning av etikettvisningar?

A4: Aspose.Tasks for .NET erbjuder omfattande anpassningsalternativ för etikettvisningar med minimala begränsningar, vilket ger användarna stor flexibilitet.

### Q5: Stöder Aspose.Tasks integration med andra projektledningsverktyg?

A5: Ja, Aspose.Tasks erbjuder sömlösa integrationsmöjligheter, vilket underlättar interoperabilitet med andra projektledningsverktyg och plattformar.

---

**Senast uppdaterad:** 2026-03-08  
**Testad med:** Aspose.Tasks 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}