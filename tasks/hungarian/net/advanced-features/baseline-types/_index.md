---
date: 2026-04-30
description: Tanulja meg, hogyan állíthat be alapvonalat, és hogyan kezelheti hatékonyan
  a projekt alapvonalakat az Aspose.Tasks for .NET segítségével.
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Az Aspose.Tasks különböző alapvonal típusai
second_title: Aspose.Tasks .NET API
title: Hogyan állítsunk be alapvonalat az Aspose.Tasks-ben – Különböző alapvonal típusok
url: /hu/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az Aspose.Tasks különböző típusú bázisvonalai

## Bevezetés

A projektmenedzsmentben a **bázisvonal helyes beállítása** döntő lehet egy olyan projekt és egy olyan projekt között, amely a pályán marad, illetve amely kicsúszik az irányítás alól. Az Aspose.Tasks for .NET egy teljes körű API-t biztosít a bázisvonalak létrehozásához, frissítéséhez és összehasonlításához, lehetővé téve a **projekt előrehaladásának nyomon követését** az eredeti tervhez képest. Ebben az útmutatóban megtanulja, hogyan állítson be bázisvonalat, hogyan dolgozzon több bázisvonal típussal, és hogyan használja az adatokat a projekt **bázisvonal és a tényleges ütemezés** elemzéséhez.

## Gyors válaszok
- **Mi a bázisvonal?** A projekt egy adott pontjában készített ütemezés, költség és munkaadatok pillanatképe.  
- **Hány bázisvonalat tud az Aspose.Tasks tárolni?** Projektenként legfeljebb 11 különálló bázisvonal.  
- **Miért állítunk be bázisvonalat?** Az aktuális teljesítmény összehasonlításához az eredeti tervvel és az eltérések azonosításához.  
- **Szükségem van licencre a kipróbáláshoz?** Ingyenes próba elérhető; licenc szükséges a termelési használathoz.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi a „bázisvonal beállítása” az Aspose.Tasks-ben?
A bázisvonal beállítása azt jelenti, hogy meghívja a `SetBaseline` metódust egy `Project` objektumon. Az API lehetővé teszi, hogy több `BaselineType` érték közül válasszon (Baseline, Baseline1 … Baseline10), így a projekt fejlődése során megőrizheti a történelmi pillanatképeket.

## Miért kezeljük a projekt bázisvonalait?
- **Eltérés mérése:** Gyorsan látható, hogy a feladatok előre vagy később vannak-e az ütemtervnél.  
- **Költségkontroll:** A bázisvonal költség összehasonlítása a tényleges kiadással.  
- **Érintetti jelentés:** Bázisvonal adatok exportálása PDF, XLSX vagy más formátumokba a tiszta kommunikáció érdekében.  
- **Forgatókönyv tervezés:** Több bázisvonal tárolása a „mi‑ha” ütemezések kiértékeléséhez.

## Előfeltételek

### 1. C# és .NET Framework ismerete
Alapvető ismeretekre van szükség a C# osztályok, metódusok és objektum‑orientált koncepciók terén.

### 2. Az Aspose.Tasks for .NET telepítése
Győződjön meg róla, hogy a könyvtár hozzá van adva a projektjéhez. Letöltheti a [Aspose.Tasks weboldaláról](https://releases.aspose.com/tasks/net/), vagy telepítheti a NuGet-en keresztül.

### 3. Integrált fejlesztőkörnyezet (IDE)
A Visual Studio (vagy bármely kompatibilis IDE) ajánlott C# kód írásához, fordításához és hibakereséséhez.

## Névterek importálása

Mielőtt elkezdenénk az Aspose.Tasks használatát a C# projektünkben, importálnunk kell a szükséges névtereket a kívánt osztályok és metódusok eléréséhez. Kövesse ezeket a lépéseket:

```csharp

```

Miután beállítottuk az előfeltételeket és importáltuk a szükséges névtereket, merüljünk el a különböző típusú bázisvonalak beállításában az Aspose.Tasks for .NET segítségével. Minden példát több lépésre bontunk a tisztaság és a könnyű megértés érdekében.

## Hogyan állítsunk be bázisvonalat az Aspose.Tasks-ben

### 1. lépés: A projektfájl betöltése
Először be kell töltenünk a projektfájlt, amelyre a bázisvonalat szeretnénk beállítani. Ez a lépés egy `Project` objektum inicializálását és a projektfájl betöltését jelenti. Íme, hogyan teheti meg:

```csharp
var project = new Project("Project2.mpp");
```

### 2. lépés: Bázisvonal beállítása
Miután a projekt betöltődött, folytathatjuk a bázisvonal beállításával. A bázisvonalak a projekt kezdeti ütemezésének pillanatképét biztosítják, amely összehasonlítási referencia pontként szolgál a projekt előrehaladtával. Használja a `SetBaseline` metódust a bázisvonal beállításához. Például a teljes projekt bázisvonalának beállításához használja a `BaselineType.Baseline` felsorolást:

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### 3. lépés: Munka a projekt bázisvonalakkal
A bázisvonal beállítása után különböző projektbázisvonal mezőkkel dolgozhat a projekt előrehaladásának pontos elemzéséhez és nyomon követéséhez. Ez a lépés a bázisvonal adatok, például a kezdési dátumok, befejezési dátumok, időtartamok és költségek elérését jelenti. Itt használhatja az Aspose.Tasks által nyújtott gazdag funkciókészletet a bázisvonal adatok igényei szerinti manipulálásához.

## Gyakori problémák és megoldások
- **Bázisvonal nem alkalmazva:** Győződjön meg róla, hogy a projektfájl mentve van a `SetBaseline` hívása után. Használja a `project.Save("output.mpp");` parancsot, ha a változtatásokat meg kell őrizni.  
- **Több bázisvonal ütközése:** Több bázisvonal beállításakor adja meg a megfelelő `BaselineType` értéket (pl. `Baseline1`, `Baseline2`).  
- **Verzióeltérés:** Ellenőrizze, hogy az Aspose.Tasks DLL verziója megegyezik a cél .NET futtatókörnyezettel.

## Gyakran ismételt kérdések

**Q: Beállíthatok több bázisvonalat egyetlen projekthez az Aspose.Tasks for .NET használatával?**  
A: Igen, az Aspose.Tasks lehetővé teszi, hogy egy projekthez legfeljebb 11 bázisvonalat állítson be, átfogó nyomon követési lehetőségekkel.

**Q: Az Aspose.Tasks kompatibilis különböző projektfájlformátumokkal?**  
A: Teljes mértékben! Az Aspose.Tasks számos projektfájlformátumot támogat, például MPP, XML és MPX, biztosítva a kompatibilitást különböző platformok között.

**Q: Hogyan jeleníthetem meg a bázisvonal adatokat a projektemben?**  
A: Az Aspose.Tasks segítségével exportálhatja a projekt adatokat népszerű formátumokba, mint a PDF vagy XLSX, így könnyen megjelenítheti és megoszthatja a bázisvonal információkat.

**Q: Az Aspose.Tasks támogatja a projektmenedzsment eszközökkel való integrációt?**  
A: Az Aspose.Tasks kiterjedt dokumentációt és támogatási fórumokat kínál, hogy a fejlesztők zökkenőmentesen integrálhassák funkcióit a népszerű projektmenedzsment eszközökkel és platformokkal.

**Q: Kipróbálhatom az Aspose.Tasks-et vásárlás előtt?**  
A: Igen, a weboldalon elérhető ingyenes próba segítségével felfedezheti az Aspose.Tasks-et, és első kézből megtapasztalhatja annak képességeit.

---

**Utoljára frissítve:** 2026-04-30  
**Tesztelve:** Aspose.Tasks for .NET (legújabb stabil kiadás)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}