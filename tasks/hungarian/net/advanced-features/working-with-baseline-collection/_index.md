---
date: 2026-04-06
description: Tanulja meg, hogyan törölheti az összes alapvonalat, és kezelheti az
  alapvonal-gyűjteményeket az Aspose.Tasks for .NET-ben lépésről lépésre bemutatott
  kódpéldákkal.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Az összes alapvonal törlése az Aspose.Tasks alapvonal-gyűjteményével
second_title: Aspose.Tasks .NET API
title: Az összes alapvonal törlése az Aspose.Tasks alapvonal-gyűjteménnyel
url: /hu/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az összes alapvonal törlése az Aspose.Tasks alapvonal-gyűjteménnyel

## Bevezetés

Az Aspose.Tasks for .NET lehetővé teszi a Microsoft Project fájlok közvetlen manipulálását .NET alkalmazásokból. Az egyik leghatékonyabb funkció a **minden alapvonal törlése** egy erőforrás esetén, ami elengedhetetlen, ha a projekt nyomon követési adatait vissza kell állítani, vagy új alapvonal időszakot kell indítani. Ebben az útmutatóban végigvezetünk a teljes folyamaton – a projektfájl betöltésétől a kiválasztott erőforráshoz tartozó összes alapvonal eltávolításáig – érthető, beszélgetős magyarázatokkal és azonnal futtatható C# kóddal.

## Gyors válaszok
- **Mit csinál a „minden alapvonal törlése”?** Eltávolít minden tárolt alapvonal rekordot a kiválasztott erőforrásról, törölve a történeti költség- és munkaadatokat.  
- **Miért lenne erre szükség?** A nyomon követés visszaállításához egy nagy projektváltozás után, vagy ha az eredeti alapvonalak már nem relevánsak.  
- **Melyik könyvtár biztosítja ezt a funkciót?** Az Aspose.Tasks for .NET.  
- **Szükség van licencre?** Egy érvényes Aspose.Tasks licenc szükséges a termelésben való használathoz; ingyenes próbaverzió is elérhető.  
- **Kompatibilis a .NET 6+ verzióval?** Igen, az API működik a .NET Framework 4.5+, a .NET Core 3.1+, valamint a .NET 5/6 környezetekkel.

## Mi az az alapvonal, és miért töröljük az összes alapvonalat?

Az alapvonal rögzíti a költség, munka és ütemezés eredeti tervét egy adott időpontban. A projekt során több alapvonalat (Alapvonal 1, Alapvonal 2 stb.) hozhatunk létre, hogy a tényleges előrehaladást különböző tervezési pillanatképekkel hasonlítsuk össze. Bizonyos esetekben – például egy projekt újraszabályozása vagy friss kezdés esetén – a történeti alapvonalak megtartása zavaró lehet. Az összes alapvonal törlése tiszta lappal szolgál, lehetővé téve új, a jelenlegi valóságot tükröző alapvonalak beállítását.

## Előfeltételek

Mielőtt a kódba merülnénk, győződjön meg róla, hogy rendelkezik a következőkkel:

1. **Visual Studio** – bármelyik legújabb kiadás (Community, Professional vagy Enterprise).  
2. **Aspose.Tasks for .NET** – töltse le a [letöltési link](https://releases.aspose.com/tasks/net/) oldaláról.  
3. **Alap C# ismeretek** – kényelmesen kell kezelnie a változókat, ciklusokat és a konzol kimenetet.  
4. **Microsoft Project fájl** (`.mpp`) – a példákban a *WorkWithBaselineCollection.mpp* nevű mintafájlt használjuk.

## Névtér importálása

Először hozzuk be a szükséges névtereket, hogy a fordító tudja, hol találja a használandó osztályokat.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## 1. lépés: A projektfájl betöltése

Elindítjuk egy meglévő Project fájl betöltését. Állítsa be a `DataDir` változót úgy, hogy az a mappára mutasson, amelyik a `.mpp` fájlt tartalmazza.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## 2. lépés: A cél erőforrás lekérése

Demonstrációként a UID = 1 értékű erőforrást kérjük le. Valós környezetben a nevének vagy más azonosítójának alapján kellene megtalálni az erőforrást.

```csharp
var resource = project.Resources.GetByUid(1);
```

## 3. lépés: A meglévő alapvonalak megjelenítése

Mielőtt bármit törölnénk, hasznos megnézni, hogy milyen alapvonalak vannak jelenleg az erőforráshoz csatolva. Ez biztosítja, hogy a megfelelő adatokat távolítja el.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## 4. lépés: Az összes alapvonal bejárása

Itt minden alapvonalon végigiterálunk, kiírva a kulcsfontosságú mutatókat, például a költséget, munkát és a megszerzett értéket (BCWP/BCWS). Ez a lépés opcionális, de hasznos naplózáshoz vagy auditáláshoz.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Az összes alapvonal törlése

Most hajtjuk végre a fő műveletet: **az összes alapvonal törlése** a kiválasztott erőforrásra vonatkozóan. Először a gyűjteményt egy listába másoljuk, hogy a bejárás közben ne módosítsuk a gyűjteményt, majd egyesével eltávolítjuk az alapvonalakat.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Ez a blokk lefutása után a `resource.Baselines.Count` értéke `0` lesz, ami megerősíti, hogy minden alapvonal rekord törlésre került.

## Gyakori problémák és tippek

- **NullReferenceException** – Győződjön meg róla, hogy a projektfájl valóban tartalmazza a célzott erőforrást; ellenkező esetben a `GetByUid` `null` értéket ad vissza.  
- **Licencelés** – Érvényes Aspose.Tasks licenc hiányában vízjel jelenik meg a kimeneten, és a funkcionalitás korlátozott.  
- **Teljesítmény** – Nagyon nagy projektek esetén érdemes a `Parallel.ForEach` használatával felgyorsítani a törlési folyamatot, de ne feledje, hogy az alapgyűjtemény nem szálbiztos.

## Gyakran feltett kérdések

**K: Kezelni tudja az Aspose.Tasks nagy projektfájlokat?**  
V: Igen, az Aspose.Tasks optimalizált a teljesítményre, és több gigabájtos `.mpp` fájlokat is hatékonyan feldolgoz.

**K: Kompatibilis-e a könyvtár minden Microsoft Project verzióval?**  
V: Az Aspose.Tasks támogatja a Project 2000-tól a Project 2024-ig terjedő verziókat, beleértve a régebbi `.mpp` formátumokat és az újabb XML‑alapú fájlokat is.

**K: Testreszabhatom az alapvonalakat a törlés előtt?**  
V: Természetesen. Bármely alapvonal‑tulajdonságot (költség, munka, dátumok) elolvashat vagy módosíthat, mielőtt eltávolítaná.

**K: Fut-e az Aspose.Tasks felhőplatformokon?**  
V: Igen, az API bármely .NET‑kompatibilis környezetben működik, beleértve az Azure App Service‑t, az AWS Lambda‑t (.NET Core) és a Docker konténereket.

**K: Hol kérhetek segítséget a közösségtől?**  
V: Látogassa meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15), ahol más fejlesztőkkel és az Aspose csapatával léphet kapcsolatba.

## Összegzés

Ebben az útmutatóban bemutattuk, hogyan **törölhetjük az összes alapvonalat** egy erőforrásról az Aspose.Tasks for .NET segítségével. A lépésről‑lépésre bemutatott kóddal visszaállíthatja az alapvonal adatokat, tisztán tarthatja a projekt nyomon követését, és felkészítheti ütemezését egy új tervezési ciklusra. Nyugodtan kísérletezzen új alapvonalak létrehozásával a törlés után, hogy lássa, hogyan frissíti a könyvtár a projektfájlt.

---

**Utoljára frissítve:** 2026-04-06  
**Tesztelve:** Aspose.Tasks 24.12 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}