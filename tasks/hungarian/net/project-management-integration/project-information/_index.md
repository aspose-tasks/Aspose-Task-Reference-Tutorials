---
title: Az MS projekt információinak kibontása az Aspose.Tasks-ból
linktitle: Projektinformációk kinyerése az Aspose.Tasks programban
second_title: Aspose.Tasks .NET API
description: Tanulja meg, hogyan bonthatja ki könnyedén az MS Project adatait az Aspose.Tasks for .NET segítségével. Merüljön el átfogó oktatóanyagunkban.
weight: 20
url: /hu/net/project-management-integration/project-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az MS projekt információinak kibontása az Aspose.Tasks-ból

## Bevezetés
Hatékonyan szeretne információkat kinyerni a Microsoft Project fájlokból az Aspose.Tasks for .NET segítségével? Ebben az oktatóanyagban lépésről lépésre végigvezetjük a folyamaton. Mielőtt azonban belemerülnénk a megvalósítás részleteibe, győződjünk meg arról, hogy mindennel rendelkezik, amire szüksége van.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
### 1. Aspose.Tasks for .NET
 Győződjön meg arról, hogy telepítette az Aspose.Tasks for .NET könyvtárat. Ha még nem tette meg, letöltheti a webhelyről[Aspose.Tasks .NET webhelyhez](https://releases.aspose.com/tasks/net/).
### 2. A SharePoint hitelesítő adatai
Szüksége lesz a hitelesítő adatokra, hogy hozzáférjen ahhoz a SharePointhoz, ahol az MS Project fájljait tárolják. Győződjön meg arról, hogy rendelkezik a következő információkkal:
- SharePoint tartomány címe
- Felhasználónév
- Jelszó
## Névterek importálása
Miután rendezte az előfeltételeket, ideje importálni a szükséges névtereket a projektbe.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Most bontsuk le több lépésre az MS Project információk kinyerésének folyamatát.
## 1. lépés: Adja meg a hitelesítő adatokat
Először is meg kell adnia SharePoint hitelesítő adatait a Project Server eléréséhez.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## 2. lépés: A Project Server Manager inicializálása
 Ezután inicializálja a`ProjectServerManager` példányt a megadott hitelesítő adatokkal.
```csharp
var reader = new ProjectServerManager(credentials);
```
## 3. lépés: Töltse le a projektlistát
Most lekérheti a projektek listáját a Project Serverről.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## 4. lépés: Projektinformációk nyomtatása
Végül ismételje meg a projektek listáját, és nyomtassa ki az információikat.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan bontsa ki az MS Project információit az Aspose.Tasks for .NET segítségével. Ezzel a tudással most már zökkenőmentesen integrálhatja ezt a funkciót .NET-alkalmazásaiba.
## GYIK
### 1. kérdés: Használhatom az Aspose.Tasks for .NET programot a Microsoft Project bármely verziójával?
V: Igen, az Aspose.Tasks for .NET támogatja a Microsoft Project különféle verzióit, beleértve a 2003-as, 2007-es, 2010-es, 2013-as, 2016-os és 2019-es verziókat.
### 2. kérdés: Az Aspose.Tasks for .NET kompatibilis Windows és Linux platformokkal is?
V: Igen, az Aspose.Tasks for .NET Windows és Linux platformokkal is kompatibilis, így sokoldalúan használható különböző fejlesztői környezetekhez.
### 3. kérdés: Kivonhatom a feladatfüggőségeket az Aspose.Tasks for .NET használatával?
V: Abszolút! Az Aspose.Tasks for .NET robusztus funkcionalitást biztosít nemcsak az alapvető projektinformációk kinyerésére, hanem a feladatok függőségeire és egyéb bonyolult részletekre is.
### 4. kérdés: Az Aspose.Tasks for .NET kínál technikai támogatást?
 V: Igen, technikai támogatást kaphat az Aspose.Tasks for .NET-hez a következőn keresztül[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15), ahol kérdéseket tehet fel, és szakértőktől kérhet segítséget.
### 5. kérdés: Kipróbálhatom az Aspose.Tasks-t .NET-hez a vásárlás előtt?
 V: Természetesen! Használhatja az Aspose.Tasks ingyenes próbaverzióját a .NET-hez a webhelyről[kiadások oldala](https://releases.aspose.com/), amely lehetővé teszi, hogy a vásárlási döntés meghozatala előtt felfedezze tulajdonságait.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
