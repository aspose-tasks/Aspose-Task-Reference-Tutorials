---
title: MS Project Rates kezelése Aspose.Tasks segítségével .NET-hez
linktitle: Kezelési arányok az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Az Aspose.Tasks for .NET segítségével könnyedén kezelheti az MS Project Rates-eket. A feladatok hatékony automatizálása a gördülékenyebb projektmunkafolyamatok érdekében.
type: docs
weight: 10
url: /hu/net/rate-recurring-tasks/handling-rates/
---
## Bevezetés
Üdvözöljük az MS Project Rates kezeléséről szóló oktatóanyagunkban az Aspose.Tasks for .NET használatával! Ebben az útmutatóban lépésről lépésre végigvezetjük a folyamaton, így biztosítva, hogy hatékonyan kezelje a díjakat az MS Project dokumentumaiban. Az Aspose.Tasks for .NET hatékony szolgáltatásokat kínál az MS Project fájlok programozott kezeléséhez, lehetővé téve a projektkezelési feladatok egyszerűsítését.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1. Visual Studio telepítve: Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren.
2.  Aspose.Tasks for .NET Library: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat. A letöltési linket megtalálod[itt](https://releases.aspose.com/tasks/net/).
3. A C# alapjai: Ismerkedjen meg a C# programozási nyelv alapjaival.
## Névterek importálása
Először is importálnia kell a szükséges névtereket a C# projektbe. Ezek a névterek hozzáférést biztosítanak az MS Project Rates kezeléséhez szükséges osztályokhoz és metódusokhoz.
## 1. lépés: Importálja az Aspose.Tasks névteret
```csharp
using Aspose.Tasks;
using System;

```
Most bontsuk fel a példát több lépésre, és értsük meg alaposan az egyes lépéseket.
## 1. lépés: Töltse be a projektfájlt
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Ebben a lépésben egy "Project1.mpp" nevű meglévő MS Project fájlt töltünk be a`Project` osztály által biztosított Aspose.Tasks.
## 2. lépés: Adjon hozzá erőforrást és állítsa be a munkát
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Itt hozzáadunk egy új "Erőforrás 1" nevű erőforrást a projekthez, és típusát "Munka"-ra állítjuk. Ennek az erőforrásnak a munkaidejét is meghatározzuk.
## 3. lépés: Állítsa be a normál tarifát
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
Ebben a lépésben az erőforrás normál díját óránként 20 USD-ra állítottuk be.
## 4. lépés: Határozza meg a kamatperiódusokat
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Itt határozzuk meg az erőforrás kamatperiódusait. A Rate1 2019. január 1. és 2019. november 11. között van beállítva, a normál és a túlóra díjakkal.
## 5. lépés: Adjon hozzá egy másik tarifaperiódust
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
Ebben az utolsó lépésben egy másik díjperiódussal adunk hozzá 2019. november 12-től 2019. december 31-ig, eltérő általános díjszabással és használati költséggel.
Gratulálunk! Sikeresen kezelte az MS Project Rates szolgáltatást az Aspose.Tasks for .NET használatával.
## Következtetés
Az MS Project Rates programozott kezelése jelentősen javíthatja a projektmenedzsment munkafolyamatát. Az Aspose.Tasks for .NET segítségével hatékonyan automatizálhatja a díjkezelési feladatokat, így időt és erőforrásokat takaríthat meg.
## GYIK
### K: Az Aspose.Tasks kezelni tudja az összetett projektstruktúrákat?
V: Igen, az Aspose.Tasks robusztus szolgáltatásokat nyújt az összetett projektstruktúrák egyszerű kezeléséhez.
### K: Az Aspose.Tasks kompatibilis az MS Project fájlok összes verziójával?
V: Az Aspose.Tasks az MS Project fájlok különféle verzióit támogatja, biztosítva a kompatibilitást a különböző platformokon.
### K: Módosíthatom a meglévő díjakat egy MS Project fájlban az Aspose.Tasks segítségével?
V: Abszolút! Az Aspose.Tasks lehetővé teszi a meglévő díjak módosítását, új díjak hozzáadását és dinamikus kezelését.
### K: Az Aspose.Tasks támogatja az egyéni díjszámításokat?
V: Igen, az Aspose.Tasks segítségével egyéni díjszámításokat hajthat végre, hogy megfeleljen a konkrét projektkövetelményeknek.
### K: Elérhető közösségi fórum vagy támogatás az Aspose.Tasks felhasználók számára?
 V: Igen, meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15)segítséget kérni és kapcsolatba lépni más felhasználókkal.