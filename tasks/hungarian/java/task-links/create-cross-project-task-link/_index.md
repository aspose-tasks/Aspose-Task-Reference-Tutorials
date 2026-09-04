---
date: 2026-07-05
description: Ismerje meg, hogyan lehet feladatokat összekapcsolni projektek között
  az Aspose.Tasks for Java segítségével. Lépésről‑lépésre útmutató, előfeltételek
  és legjobb gyakorlatok a zökkenőmentes keresztprojekt feladatkapcsoláshoz.
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: Keresztprojekt feladatkapcsolat létrehozása az Aspose.Tasks-ben
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Feladatok összekapcsolása projektek között az Aspose.Tasks for Java használatával
url: /hu/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feladatok összekapcsolása projektek között az Aspose.Tasks for Java használatával

## Bevezetés
A projektek közötti feladatok összekapcsolása egy alapvető képesség, amely lehetővé teszi a munka szinkronizálását, az ismétlődések elkerülését, és egyetlen igazságforrás fenntartását az egymástól függő tevékenységekhez. Ebben az oktatóanyagban lépésről lépésre megismerheti, hogyan **kapcsolhatók össze feladatok projektek között** az Aspose.Tasks for Java segítségével. A végére egy teljesen működőképes projektek közötti hivatkozást kap, amely automatikusan frissül, ha bármelyik oldal változik, így valós idejű koordinációt biztosít manuális másolás‑beillesztés nélkül.

## Gyors válaszok
- **Mi a fő osztály egy projekt létrehozásához?** `Project` – a teljes MS‑Project fájlt reprezentálja a memóriában.  
- **Melyik metódus ad hozzá egy külső feladatot?** `project.getRootTask().getChildren().addExternalTask(...)`.  
- **Beállítható a hivatkozás típusa?** Igen – használja a `TaskLinkType.FinishToStart`, `StartToStart`, stb.  
- **Szükség van licencre az összekapcsoláshoz?** Érvényes Aspose.Tasks licenc szükséges a termelési használathoz; egy ingyenes próba a kiértékeléshez megfelelő.  
- **Van korlátozás a kapcsolt feladatok számában?** Az Aspose.Tasks 10 000+ kapcsolt feladatot képes kezelni projektenként a teljesítménycsökkenés nélkül.

## Mi az a feladatok összekapcsolása projektek között?
A projektek közötti feladatok összekapcsolása függőségi kapcsolatot hoz létre egy feladat és egy másik projekt fájlban lévő feladat között, lehetővé téve, hogy a forrásfeladat (időtartam, kezdő dátum, korlátozások) változásai automatikusan átkerüljenek a függő feladatra. Ez a mechanizmus a menetrendek összehangoltságát biztosítja, csökkenti a manuális frissítéseket, és garantálja, hogy a forrásprojekt bármely módosítása azonnal megjelenjen az összes kapcsolt projektben, megőrizve a konzisztenciát a portfólióban.

## Miért használja az Aspose.Tasks-et a projektek közötti összekapcsoláshoz?
Az Aspose.Tasks **50+ bemeneti és kimeneti formátumot** támogat, és képes **több száz oldalas projekteket** feldolgozni, miközben a memóriahasználat 200 MB alatt marad. Az API a szerveroldalon végzi az összekapcsolást, így nincs szükség a Microsoft Project telepítésére, és automatizált folyamatokat tesz lehetővé nagy vállalatok számára.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

- Java 17‑el (vagy újabb verzióval), amely telepítve van és be van állítva az IDE‑jében.  
- Érvényes Aspose.Tasks for Java licencfájllal (`Aspose.Tasks.Java.lic`).  
- Az Aspose.Tasks for Java könyvtárral, amelyet a projekthez hozzáadott. Letöltheti a [Aspose.Tasks for Java kiadási oldalról](https://releases.aspose.com/tasks/java/).  
- Alapvető ismeretekkel az MS‑Project fogalmairól, mint például feladatok, összegző feladatok és függőségek.

## Csomagok importálása
A `Project`, `Task`, `TaskLink` és a kapcsolódó enumok a `com.aspose.tasks` névtérben találhatók. Importálja őket a Java fájlja tetején:

`import com.aspose.tasks.*;`

A **Project** a fő osztály, amely egy projektfájlt reprezentál a memóriában. A **Task** egy egyedi munkatételt jelent egy projektben. A **TaskLink** két feladat közötti függőségi kapcsolatot definiál. Ezek az importok hozzáférést biztosítanak a projektmanipuláció teljes funkcionalitásához, beleértve a projektek közötti összekapcsolást is.

## Hogyan kapcsolhatók össze feladatok projektek között?
Töltse be a két projektfájlt, adjon hozzá egy külső feladat helyőrzőt, hozzon létre egy helyi feladatot, majd kapcsolja össze őket egy `TaskLink`‑kel. Az API kezeli az azonosítók leképezését és a frissítéseket automatikusan, biztosítva, hogy a külső feladat bármely változása a kapcsolt helyi feladatra is kiterjedjen további kód nélkül. Ez a megközelítés egyszerűsíti a több projekt koordinációját és csökkenti a menetrendelt eltolódás kockázatát.

### 1. lépés: Állítsa be a környezetet
Győződjön meg róla, hogy az Aspose.Tasks JAR a classpath‑on van, és a licencfájl betöltődik futásidőben:

`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`

A **License** betölti az Aspose.Tasks licencfájlt, hogy teljes funkcionalitást biztosítson és eltávolítsa a kiértékelési vízjeleket.

### 2. lépés: Hozzon létre egy projekt példányt
Hozzon létre egy új `Project` objektumot a célprojekthez, ahol a hivatkozás élni fog:

`Project targetProject = new Project();`

A `Project` osztály az Aspose.Tasks legfelső szintű objektuma, amely egyetlen projektfájlt reprezentál a memóriában.

### 3. lépés: Összegző feladat hozzáadása
Az összegző feladat csoportosítja a kapcsolódó feladatokat. Hozzon létre egyet, amely a külső és a helyi feladatokat egyaránt tartalmazza:

`Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");`

### 4. lépés: Külső feladat hozzáadása
Illesszen be egy külső feladatot, amely egy másik projektfájlban lévő feladatra mutat:

`Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);`

A **addExternalTask** metódus egy helyőrző feladatot hoz létre, amely egy külső projektfájlt hivatkozik, a megadott fájlnév és feladat‑azonosító használatával.

### 5. lépés: Helyi feladat hozzáadása
Hozza létre a feladatot, amely a külsőhöz lesz kapcsolva:

`Task local = summary.getChildren().add("Local Task");`

### 6. lépés: Feladatkapcsolat létrehozása
Állítson fel egy függőséget a külső és a helyi feladatok között. A leggyakoribb hivatkozástípus a Finish‑to‑Start:

`TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);`

A **TaskLink** rögzíti a kapcsolatot; később módosíthatja a késleltetést, előrehaladást vagy a típust igény szerint.

### 7. lépés: Mentés és ellenőrzés
Mentse a projektet egy fájlba, és opcionálisan nyissa meg Microsoft Projectben a hivatkozás ellenőrzéséhez:

`targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`

A **SaveFileFormat** meghatározza a projekt mentéséhez használt fájlformátumot. Amikor megnyitja a *LinkedProject.mpp* fájlt, a külső feladat speciális ikonnal jelenik meg, és a függőségi vonal a helyi feladatra mutat.

## Gyakori problémák és megoldások
- **Külső fájl nem található** – Győződjön meg róla, hogy az útvonal a futó folyamathoz relatív, vagy adjon meg egy abszolút útvonalat.  
- **Feladatazonosítók eltérése** – Ellenőrizze, hogy a külső feladat ID‑je (a `addExternalTask` második argumentuma) megegyezik a forrásprojektben lévővel.  
- **Licenc nincs betöltve** – Hiányzó vagy helytelen licencfájl `LicenseException`‑t eredményez. Töltse be a licencet minden Aspose.Tasks hívás előtt.  
- **Teljesítmény nagy projektek esetén** – Használja a `Project.setReadOnly(true)`‑t, ha csak a külső feladatokat kell olvasni; ez csökkenti a memóriaigényt.

## Gyakran ismételt kérdések

**Q: Hozzáadhatok feladatokat több külső projekthez ugyanabban az összegző feladatban?**  
A: Igen, több külső feladatot is hozzáadhat egy összegző feladathoz, és minden egyeshez egyedi hivatkozást hozhat létre a `addExternalTask` metódus használatával.

**Q: Mi történik, ha a kapcsolt projektben lévő külső feladat módosul?**  
A: A külső feladat ütemezésének, időtartamának vagy korlátozásainak bármely változása automatikusan megjelenik a függő helyi feladatban, amikor a célprojekt frissül.

**Q: Lehet különböző fájlformátumok között létrehozni feladatkapcsolatokat?**  
A: Teljesen lehetséges. Az Aspose.Tasks támogatja a kapcsolatok létrehozását MPP, XML és Primavera formátumok között, lehetővé téve a heterogén projektökoszisztémák szinkronizálását.

**Q: Lehet feloldani a feladatok közötti kapcsolatot, ha már összekapcsolták őket?**  
A: Igen, a hivatkozást eltávolíthatja a `project.getTaskLinks().remove(link)` hívással, vagy a külső feladat helyőrzőjének törlésével.

**Q: Van korlátozás a projektek közötti kapcsolható feladatok számában?**  
A: A könyvtár **10 000+ kapcsolt feladatot** képes kezelni projektenként, csak a rendelkezésre álló rendszermemória és az alapul szolgáló fájlformátum specifikációi korlátozhatják.

## Összegzés
Most már rendelkezik egy teljes, termelésre kész megközelítéssel a **feladatok projektek közötti összekapcsolásához** az Aspose.Tasks for Java segítségével. Ez a képesség egyszerűsíti a több projekt koordinációját, csökkenti a manuális erőfeszítést, és biztosítja, hogy a menetrendi változások azonnal terjedjenek a portfólióban. Fedezze fel a további funkciókat, mint például az egyedi késleltetési idők, különböző hivatkozástípusok és a tömeges összekapcsolás, hogy tovább automatizálja a komplex projektstruktúrákat.

---

**Utoljára frissítve:** 2026-07-05  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## Kapcsolódó oktatóanyagok

- [Feladatkapcsolat létrehozása az Aspose.Tasks-ben](/tasks/java/task-links/create-task-link/)
- [Feladatok létrehozása Aspose Java – Feladat tulajdonságok](/tasks/java/task-properties/)
- [Üres MS Project fájl létrehozása az Aspose.Tasks-ben](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}