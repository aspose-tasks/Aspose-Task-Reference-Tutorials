---
title: Naptárgyűjtemény kezelése az Aspose.Tasks alkalmazásban
linktitle: Naptárgyűjtemény kezelése az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti hatékonyan a naptárgyűjteményeket az Aspose.Tasks for .NET-ben. Könnyedén hozhat létre, módosíthat és kezelhet naptárakat.
weight: 11
url: /hu/net/calendar-scheduling/calendar-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Naptárgyűjtemény kezelése az Aspose.Tasks alkalmazásban

## Bevezetés

Ebben az oktatóanyagban megvizsgáljuk, hogyan kezelheti a naptárgyűjteményeket az Aspose.Tasks for .NET-ben. A naptárak döntő szerepet játszanak a projektmenedzsmentben, meghatározzák a munkanapokat, ünnepnapokat és kivételeket. Az Aspose.Tasks robusztus funkcionalitást biztosít a projekteken belüli naptárak kezeléséhez.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:

1. Visual Studio: Telepítse a Visual Studio-t vagy bármely más kompatibilis IDE-t a .NET-fejlesztéshez.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET webhelyet innen[itt](https://releases.aspose.com/tasks/net/).
3. A C# alapszintű ismerete: A C# programozási nyelv ismerete előnyt jelent.

## Névterek importálása

Először is importáljuk az Aspose.Tasks használatához szükséges névtereket:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Új naptár létrehozása

###  1. lépés: Inicializáljon egy újat`Project` object.
```csharp
var project = new Project();
```

### 2. lépés: Naptárak hozzáadása a projekt naptárgyűjteményéhez.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### 3. lépés: Ismételje meg a naptárakat, és jelenítse meg a nevüket.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Naptár cseréje új naptárra

### 1. lépés: Töltsön be egy meglévő projektet.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 2. lépés: Távolítsa el a meglévő naptárt (ha van).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### 3. lépés: Új naptár hozzáadása.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Naptár lekérése név vagy azonosító alapján

### 1. lépés: Töltse be a projektet.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 2. lépés: Naptárak lekérése név vagy UID alapján.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### 3. lépés: Jelenítse meg a naptár részleteit.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Iterálás a naptárak felett

### 1. lépés: Töltse be a projektet.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 2. lépés: A naptárak számának lekérése.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### 3. lépés: Ismételje meg a naptárgyűjteményt és a megjelenített neveket.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Szabványos naptár készítése

### 1. lépés: Inicializáljon egy új projektet.
```csharp
var project = new Project();
```

### 2. lépés: Határozzon meg egy új naptárt, és tegye szabványossá.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### 3. lépés: Mentse el a projektet.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Következtetés

A naptárgyűjtemények kezelése az Aspose.Tasks for .NET-ben elengedhetetlen a hatékony projektmenedzsmenthez. A biztosított funkciókkal hatékonyan hozhat létre, módosíthat és kezelhet naptárakat a projekt igényei szerint.

## GYIK

### 1. kérdés: Létrehozhatok egyéni munkanapokat az Aspose.Tasks alkalmazásban?

1. válasz: Igen, létrehozhat egyéni munkanapokat, ha kivételeket ad hozzá a naptárokhoz.

### 2. kérdés: Lehetséges naptárak importálása Microsoft Project fájlokból?

2. válasz: Az Aspose.Tasks feltétlenül támogatja a naptárak importálását a Microsoft Project fájlokból.

### 3. kérdés: Hogyan távolíthatok el egy adott naptárt egy projektből?

 3. válasz: Eltávolíthat egy naptárt, ha letölti a gyűjteményből, majd felhívja a`Remove` módszer.

### 4. kérdés: Az Aspose.Tasks támogatja a naptárak különböző formátumokba történő exportálását?

4. válasz: Igen, az Aspose.Tasks lehetővé teszi a naptárak exportálását különböző formátumokba, például XML, MPP stb.

### 5. kérdés: Testreszabhatom a munkaidőt adott napokra a naptárban?

5. válasz: Természetesen a naptárban kivételekkel meghatározhatja az egyes napok munkaidejét.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
