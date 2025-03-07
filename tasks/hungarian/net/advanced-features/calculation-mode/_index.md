---
title: Számítási mód az Aspose.Tasks-ban
linktitle: Számítási mód az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti hatékonyan a számítási módokat az Aspose.Tasks for .NET alkalmazásban a projektütemezés és a feladatfüggőségek egyszerűsítéséhez.
weight: 29
url: /hu/net/advanced-features/calculation-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Számítási mód az Aspose.Tasks-ban

## Bevezetés

Az Aspose.Tasks for .NET egy hatékony API, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak Microsoft Project fájlokkal .NET-alkalmazásaikban. A projektfájlokkal végzett munka egyik kulcsfontosságú szempontja a számítási módok kezelése, amelyek meghatározzák a feladatok és a projekt ütemezésének kiszámítását és frissítését. Ebben az oktatóanyagban elmélyülünk az Aspose.Tasks for .NET által támogatott különféle számítási módokban, és bemutatjuk azok hatékony használatát.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:

1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat innen[itt](https://releases.aspose.com/tasks/net/).
3. A C# programozás alapjai: Ismerkedjen meg a C# programozási koncepciókkal.

## Névterek importálása

Mielőtt elkezdenénk dolgozni az Aspose.Tasks for .NET-el, importáljuk a szükséges névtereket:

```csharp
using Aspose.Tasks;
using System;


```

## Automatikus számítási mód alkalmazása

### 1. lépés: Hozzon létre egy új projektpéldányt

 Inicializáljon egy újat`Project` objektumot, és állítsa be`CalculationMode` tulajdonát`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### 2. lépés: Állítsa be a projekt kezdési dátumát, és adjon hozzá feladatokat

Határozza meg a projekt kezdési dátumát, és adjon hozzá feladatokat.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### 3. lépés: A feladatok összekapcsolása

Hozzon létre függőséget a feladatok között.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### 4. lépés: Ellenőrizze az újraszámított dátumokat

Ellenőrizze, hogy a dátumok automatikusan újra lettek-e számítva.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Szükség szerint adjon hozzá további ellenőrzéseket
```

## Kézi számítási mód alkalmazása

### 1. lépés: Hozzon létre egy új projektpéldányt

 Inicializáljon egy újat`Project` objektumot, és állítsa be`CalculationMode` tulajdonát`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### 2. lépés: Állítsa be a projekt kezdési dátumát, és adjon hozzá feladatokat

Határozza meg a projekt kezdési dátumát, és adjon hozzá feladatokat.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### 3. lépés: Ellenőrizze a feladat tulajdonságait

Ellenőrizze, hogy a feladat tulajdonságai helyesen vannak-e beállítva kézi módban.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Szükség szerint adjon hozzá további ellenőrzéseket
```

### 4. lépés: A feladatok összekapcsolása és a dátumok ellenőrzése

Kapcsolja össze a feladatokat, és ellenőrizze, hogy nem számítják-e újra a dátumokat.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Nincs számítási mód alkalmazása

### 1. lépés: Hozzon létre egy új projektpéldányt

 Inicializáljon egy újat`Project` objektumot, és állítsa be`CalculationMode` tulajdonát`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### 2. lépés: Új feladat hozzáadása

Adjon hozzá egy új feladatot a projekthez.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### 3. lépés: Ellenőrizze a feladat tulajdonságait

Ellenőrizze, hogy a feladat tulajdonságait nem számítják-e ki automatikusan.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Szükség szerint adjon hozzá további ellenőrzéseket
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk az Aspose.Tasks for .NET-ben elérhető számítási módokat, és megtanultuk, hogyan kell ezeket gyakorlati forgatókönyvekben alkalmazni. Akár automatikus, akár manuális, akár nem számítási módra van szüksége, az Aspose.Tasks rugalmasságot biztosít a projekt követelményeinek megfelelően.

## GYIK

### 1. kérdés: Meg tudom változtatni a számítási módot dinamikusan futás közben?

1. válasz: Igen, a futási idő alatt bármikor módosíthatja a projekt számítási módját, ha módosítja a`CalculationMode` ingatlan.

### 2. kérdés: Az Aspose.Tasks támogat más projektmenedzsment fájlformátumokat a Microsoft Projecten kívül?

2. válasz: Az Aspose.Tasks elsősorban a Microsoft Project fájlformátumokra összpontosít, de más formátumokat is támogat, mint például a Primavera P6 XML, a Primavera DB és az Asta Powerproject XML.

### 3. kérdés: Az Aspose.Tasks alkalmas kis léptékű és vállalati szintű projektekre is?

A3: Abszolút! Az Aspose.Tasks úgy lett kialakítva, hogy kielégítse mind a kis léptékű, mind a vállalati szintű projektek igényeit átfogó szolgáltatásaival és robusztus API-ival.

### 4. kérdés: Integrálhatom az Aspose.Tasks-t más .NET könyvtárakkal és keretrendszerekkel?

4. válasz: Igen, az Aspose.Tasks zökkenőmentesen integrálható más .NET-könyvtárakba és -keretrendszerekbe, hogy javítsa alkalmazásai funkcionalitását.

### 5. kérdés: Elérhető közösségi fórum vagy támogatási csatorna az Aspose.Tasks felhasználók számára?

 A5: Igen, meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) közösségi támogatásra és beszélgetésekre.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
