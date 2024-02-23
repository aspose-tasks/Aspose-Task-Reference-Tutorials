---
title: Szerver Save MS Project Options for Aspose.Tasks
linktitle: A Project Server mentési beállításai az Aspose.Tasks számára
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan mentheti a Microsoft Project beállításait az Aspose.Tasks számára a Project Server integrációjával. Javítsa projektmenedzsment munkafolyamatait.
type: docs
weight: 16
url: /hu/net/saving-options/project-server-save-options/
---
## Bevezetés
Ebben az oktatóanyagban az Aspose.Tasks Microsoft Project beállításainak Project Server használatával történő mentésével foglalkozunk. Az Aspose.Tasks egy hatékony .NET API, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak Microsoft Project fájlokkal. A Project Server képességeit kihasználva zökkenőmentesen integrálhatjuk az Aspose.Tasks-t projektmenedzsment munkafolyamatainkba. Ez az oktatóanyag lépésről lépésre végigvezeti a folyamaton.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  Aspose.Tasks for .NET: Az Aspose.Tasks for .NET telepítése a[letöltési link](https://releases.aspose.com/tasks/net/).
   
2. Hozzáférés a Project Serverhez: Szüksége lesz hozzáférési hitelesítő adatokra és a Project Server példány URL-címére. Ha nem rendelkezik ilyennel, ingyenes próbaverziót szerezhet be[itt](https://releases.aspose.com/).
3. Microsoft Project File: Készítse elő az Aspose.Tasks segítségével menteni kívánt Microsoft Project fájlt (.mpp).

## Névterek importálása
Először is importálnia kell a szükséges névtereket a projektben:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## 1. lépés: Inicializálja a projektet és a hitelesítő adatokat
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Ügyeljen arra, hogy cserélje ki`"Your Document Directory"`, `URL`, `Domain`, `UserName` ,és`Password` a tényleges értékeiddel.
## 2. lépés: A Project Server Manager létrehozása
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## 3. lépés: Adja meg a mentési beállításokat
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Állítsa be a`ProjectGuid`, `ProjectName`, `Timeout` ,és`PollingInterval` az Ön igényei szerint.
## 4. lépés: Projekt mentése a kiszolgálóra
```csharp
manager.CreateNewProject(project, options);
```
Ezzel elmenti a projektet a Project Serverre a megadott beállításokkal.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan mentheti el a Microsoft Project beállításait az Aspose.Tasks számára a Project Server integrációjával. Ha követi ezeket a lépéseket, az Aspose.Tasks zökkenőmentesen beépíthető a projektmenedzsment munkafolyamataiba, növelve a hatékonyságot és a termelékenységet.
## GYIK
### K: Használhatom az Aspose.Tasks-t a Microsoft Project különböző verzióival?
V: Igen, az Aspose.Tasks támogatja a Microsoft Project különféle verzióit, biztosítva a kompatibilitást a különböző környezetekben.
### K: Elérhető az Aspose.Tasks próbaverziója?
 V: Igen, beszerezheti az Aspose.Tasks ingyenes próbaverzióját a webhelyről[itt](https://releases.aspose.com/).
### K: Az Aspose.Tasks támogatja a többszálú feldolgozást?
V: Igen, az Aspose.Tasks szálbiztosra lett tervezve, lehetővé téve a projektadatok egyidejű elérését.
### K: Testreszabhatom a mentési beállításokat a Project Server integráció használatakor?
V: Igen, igényei szerint testreszabhatja a mentési beállításokat, például a projekt nevét, az időtúllépést és a lekérdezési intervallumot.
### K: Hol találok támogatást az Aspose.Tasks számára?
 V: Támogatást és segítséget találhat a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).