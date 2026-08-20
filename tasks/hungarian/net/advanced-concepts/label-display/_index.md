---
date: 2026-03-08
description: Tanulja meg, hogyan állíthatja be a címke megjelenítését és testreszabhatja
  a napcímkét a projektmenedzsmentben az Aspose.Tasks for .NET használatával, javítva
  az olvashatóságot és a tisztaságot.
linktitle: Displaying Labels in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hogyan állítsuk be a címke megjelenítését az Aspose.Tasks for .NET-ben
url: /hu/net/advanced-concepts/label-display/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a címke megjelenítését az Aspose.Tasks for .NET-ben

## Bevezetés

Amikor projektmenedzsment megoldást építesz a **Aspose.Tasks for .NET** használatával, a **címke beállítása** opciók ismerete elengedhetetlen a menetrendek könnyen olvashatóvá tételéhez. Akár perc‑perces pontosságra, akár magas szintű éves nézetre van szükséged, a címke megjelenítés testreszabása lehetővé teszi, hogy a idővonalat pontosan úgy mutasd be, ahogy a résztvevők elvárják. Ebben az útmutatóban lépésről‑lépésre bemutatjuk a címke megjelenítésének beállítását percek, órák, napok, hetek, hónapok és évek esetén, valamint megmutatjuk, hogyan **testreszabhatod a napcímke** formázását a maximális érthetőség érdekében.

## Gyors válaszok
- **Mi jelent a “címke beállítása”?** A `DisplayOptions` tulajdonságok konfigurálására utal, amelyek szabályozzák, hogyan jelennek meg az időegységek egy projektfájlban.  
- **Melyik címkét változtathatom meg?** A percek, órák, napok, hetek, hónapok és évek mind konfigurálhatók.  
- **Szükségem van licencre?** Érvényes Aspose.Tasks licenc szükséges a termelésben való használathoz; egy ingyenes próba verzió teszteléshez elegendő.  
- **Támogatott a .NET Core-on?** Igen, az API működik .NET Core, .NET 5/6 és a teljes .NET Framework környezetben.  
- **Módosíthatom a címkét futásidőben?** Természetesen – a megjelenítési beállításokat bármikor módosíthatod a projekt mentése előtt.

## Mi az a címke megjelenítés az Aspose.Tasks-ben?

A címke megjelenítés határozza meg az időegységek (perc, óra, nap stb.) szöveges ábrázolását a Gantt-diagramon és az időskálán. A megfelelő `DisplayOptions` tulajdonság beállításával megmondod az Aspose.Tasks-nek, hogyan jelenítse meg ezeket az egységeket, ami jelentősen javíthatja a projekt olvashatóságát.

## Miért testreszabjuk a címke megjelenítéseket?

- **Javított olvashatóság:** A résztvevők azonnal megérthetik a menetrend részletességét.  
- **Következetes jelentés:** Összhangba hozza a vizuális kimenetet a vállalati szabványokkal (például a „Mo” használata a hónapokhoz).  
- **Rugalmasság:** Váltás a részletes és a magas szintű nézetek között anélkül, hogy módosítanád a háttérben lévő ütemezési adatokat.

## Előfeltételek

1. **C# ismeretek** – alapvető ismeretek a C# szintaxisról és a .NET projekt felépítéséről.  
2. **Aspose.Tasks for .NET** – töltsd le és telepítsd a könyvtárat innen: [here](https://releases.aspose.com/tasks/net/).  
3. **Fejlesztői környezet** – Visual Studio, VS Code vagy bármely IDE, amely támogatja a .NET fejlesztést.

## Névterek importálása

Mielőtt elkezdenéd, importáld a szükséges névtereket:

```csharp
using Aspose.Tasks;
using Aspose.Tasks;
```

## Hogyan állítsuk be a címke megjelenítését percekhez

### 1. Perccímkék megjelenítése

A perccímke beállításához használd a `MinuteLabel` tulajdonságot:

```csharp
public void WorkWithMinuteLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the minute label is displayed
    project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.M;
}
```

## Hogyan állítsuk be a címke megjelenítését órákhoz

### 2. Óracímkék megjelenítése

```csharp
public void WorkWithHourLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the hour label is displayed
    project.DisplayOptions.HourLabel = HourLabelDisplay.H;
}
```

## A napcímke megjelenítésének testreszabása

### 3. Napcímkék megjelenítése

```csharp
public void WorkWithDayLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the day label is displayed
    project.DisplayOptions.DayLabel = DayLabelDisplay.D;
}
```

## Hogyan állítsuk be a címke megjelenítését hetekhez

### 4. Heticímkék megjelenítése

```csharp
public void WorkWithWeekLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the week label is displayed
    project.DisplayOptions.WeekLabel = WeekLabelDisplay.W;
}
```

## Hogyan állítsuk be a címke megjelenítését hónapokhoz

### 5. Hónapcímkék megjelenítése

```csharp
public void WorkWithMonthLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the month label is displayed
    project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mo;
}
```

## Hogyan állítsuk be a címke megjelenítését évekhez

### 6. Évcímkék megjelenítése

```csharp
public void WorkWithYearLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the year label is displayed
    project.DisplayOptions.YearLabel = YearLabelDisplay.Y;
}
```

## Gyakori buktatók és tippek

- **Tipp:** Mindig állítsd be a címke megjelenítést *a projekt mentése előtt*; a mentés után végzett módosítások nem jelennek meg a fájlban.  
- **Buktató:** Nem támogatott enum érték használata `ArgumentException`-t dob. Tartsd magad a biztosított `*LabelDisplay` enumokhoz.  
- **Tipp:** Ha különböző címkestílusokra van szükséged külön nézetekhez, hozz létre külön `Project` példányokat vagy klónozd a `DisplayOptions` objektumot.

## Következtetés

Az **címke beállítása** opciók elsajátításával az Aspose.Tasks-ben finomhangolt irányítást kapsz a projektmenetrendek vizuális megjelenítése felett. Akár a napcímkét testreszabod egy napi scrum táblához, akár az évcímkét állítod egy többéves ütemtervhez, ezek a beállítások segítenek átláthatóbb, professzionálisabb projekt dokumentációt nyújtani.

## GyIK

### Q1: Testreszabhatom a címke megjelenítéseket a projekt egyes szakaszaira?

A1: Igen, az Aspose.Tasks for .NET finomhangolt vezérlést biztosít a címke megjelenítések felett, lehetővé téve a projekt egyes szakaszainak testreszabását igény szerint.

### Q2: Kompatibilis az Aspose.Tasks a népszerű .NET keretrendszerekkel?

A2: Igen, az Aspose.Tasks for .NET kompatibilis különböző .NET keretrendszerekkel, beleértve a .NET Core-t és a .NET Framework-öt.

### Q3: Dinamikusan változtathatom a címke megjelenítéseket a projekt követelményei alapján?

A3: Teljesen, az Aspose.Tasks for .NET rugalmassága lehetővé teszi a címke megjelenítések dinamikus módosítását a projekt változó követelményei alapján.

### Q4: Vannak korlátozások a címke megjelenítések testreszabásában?

A4: Az Aspose.Tasks for .NET széles körű testreszabási lehetőségeket kínál a címke megjelenítésekhez, minimális korlátozásokkal, így a felhasználók nagy rugalmasságot élveznek.

### Q5: Támogatja az Aspose.Tasks más projektmenedzsment eszközökkel való integrációt?

A5: Igen, az Aspose.Tasks zökkenőmentes integrációs lehetőségeket biztosít, elősegítve az interoperabilitást más projektmenedzsment eszközökkel és platformokkal.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}