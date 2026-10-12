---
date: 2026-10-10
description: Tanulja meg, hogyan adjon hozzá extended attribute-et az Aspose.Tasks-ben,
  használja az evaluation functions-t, és generáljon project reports-ot ezzel a Java
  project management library-vel.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Evaluation Functions támogatása az Aspose.Tasks képletekben
og_description: Tanulja meg, hogyan adjon hozzá extended attribute-et az Aspose.Tasks-ben,
  használja az evaluation functions-t, és generáljon project reports-ot ezzel a Java
  project management library-vel.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Hogyan adjon hozzá extended attribute-et az Aspose.Tasks képletekben
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Hogyan adjon hozzá extended attribute-et az Aspose.Tasks képletekben
url: /hu/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjon hozzá kiterjesztett attribútumot az Aspose.Tasks képletekben

## Bevezetés
Aspose.Tasks for Java egy **Java projektmenedzsment könyvtár**, amely lehetővé teszi projektjelentések generálását egy `Project` objektum Java-ban történő létrehozásával, és a Microsoft Project függvények közvetlen kiértékelésével a kódban. Ezeknek a képleteknek a beágyazásával összetett számításokat végezhet, egyedi jelentéseket generálhat, és automatizálhatja a projekt elemzését anélkül, hogy elhagyná a fejlesztői környezetet. Ebben az útmutatóban végigvezetjük a projektobjektum létrehozását, egy kiterjesztett attribútum hozzáadását, és a kiértékelő függvények használatát a **add custom field task** adatokhoz.

## Gyors válaszok
- **Mi jelent a “create project object java”?** Létrehoz egy memóriában lévő `Project` példányt, amelyet programozottan kezelhet.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (letöltés a hivatalos oldalról).  
- **Szükségem van licencre?** Egy ideiglenes vagy teljes Aspose.Tasks licenc szükséges a termeléshez; ingyenes próba elérhető.  
- **Használhatok egyedi mezőket?** Igen – **add extended attribute** hozzáadható a feladatokhoz, és egyedi mezőként kezelhető.  
- **Ez kompatibilis minden Project fájlformátummal?** Az Aspose.Tasks 3 fő formátumot (MPP, MPT, XML) és több mint 50 további be- és kimeneti formátumot támogat.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. **Java fejlesztői környezet** – JDK 8+ és egy IDE, például IntelliJ IDEA vagy Eclipse.  
2. **Aspose.Tasks for Java könyvtár** – Töltse le és adja hozzá a könyvtárat a [Aspose.Tasks for Java letöltési oldalról](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Adja hozzá az Aspose.Tasks névteret a Java osztályához, hogy dolgozhasson projektek, feladatok és kiterjesztett attribútumok kezelésével:

```java
import com.aspose.tasks.*;
```

## Projektjelentés generálása – create project object java
A `Project` osztály egy Microsoft Project fájlt reprezentál memóriában, feladatokat, erőforrásokat és egyedi adatokat tesz elérhetővé. Ennek az osztálynak a példányosítása egy tárolót biztosít az összes projekt elemhez, amelyet definiálni fog.

```java
Project project = new Project();
```

A fenti sor **creates project object java**-t hoz létre, amely üres és testreszabásra kész.

## Hogyan adjon hozzá kiterjesztett attribútumot
A `ExtendedAttributeDefinition` osztály egy egyedi mezőt definiál, amely feladatokhoz csatolható. Egy kiterjesztett attribútum hozzáadásához hozza létre ennek az osztálynak egy példányát `Number` típussal, adjon neki egy alias-t, például „Sine”, adja hozzá a projekt `ExtendedAttributes` gyűjteményéhez, majd kapcsolja minden feladathoz, amelyik igényli az egyedi mezőt.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Itt **add extended attribute** típusú `Number` attribútumot adunk hozzá „Sine” névvel, és összekapcsoljuk a feladatokkal.

## A kiterjesztett attribútum hozzáadása a projekthez
Regisztrálja az attribútumdefiníciót a projektben, hogy minden feladat hivatkozhasson rá.

```java
project.getExtendedAttributes().add(attr);
```

## Új feladat létrehozása
`Task` egy munkatételt képvisel a projektben, és tartalmazhat egyedi mezőket.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Egyedi mező feladat hozzáadása a projekthez
Kapcsolja össze a korábban definiált kiterjesztett attribútumot az újonnan létrehozott feladattal, így a feladat egy egyedi „Sine” mezőt kap, amelyet képletekben vagy számításokban használhat.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Most a feladat egy egyedi „Sine” mezőt tartalmaz, amelyet képletekben vagy számításokban használhat. Ez az a mód, ahogyan programozottan **add custom field task** adatokat ad hozzá.

## Miért használjunk kiértékelő függvényeket?
A kiértékelő függvények lehetővé teszik natív Microsoft Project képletek (pl. `Sin([Start])`) közvetlen beágyazását az Aspose.Tasks-be, így külső feldolgozás nélkül végezhet el számításokat menet közben. Ez egy helyen tartja a projekt logikáját, csökkenti az adat‑szinkronizációs hibákat, és felgyorsítja a jelentéskészítést. Az Aspose.Tasks több mint 100 MS Project függvény kiértékelését támogatja, átfogó számítási motorral Java-ban.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **Formula returns `NaN`** | Ellenőrizze, hogy az egyedi mező típusa megfelel-e a várt numerikus típusnak. |
| **Extended attribute not visible** | Győződjön meg róla, hogy az attribútumdefiníció a projekthez **előtt** kerül hozzáadásra, mielőtt feladatokat hozna létre. |
| **License exception** | Telepítsen egy ideiglenes vagy teljes **Aspose.Tasks license**-t; a próbaverzió bizonyos funkciókat korlátozhat. |
| **Missing temporary license** | Szerezzen egy **temporary Aspose license**-t az Aspose weboldaláról. |

## Gyakran ismételt kérdések

**Q: Kezelheti az Aspose.Tasks for Java a komplex MS Project képleteket?**  
A: Igen, az Aspose.Tasks for Java támogatja a széles körű MS Project függvények kiértékelését, lehetővé téve a komplex számításokat Java alkalmazásokban.

**Q: Kompatibilis az Aspose.Tasks for Java a Microsoft Project fájlok különböző verzióival?**  
A: Igen, az Aspose.Tasks for Java támogatja a Microsoft Project fájlok különböző verzióit, beleértve az MPP, MPT és XML formátumokat.

**Q: Próbálhatom ki az Aspose.Tasks for Java-t vásárlás előtt?**  
A: Igen, letölthet egy ingyenes próbaverziót az Aspose.Tasks for Java-ból a weboldalról: [Aspose.Tasks for Java vásárlási oldal](https://purchase.aspose.com/buy).

**Q: Hogyan kaphatok támogatást az Aspose.Tasks for Java-hoz?**  
A: Támogatást kaphat az Aspose.Tasks közösségi fórumról: [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Elérhető ideiglenes licenc az Aspose.Tasks for Java-hoz?**  
A: Igen, ideiglenes licencet szerezhet a teszteléshez az Aspose weboldalról: [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

## Következtetés
A lépések követésével megtanulta, hogyan **create project object**, **add extended attribute**, és hogyan használja a kiértékelő függvényeket a **generate project report** automatikus létrehozásához. Most kibővítheti ezt az alapot, hogy fejlettebb projekt-analitikákat, egyedi irányítópultokat vagy automatizált ütemező eszközöket építsen – mindezt az Aspose.Tasks for Java hajtja.

---

**Legutóbb frissítve:** 2026-10-10  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.10  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Egyedi oszlopok és kiterjesztett attribútumok Java projektmenedzsmentben](/tasks/java/project-management/extended-attributes/)
- [Kiterjesztett feladat attribútumok olvasása Aspose.Tasks for Java-val](/tasks/java/task-properties/extended-task-attributes/)
- [Hogyan használjuk az Aspose.Tasks for Java-t – Kiterjesztett attribútumok hozzáadása erőforrás hozzárendelésekhez](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}