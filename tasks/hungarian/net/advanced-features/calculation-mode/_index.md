---
date: 2026-03-24
description: Ismerje meg, hogyan állíthatja be a számítási módot az Aspose.Tasks for
  .NET-ben, beleértve az automatikus, a manuális és a „none” módot a feladatfüggőségek
  kezeléséhez.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Hogyan állítsuk be a számítási módot az Aspose.Tasks .NET-ben
url: /hu/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a számítási módot az Aspose.Tasks for .NET-ben

## Bevezetés

Az Aspose.Tasks for .NET egy erőteljes API, amely lehetővé teszi a Microsoft Project fájlok programozott kezelését. Az egyik legfontosabb beállítás, amellyel találkozni fog, a **calculation mode**, amely szabályozza, hogyan frissülnek a feladatok dátumai és a projekt ütemezései. Ebben az útmutatóban megtanulja **how to set calculation** módot, megismeri a **automatic calculation mode**, **manual calculation mode**, és **none calculation mode** lehetőségeket, és látja, hogyan befolyásolják ezek a **manage task dependencies**, **create project start date**, és **link tasks finish‑start** kapcsolatok.

## Gyors válaszok
- **What is calculation mode?** Meghatározza, hogy a feladatok dátumai automatikusan, manuálisan vagy egyáltalán nem kerülnek újraszámításra.  
- **Why use manual calculation mode?** Teljes ellenőrzést biztosít a menetrend frissítésének időpontja felett, ami nagy mennyiségű frissítésnél hasznos.  
- **Which mode is default?** Az automatikus számítási mód, amely a módosítások után azonnal frissíti a dátumokat.  
- **Can I change the mode at runtime?** Igen—egyszerűen állítsa be a `CalculationMode` tulajdonságot a `Project` objektumon.  
- **Do I need a license?** Egy érvényes Aspose.Tasks licenc szükséges a termelésben való használathoz.

## Mi az a “how to set calculation” az Aspose.Tasks-ben?

A számítási mód beállítása olyan egyszerű, mint egy enum érték hozzárendelése a `Project.CalculationMode` tulajdonsághoz. Az enum három lehetőséget kínál: `Automatic`, `Manual` és `None`. A megfelelő mód kiválasztása a munkafolyamatától függ—akár azonnali frissítéseket, kötegelt feldolgozást vagy teljes ellenőrzést szeretne.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik:

1. **Visual Studio** – bármelyik legújabb verzió (2019, 2022 vagy későbbi).  
2. **Aspose.Tasks for .NET** – töltse le és telepítse a könyvtárat innen: [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – legyen jártas konzolalkalmazások létrehozásában és a NuGet csomagok használatában.

## Névterek importálása

Mielőtt elkezdenénk dolgozni az Aspose.Tasks for .NET-tel, importáljuk a szükséges névtereket:

```csharp
using Aspose.Tasks;
using System;
```

## A számítási mód beállítása

Az alábbiakban lépésről‑lépésre példákat talál minden számítási módra. A kódrészek változatlanok az eredeti útmutatóból; a környező magyarázatok a tisztaság kedvéért bővítve lettek.

### Automatikus számítási mód alkalmazása

Az automatikus mód azonnal újraszámítja a dátumokat, amikor feladatokat vagy kapcsolatokat módosít.

#### 1. lépés: Új Project példány létrehozása

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### 2. lépés: Projekt kezdődátum beállítása és feladatok hozzáadása

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### 3. lépés: Feladatok összekapcsolása (befejezés‑kezdés)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### 4. lépés: Újraszámított dátumok ellenőrzése

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Manuális számítási mód alkalmazása

#### 1. lépés: Új Project példány létrehozása

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### 2. lépés: Projekt kezdődátum beállítása és feladatok hozzáadása

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### 3. lépés: Feladat tulajdonságok ellenőrzése

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### 4. lépés: Feladatok összekapcsolása és dátumok ellenőrzése (nincs automatikus újraszámítás)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### None számítási mód alkalmazása

#### 1. lépés: Új Project példány létrehozása

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### 2. lépés: Új feladat hozzáadása

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### 3. lépés: Feladat tulajdonságok ellenőrzése (nincs automatikus azonosító)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Gyakori problémák és megoldások

| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| A dátumok nem frissülnek a feladatok összekapcsolása után | A projekt **Manual** vagy **None** módban van | Állítsa be a `project.CalculationMode = CalculationMode.Automatic` értéket, vagy hívja meg manuálisan a `project.Calculate()` metódust |
| A feladatazonosítók 0 maradnak | **None** mód használata megakadályozza az azonosítók generálását | Váltson **Automatic** vagy **Manual** módra, majd számolja újra |
| A kapcsolás `ArgumentException` hibával meghiúsul | A megelőző feladat kezdődátuma későbbi, mint az utódé, ha **Manual** módban nincs újraszámítás | Győződjön meg a helyes kezdődátumokról, vagy számolja újra a kapcsolatok hozzáadása után |

## Gyakran feltett kérdések

**Q1: Módosíthatom a számítási módot dinamikusan a futásidőben?**  
A1: Igen, a `CalculationMode` tulajdonságot a kódban bármikor módosíthatja, és ha azonnali frissítésre van szükség, meghívhatja a `project.Calculate()` metódust.

**Q2: Az Aspose.Tasks támogat más projektmenedzsment fájlformátumokat a Microsoft Projecten kívül?**  
A2: Az Aspose.Tasks elsősorban a Microsoft Project formátumokra fókuszál, de támogatja a Primavera P6 XML, Primavera DB és az Asta Powerproject XML formátumokat is.

**Q3: Az Aspose.Tasks alkalmas kis‑ és vállalati szintű projektekre egyaránt?**  
A3: Teljes mértékben. Az API egyszerű feladatlistáktól a komplex, több fázisból álló vállalati ütemezésekig skálázható.

**Q4: Integrálhatom az Aspose.Tasks-et más .NET könyvtárakkal és keretrendszerekkel?**  
A4: Igen, az Aspose.Tasks-et kombinálhatja ASP.NET, WPF, Xamarin vagy bármely más .NET technológiával, hogy gazdag projektmenedzsment megoldásokat építsen.

**Q5: Van közösségi fórum vagy támogatási csatorna az Aspose.Tasks felhasználók számára?**  
A5: Igen, a [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) felkeresve közösségi támogatást és megbeszéléseket találhat.

---

**Utoljára frissítve:** 2026-03-24  
**Tesztelt verzió:** Aspose.Tasks 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}