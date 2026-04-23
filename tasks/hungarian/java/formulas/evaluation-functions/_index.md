---
date: 2026-02-13
description: Tanulja meg, hogyan generáljon projektjelentést egy projektobjektum Java‑ban
  történő létrehozásával, kiterjesztett attribútumok hozzáadásával, és az Aspose.Tasks
  értékelő függvényeinek használatával.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Projektjelentés generálása – Projektobjektum létrehozása Java
url: /hu/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az Aspose.Tasks képletek értékelési függvényeinek támogatása

## Bevezetés
Az Aspose.Tasks for Java lehetővé teszi, hogy **generate project report** készítsen úgy, hogy Java-ban egy **project object**-et hoz létre, és közvetlenül a kódban értékeli a Microsoft Project függvényeket. Ezeknek a képleteknek a beágyazásával összetett számításokat végezhet, egyedi jelentéseket generálhat, és automatizálhatja a projekt elemzést anélkül, hogy elhagyná a fejlesztői környezetet. Ebben az útmutatóban végigvezetünk a projektobjektum létrehozásán, egy kiterjesztett attribútum hozzáadásán, és az értékelési függvények használatán a **add custom field task** adatokhoz.

## Gyors válaszok
- **Mi jelent a “create project object java”?** Létrehoz egy memóriában lévő `Project` példányt, amelyet programozott módon módosíthat.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (download from the official site).  
- **Szükségem van licencre?** Egy ideiglenes vagy teljes Aspose.Tasks licenc szükséges a termelési használathoz; ingyenes próba verzió elérhető.  
- **Használhatok egyéni mezőket?** Igen – **add extended attribute**-t hozzáadhat a feladatokhoz, és egyéni mezőként kezelheti.  
- **Kompatibilis-e minden Project fájlformátummal?** Az Aspose.Tasks támogatja az MPP, MPT és XML formátumokat.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik a következőkkel:

1. **Java fejlesztői környezet** – JDK 8+ és egy IDE, például IntelliJ IDEA vagy Eclipse.  
2. **Aspose.Tasks for Java könyvtár** – Töltse le és illessze be a könyvtárat a [Aspose.Tasks for Java letöltési oldalról](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Adja hozzá az Aspose.Tasks névteret a Java osztályához, hogy projektjekkel, feladatokkal és kiterjesztett attribútumokkal dolgozhasson:

```java
import com.aspose.tasks.*;
```

## Projektjelentés generálása – create project object java
Hozzon létre egy új `Project` objektumot. Ez fogja szolgálni a tárolóként minden feladat, erőforrás és egyéni adat számára, amelyet definiálni fog.

```java
Project project = new Project();
```

A fenti sor **creates project object java**-t hoz létre, amely üres és készen áll a testreszabásra.

## Kiterjesztett attribútum hozzáadása
Definiáljon egy kiterjesztett attribútumot, amely egyéni numerikus adatot (pl. szinusz értéket) tárol minden feladathoz.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Itt **add extended attribute**-t adunk hozzá `Number` típusú, “Sine” nevű attribútumként, és társítjuk a feladatokhoz.

## Kiterjesztett attribútum hozzáadása a projekthez
Regisztrálja az attribútumdefiníciót a projektben, hogy minden feladat hivatkozhasson rá.

```java
project.getExtendedAttributes().add(attr);
```

## Új feladat létrehozása
Adjon hozzá egy egyszerű, “Task” nevű feladatot a projekt gyökérfeladata alá.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Kiterjesztett attribútum társítása a feladathoz
Kapcsolja össze a korábban definiált kiterjesztett attribútumot az újonnan létrehozott feladattal.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Most a feladat egy egyéni “Sine” mezőt tartalmaz, amelyet képletekben vagy számításokban használhat. Ez az a mód, ahogyan programozott módon **add custom field task** adatokat ad hozzá.

## Miért használjunk értékelési függvényeket?
A MS Project függvények beágyazása az Aspose.Tasks képletekbe lehetővé teszi, hogy:

- Végrehajtson valós‑időben számításokat (pl. `Sin([Start])`) külső eszközök nélkül.  
- Minden projektlogikát egyetlen, karbantartható kódbázisban tartson.  
- Dinamikus jelentéseket generáljon, amelyek tükrözik a valós‑időben változó adatokat, segítve a **generate project report** automatikus elkészítését.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **Formula visszaadja a `NaN` értéket** | Ellenőrizze, hogy az egyéni mező típusa megegyezik-e a várt numerikus típussal. |
| **Kiterjesztett attribútum nem látható** | Győződjön meg róla, hogy az attribútumdefiníció a feladatok létrehozása **előtt** hozzá van adva a projekthez. |
| **Licenc kivétel** | Telepítsen egy ideiglenes vagy teljes **Aspose.Tasks licencet**; a próbaverzió bizonyos funkciókat korlátozhat. |
| **Hiányzó ideiglenes licenc** | Szerezzen **ideiglenes Aspose licencet** az Aspose weboldaláról. |

## Gyakran Ismételt Kérdések

**Q: Kezelni tudja az Aspose.Tasks for Java a komplex MS Project képleteket?**  
A: Igen, az Aspose.Tasks for Java támogatja a széles körű MS Project függvények értékelését, lehetővé téve a komplex számításokat Java alkalmazásokban.

**Q: Kompatibilis-e az Aspose.Tasks for Java a Microsoft Project fájlok különböző verzióival?**  
A: Igen, az Aspose.Tasks for Java támogatja a Microsoft Project fájlok különböző verzióit, beleértve az MPP, MPT és XML formátumokat.

**Q: Próbálhatom-e az Aspose.Tasks for Java-t vásárlás előtt?**  
A: Igen, letöltheti az Aspose.Tasks for Java ingyenes próba verzióját a [itt](https://purchase.aspose.com/buy) található weboldalról.

**Q: Hogyan kaphatok támogatást az Aspose.Tasks for Java-hoz?**  
A: Támogatást kaphat az Aspose.Tasks közösségi fórumon [itt](https://forum.aspose.com/c/tasks/15).

**Q: Elérhető ideiglenes licenc az Aspose.Tasks for Java-hoz?**  
A: Igen, ideiglenes licencet szerezhet tesztelési célra az Aspose weboldalról [itt](https://purchase.aspose.com/temporary-license/).

## Összegzés
Hozzávettem ezekhez a lépésekhez, megtanulta, hogyan **create project object**, **add extended attribute**, és hogyan használja az értékelési függvényeket a **generate project report** automatikus elkészítéséhez. Most már bővítheti ezt az alapot, hogy fejlettebb projekt-analitikát, egyedi irányítópultokat vagy automatizált ütemező eszközöket építsen – mindezt az Aspose.Tasks for Java hajtja.

---

**Legutóbb frissítve:** 2026-02-13  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.10  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}