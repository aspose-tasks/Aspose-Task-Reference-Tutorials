---
date: 2026-10-15
description: Ismerje meg, hogyan hozhat létre activity-t, állíthatja be a data directory-t,
  testreszabhatja a table fields-et, és mentheti a project-et MPP formátumban az Aspose.Tasks
  for Java segítségével. Lépésről‑lépésre útmutató Java fejlesztőknek.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Hogyan hozhatunk létre activity-t és állíthatjuk be a data directory-t
  az Aspose.Tasks for Java használatával
og_description: Hogyan hozhat létre activity-t, testreszabhatja a table fields-et
  és mentheti a project-et MPP formátumban az Aspose.Tasks for Java használatával.
  Kövesse ezt a részletes útmutatót a gyors megvalósításhoz.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Hogyan hozhatunk létre activity-t és állíthatjuk be a data directory-t az
  Aspose.Tasks for Java-ban
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Hogyan hozhatunk létre activity-t és állíthatjuk be a data directory-t az Aspose.Tasks
  for Java használatával
url: /hu/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozhatunk létre tevékenységet és állíthatjuk be az adatkönyvtárat az Aspose.Tasks for Java használatával

## Bevezetés
Ebben az oktatóanyagban megtudja, hogyan **hozhat létre tevékenységet** programozottan, hogyan konfigurálja a **adatkönyvtárat**, és hogyan **mentse a projektet MPP formátumban**, miközben **testreszabja a táblamezőket** egy Gantt-diagram nézetben. Az Aspose.Tasks for Java egy erőteljes API, amely több mint 30 bemeneti és kimeneti formátumot támogat, és akár 10 000 feladatot is képes feldolgozni anélkül, hogy az egész fájlt a memóriába töltené. A útmutató végére képes lesz automatizálni a projekt létrehozását, egyéni attribútumokkal gazdagítani a feladatokat, és egy Microsoft Project számára készen álló MPP fájlt előállítani.

## Gyors válaszok
- **Mi az első lépés?** Állítsa be az adatkönyvtár elérési útját, ahol a projektfájlok találhatók.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (letölthető a hivatalos weboldalról).  
- **Hozzáadhatok egyéni attribútumokat?** Igen – definiálhat kiterjesztett attribútumokat és megjelenítheti őket a Gantt-diagramon.  
- **Szükségem van licencre a teszteléshez?** Ideiglenes licenc áll rendelkezésre értékelési célokra.  
- **Melyik IDE a legjobb?** Bármely Java IDE (IntelliJ IDEA, Eclipse, NetBeans) működik.

## Mi az a „adatkönyvtár beállítása”, és miért fontos?
Az adatkönyvtár beállítása megmondja az Aspose.Tasks‑nek, hol olvassa és írja a projektfájlokat. Helytelen útvonal nélkül az API nem tudja megtalálni a `.mpp` fájlokat, ami `FileNotFoundException` hibákhoz vezet. Ennek a könyvtárnak a definiálása a kód elején ismételhető munkafolyamatot biztosít, és elkülöníti a fájlrendszer kérdéseit az üzleti logikától.

## Miért testre szabjuk a táblamezőket egy Gantt-diagramon?
Az egyéni táblamezők lehetővé teszik további információk – például egyéni attribútumok, erőforrásadatok vagy projektspecifikus megjegyzések – közvetlen megjelenítését a Gantt-nézetben. Ez csökkenti a külön jelentések szükségességét, és egy adatgazdag vizualizációt biztosít a döntéshozók számára, amely akár 30 %-kal is felgyorsíthatja a döntéshozatalt.

## Hogyan hozhatunk létre új tevékenységet?
Új tevékenységet (feladatot) úgy hoz létre, hogy egy `Task` objektumot példányosít, majd hozzáadja a projekt gyökérfeladat-gyűjteményéhez. Ez a megközelítés lehetővé teszi nagy ütemtervek automatikus generálását, feladatadatok külső rendszerekből való beolvasását, vagy tömeges frissítések alkalmazását manuális szerkesztés nélkül.

## Előfeltételek
1. **Java Development Kit (JDK)** – 8-as vagy újabb verzió.  
2. **Aspose.Tasks for Java** – töltse le a **Aspose.Tasks Java kiadási oldaláról**.  
3. **IDE** – IntelliJ IDEA, Eclipse vagy bármely általad preferált Java‑kompatibilis szerkesztő.  

## Csomagok importálása
A `com.aspose.tasks` névtér tartalmazza az összes szükséges osztályt a projektmanipulációhoz. Ennek importálása hozzáférést biztosít a `Project`, `Task`, `ExtendedAttributeDefinition` és más alapvető típusokhoz.

```java
import com.aspose.tasks.*;
```

## Maven függőség (opcionális)
Ha Maven‑nel kezeli a projektet, adja hozzá az Aspose.Tasks függőséget a `pom.xml`‑hez. Ez biztosítja, hogy a könyvtár automatikusan fel legyen oldva a build során.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Lépésről‑lépésre útmutató

### 1. lépés: adatkönyvtár beállítása
Határozza meg azt a mappát, amely a projektfájlokat tartalmazza. A `dataDir` változó az abszolút útvonalat tárolja, és a teljes oktatóanyag során újra felhasználásra kerül.

```java
String dataDir = "Your Data Directory";
```

Cserélje le a `"Your Data Directory"` szöveget a teljes útvonalra, ahol a `project.mpp` található, például `C:/Projects/MyGantt`.

### 2. lépés: projektfájl betöltése
A `Project` az Aspose.Tasks felső szintű objektuma, amely egyetlen Microsoft Project fájlt reprezentál a memóriában. Egy meglévő fájl betöltése hozzáférést biztosít a feladatokhoz, erőforrásokhoz és táblákhoz.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 3. lépés: új tevékenység hozzáadása
A `Task` egy egyedi tevékenységet képvisel az ütemtervben. Egy feladat hozzáadása a gyökérfeladat-gyűjteményhez a projekt hierarchiájának legfelső szintjén helyezi el azt.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### 4. lépés: egyéni attribútum definiálása
Az `ExtendedAttributeDefinition` lehetővé teszi újrahasználható egyéni mező létrehozását, amely bármely feladathoz, erőforráshoz vagy hozzárendeléshez csatolható.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### 5. lépés: egyéni attribútum hozzáadása a feladathoz
Az `ExtendedAttribute` az egyéni attribútum konkrét példánya, amelyet egy adott feladathoz rendelünk.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### 6. lépés: tábla testreszabása – egyéni attribútum hozzáadása oszlopként
A `TableField` egy oszlopot ír le a Gantt-diagram táblájában. Egy `TableField` hozzáadásával, amely a saját attribútumra hivatkozik, láthatóvá teszi azt a diagram nézetben.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### 7. lépés: projekt mentése
A `project.save` meghívása minden változást egy új fájlba ment. A `SaveFileFormat.MPP` állandó azt jelzi, hogy az Aspose.Tasks a fájlt a Microsoft Project natív bináris formátumában írja.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **FileNotFoundException** a projekt betöltésekor | A **set data directory** útvonal helytelen vagy hiányzik a záró perjel. | Ellenőrizze, hogy a `dataDir` a pontos mappára mutat, és tartalmazza a megfelelő fájlelválasztót (`/` vagy `\\`). |
| Egyéni attribútum nem látható a Gantt nézetben | A táblamezőt a rossz indexen adták hozzá, vagy az oszlopszélesség túl kicsi. | Győződjön meg róla, hogy a `table.getTableFields().add(3, attrField);` érvényes indexet használ, és szükség szerint állítsa be a `setWidth` értékét. |
| LicenseException mentéskor | Nem érvényes licenc lett alkalmazva termelési környezetben. | Alkalmazzon ideiglenes vagy állandó licencet a `project.save()` hívása előtt. |

## Gyakran ismételt kérdések

**Q:** **Használhatom az Aspose.Tasks‑et más programozási nyelvekkel?**  
**A:** Igen, az Aspose.Tasks elérhető .NET, Java és C++ számára.

**Q:** **Elérhető ingyenes próba az Aspose.Tasks‑hez?**  
**A:** Igen, letölthet egy ingyenes próbaverziót a **Aspose.Tasks free trial download page**.

**Q:** **Hol találok támogatást az Aspose.Tasks‑hez?**  
**A:** Támogatást és kérdéseket a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15) talál.

**Q:** **Hogyan vásárolhatok licencet az Aspose.Tasks‑hez?**  
**A:** Licencet a **Aspose.Tasks purchase page** vásárolhat.

**Q:** **Szükségem van ideiglenes licencre tesztelési célokra?**  
**A:** Igen, ideiglenes licencet a **temporary license request page** kaphat.

## Következtetés
Most már tudja, **hogyan hozhat létre tevékenységet**, hogyan állíthatja be az adatkönyvtárat, hogyan definiálhat és csatolhat egyéni attribútumot, és **hogyan mentheti a projektet MPP formátumban**, miközben **testreszabja a táblamezőket** egy Gantt-diagram nézetben az Aspose.Tasks for Java használatával. Ezek a lehetőségek teljes programozott irányítást biztosítanak a projektadatok felett, lehetővé téve az automatizált ütemterv‑generálást és a gazdagabb vizuális jelentést a résztvevők számára.

---

**Legutóbb frissítve:** 2026-10-15  
**Tesztelve:** Aspose.Tasks Java 24.12 (legújabb)  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan hozzunk létre üres projektfájlt az Aspose.Tasks-ben (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [Hogyan hozzunk létre MPP fájlt – Üres projekt létrehozása és mentése MPP formátumban az Aspose.Tasks használatával](/tasks/java/project-configuration/create-save-mpp/)
- [Hogyan hozzunk létre projektet aspose.tasks – Új feladat attribútumainak beállítása](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}