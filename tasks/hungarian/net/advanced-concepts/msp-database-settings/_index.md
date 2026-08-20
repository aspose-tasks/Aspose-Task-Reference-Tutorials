---
date: 2026-03-14
description: Tanulja meg, hogyan határozza meg a Microsoft Project adatbázis sémáját
  az Aspose.Tasks segítségével, és hogyan importálja a projektadatokat .NET alkalmazásokba.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Adatbázis séma megadása a Project DB-hez az Aspose.Tasks segítségével
url: /hu/net/advanced-concepts/msp-database-settings/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beállítások a Microsoft Project adatbázishoz az Aspose.Tasks-ben

## Bevezetés

Ha .NET alkalmazásokban Microsoft Project adatbázisokkal dolgozik az Aspose.Tasks használatával, akkor **meg kell adnia az adatbázis sémát** és be kell állítania a szükséges konfigurációkat a **projektadatok** zökkenőmentes importálásához. Ez az útmutató lépésről lépésre végigvezeti Önt a folyamaton, bemutatva, **hogyan konfigurálja a kapcsolati** adatokat, **hogyan hozza létre a .NET kapcsolati karakterláncot**, és végül **hogyan mentse a projektet MPP formátumban**.

## Gyors válaszok
- **Mi a fő cél?** Az adatbázis séma megadása és egy Project adatbázis importálása egy .NET alkalmazásba.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for .NET.  
- **Hogyan csatlakozom a Project Serverhez?** A megfelelő SQL kapcsolati karakterlánc felépítésével és a `MspDbSettings` használatával.  
- **Milyen fájlformátum jön létre?** Egy MPP fájl, amelyet a `SaveFileFormat.Mpp` ment.  
- **Megváltoztathatom a séma nevét?** Igen, állítsa be a `Schema` tulajdonságot a `MspDbSettings`‑ben.

## Hogyan adja meg az adatbázis sémát a Project DB-hez

Fontos megérteni, **miért lehet szükség az adatbázis séma megadására**. Sok vállalati környezetben a Project Server adatbázisa egy egyedi sémában (pl. `dbo`, `psdata`) található. A séma explicite beállításával biztosítható, hogy az Aspose.Tasks a megfelelő táblákat kérdezze le, elkerülve a futásidejű hibákat és garantálva a pontos adatimportálást.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következőkkel rendelkezik:

1. Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks könyvtárat [innen](https://releases.aspose.com/tasks/net/).  
2. Hozzáférés egy Microsoft Project adatbázishoz: Rendelkeznie kell egy Microsoft Project adatbázishoz való hozzáféréssel az adatok importálásához.  

## Névterek importálása

Először győződjön meg arról, hogy a szükséges névtereket importálja a projektjébe:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## 1. lépés: Kapcsolati karakterlánc létrehozása

Állítsa össze a kapcsolati karakterláncot a Microsoft Project adatbázishoz. Itt **létrehozza a .NET kapcsolati karakterláncot**, és meghatározza, **hogyan csatlakozik a Project Serverhez**.

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

> **Pro tip:** Ellenőrizze duplán a `DataSource` és `InitialCatalog` értékeket; ezeknek meg kell egyezniük a szerver címmel és a közzétett adatbázis nevével.

## 2. lépés: MspDbSettings konfigurálása

Hozzon létre egy `MspDbSettings` példányt, adja át a kapcsolati karakterláncot, és **adja meg az adatbázis sémát** a `Schema` tulajdonság beállításával. Ez tájékoztatja az Aspose.Tasks‑t, hogy melyik sémát kérdezze le.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Itt megadjuk a projekt GUID‑ját is, amely az adott projektet azonosítja, amelyet be szeretnénk tölteni.

## 3. lépés: Projektadatok betöltése

Hozzon létre egy `Project` objektumot a konfigurált beállításokkal. Ez a lépés hatékonyan **importálja a projektadatokat** az adatbázisból egy .NET objektumba.

```csharp
var project = new Project(settings);
```

## 4. lépés: Projektadatok mentése

Végül mentse a betöltött projektet egy MPP fájlba a lemezen. Ez bemutatja, **hogyan mentse a projektet MPP‑ként** az Aspose.Tasks API‑val.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

A kód futtatása után megtalálja a `ImportProjectDataFromDatabase_out.mpp` fájlt a kimeneti könyvtárban, készen arra, hogy megnyissa a Microsoft Projectben.

## Összegzés

Ebben az útmutatóban megtanulta, hogyan **adja meg az adatbázis sémát** egy Microsoft Project adatbázishoz, **konfigurálja a kapcsolatot**, **importálja a projektet**, és **mentse a projektet MPP‑ként** az Aspose.Tasks for .NET használatával. Ezek a lépések lehetővé teszik a Project Server adatok zökkenőmentes integrálását egyedi alkalmazásaiba, és segítenek robusztus projektmenedzsment megoldásokat építeni.

## Gyakran Ismételt Kérdések

### Q1: Használhatom az Aspose.Tasks‑et különböző verziójú Microsoft Project adatbázisokkal?
A1: Igen, az Aspose.Tasks különböző Microsoft Project adatbázis verziókat támogat, így rugalmas integrációt biztosít.

### Q2: Hogyan háríthatom el a kapcsolati problémákat az adatbázissal?
A2: Győződjön meg arról, hogy a kapcsolati karakterlánc helyesen van beállítva a megfelelő hitelesítő adatokkal és adatbázis részletekkel. További információért tekintse meg a dokumentációt vagy kérjen segítséget a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15).

### Q3: Van elérhető próbaverzió az Aspose.Tasks‑hez?
A3: Igen, egy ingyenes próbaverziót letölthet [innen](https://releases.aspose.com/).

### Q4: Testreszabhatom a sémát az adatbázis interakcióhoz?
A4: Igen, a `MspDbSettings` objektum `Schema` tulajdonságával megadhatja a saját adatbázis struktúrájának megfelelő sémát.

### Q5: Hol találok részletesebb dokumentációt az Aspose.Tasks használatáról?
A5: A részletes dokumentációt felfedezheti [itt](https://reference.aspose.com/tasks/net/), ahol alapos betekintést nyerhet az Aspose.Tasks funkcióiba.

**K: Működik ez a megközelítés Azure SQL adatbázisokkal?**  
A: Teljes mértékben. Csak állítsa be a `DataSource`‑t az Azure szerver nevére, és győződjön meg róla, hogy a TLS/SSL beállítások engedélyezve vannak.

**K: Hogyan kezeljem a nagy méretű Project adatbázisokat időkorlát túllépés nélkül?**  
A: Növelje a `ConnectTimeout` értékét a kapcsolati karakterláncban, és szükség esetén töltse be a projekteket kötegekben.

---

**Utoljára frissítve:** 2026-03-14  
**Tesztelve:** Aspose.Tasks 24.12 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}