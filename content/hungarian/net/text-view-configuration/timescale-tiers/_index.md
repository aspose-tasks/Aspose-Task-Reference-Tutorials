---
title: A Gantt-diagram időskála-szintjeinek konfigurálása az Aspose.Tasks-ban
linktitle: Időskálás szintek konfigurálása az Aspose.Tasks programban
second_title: Aspose.Tasks .NET API
description: Fedezze fel az Aspose.Tasks for .NET-et az időskála-szintek konfigurálásához a Gantt-diagram nézetben a projekt idővonalának pontos megjelenítéséhez. #Aspose.Tasks #MS Project
type: docs
weight: 16
url: /hu/net/text-view-configuration/timescale-tiers/
---
## Bevezetés
A projektmenedzsment dinamikus környezetében a hatékony vizualizáció kulcsfontosságú az idővonalak és határidők megértéséhez. Az Aspose.Tasks for .NET hatékony eszközkészletet biztosít, és ebben az oktatóanyagban azt vizsgáljuk meg, hogyan konfigurálhatunk időskála-szinteket a Gantt-diagram nézetben való optimális megjelenítés érdekében. Kövesse ezeket a lépésenkénti utasításokat a projekt megjelenítésének javításához.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik az alábbiakkal:
- C# és .NET alapismeretek.
-  Aspose.Tasks for .NET könyvtár telepítve. Letöltheti[itt](https://releases.aspose.com/tasks/net/).
- NET-alkalmazásfejlesztéshez beállított fejlesztői környezet.
## Névterek importálása
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Most bontsuk le a példa minden lépését.
## 1. lépés: A projekt inicializálása és a feladathivatkozások hozzáadása
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Itt létrehozunk egy projektet, és feladatkapcsolatokat hozunk létre az „1. feladat” és a „2. feladat” között.
## 2. lépés: A Gantt-diagram nézet konfigurálása
```csharp
var view = (GanttChartView)project.DefaultView;
```
A testreszabáshoz nyissa meg a Gantt-diagram nézetet.
## 3. lépés: Hangolja be a középső időskálát
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Testreszabhatja a középső időskála réteget a hetek megjelenítéséhez meghatározott címkékkel és igazítással.
## 4. lépés: Adja hozzá a legjobb időskálát
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Adjon hozzá egy felső időskálát a hónapok megjelenítéséhez.
## 5. lépés: A középső szint dátumainak testreszabása
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Tegye személyre a hónap címkéit a jobb megjelenítés érdekében.
## 6. lépés: Állítsa be a projekt időskáláját
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Határozza meg a projekt időskáláját a teljes idővonal szabályozásához.
## 7. lépés: Mentse el a projektet testreszabott időskálával
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Mentse el a projektet a megadott időskálával.
## Következtetés
Összefoglalva, az Aspose.Tasks for .NET időskáláinak konfigurálása lehetővé teszi a projekt idővonalainak testreszabottabb és tetszetősebb megjelenítését. Ezek a lépések lehetővé teszik, hogy létrehozzon egy Gantt-diagram nézetet, amely pontosan megfelel a projektmenedzsment igényeinek.
## GYIK
### Használhatom az Aspose.Tasks-t más .NET könyvtárakkal?
Igen, az Aspose.Tasks zökkenőmentesen integrálható más .NET-könyvtárakba, rugalmasságot kínálva a fejlesztői veremben.
### Kapható-e ideiglenes licenc tesztelési célokra?
 Igen, kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/) értékeléshez.
### Vannak további testreszabási lehetőségek a Gantt-diagram nézethez?
Természetesen az Aspose.Tasks kiterjedt testreszabási lehetőségeket kínál a Gantt-diagram nézethez, hogy megfeleljen a különböző projektkövetelményeknek.
### Megjeleníthetem az időskálákat különböző formátumokban?
Természetesen felfedezhet különféle formátumokat és stílusokat az időskálás ábrázoláshoz, hogy a legjobban illeszkedjen a projekt környezetéhez.
### Létezik közösségi fórum az Aspose.Tasks támogatására?
 Igen, látogassa meg a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) közösségi támogatásra és beszélgetésekre.