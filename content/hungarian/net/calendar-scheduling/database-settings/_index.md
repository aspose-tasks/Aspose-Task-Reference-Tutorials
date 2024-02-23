---
title: Adatbázis-beállítások az Aspose.Tasks-ban
linktitle: Adatbázis-beállítások az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan importálhat projekteket Primavera adatbázisból az Aspose.Tasks for .NET segítségével. Ebben az átfogó oktatóanyagban lépésről lépésre kaphat útmutatást.
type: docs
weight: 29
url: /hu/net/calendar-scheduling/database-settings/
---
## Bevezetés

Az Aspose.Tasks for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy Microsoft Project fájlokkal dolgozzanak .NET-alkalmazásaikban. Ebben az oktatóanyagban a projektek Primavera adatbázisból történő importálására összpontosítunk az Aspose.Tasks segítségével.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- C# programozási nyelv alapismerete.
- A Visual Studio telepítve van a rendszerére.
-  Aspose.Tasks for .NET könyvtár telepítve. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
- Hozzáférés egy Primavera adatbázishoz, a szükséges engedélyekkel együtt.

## Névterek importálása

Először is importálnia kell a szükséges névtereket a C# projektbe. Ezek a névterek hozzáférést biztosítanak az Aspose.Tasks for .NET használatához szükséges osztályokhoz és metódusokhoz.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Most bontsuk fel a megadott példakódot több lépésre:

## 1. lépés: Adja meg a kapcsolati karakterláncot

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 Ebben a lépésben meghatározzuk a kapcsolati karakterláncot a Primavera adatbázishoz való csatlakozáshoz. Győződjön meg róla, hogy cseréli`DataDir` azzal a könyvtárral, ahol az adatbázisfájl található.

## 2. lépés: Adatbázis-beállítások létrehozása

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 Itt létrehozunk egy példányt`PrimaveraDbSettings` osztályba, paraméterként átadva a kapcsolati karakterláncot és a projektazonosítót. Állítsa be a projektazonosítót igényei szerint.

## 3. lépés: Állítsa be a szolgáltató invariáns nevét

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Adja meg a szolgáltató invariáns nevét. Ebben a példában az SQLite-ot használjuk, de az adatbázis-szolgáltatótól függően módosíthatja.

## 4. lépés: Töltse be a projektet

```csharp
var project = new Project(settings);
```

 Újat csinálni`Project` objektum, paraméterként adja át az adatbázis beállításait.

## 5. lépés: Projekt mentése

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Végül mentse a projektet a kívánt helyre a megadott fájlformátummal.

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan importálhatunk projekteket egy Primavera adatbázisból az Aspose.Tasks for .NET segítségével. A megadott lépéseket követve zökkenőmentesen integrálhatja a projektimportálási funkciókat .NET-alkalmazásaiba.

## GYIK

### 1. kérdés: Importálhatok projekteket különböző adatbázis-szolgáltatóktól az Aspose.Tasks for .NET használatával?

1. válasz: Igen, importálhat projekteket különböző adatbázis-szolgáltatóktól a kapcsolati karakterlánc és a szolgáltató invariáns nevének megfelelő módosításával.

### 2. kérdés: Elérhető ingyenes próbaverzió az Aspose.Tasks for .NET számára?

 2. válasz: Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját a .NET-hez[itt](https://releases.aspose.com/).

### 3. kérdés: Hol találom az Aspose.Tasks for .NET dokumentációját?

 V3: Megtalálható a dokumentáció[itt](https://reference.aspose.com/tasks/net/).

### 4. kérdés: Hogyan kaphatok támogatást az Aspose.Tasks for .NET-hez?

 4. válasz: Támogatást kaphat az Aspose.Tasks közösségi fórumon[itt](https://forum.aspose.com/c/tasks/15).

### 5. kérdés: Szükségem van ideiglenes licencre az Aspose.Tasks for .NET használatához?

 5. válasz: Ha szeretné értékelni a könyvtár teljes funkcionalitását, szerezzen be egy ideiglenes licencet a webhelyről[itt](https://purchase.aspose.com/temporary-license/).