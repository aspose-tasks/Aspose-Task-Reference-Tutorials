---
title: Microsoft Project Database beállításai az Aspose.Tasks alkalmazásban
linktitle: Microsoft Project Database beállításai az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan konfigurálhatja a Microsoft Project adatbázis-beállításait az Aspose.Tasks segítségével a .NET-alkalmazásokba való zökkenőmentes integráció érdekében.
type: docs
weight: 19
url: /hu/net/advanced-concepts/msp-database-settings/
---
## Bevezetés

Ha Microsoft Project adatbázisokkal dolgozik .NET-alkalmazásaiban az Aspose.Tasks segítségével, akkor konfigurálnia kell a szükséges beállításokat a projektadatok zökkenőmentes importálásához. Ez az oktatóanyag lépésről lépésre végigvezeti a folyamaton.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:

1.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks könyvtárat innen[itt](https://releases.aspose.com/tasks/net/).
2. Hozzáférés egy Microsoft Project adatbázishoz: Az adatok importálásához hozzáféréssel kell rendelkeznie egy Microsoft Project adatbázishoz.

## Névterek importálása

Először győződjön meg arról, hogy a szükséges névtereket importálta a projektbe:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## 1. lépés: Hozzon létre kapcsolati karakterláncot

Hozza létre a kapcsolati karakterláncot a Microsoft Project adatbázishoz. Íme egy példa:

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

Ügyeljen arra, hogy a helyőrző értékeket lecserélje a tényleges adatbázis hitelesítő adataira.

## 2. lépés: Az MspDbSettings konfigurálása

 Hozzon létre egy példányt a`MspDbSettings` és adja meg a csatlakozási karakterláncot a projekt GUID-jével együtt:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## 3. lépés: Töltse be a projektadatokat

 Példányosítás a`Project` objektum a konfigurált beállításokkal:

```csharp
var project = new Project(settings);
```

## 4. lépés: Projektadatok mentése

Mentse el a betöltött projektadatokat egy fájlba:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan konfigurálhatja a Microsoft Project adatbázisokhoz való hozzáférési beállításokat az Aspose.Tasks for .NET használatával. Ezen lépések követésével zökkenőmentesen importálhatja a projektadatokat alkalmazásaiba, megkönnyítve ezzel a hatékony projektmenedzsmentet.

## GYIK

### 1. kérdés: Használhatom az Aspose.Tasks programot a Microsoft Project adatbázisok különböző verzióival?

1. válasz: Igen, az Aspose.Tasks támogatja a Microsoft Project adatbázisok különféle verzióit, ami rugalmasságot tesz lehetővé az integrációban.

### 2. kérdés: Hogyan háríthatom el a csatlakozási problémákat az adatbázissal?

 2. válasz: Győződjön meg arról, hogy a kapcsolati karakterlánc megfelelően van konfigurálva a megfelelő hitelesítő adatokkal és adatbázis-részletekkel. Tekintse meg a dokumentációt, vagy kérjen támogatást a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).

### 3. kérdés: Elérhető az Aspose.Tasks próbaverziója?

 3. válasz: Igen, elérheti az ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).

### 4. kérdés: Testreszabhatom a sémát az adatbázis-interakcióhoz?

 4. válasz: Igen, megadhatja a sémát a`MspDbSettings` objektumot az adatbázis szerkezetének megfelelően.

### 5. kérdés: Hol találhatok részletesebb dokumentációt az Aspose.Tasks használatáról?

 V5: Megtekintheti az átfogó dokumentációt[itt](https://reference.aspose.com/tasks/net/) az Aspose.Tasks funkcióinak részletes betekintéséért.