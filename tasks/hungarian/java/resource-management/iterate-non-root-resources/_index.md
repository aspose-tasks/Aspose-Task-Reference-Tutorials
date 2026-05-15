---
date: 2026-01-13
description: Tanulja meg, hogyan iterálhat a nem gyökér erőforrásokon a Microsoft
  Project fájlokban az Aspose.Tasks for Java használatával.
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Nem-gyökér erőforrások iterálása az Aspose.Tasks for Java-val
url: /hu/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nem-gyökér erőforrások bejárása az Aspose.Tasks for Java-val

## Bevezetés
Az Aspose.Tasks for Java egy erőteljes könyvtár, amely fejlesztőknek tiszta, objektum‑orientált módot biztosít a Microsoft Project fájlok kezelésére. Ebben az útmutatóban megtanulja, **hogyan járja be a nem-gyökér erőforrásokat**, így olvashat, módosíthat vagy elemezhet erőforrás adatokat anélkül, hogy a gyökér helyőrzővel kellene foglalkoznia. Legyen szó jelentéskészítő eszközről, migrációs szkriptről vagy egyedi ütemezőről, ennek a technikának a elsajátítása pontosabbá és hatékonyabbá teszi a kódját.

## Gyors válaszok
- **Mit jelent a „nem‑gyökér erőforrás”?** Egy erőforrás, amely nem az alapértelmezett „Project” helyőrző (a gyökér csomópont).  
- **Miért szűrjük ki a gyökér erőforrást?** A gyökérnek nincs hasznos ütemezési adata, és csak elmoshatja a jelentéseket.  
- **Melyik Aspose.Tasks osztály biztosítja az erőforrás gyűjteményt?** `Project.getResources()`.  
- **Szükség van licencre ehhez a kódhoz?** Fejlesztéshez egy ingyenes próba verzió működik; a termeléshez kereskedelmi licenc szükséges.  
- **Használható ez a Java 17‑tel?** Igen – az Aspose.Tasks támogatja a Java 8‑at és újabbat.

## Előfeltételek
Mielőtt a kódba merülnél, győződj meg róla, hogy a következők rendelkezésre állnak:

1. **Java Development Kit (JDK)** – Telepítsd a legújabb JDK‑t az [Oracle weboldaláról](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java library** – Szerezd be a legújabb JAR‑t a [letöltési oldalról](https://releases.aspose.com/tasks/java/).  

## Csomagok importálása
A Java projektedben importáld a szükséges Aspose.Tasks osztályokat:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## 1. lépés: Az adatkönyvtár beállítása
```java
String dataDir = "Your Data Directory";
```
Cseréld le a `"Your Data Directory"`‑t arra az abszolút útvonalra, ahol a `.mpp` fájljaid találhatók.

## 2. lépés: A projektfájl betöltése
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
Ez egy `Project` példányt hoz létre, amely betölti a **ResourceCosts.mpp**‑t a megadott mappából.

## 3. lépés: Nem-gyökér erőforrások bejárása
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
A ciklus végigjár minden `Resource` objektumot a projektben. Az `isRoot()` ellenőrzés kihagyja a beépített gyökér erőforrást, a `System.out.println` utasítás pedig kiírja minden **nem‑gyökér erőforrás** nevét.

## Hogyan járjuk be a nem-gyökér erőforrásokat
A fenti kódrészlet bemutatja a fő mintát:

1. Szerezd meg a teljes gyűjteményt a `prj.getResources()`‑vel.  
2. Használd az `isRoot()`‑t a helyőrző kiszűréséhez.  
3. Hozz hozzá bármely erőforrás mezőt (pl. `Rsc.NAME`, `Rsc.COST`) igény szerint.

Kiterjesztheted ezt a mintát költségek aggregálására, CSV‑be exportálásra vagy egyedi üzleti szabályok alkalmazására.

## Gyakori hibák és tippek
- **Null ellenőrzések** – Egyes erőforrásoknak opcionális mezői lehetnek; mindig védd a `null` értéket a `get()` hívásakor.  
- **Teljesítmény** – Nagyon nagy projektek esetén fontold meg egy index‑alapú ciklus használatát, hogy elkerüld a köztes gyűjtemények létrehozását.  
- **Licencelés** – A kód licenc nélküli futtatása vízjelet ad az exportált fájlokhoz; gondoskodj a licenc aktiválásáról a alkalmazás indításakor.

## Összegzés
Ezeket a lépéseket követve most már tudod, **hogyan járj be a nem-gyökér erőforrásokat** az Aspose.Tasks for Java segítségével. Ez a technika lehetővé teszi, hogy a tényleges projekt erőforrásokra koncentrálj, tisztítsd meg az adatkinyeréseket, és megbízhatóbb projekt‑menedzsment megoldásokat építs.

## GYIK
### Használhatom az Aspose.Tasks for Java‑t új projektfájlok létrehozására?
Igen, az Aspose.Tasks teljes CRUD (Create, Read, Update, Delete) képességeket biztosít az MPP, MPT és XML projektformátumokhoz.  

### Támogatja az Aspose.Tasks az összes Microsoft Project fájlverziót?
Abszolút. Kezeli a Project 2003‑2019 fájlokat, beleértve a legújabb MPP specifikációkat.  

### Kompatibilis az Aspose.Tasks a Java keretrendszerekkel, például a Spring‑kel?
Igen, a könyvtárat be lehet injektálni Spring bean‑ekbe, vagy használhatod bármely standard Java alkalmazásban.  

### Testreszabhatom a projekt adatmezőket az Aspose.Tasks segítségével?
Természetesen. Az API lehetővé teszi egyedi mezők hozzáadását, módosítását vagy törlését feladatoknál, erőforrásoknál és hozzárendeléseknél.  

### Nyújt-e az Aspose.Tasks fejlesztőknek támogatást és dokumentációt?
A termék átfogó API dokumentációt, kódmintákat és egy dedikált támogatási fórumot tartalmaz a gyors segítségnyújtáshoz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utolsó frissítés:** 2026-01-13  
**Tesztelt verzió:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose  

---