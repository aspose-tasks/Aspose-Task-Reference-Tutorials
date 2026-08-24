---
date: 2026-08-24
description: Ismerje meg, hogyan adhat hozzá erőforrást az MS Projectben, állíthatja
  be a standard díjat és egyéb erőforrás‑tulajdonságokat az Aspose.Tasks for Java
  használatával, és kezelheti hatékonyan az erőforrásokat.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Erőforrás‑tulajdonságok beállítása az Aspose.Tasks-ben
og_description: Erőforrás hozzáadása az MS Projecthez és standard díj beállítása az
  Aspose.Tasks for Java használatával. Ismerje meg az előfeltételeket, a lépésről‑lépésre
  kódot és a hibaelhárítást ebben a tömör útmutatóban.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Erőforrás hozzáadása az MS Projecthez és díj beállítása az Aspose.Tasks
  (Java) segítségével
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Hogyan adjon hozzá erőforrást az MS Projecthez az Aspose.Tasks használatával
url: /hu/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erőforrás hozzáadása MS Projecthez és díj beállítása az Aspose.Tasks-ben

## Bevezetés
Ha Java alkalmazásokat fejleszt, amelyeknek Microsoft Project fájlok olvasására vagy írására van szükségük, **erőforrás hozzáadása MS projekthez** és a szabványos díj konfigurálása rutinszerű, de alapvető feladat. Ebben az útmutatóban megmutatjuk, hogyan hozhat létre egy `Project` objektumot, adjon hozzá egy erőforrást, és állítsa be a szabványos és a túlóra díjakat az Aspose.Tasks for Java segítségével. A végére képes lesz automatizálni a költségszámításokat és naprakészen tartani a projekt ütemterveket anélkül, hogy a Microsoft Project telepítve lenne.

## Gyors válaszok
- **Melyik osztály képviseli a Project fájlt?** `Project`
- **Melyik hívás ad hozzá egy új erőforrást?** `project.getResources().add()`
- **Hogyan állítja be a standard díjat?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Szükséges licenc a termeléshez?** Igen, érvényes Aspose.Tasks licencet kell betölteni.
- **Mely Java verziók támogatottak?** Java 8 és újabb (Java 17+ ajánlott).

## Mi az a „standard díj beállítása”?
A *standard díj beállítása* művelet egy alapértelmezett óradíjat rendel egy erőforráshoz. Ezt a díjat a projektmenedzserek használják a munkaerőköltségek számításához, költségjelentések generálásához és költségvetések előrejelzéséhez, biztosítva, hogy a költségszámítások tükrözzék az egyes erőforrások által a projekt életciklusa során végzett munka várható árát.

## Miért állítsuk be a díjakat az Aspose.Tasks segítségével?
Az Aspose.Tasks **több mint 50 bemeneti és kimeneti formátumot** képes feldolgozni, többek között MPP, MPX, XML és Primavera fájlokat, és több száz oldalas projekteket kezel anélkül, hogy a teljes fájlt a memóriába kellene tölteni. Ez lehetővé teszi a nagy áteresztőképességű kötegelt feldolgozást Windows, Linux vagy macOS szervereken, csökkentve a manuális munkát akár 90 %-kal a tipikus automatizálási forgatókönyvekben.

## Előkövetelmények
Mielőtt elkezdené, győződjön meg róla, hogy az alábbi elemek készen állnak:

### Java fejlesztői környezet beállítása
1. Telepítse a JDK 8-at vagy újabbat. Letöltheti a [Oracle weboldalról](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Válasszon egy IDE-t, például IntelliJ IDEA, Eclipse vagy NetBeans, és állítsa be Java fejlesztéshez.

### Aspose.Tasks for Java telepítése
1. Töltse le a legújabb Aspose.Tasks for Java csomagot a [letöltési oldalról](https://releases.aspose.com/tasks/java/).  
2. Adja hozzá a JAR fájlokat a projekt classpath-jához, vagy deklarálja a Maven/Gradle függőséget a termék dokumentációjában bemutatott módon.

## Csomagok importálása
Importálja a szükséges Aspose.Tasks alaposztályokat. Ez a lépés hozzáférést biztosít a később használt `Project`, `Resource` és `Rsc` típusokhoz.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## 1. lépés: projektobjektum létrehozása
A `Project` osztály a felső szintű objektum, amely egy teljes MS Project fájlt reprezentál a memóriában. Példányosítása egy üres projektet hoz létre, amelyet feladatokkal, erőforrásokkal és egyéb adatokkal tölthet fel.

```java
Project project = new Project();
```

## 2. lépés: erőforrás hozzáadása (add resource ms project)
A `Resource` osztály egyetlen projekt erőforrást modellez, például személyt, berendezést vagy anyagot. Erőforrás hozzáadása a `project.getResources().add()` hívással egy nem‑null `Resource` példányt ad vissza, amely készen áll a tulajdonságok konfigurálására.

```java
Resource rsc = project.getResources().add("Rsc");
```

## 3. lépés: erőforrás tulajdonságainak beállítása (how to set rates)
Az `Rsc` enum tartalmazza az erőforrás mezőkhöz tartozó állandókat, például a `STANDARD_RATE` és `OVERTIME_RATE` értékeket.  
A szabványos és a túlóra díjakat a `Resource` objektum `set` metódusának meghívásával, a megfelelő `Rsc` enum értékekkel állítja be. A díjak `BigDecimal`‑ként tárolódnak a pénzügyi pontosság megőrzése érdekében.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Javítás |
|----------|------------------|---------|
| `NullPointerException` a `set` hívásakor | Az erőforrás nem lett megfelelően hozzáadva. | Győződjön meg arról, hogy a `project.getResources().add()` nem null `Resource`-t ad vissza. |
| A díjak 0-ként jelennek meg a mentett fájlban | `int` használata `BigDecimal` helyett. | Mindig használja a `BigDecimal.valueOf()`-t pénzügyi értékekhez. |
| Licenc nem található | A licencfájl nem lett betöltve a `Project` létrehozása előtt. | Töltse be a licencet (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) a program indításakor. |

## Összegzés
Most már tudja, hogyan **adjon hozzá erőforrást MS projekthez**, hogyan hozza létre a `Project` objektumot, és hogyan **állítsa be a szabványos és túlóra díjakat** az Aspose.Tasks for Java segítségével. Ez a képesség lehetővé teszi a költségszámítások automatizálását, egyedi jelentések generálását és az MS Project erőforrások teljes körű kezelését bármely Java alkalmazásból.

## Gyakran ismételt kérdések
**Q: Kezelni tudja az Aspose.Tasks for Java a komplex MS Project fájlokat?**  
A: Igen, támogatja az összes fő Project formátumot, beleértve a több ezer feladatot és erőforrást tartalmazó nagy fájlokat is, minden mezőt megőriz adatvesztés nélkül.

**Q: Elérhető ingyenes próba?**  
A: Igen, hozzáférhet az Aspose.Tasks for Java ingyenes próbaverziójához a [Aspose.Tasks ingyenes próbaoldalon](https://releases.aspose.com/).

**Q: Hol kaphatok támogatást az Aspose.Tasks for Java-hez?**  
A: Segítséget kérhet a [támogatási fórumon](https://forum.aspose.com/c/tasks/15).

**Q: Hogyan szerezhetek ideiglenes licencet értékeléshez?**  
A: Ideiglenes licenc elérhető a [temporary license page](https://purchase.aspose.com/temporary-license/) oldalon.

**Q: Hol vásárolhatok licencelt verziót?**  
A: Teljes licencet vásárolhat a [purchase page](https://purchase.aspose.com/buy) oldalon.

---

**Utolsó frissítés:** 2026-08-24  
**Tesztelve:** Aspose.Tasks for Java 24.12 (legújabb a kiadás időpontjában)  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan hozzunk létre erőforrásokat – Erőforrás-kezelés az Aspose.Tasks for Java-val](/tasks/java/resource-management/)
- [Erőforrás hozzáadása projekthez az Aspose.Tasks for Java-val](/tasks/java/resource-management/create-resources/)
- [Hogyan adjunk hozzá erőforrást projekthez és kezeljük a szintelési késleltetés tulajdonságait az Aspose.Tasks-ben](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}