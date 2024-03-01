---
title: Egyéni projekttulajdon-gyűjtemény kezelése az Aspose.Tasks-ban
linktitle: Egyéni projekttulajdon-gyűjtemény kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti hatékonyan az egyéni projekttulajdonságokat az Aspose.Tasks for .NET-ben, javítva ezzel a projektkezelési élményt.
type: docs
weight: 24
url: /hu/net/calendar-scheduling/custom-project-property-collection/
---
## Bevezetés

Készen áll arra, hogy bővítse projektmenedzsment-élményét az Aspose.Tasks for .NET segítségével? Az egyéni projekttulajdonságok kezelése a projektmenedzsment kulcsfontosságú eleme, amely lehetővé teszi a projekt követelményeihez szabott metaadatok hozzáadását. Ebben az oktatóanyagban bemutatjuk, hogyan dolgozhat hatékonyan egyéni projekttulajdon-gyűjteményekkel az Aspose.Tasks for .NET használatával.

## Előfeltételek

Mielőtt folytatnánk, győződjön meg arról, hogy beállította a következő előfeltételeket:

1. Visual Studio Environment: A Visual Studio telepítve legyen a rendszerére.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET webhelyről[letöltési link](https://releases.aspose.com/tasks/net/).
3. C# alapismeretek: Ismerkedjen meg a C# programozási nyelv alapjaival.

## Névterek importálása

Kezdje a szükséges névterek importálásával az Aspose.Tasks for .NET használatához:

```csharp
using Aspose.Tasks;
using System;


```

Bontsuk fel a példakódot több lépésre az átfogó megértés érdekében:

## 1. lépés: A projekt inicializálása

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

Ez a lépés inicializál egy új projektet az Aspose.Tasks használatával.

## 2. lépés: Ellenőrizze az egyéni tulajdonságok gyűjteményének készségét

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

Ez a kód ellenőrzi, hogy az egyéni tulajdonságok gyűjteménye csak olvasható-e.

## 3. lépés: Adjon hozzá egyéni tulajdonságokat

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

Itt egyéni tulajdonságokat adunk a projekthez, támogatva a logikai, dátum-idő, dupla és karakterlánc típusokat.

## 4. lépés: Nyissa meg az egyéni tulajdonságokat

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

Ez a ciklus lehetővé teszi számunkra, hogy az egyéni tulajdonságokon keresztül ismételgessünk, és megjelenítsük azok típusát, nevét és értékét.

## 5. lépés: Egyéni tulajdonságérték lekérése

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

Ez a kód lekéri az „Egyéni név” nevű konkrét egyéni tulajdonság értékét.

## 6. lépés: Ismételje meg az egyéni tulajdonságneveket

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

Itt ismételgetjük az egyéni tulajdonságok neveit, és megjelenítjük azokat.

## 7. lépés: Távolítsa el vagy törölje az egyéni tulajdonságokat

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

Eltávolíthat egy adott egyéni tulajdonságot a neve alapján, vagy törölheti a teljes gyűjteményt.

## Következtetés

Az egyéni projekttulajdon-gyűjtemények elsajátítása az Aspose.Tasks for .NET-ben lehetővé teszi a projekt metaadatainak hatékony kezelését. Ennek a lépésről lépésre szóló útmutatónak a követésével zökkenőmentesen integrálhatja az egyéni tulajdonságokat a projektmenedzsment munkafolyamatába, javítva ezzel a szervezettséget és a hatékonyságot.

## GYIK

### 1. kérdés: Hozzáadhatok bármilyen adattípus egyéni tulajdonságát a projektemhez az Aspose.Tasks for .NET használatával?

1. válasz: Igen, felvehet egyéni tulajdonságokat, amelyek támogatják a logikai, dátum-idő, dupla és karakterlánc típusokat.

### 2. kérdés: Lehetséges az Aspose.Tasks for .NET egyéni tulajdonságneveinek átírása?

 2. válasz: Természetesen ismételhet egyéni tulajdonságnevek között a`Names` ingatlan.

### 3. kérdés: Hogyan távolíthatok el egy adott egyéni tulajdonságot a projektemből?

 3. válasz: Eltávolíthat egy egyéni tulajdonságot a neve alapján a`Remove` módszer.

### 4. kérdés: Az Aspose.Tasks for .NET támogatja az ideiglenes licenceket?

4. válasz: Igen, az Aspose webhelyéről ideiglenes licencet szerezhet értékelési célokra.

### 5. kérdés: Hol találok támogatást vagy további segítséget az Aspose.Tasks for .NET-hez?

 5. válasz: Látogassa meg az Aspose.Tasks fórumot[itt](https://forum.aspose.com/c/tasks/15) bármilyen kérdésért vagy segítségért.