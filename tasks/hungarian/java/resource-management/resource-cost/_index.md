---
date: 2026-01-15
description: Tanulja meg, hogyan dolgozhat a Microsoft Project fájlokban ütemezett
  költségvetett munkával az Aspose.Tasks for Java segítségével. Kövesse lépésről‑lépésre
  útmutatónkat.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Költségvetett költségű munka ütemezése az Aspose.Tasks for Java-val
url: /hu/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ütemezett költségvetési munka (BCWS) az Aspose.Tasks for Java segítségével

## Bevezetés

A **budgeted cost work scheduled** (BCWS) kezelése elengedhetetlen a projekt nyomon követéséhez és ahhoz, hogy a pénzügyi előrejelzés összhangban legyen a tervezett munkával. A Microsoft Projectben a BCWS azt a pénzösszeget jelöli, amelyet a megadott dátumig ütemezett munkára el kellett volna költeni. Az Aspose.Tasks for Java teljes programozási vezérlést biztosít ezek felett az értékek felett, lehetővé téve a forrásköltségek olvasását, módosítását és jelentéskészítését anélkül, hogy manuálisan megnyitná a .mpp fájlt. Ebben az útmutatóban egy komplett példán keresztül mutatjuk be, hogyan töltsünk be egy projektet, járjuk be annak erőforrásait, és jelenítsük meg az ütemezett költségvetési munkát a többi kulcsfontosságú költségmutatóval együtt.

## Gyors válaszok
- **Mit jelent a BCWS?** Budgeted Cost Work Scheduled – a tervezett költség a napig ütemezett munkára.  
- **Melyik API‑tulajdonság adja vissza a BCWS‑t?** `Rsc.BCWS` egy `Resource` objektumon.  
- **Szükségem van licencre a minta futtatásához?** Egy ingyenes értékelő licenc elegendő a teszteléshez; a teljes licenc a termeléshez kötelező.  
- **Módosíthatom a BCWS értékeket?** Igen, a `Rsc.BCWS` mezőt bármely más numerikus mezőhöz hasonlóan beállíthatja.  
- **Mely Project‑verziók támogatottak?** Minden Microsoft Project verzió 2000‑től a legújabb .mpp formátumig.

## Mi az ütemezett költségvetési munka (BCWS)?

**Budgeted Cost Work Scheduled (BCWS)** egy teljesítménymutató, amely azt a költséget tükrözi, amelyet a megadott időpontig tervezett munkáért el kellett volna költeni. Az Earned Value Management (EVM) egyik alappillére, és segít a projektmenedzsereknek a tervezett és a tényleges kiadások összehasonlításában.

## Előfeltételek

Mielőtt a kódba merülnénk, győződjön meg róla, hogy:

1. Jól ismeri a Java alapjait.  
2. Az Aspose.Tasks for Java hozzá van adva a projekthez (Maven/Gradle vagy JAR).  
3. Van egy Microsoft Project fájlja (`.mpp`), amely tartalmaz költségadatokkal rendelkező erőforrásokat (pl. *ResourceCosts.mpp*).

## Importálás csomagok

Először importálja az Aspose.Tasks osztályait, amelyek a projektek és erőforrások kezeléséhez szükségesek:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## 1. lépés: Adatkönyvtár meghatározása

```java
String dataDir = "Your Data Directory";
```

Cserélje le a `"Your Data Directory"` értéket arra az abszolút vagy relatív útvonalra, ahol a *ResourceCosts.mpp* található.

## 2. lépés: MS Project fájl betöltése

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

A `Project` konstruktor beolvassa a .mpp fájlt, és egy memóriában tárolt reprezentációt hoz létre, amelyet lekérdezhet.

## 3. lépés: Erőforrások bejárása

```java
for (Resource res : prj.getResources()) {
```

Ez a ciklus végigjárja a projektben definiált összes erőforrást, és hozzáférést biztosít azok költségmezőihez.

## 4. lépés: Erőforrás neve és költségei ellenőrzése

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

Az `if` blokkban:

* Kiírjuk a **teljes költséget** (`Rsc.COST`).  
* Kiírjuk a **ténylegesen elvégzett munka költségét** (`Rsc.ACWP`).  
* Kiírjuk az **ütemezett költségvetési munkát** (`Rsc.BCWS`) – ez a fő mutató, amelyre fókuszálunk.  
* Kiírjuk a **ténylegesen elvégzett költségvetési munkát** (`Rsc.BCWP`).

E négy érték gyors áttekintést nyújt a projekt pénzügyi állapotáról.

## Miért fontos az ütemezett költségvetési munka (BCWS) nyomon követése

* **Korai figyelmeztetés:** Ha a BCWS lényegesen magasabb a tényleges költségnél, erőforrásokat túlzottan allokálhat.  
* **Earned Value elemzés:** A BCWS kulcsfontosságú bemenet a Cost Variance (CV) és a Schedule Variance (SV) számításához.  
* **Előrejelzés:** A pontos BCWS adatok segítenek a jövőbeni cash‑flow igények előrejelzésében és a stakeholder‑jelentésekben.

## Gyakori problémák és hibaelhárítás

| Tünet | Valószínű ok | Megoldás |
|-------|--------------|----------|
| `null` jelenik meg a BCWS‑nél | Az erőforrásnak nincs költségár táblázata definiálva | Definiáljon költségár táblázatot az erőforrás számára a Microsoft Projectben, vagy állítsa be programozottan a `Rsc.COST_RATE_TABLE` segítségével |
| `ArrayIndexOutOfBoundsException` erőforrások bejárásakor | A projektfájl sérült vagy üres erőforrásbejegyzéseket tartalmaz | Ellenőrizze a .mpp fájlt a Microsoft Projectben, és távolítsa el az üres erőforrásokat |
| Váratlan értékek (pl. negatív BCWS) | Egyedi mezők felülírják a szabványos költségmezőket | Győződjön meg arról, hogy a szabványos `Rsc.BCWS` mezőt használja, és nem egy azonos nevű egyedi mezőt |

## Gyakran ismételt kérdések

**Q: Programozottan frissíthetem a BCWS értékét?**  
A: Igen. Használja a `res.set(Rsc.BCWS, newValue)` metódust, majd mentse a projektet a `prj.save("Updated.mpp")` paranccsal.

**Q: Az Aspose.Tasks támogatja a többvalutás projekteket?**  
A: Teljes mértékben. A költségmezők tiszteletben tartják a projektfájlban definiált pénznembeállításokat.

**Q: Van mód ezeknek a költségmutatóknak CSV‑be exportálására?**  
A: Az erőforrások bejárása közben az értékeket egy `StringBuilder`‑be írhatja, vagy használhat CSV‑könyvtárat a fájl generálásához.

**Q: Miben különbözik a BCWS a BCWP‑től?**  
A: A BCWS a tervezett költség az ütemezett munkára, míg a BCWP (Budgeted Cost Work Performed) a tervezett költség a ténylegesen befejezett munkára vonatkozik.

**Q: Szükség van speciális licencre a költségadatok olvasásához?**  
A: Az értékelő licenc teljes olvasási/írási hozzáférést biztosít; a kereskedelmi licenc a termelési környezetben kötelező.

## Összegzés

Az Aspose.Tasks for Java használatával pontos, programozott hozzáférést kap a **budgeted cost work scheduled** és más fontos költségmutatókhoz. Ez lehetővé teszi egyedi irányítópultok építését, az Earned Value jelentések automatizálását, és a projektek pénzügyi nyomon követését – mindezt anélkül, hogy manuálisan kellene kezelnie a Microsoft Projectet.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose