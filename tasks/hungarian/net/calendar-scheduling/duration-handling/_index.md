---
title: Időtartam kezelése az Aspose.Tasks-ban
linktitle: Időtartam kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti hatékonyan az időtartamokat az Aspose.Tasks for .NET-ben a lépésről lépésre bemutatott oktatóanyagok segítségével.
type: docs
weight: 30
url: /hu/net/calendar-scheduling/duration-handling/
---
## Bevezetés

Az időtartamok hatékony kezelése kulcsfontosságú a projektmenedzsment alkalmazásokban. Az Aspose.Tasks for .NET robusztus funkcionalitást biztosít az időtartamok hatékony kezeléséhez. Ebben az oktatóanyagban az Aspose.Tasks for .NET használatával történő időtartamkezelés különböző szempontjait vizsgáljuk meg.

## Előfeltételek

Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1. Alapvető C# ismerete: A C# programozási nyelv ismerete elengedhetetlen a példák megértéséhez és megvalósításához.
2. Visual Studio: Telepítse a Visual Studio IDE-t .NET-alkalmazások létrehozásához és futtatásához.
3.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).

## Névterek importálása

Először is importáljuk a szükséges névtereket az Aspose.Tasks funkciók használatához:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Bontsuk le az egyes példákat több lépésre, lépésről lépésre útmutató formátumban:

## A feladatok időtartamának frissítése

### 1. lépés: Töltse be a projektfájlt

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 2. lépés: Feladat és időtartam lekérése

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### 3. lépés: Frissítés időtartama

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### 4. lépés: A frissített időtartam megjelenítése

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## A feladatok időtartamának kivonása

### 1. lépés: Töltse be a projektfájlt

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 2. lépés: Feladat és időtartam lekérése

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### 3. lépés: Az időtartam kivonása

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### 4. lépés: A frissített időtartam megjelenítése

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Időtartam konvertálása Időtartammá

### 1. lépés: Töltse be a projektfájlt

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 2. lépés: Feladat és időtartam lekérése

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### 3. lépés: Konvertálja az időtartamot időtávra

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## Az időtartam konvertálása karakterláncra

### 1. lépés: Töltse be a projektfájlt

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 2. lépés: Feladat és időtartam lekérése

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### 3. lépés: Konvertálja az időtartamot karakterláncra

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## Következtetés

Ebben az oktatóanyagban az Aspose.Tasks for .NET időtartamának kezelésének különböző szempontjait ismertettük. Az időtartamok megértése és hatékony kezelése létfontosságú a sikeres projektmenedzsmenthez. Az Aspose.Tasks átfogó funkciókat kínál az időtartamkezelési feladatok egyszerűsítésére a .NET-alkalmazásokban.

## GYIK

### 1. kérdés: Mi az Aspose.Tasks for .NET?

1. válasz: Az Aspose.Tasks for .NET egy hatékony könyvtár a Microsoft Project fájlokkal való munkavégzéshez .NET alkalmazásokban.

### 2. kérdés: Az Aspose.Tasks kezelni tudja az összetett projektstruktúrákat?

2. válasz: Igen, az Aspose.Tasks könnyedén kezeli az összetett projektstruktúrákat, és kiterjedt API-kat biztosít a manipulációhoz.

### 3. kérdés: Az Aspose.Tasks for .NET kompatibilis a .NET Core-val?

3. válasz: Igen, az Aspose.Tasks for .NET kompatibilis a .NET Core-al, így többplatformos alkalmazásokban is használható.

### 4. kérdés: Az Aspose.Tasks támogatja a Microsoft Project fájlok olvasását és írását?

4. válasz: Igen, az Aspose.Tasks támogatja a Microsoft Project fájlok olvasását és írását különféle formátumokban, beleértve az MPP, XML és MPX formátumokat.

### 5. kérdés: Elérhető-e próbaverzió az Aspose.Tasks .NET-hez?

5. válasz: Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját a .NET-hez[itt](https://releases.aspose.com/).