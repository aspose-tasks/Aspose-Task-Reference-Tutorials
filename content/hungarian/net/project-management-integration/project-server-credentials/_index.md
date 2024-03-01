---
title: Az MS Project Server hitelesítő adatainak kezelése az Aspose.Tasks alkalmazásban
linktitle: Project Server hitelesítő adatok kezelése az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti zökkenőmentesen az MS Project Server hitelesítő adatait az Aspose.Tasks for .NET segítségével. Növelje a projektmenedzsment hatékonyságát.
type: docs
weight: 22
url: /hu/net/project-management-integration/project-server-credentials/
---
## Bevezetés
projektmenedzsment területén a hatékony koordináció és a zökkenőmentes kommunikáció kulcsfontosságú a sikeres projektvégrehajtáshoz. Az Aspose.Tasks for .NET átfogó megoldást kínál a Microsoft Project Server hitelesítő adatainak kezelésére, lehetővé téve a felhasználók számára a projektadatok biztonságos elérését és kezelését. Ez az oktatóanyag az MS Project Server hitelesítő adatainak kezelését mutatja be az Aspose.Tasks for .NET használatával, és végigvezeti a felhasználókat az egyes lépéseken a zökkenőmentes élmény biztosítása érdekében.
## Előfeltételek
Mielőtt elkezdené az MS Project Server hitelesítő adatainak Aspose.Tasks for .NET segítségével történő kezelését, győződjön meg arról, hogy teljesülnek a következő előfeltételek:
### 1. Az Aspose.Tasks telepítése .NET-hez
 Kezdésként töltse le és telepítse az Aspose.Tasks for .NET programot a mellékelt webhelyről[letöltési link](https://releases.aspose.com/tasks/net/). Kövesse a telepítési utasításokat a könyvtár .NET-környezetébe történő zökkenőmentes integrálásához.
### 2. Hozzáférés a hitelesítő adatokhoz
Gyűjtse össze az MS Project Server eléréséhez szükséges hitelesítő adatokat. Ez magában foglalja a Project Serverhez társított SharePoint tartománycímet, felhasználónevet és jelszót.

## Névterek importálása
A .NET-projektben importálja a szükséges névtereket az Aspose.Tasks for .NET által biztosított funkciók hatékony kihasználásához.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## 1. lépés: Határozza meg a dokumentumkönyvtár elérési útját
```csharp
String DataDir = "Your Document Directory";
```
## 2. lépés: Állítsa be a SharePoint tartomány címét, felhasználónevét és jelszavát
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## 3. lépés: Hozzon létre Project Server hitelesítő adatokat
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## 4. lépés: Töltse be a projektfájlt
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## 5. lépés: A Project Server Manager inicializálása
```csharp
var manager = new ProjectServerManager(credentials);
```
## 6. lépés: Új projekt létrehozása
```csharp
manager.CreateNewProject(newProject);
```
## 7. lépés: Töltse le a projektlistát
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## 8. lépés: Ismétlés a projektlistán keresztül
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Következtetés
Az MS Project Server hitelesítő adatainak hatékony kezelése kiemelkedően fontos az egyszerűsített projektmenedzsmenthez. Az Aspose.Tasks for .NET leegyszerűsíti ezt a folyamatot azáltal, hogy robusztus funkciókat biztosít. Az ebben az oktatóanyagban felvázolt útmutató lépésenkénti követésével a felhasználók zökkenőmentesen integrálhatják az Aspose.Tasks for .NET-et projektjeikbe, így biztosítva a projektadatok biztonságos elérését és kezelését.
## GYIK
### K: Az Aspose.Tasks for .NET kompatibilis a Microsoft Project Server összes verziójával?
V: Az Aspose.Tasks for .NET kompatibilis a Microsoft Project Server különféle verzióival, sokoldalúságot és rugalmasságot biztosítva a felhasználók számára.
### K: Integrálhatom az Aspose.Tasks for .NET-et a meglévő .NET-projektembe?
V: Igen, az Aspose.Tasks for .NET zökkenőmentesen integrálható a meglévő .NET-projektekbe, ami elősegíti a hatékony projektkezelési lehetőségeket.
### K: Az Aspose.Tasks for .NET támogatja a projekt erőforrásainak elérését?
V: Természetesen az Aspose.Tasks for .NET átfogó támogatást nyújt a projekterőforrásokhoz való hozzáféréshez és azok kezeléséhez, növelve a projektmenedzsment hatékonyságát.
### K: Rendelkezésre állnak-e licencelési lehetőségek az Aspose.Tasks for .NET számára?
V: Igen, az Aspose.Tasks for .NET rugalmas licencelési lehetőségeket kínál, beleértve az ideiglenes licenceket próbacélokra és a teljes licenceket kereskedelmi használatra.
### K: Hol kérhetek segítséget vagy támogatást az Aspose.Tasks for .NET-hez?
 V: Az Aspose.Tasks for .NET-re vonatkozó kérdéseivel vagy segítségével kapcsolatban keresse fel a támogatási fórumot a következő címen:[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).## Teljes forráskód