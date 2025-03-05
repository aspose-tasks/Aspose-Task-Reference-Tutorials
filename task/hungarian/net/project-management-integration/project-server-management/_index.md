---
title: MS Project Server kezelése Aspose.Tasks segítségével
linktitle: Project Server kezelése az Aspose.Tasks segítségével
second_title: Aspose.Tasks .NET API
description: Oldja fel az MS Project Server zökkenőmentes kezelését az Aspose.Tasks for .NET segítségével. Automatizálja a projektfeladatokat könnyedén.
type: docs
weight: 23
url: /hu/net/project-management-integration/project-server-management/
---
## Bevezetés
Ebben az oktatóanyagban az MS Project Server kezelésével foglalkozunk az Aspose.Tasks for .NET használatával. Az Aspose.Tasks egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak Microsoft Project fájlokkal, lehetővé téve a projektadatok zökkenőmentes integrációját és kezelését.
## Előfeltételek
Mielőtt belevágnánk az MS Project Server Aspose.Tasks segítségével történő kezelésébe, győződjön meg arról, hogy beállította a következő előfeltételeket:
1. Microsoft Project Server: Hozzá kell férnie egy olyan Microsoft Project Server-példányhoz, ahol rendszergazdai jogosultságokkal vagy legalább jogosultságokkal rendelkezik projektek létrehozásához és kezeléséhez.
2.  Aspose.Tasks for .NET Library: Győződjön meg arról, hogy letöltötte és telepítette az Aspose.Tasks for .NET könyvtárat. Letöltheti a[weboldal](https://releases.aspose.com/tasks/net/).
3. Hitelesítési adatok: Szerezze be a szükséges hitelesítési adatokat az MS Project Server példányával történő hitelesítéshez. Ez általában felhasználónevet és jelszót tartalmaz.
## Névterek importálása
Mielőtt elkezdené, győződjön meg arról, hogy importálta a szükséges névtereket a C# kódban:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## 1. lépés: A hitelesítési adatok beállítása
Először is be kell állítania a hitelesítési adatokat az MS Project Server-példányhoz való csatlakozáshoz. Ez magában foglalja a domain címét, felhasználónevét és jelszavát.
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## 2. lépés: Töltse be a projektet
Ezután töltse be az Aspose.Tasks segítségével kezelni kívánt MS Project fájlt.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## 3. lépés: A Project Server Manager létrehozása
 Példányosítás a`ProjectServerManager` objektumot a korábban meghatározott hitelesítő adatok használatával.
```csharp
var manager = new ProjectServerManager(credentials);
```
## 4. lépés: Adja meg a mentési beállításokat
Adjon meg konkrét mentési beállításokat a projekthez. Például beállíthat egy időtúllépést a művelethez.
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## 5. lépés: Projekt létrehozása vagy frissítése
Végül hozza létre vagy frissítse a projektet az MS Project Serveren.
```csharp
manager.CreateNewProject(project, options);
```
Gratulálunk! Sikeresen kezelte az MS Project Servert az Aspose.Tasks for .NET használatával.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan kezelhető az MS Project Server programozottan az Aspose.Tasks for .NET használatával. A megadott lépésekkel zökkenőmentesen integrálhatja az Aspose.Tasks-t .NET-alkalmazásaiba, így automatizálhatja az MS Project Server projektkezelési feladatait.
## GYIK
### K: Az Aspose.Tasks kompatibilis a Microsoft Project Server összes verziójával?
V: Az Aspose.Tasks támogatja a Microsoft Project Server különféle verzióival való integrációt, biztosítva a kompatibilitást a különböző környezetekben.
### K: Végezhetek tömeges műveleteket a projekteken az Aspose.Tasks használatával?
V: Igen, az Aspose.Tasks lehetővé teszi tömeges műveletek végrehajtását, például projektek létrehozását, frissítését és törlését az MS Project Serveren.
### K: Az Aspose.Tasks támogatást nyújt a projektütemezéshez és az erőforrás-kezeléshez?
V: Természetesen az Aspose.Tasks átfogó támogatást nyújt a projektütemezéshez, az erőforrás-elosztáshoz és a feladatkezelési funkciókhoz.
### K: Lehetséges-e automatizálni a jelentéskészítési feladatokat az Aspose.Tasks segítségével?
V: Igen, az Aspose.Tasks lehetővé teszi, hogy automatizálja a projektadatokon alapuló egyéni jelentések előállítását, megkönnyítve a projektek hatékony nyomon követését és elemzését.
### K: Kipróbálhatom az Aspose.Tasks-t a vásárlás előtt?
 V: Igen, felfedezheti az Aspose.Tasks képességeit, ha ingyenes próbaverziót ér el a[weboldal](https://purchase.aspose.com/temporary-license/).