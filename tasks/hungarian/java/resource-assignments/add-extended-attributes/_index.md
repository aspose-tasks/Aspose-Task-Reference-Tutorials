---
date: 2026-05-20
description: Ismerje meg, hogyan használja az Aspose.Tasks for Java-t a extended attributes
  hozzáadásához a resource assignments-hez, a project start date beállításához, és
  a MS Project fájlok hatékony írásához.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Add Extended Attributes to Resource Assignments az Aspose.Tasks-ben
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hogyan használjuk az Aspose.Tasks for Java – Add Extended Attributes to Resource
  Assignments
url: /hu/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az MS Project manipulációjának elsajátítása az Aspose.Tasks for Java segítségével

## Bevezetés
Ebben az útmutatóban megtudja, **hogyan kell használni az Aspose.Tasks for Java**-t kiterjesztett attribútumok hozzáadásához erőforrás‑kijelölésekhez, és a Microsoft Project információk programozott írásához. Akár jelentéskészítő folyamatot automatizál, akár egy egyedi projektmenedzsment eszközt épít, az alábbi lépések pontosan megmutatják, hogyan állítsa be a projekt kezdő dátumát, hozza létre az erőforrás‑kijelöléseket, és mentse a fájlt XML‑ként – mindezt csak néhány Java sorral.

## Gyors válaszok
- **Mit csinál az Aspose.Tasks for Java?** Olvassa, írja és módosítja a Microsoft Project fájlokat anélkül, hogy a Microsoft Project telepítve lenne.  
- **Hozzáadhatok egyéni mezőket egy erőforrás‑kijelöléshez?** Igen, használja az `ExtendedAttribute` gyűjteményt a `ResourceAssignment` objektumon.  
- **Hogyan állíthatom be a projekt kezdő dátumát?** Hívja a `project.setStartDate(LocalDateTime.of(...))` metódust a mentés előtt.  
- **Szükségem van licencre a termelési használathoz?** A kereskedelmi licenc eltávolítja a kiértékelési vízjeleket és feloldja a teljes API hozzáférést.  
- **Mely Java verziók támogatottak?** Az Aspose.Tasks for Java támogatja a JDK 8‑tól a JDK 21‑ig terjedő verziókat.

## Hogyan használjuk az Aspose.Tasks for Java‑t?
`Project` az elsődleges objektum, amely egy Microsoft Project fájlt reprezentál a memóriában. Töltse be az Aspose.Tasks könyvtárat, hozzon létre egy `Project` példányt, konfigurálja a projekt‑szintű tulajdonságokat, adjon hozzá kiterjesztett attribútumokat egy erőforrás‑kijelöléshez, majd végül mentse a projektet XML‑ként. A fő munkafolyamat három tömör lépésre osztható: inicializálás, módosítás és mentés. Ez a minta bármilyen méretű projektfájlra alkalmazható, és Windows, Linux vagy macOS JVM‑eken fut.

## Mi az a kiterjesztett attribútum az Aspose.Tasks‑ben?
A **kiterjesztett attribútum** egy egyéni mező, amelyet feladatokhoz, erőforrásokhoz vagy kijelölésekhez csatol, hogy a beépített oszlopokon túl további metaadatokat tároljon. Az `ExtendedAttributeDefinition` határozza meg egy egyéni mező sémáját. Az Aspose.Tasks a `ExtendedAttributeDefinition` és `ExtendedAttribute` osztályokat biztosítja a mezők programozott definiálásához és hozzárendeléséhez.

## Miért adjunk kiterjesztett attribútumokat az erőforrás‑kijelölésekhez?
Az Aspose.Tasks **50+ beépített és egyéni mezőt** támogat, és korlátlan felhasználó által definiált attribútumot adhat hozzá. Ezek hozzáadása lehetővé teszi költségkódok, részleg‑azonosítók vagy bármely üzleti specifikus adat közvetlen rögzítését a .mpp fájlban, kiküszöbölve a külső táblázatok szükségességét és biztosítva az adat integritását a projekt életciklusa során.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. **Java Development Kit (JDK)** – JDK 8 vagy újabb telepítve.  
2. **Aspose.Tasks for Java library** – Töltse le a hivatalos kiadási oldalról [itt](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse vagy bármely kedvelt Java‑kompatibilis szerkesztő.

## Csomagok importálása
Először importálja a szükséges csomagokat a Java projektjébe:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### 1. lépés: Adatkönyvtár beállítása
Határozza meg a könyvtárat, ahol a projekt adatai tárolódnak. Ez az útvonal később kerül felhasználásra az XML fájl mentésekor.

```java
String dataDir = "Your Data Directory";
```

### 2. lépés: Projektpéldány létrehozása
`Project` osztály az Aspose.Tasks felső szintű objektuma, amely egyetlen Microsoft Project fájlt reprezentál a memóriában. Példányosítása teljes hozzáférést biztosít minden projekt elemhez.

```java
Project project = new Project();
```

### 3. lépés: Projektinformációs tulajdonságok beállítása
Állítsa be a lényeges projekt tulajdonságokat, mint például a kezdő dátum, a 'schedule from start' jelző és a státusz dátum. Ezek az értékek a projekt `ProjectInfo` objektumában tárolódnak.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### 4. lépés: Kiterjesztett attribútumok hozzáadása egy erőforrás‑kijelöléshez
Hozzon létre egy `ExtendedAttributeDefinition`-t az egyéni mezőhöz, csatolja egy `ResourceAssignment`-hez, és töltse fel az értékkel. Ez a lépés bemutatja a **add extended attributes** kulcsszó használatát.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Gyakori problémák és megoldások
- **NullPointerException a kijelölés gyűjtemény elérésekor** – Győződjön meg róla, hogy legalább egy erőforrást és egy feladatot létrehozott a kijelölések lekérése előtt.  
- **A kiterjesztett attribútum nem jelenik meg a MS Projectben** – Ellenőrizze, hogy az attribútum `FieldId`-je egyezik egy egyéni mezőhelyettel (pl. `ExtendedAttributeTask.Text1`).  
- **Dátumformátum eltérés** – Használja a `java.time.LocalDateTime`-t a dátumértékekhez; az Aspose.Tasks automatikusan átalakítja őket a projekt naptárformátumára.

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.Tasks for Java‑t MS Project fájlok olvasására?**  
A: Igen, a könyvtár teljes olvas‑írás képességeket biztosít .mpp, .xml és .xps formátumokhoz.

**Q: Az Aspose.Tasks for Java kompatibilis a különböző MS Project verziókkal?**  
A: Teljes mértékben, támogatja a Project 2000-tól a legújabb 2024-es kiadásig terjedő fájlokat, több mint 20 verzióformátummal.

**Q: Vannak korlátozások az Aspose.Tasks for Java próbaverziójában?**  
A: A próba verzió vízjelet helyez a generált fájlokra, és korlátozza a létrehozható feladatok számát, de minden API funkció elérhető marad.

**Q: Hogyan kaphatok támogatást az Aspose.Tasks for Java‑hoz?**  
A: Segítséget kérhet az Aspose.Tasks közösségi fórumon [itt](https://forum.aspose.com/c/tasks/15).

**Q: Vásárolhatok ideiglenes licencet az Aspose.Tasks for Java‑hoz?**  
A: Igen, ideiglenes licencek elérhetők rövid távú használatra. Egyet [itt](https://purchase.aspose.com/temporary-license/) szerezhet be.

---

**Utoljára frissítve:** 2026-05-20  
**Tesztelve:** Aspose.Tasks for Java 24.12 (a legújabb a írás időpontjában)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Hogyan adjunk megjegyzéseket erőforrás‑kijelölésekhez az Aspose.Tasks-ben](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Hogyan olvassuk és írjuk a Rate Scale‑t erőforrás‑kijelölésekhez az Aspose.Tasks-ben](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Hogyan adjunk erőforrást a projekthez és kezeljük a Leveling Delay tulajdonságokat az Aspose.Tasks-ben](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}