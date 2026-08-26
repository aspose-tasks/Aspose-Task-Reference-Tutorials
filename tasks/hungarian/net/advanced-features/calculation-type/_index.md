---
date: 2026-03-24
description: Tanulja meg, hogyan állítható be a számítás az Aspose.Tasks for .NET-ben,
  példákkal az összegző értékek kiszámításához, a számítási képlet meghatározásához
  és a rollup összegzés konfigurálásához.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hogyan állítsuk be a számítási típust az Aspose.Tasks-ben
url: /hu/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a számítási típust az Aspose.Tasks-ben

## Bevezetés

Ha **hogyan állítsuk be a számítási** szabályokat a feladatokra és összegző sorokra egy Microsoft Project fájlban, ez a bemutató pontosan ezt mutatja be az Aspose.Tasks for .NET használatával. Végigvezetünk egy teljes **számítási típus példán**, bemutatjuk, hogyan **számítsuk ki az összegző értékeket**, és elmagyarázzuk, hogyan **definiáljuk a számítási képletet** és **konfiguráljuk az összegző rollup-ot** a kiterjesztett attribútumokhoz. A végére képes leszel feladatot hozzáadni egy projekthez, egyedi számítási logikát beállítani, és magabiztosan irányítani a roll‑up viselkedést.

## Gyors válaszok
- **Mi a fő cél?** A feladat- és összegző értékek számításának szabályozása egy Project fájlban.  
- **Melyik API osztályt használjuk?** `ExtendedAttributeDefinition` együtt a `CalculationType` és a `SummaryRowsCalculationType` osztályokkal.  
- **Használhatok képletet?** Igen – állítsd be `CalculationType = CalculationType.Formula` és add meg a képlet karakterláncot.  
- **Hogyan roll‑up‑oljam az összegző értékeket?** Használd a `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` beállítást, és adj meg egy `RollupType` értéket, például `Average`.  
- **Szükség van licencre?** Egy érvényes Aspose.Tasks licenc szükséges a termelésben való használathoz.

## Mi az a Calculation Type és hogyan állítsuk be a számítást?

A `CalculationType` azt határozza meg az Aspose.Tasks számára, hogyan számítsa ki egy kiterjesztett attribútum értékét. Választhatsz statikus értéket, képletet, vagy hagyhatod, hogy a könyvtár a gyermek feladatokból roll‑up‑olja az értékeket. A számítás helyes beállítása elengedhetetlen, ha a projektet egyedi üzleti szabályok szerint szeretnéd frissíteni manuális beavatkozás nélkül.

## Miért használjuk a számítási típust az összegző értékek kiszámításához?

Amikor egy projekt összegző feladatokat tartalmaz, gyakran szükség van arra, hogy az összegző sorok aggregált adatokat mutassanak (pl. teljes költség, átlagos időtartam). A **calculate summary values** beállításával a `SummaryRowsCalculationType` és a `RollupType` segítségével az Aspose.Tasks automatikusan szinkronban tartja ezeket az aggregációkat, amikor egyedi feladatokat módosítasz.

## Előfeltételek

Mielőtt elkezdenénk, győződj meg róla, hogy rendelkezel:

1. Alapvető C# és .NET keretrendszer ismeretekkel.  
2. Telepített Visual Studio-val (bármely friss verzió).  
3. Az Aspose.Tasks for .NET könyvtárral – letöltheted [innen](https://releases.aspose.com/tasks/net/).  
4. Hozzáféréssel a hivatalos Aspose.Tasks for .NET dokumentációhoz, amely [itt](https://reference.aspose.com/tasks/net/) érhető el.

## Namespace-ek importálása

Mielőtt a példába merülnél, importáld a szükséges namespace-eket:

```csharp
using Aspose.Tasks;
using System;
```

## 1. lépés: Új Project létrehozása

Először egy üres `Project` objektumot hozunk létre, amely a feladatokat és az egyedi attribútumokat tárolja.

```csharp
var project = new Project();
```

## 2. lépés: Feladat hozzáadása a projekthez

Most **feladatot adunk a projekthez** egy egyszerű feladat létrehozásával, a kezdő dátum beállításával és egy napos időtartammal.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## 3. lépés: Számítási típus definiálása egy kiterjesztett attribútumhoz (Képlet példa)

Itt egy kiterjesztett attribútum definíciót hozunk létre, amelynek értéke egy képlettel számítódik. Ez egy **calculation type example** bemutató, és megmutatja, hogyan **definiáljuk a számítási képletet**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## 4. lépés: Számítási típus definiálása összegző sorokhoz (Rollup összegző konfigurálása)

Ezután egy másik kiterjesztett attribútum definíciót hozunk létre, amely azt mondja az Aspose.Tasks-nek, hogy **configure rollup summary** az *Average* roll‑up típussal. Ez a tipikus módja a **calculate summary values** meghatározásának költség, munka vagy egyedi mezők esetén.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Gyakori problémák és hibaelhárítás

| Tünet | Valószínű ok | Megoldás |
|---------|--------------|-----|
| A képlet `null`-t ad vissza | Hibás mezőreferencia a képletben | Ellenőrizd a mező nevét szögletes zárójelek között (pl. `[Start]` nem `[stARt]`). |
| Az összegző sorok 0-t mutatnak | `SummaryRowsCalculationType` nincs beállítva vagy rossz `RollupType` | Győződj meg róla, hogy `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` és megfelelő `RollupType` van kiválasztva. |
| A projekt nem töltődik be az attribútumok hozzáadása után | Az attribútum definíció és a feladat használata közti eltérés | Add hozzá az attribútum definíciót **mielőtt** bármely feladathoz hozzárendelnéd. |

## Összegzés

Ebben a bemutatóban áttekintettük, **hogyan állítsuk be a számítási szabályokat** az Aspose.Tasks for .NET-ben, egy egyszerű feladat létrehozásától a képleten alapuló és roll‑up‑on alapuló számítási típusok definiálásáig. E beállítások elsajátításával finomhangolt vezérlést nyerhetsz a **calculate summary values** felett, lehetővé téve a gazdagabb projektanalitikát manuális táblázatkezelés nélkül.

## GyIK

### Q1: Mi az a Calculation Type az Aspose.Tasks-ben?

A1: A Calculation Type az Aspose.Tasks-ben meghatározza, hogyan számítják ki az értékeket a feladatok és összegző feladatok esetén a projektben, olyan lehetőségekkel, mint a Formula és a Rollup.

### Q2: Hogyan állíthatom be a Calculation Type-ot egy kiterjesztett attribútumhoz?

A2: A Calculation Type-ot egy kiterjesztett attribútumhoz a CalculationType tulajdonság megfelelő beállításával definiálhatod.

### Q3: Testreszabhatom a Calculation Type-ot az összegző sorokban egy projektben?

A3: Igen, az Aspose.Tasks lehetővé teszi, hogy meghatározd a Calculation Type-ot az összegző sorokhoz, így az értékek számítását a saját igényeid szerint alakíthatod.

### Q4: Vannak különböző Rollup Type-ok az összegző feladatok számításához?

A4: Igen, az Aspose.Tasks több Rollup Type-ot kínál, például Average, Sum és Count, az összegző feladatok értékeinek kiszámításához.

### Q5: Hol találok további forrásokat az Aspose.Tasks for .NET-hez?

A5: A [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) dokumentációját és közösségi támogatási fórumait böngészheted részletes útmutatók és segítségért.

---

**Utoljára frissítve:** 2026-03-24  
**Tesztelt verzió:** Aspose.Tasks for .NET (legújabb kiadás)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}