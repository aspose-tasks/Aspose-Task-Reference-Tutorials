---
date: 2026-06-05
description: Tanulja meg, hogyan hozhat létre resource assignment-et az Aspose.Tasks
  for Java segítségével, hogyan adhat hozzá erőforrásokat egy projekthez, és hogyan
  kezelheti a leveling delay properties-t.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Leveling Delay Properties kezelése a Resource Assignments esetén az Aspose.Tasks-ben
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Resource Assignment létrehozása az Aspose.Tasks for Java segítségével
url: /hu/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erőforrás-hozzárendelés létrehozása az Aspose.Tasks for Java segítségével

Ebben az átfogó útmutatóban megtanulja, **hogyan hozhat létre erőforrás-hozzárendelést aspotasks** az Aspose.Tasks könyvtár Java-hoz használatával. Akár egy egyedi ütemező motoron dolgozik, tömeges projektfrissítéseket automatizál, vagy egyszerűen csak Microsoft Project fájlokat kell manipulálnia asztali alkalmazás nélkül, ezen lépések elsajátítása lehetővé teszi, hogy projektadatai pontosak és teljesen irányíthatóak legyenek.

## Gyors válaszok
- **Mi a jelentése a „add resource to project” kifejezésnek?** Új erőforrás-bejegyzést hoz létre, amely később feladatokhoz rendelhető.  
- **Beállíthatok szintezési késleltetést a hozzárendelés után?** Igen, a `Asn.DELAY` vagy `Asn.LEVELING_DELAY` mezők használatával.  
- **Szükségem van licencre a kód futtatásához?** Egy ingyenes próba verzió fejlesztéshez működik; a termeléshez fizetett licenc szükséges.  
- **Melyik Java verzió támogatott?** Java 8 vagy újabb.  
- **Ez kompatibilis minden MS Project fájlformátummal?** Az Aspose.Tasks 12+ formátumot támogat—beleértve a .MPP, .XML, .XER, .CSV, .PDF és egyebeket.

## Mi a „add resource to project” az Aspose.Tasks-ben?
Erőforrás hozzáadása egy projekthez azt jelenti, hogy egy `Resource` objektumot hozunk létre a `Project` modellben. Ez az objektum később a `ResourceAssignment` segítségével kapcsolható feladatokhoz, lehetővé téve a munka, költségek és szintezési beállítások nyomon követését. Egy erőforrás beszúrásával a tervezőnek van valami, amit kioszthat, és később lekérdezheti vagy módosíthatja annak tulajdonságait, például elérhetőségét, díjszabásait és naptár hozzárendeléseit.

## Miért kell kezelni a szintezési késleltetés tulajdonságait?
A szintezési késleltetés azt mondja meg a tervezőnek, hogy halassza el a túlterhelt hozzárendelés kezdését, így a munkát egyenletesebben osztja el az idővonalon. Ennek a késleltetésnek a beállításával elkerülhetők a valótlan kezdési dátumok, csökkenthetők a túlterhelés figyelmeztetések, és olyan ütemtervet hozhatunk létre, amely tükrözi a valós erőforrás-korlátokat. A késleltetés finomhangolása továbbá pontosabb kontrollt biztosít arról, mennyi szabadidőt szúrhat be a motor, segítve a projekt határidők betartását, miközben tiszteletben tartja az erőforrás-korlátokat.

## Hogyan hozhatunk létre erőforrás-hozzárendelést aspotasks?
Töltse be a `Project` objektumot, adjon hozzá egy feladatot, hozzon létre egy erőforrást, majd kössük össze őket egy `ResourceAssignment` segítségével. Ez az vég‑től‑végig folyamat lehetővé teszi, hogy programozottan felépítsen egy teljes projektstruktúrát, és azonnal szabályozza a szintezési késleltetést a hozzárendelésen. A folyamat bemutatja a fő munkafolyamatot: projekt inicializálása, feladat definiálása, erőforrás létrehozása, hozzárendelés összekapcsolása, majd végül a szintezési késleltetés alkalmazása.

## Előfeltételek
1. Java Development Kit (JDK): Győződjön meg róla, hogy a rendszerén telepítve van a Java JDK. Letöltheti és telepítheti a [weboldalról](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Aspose.Tasks for Java könyvtár: Töltse le az Aspose.Tasks for Java könyvtárat a [letöltési oldalról](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Az alábbi importok hozzák be a projektmanipulációhoz szükséges Aspose.Tasks alaposztályokat.  
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Hogyan hozhatunk létre erőforrás-hozzárendelést aspotasks?
Töltse be a `Project` objektumot, adjon hozzá egy feladatot, hozzon létre egy erőforrást, majd kössük össze őket egy `ResourceAssignment` segítségével. Ez az vég‑től‑végig folyamat lehetővé teszi, hogy programozottan felépítsen egy teljes projektstruktúrát, és azonnal szabályozza a szintezési késleltetést a hozzárendelésen. A folyamat bemutatja a fő munkafolyamatot: projekt inicializálása, feladat definiálása, erőforrás létrehozása, hozzárendelés összekapcsolása, majd végül a szintezési késleltetés alkalmazása.

## 1. lépés: Projekt objektum létrehozása
A `Project` osztály az Aspose.Tasks felső szintű tárolója, amely egy teljes projektfájlt reprezentál a memóriában. Példányosítása tiszta kiindulási pontot ad a feladatok, erőforrások és hozzárendelések hozzáadásához.  
```java
Project prj = new Project();
```

## 2. lépés: Feladat létrehozása
A `Task` osztály egyetlen munkatételt képvisel az ütemezésben. Feladat hozzáadása bemutatja, **hogyan adhatunk feladatot** programozottan, és célpontot biztosít a közeljövőben létrehozandó erőforrás-hozzárendeléshez.  
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## 3. lépés: Feladat kezdő dátumának és időtartamának beállítása
Határozza meg, mikor kezdődik a feladat és mennyi ideig tart. A megfelelő kezdő dátumok elengedhetetlenek, mivel a szintezési számítások ezeket használják alapként a később megadott késleltetéshez.  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## 4. lépés: Erőforrás hozzáadása
Most **add resource to project** úgy, hogy létrehozunk egy új `Resource` bejegyzést. A `Resource` osztály egy személy, berendezés vagy anyag reprezentációja, amely feladatokhoz rendelhető.  
```java
Resource resource = prj.getResources().add("Resource 1");
```

## 5. lépés: Erőforrás-hozzárendelés létrehozása
A `ResourceAssignment` összekapcsol egy `Task` és egy `Resource` objektumot. Ez a kapcsolat lehetővé teszi, hogy egy adott erőforrásra vonatkozó munkát, költséget és szintezési részleteket rögzítsen egy adott feladatra.  
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## 6. lépés: Szintezési késleltetés beállítása
Állítsa be a szintezési késleltetést a hozzárendeléshez. Nullára állítva nincs további késleltetés, de az értéket igény szerint módosíthatja. Az `Asn.DELAY` mező a késleltetést percben tárolja; az `Asn.LEVELING_DELAY` egy szinonima, amely ugyanúgy működik.  
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## 7. lépés: Eredmények megjelenítése
Nyomtassa ki a fontos tulajdonságokat, hogy ellenőrizze, minden helyesen lett beállítva. Ez a lépés segít megerősíteni, hogy az erőforrás, a feladat és a késleltetési értékek pontosan úgy vannak, ahogy elvárja, mielőtt a fájlt mentené.  
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Gyakori hibák és tippek
- **Hiba:** Ha elfelejti beállítani a feladat kezdő dátumát, a hozzárendelés alapértelmezés szerint a projekt kezdetére kerül.  
- **Tipp:** Használja a `prj.getDuration(value, TimeUnitType.Day)` metódust a késleltetés finomságának szabályozásához.  
- **Tipp:** Több erőforrás hozzáadása után hívja meg a `prj.updateResourceAssignments()` metódust, hogy az ütemező újraszámolja a szintezést.  
- **Pro tipp:** Nagy projektek (10 000+ feladat) esetén kapcsolja be a `prj.setAutoCalculate(false)` beállítást a tömeges frissítések előtt, majd a végén egyszer hívja meg a `prj.calculate()` metódust a teljesítmény javítása érdekében.

## Gyakran ismételt kérdések

**Q: Használhatom az Aspose.Tasks-et más Java könyvtárakkal?**  
A: Igen, az Aspose.Tasks zökkenőmentesen integrálódik olyan könyvtárakkal, mint a Jackson JSON kezeléshez vagy az Apache POI további táblázatkezelési műveletekhez, lehetővé téve, hogy gazdagabb projektmenedzsment megoldásokat építsen.

**Q: Az Aspose.Tasks kompatibilis a Microsoft Project különböző verzióival?**  
A: Az Aspose.Tasks 12+ fájlformátumot támogat—beleértve a .MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML és .MPP12 formátumokat—ezáltal zökkenőmentes round‑trip szerkesztést biztosít minden fő Project verzióban.

**Q: Hol találok további támogatást az Aspose.Tasks-hez?**  
A: Támogatást és közösségi beszélgetéseket a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15) talál.

**Q: Próbálhatom-e ki az Aspose.Tasks-et vásárlás előtt?**  
A: Igen, egy teljes funkcionalitású ingyenes próba elérhető a [kiadások oldaláról](https://releases.aspose.com/).

**Q: Hogyan szerezhetek ideiglenes licencet értékeléshez?**  
A: Kérjen ideiglenes licencet a [ideiglenes licenc oldalról](https://purchase.aspose.com/temporary-license/), hogy a könyvtárat korlátozások nélkül futtathassa.

---

**Utolsó frissítés:** 2026-06-05  
**Tesztelve ezzel:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Erőforrás-hozzárendelések létrehozása az Aspose.Tasks-ben](/tasks/java/resource-assignments/create-resource-assignments/)
- [Erőforrás-hozzárendelés költségvetés kezelése Java-ban az Aspose.Tasks használatával](/tasks/java/resource-assignments/assignment-budget/)
- [Hogyan állítsuk le a hozzárendelést és folytassuk az erőforrás-hozzárendeléseket az Aspose.Tasks-ben](/tasks/java/resource-assignments/stop-resume-assignment/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}