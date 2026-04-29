---
date: 2026-01-18
description: Ismerje meg, hogyan állíthatja be a standard díjat és egyéb erőforrás‑tulajdonságokat
  az MS Projectben az Aspose.Tasks for Java használatával, beleértve, hogyan adhat
  hozzá erőforrást az MS Projecthez, és hogyan kezelheti hatékonyan az erőforrásokat.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan állítsuk be az alapdíjat az erőforrásokhoz az Aspose.Tasks-ben
url: /hu/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Állítsa be a szabványos díjat az erőforrásokhoz az Aspose.Tasks-ben

## Bevezetés
Ha Java‑alkalmazásokat fejleszt, amelyeknek Microsoft Project fájlokkal kell együttműködniük, a **szabványos díj** beállítása egy erőforrásra az egyik leggyakoribb feladat. Ebben az oktatóanyagban megtanulja, hogyan **állítsa be a szabványos díjat** és más erőforrás‑tulajdonságokat az Aspose.Tasks for Java használatával. A útmutató végére képes lesz projektobjektumot létrehozni, erőforrást hozzáadni egy MS Project fájlhoz, és magabiztosan kezelni a MS Project erőforrásait.

## Gyors válaszok
- **Mi a fő osztály a Project fájlok kezeléséhez?** `Project`
- **Melyik metódus ad hozzá új erőforrást?** `project.getResources().add()`
- **Hogyan állítja be a szabványos díjat?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Szükségem van licencre a termeléshez?** Igen, érvényes Aspose.Tasks licenc szükséges.
- **Melyik Java verzió támogatott?** Java 8+ (az aktuális JDK ajánlott).

## Mi az a „set standard rate”?
A *set standard rate* művelet egy alapértelmezett óradíjat rendel egy erőforráshoz. A projektmenedzserek ezt az értéket használják a munkaerőköltségek számításához, költségjelentések generálásához és a költségvetés előrejelzéséhez.

## Miért állítsunk díjakat az Aspose.Tasks használatával?
- **Microsoft Project telepítés nélkül** – a fájlok közvetlen manipulálása Java‑ból.
- **Teljes pontosság** – minden erőforrás‑mező, beleértve a túlórát és a költségdíjakat, megmarad.
- **Keresztplatformos** – működik Windows, Linux és macOS rendszereken.
- **Automatizálásra alkalmas** – ideális kötegelt feldolgozáshoz vagy CI pipeline‑ok integrálásához.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy a következőkkel rendelkezik:

### Java Development Environment Setup
1. **Telepítse a JDK‑t:** Győződjön meg róla, hogy a Java Development Kit (JDK) telepítve van a rendszerén. Letöltheti a [Oracle weboldaláról](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. **IDE beállítása:** Válasszon egy integrált fejlesztői környezetet (IDE), például IntelliJ IDEA, Eclipse vagy NetBeans, és állítsa be a gépén.

### Aspose.Tasks for Java Installation
1. **Töltse le az Aspose.Tasks for Java‑t:** Látogasson el a [letöltési oldalra](https://releases.aspose.com/tasks/java/) és szerezze be a legújabb verziót.
2. **Integrálja a projektbe:** Adja hozzá az Aspose.Tasks for Java könyvtárat a Java projektjéhez függőségként.

## Csomagok importálása
A kezdéshez importálnia kell a szükséges csomagokat az Aspose.Tasks for Java‑ból a projektjébe. Ez a lépés biztosítja, hogy hozzáférjen a szükséges funkciókhoz.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## 1. lépés: Projekt objektum létrehozása
A **projekt objektum** létrehozása az első lépés minden MS Project manipulációhoz. Ez képviseli a teljes projektfájlt a memóriában.

```java
Project project = new Project();
```

## 2. lépés: Erőforrás hozzáadása (add resource ms project)
Most **hozzáadunk egy erőforrást** a Resources gyűjtemény használatával. Az erőforrás neve lehet bármi, ami értelmes a menetrendjében.

```java
Resource rsc = project.getResources().add("Rsc");
```

## 3. lépés: Erőforrás tulajdonságok beállítása (how to set rates)
Itt **beállítjuk a szabványos díjat**, és bemutatjuk, hogyan állítható be a túlóra díja is. Ezeket a díjakat `BigDecimal` értékekként tároljuk a pontosság megőrzése érdekében.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| `NullPointerException` when calling `set` | Az erőforrás nem lett megfelelően hozzáadva. | Győződjön meg róla, hogy a `project.getResources().add()` nem null `Resource`‑t ad vissza. |
| `Rates appear as 0 in the saved file` | `int` típus használata `BigDecimal` helyett. | Mindig használja a `BigDecimal.valueOf()`‑t pénzügyi értékekhez. |
| `License not found` | A licencfájl nem lett betöltve a `Project` létrehozása előtt. | Töltse be a licencet (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) a program elején. |

## Következtetés
Ezeknek a lépéseknek a követésével megtanulta, hogyan **hozzon létre egy projekt objektumot**, **adjunk hozzá egy erőforrást MS Project‑hez**, és **állítsa be a szabványos díjat** valamint más erőforrás‑tulajdonságokat. Ez lehetővé teszi a költségszámítások automatizálását, egyedi jelentések generálását, és a MS Project erőforrások teljes körű kezelését Java‑ból.

## GyIK
### Kezelhet-e az Aspose.Tasks for Java összetett MS Project fájlokat?
Igen, az Aspose.Tasks for Java képes kezelni a különféle MS Project fájlformátumokat, beleértve a komplex, nagy feladathierarchiákat tartalmazókat is.

### Van-e ingyenes próba az Aspose.Tasks for Java‑hoz?
Igen, ingyenes próbaverziót érhet el az Aspose.Tasks for Java‑ból [innen](https://releases.aspose.com/).

### Hol találok támogatást az Aspose.Tasks for Java‑hoz?
Segítséget kérhet és részt vehet a megbeszélésekben az Aspose.Tasks for Java‑hoz a [támogatási fórumon](https://forum.aspose.com/c/tasks/15).

### Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks for Java‑hoz?
Ideiglenes licencet kérhet a [temporary license page](https://purchase.aspose.com/temporary-license/) oldalon értékelési célokra.

### Hol vásárolhatok licencelt verziót az Aspose.Tasks for Java‑hoz?
Licencelt verziót vásárolhat a [purchase page](https://purchase.aspose.com/buy) oldalon.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utolsó frissítés:** 2026-01-18  
**Tesztelve ezzel:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Szerző:** Aspose