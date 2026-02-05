---
date: 2026-02-05
description: Ismerje meg, hogyan adhat hozzá ünnepnapokat egy naptárhoz, rendelje
  hozzá a naptárat egy projekthez, és mentse el az MS Project fájlt MPP formátumban
  az Aspose.Tasks for Java segítségével.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ünnepnapok hozzáadása a naptárhoz és mentés MPP formátumban az Aspose.Tasks
  segítségével
url: /hu/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ünnepnapok hozzáadása a naptárhoz és mentés MPP formátumban az Aspose.Tasks segítségével

## Bevezetés

A modern projektmenedzsmentben gyakran szükség van **add holidays to calendar** fájlok hozzáadására, egy **MS Project calendar** létrehozására, majd a menetrend megosztására natív MPP formátumban. Akár több forrásból származó ütemterveket konszolidálsz, akár régi adatokat migrálsz, a naptár programozott generálása kiküszöböli a kézi hibákat és felgyorsítja a szállítást. Ez az útmutató végigvezet a teljes folyamaton: naptár létrehozása MS Projectben, testreszabása ünnepnapokkal, **assign calendar to project**, és végül **convert project to MPP** az Aspose.Tasks Java API használatával.

## Gyors válaszok
- **Miről szól ez az útmutató?** Adding holidays to a calendar, assigning it to a project, and saving the result as an MPP file with Aspose.Tasks for Java.  
- **Szükségem van licencre?** A free trial works for development; a commercial license is required for production.  
- **Melyik Java verzió szükséges?** Java 8 or higher (JDK 8+).  
- **Testreszabhatom a naptárat?** Yes – you can add working times, exceptions, and holidays.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc egy alap naptárhoz.  

## Mi az a “create calendar MS Project”?

A calendar MS Project létrehozása azt jelenti, hogy programozott módon definiáljuk a munkanapokat, órákat és kivételeket, amelyek a feladatok ütemezését vezérlik egy Microsoft Project fájlban. Az Aspose.Tasks használatával **java create project calendar**, módosíthatja, és a változtatásokat mentheti anélkül, hogy a Microsoft Project felhasználói felületét megnyitná.

## Miért használjuk az Aspose.Tasks-et ehhez a feladathoz?

- **Full .NET/Java compatibility** – minden olyan platformon működik, amely támogatja a Java-t.  
- **No COM or Office installation needed** – ideális szerveroldali automatizáláshoz és **automate schedule generation**.  
- **Rich API** – támogat minden naptár tulajdonságot, beleértve az egyedi munkahétet és ünnepnapokat.  
- **Direct MPP output** – **save project as MPP** közvetlenül, közbenső konverziók nélkül.  

## Előfeltételek

1. **Java Development Kit (JDK) 8+** – győződjön meg róla, hogy a `java -version` 1.8 vagy újabb verziót jelent.  
2. **Aspose.Tasks for Java** – töltse le a legújabb JAR-t a [Aspose website](https://releases.aspose.com/tasks/java/) oldalról.  
3. **IDE** – IntelliJ IDEA, Eclipse, vagy bármelyik kedvenc szerkesztő.  
4. **Basic Java knowledge** – ismerje a osztályokat, metódusokat és a fájl I/O-t.  

## Hogyan adjunk ünnepnapokat a naptárhoz

Az alábbiakban minden lépést végigvezetünk, a környezet beállításától a végső MPP fájl mentéséig. A kódrészek változatlanok maradnak az eredeti útmutatóból; a környező magyarázatok a tisztaság kedvéért kibővítésre kerültek.

### 1. lépés: Szükséges csomagok importálása

Először hozza be az Aspose.Tasks osztályokat és a Java segédprogramokat a láthatóságba.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### 2. lépés: Adatkönyvtár beállítása

Határozza meg, hogy hol lesznek az bemeneti sablon és a kimeneti fájlok. Cserélje le a helyőrzőt a gépén lévő tényleges útvonalra.

```java
String dataDir = "Your Data Directory";
```

### 3. lépés: Bemeneti és kimeneti fájlnevek meghatározása

Betöltünk egy meglévő MPP fájlt (vagy egy üres projektet), és az eredményt egy új fájlba írjuk.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### 4. lépés: Projekt betöltése és új naptár hozzáadása

Hozzon létre egy `Project` példányt a forrásfájlból, és adjon hozzá egy **“Calendar 1”** nevű naptárat.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### 5. lépés: A naptár testreszabása (opcionális)

Ha konkrét munkaidőket, ünnepnapokat vagy kivételeket kell hozzáadni, hívja meg a saját segédfüggvényét. A példa a `GetTestCalendar` helyőrzőt használja.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** Közvetlenül módosíthatja a `cal1.getWeekDays()`-t, hogy beállítsa a heti napok munkaóráit, vagy használja a `cal1.getExceptions()`-t **add holidays to calendar**.

### 6. lépés: Naptár hozzárendelése a projekthez

Adja meg a projektnek, hogy az összes ütemezési számításához az újonnan létrehozott naptárat használja.

```java
project.set(Prj.CALENDAR, cal1);
```

### 7. lépés: Projekt mentése MPP formátumban

Most **convert project to MPP** a `SaveFileFormat.Mpp` opcióval történő mentéssel.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### 8. lépés: Sikeres befejezés megerősítése

Egy egyszerű konzol üzenet jelzi, hogy a folyamat hibamentesen befejeződött.

```java
System.out.println("Process completed Successfully");
```

## Gyakori felhasználási esetek

- **Automated schedule generation** ismétlődő projektekhez (pl. heti sprint).  
- **Migrating legacy CSV or Excel calendars** egy teljes funkcionalitású MS Project fájlba.  
- **Server‑side reporting** ahol egy webszolgáltatás kérésre MPP fájlt ad vissza.  

## Hibaelhárítás és gyakori buktatók

| Probléma | Ok | Megoldás |
|----------|----|----------|
| `NullPointerException` on `project.save` | `dataDir` egy nem létező mappára mutat | Győződjön meg arról, hogy a könyvtár létezik, vagy hozza létre programból. |
| A naptár nincs alkalmazva a feladatokra | A feladatok még mindig az alapértelmezett naptárra hivatkoznak | A `Prj.CALENDAR` beállítása után frissítse minden feladat `Task.CALENDAR` értékét is, ha korábban felül lett írva. |
| A kimeneti fájl 0 KB | Hiányzó írási jogosultság | Futtassa a JVM-et megfelelő fájlrendszer jogosultságokkal, vagy válasszon írható útvonalat. |

## Gyakran ismételt kérdések

**Q: Az Aspose.Tasks for Java kompatibilis a különböző MS Project verziókkal?**  
A: Igen, az Aspose.Tasks for Java széles körű MS Project verziókat támogat, a Project 2007-től a legújabb kiadásig, biztosítva a zökkenőmentes kompatibilitást.

**Q: Testreszabhatom a naptárakat a projekt specifikus követelményei szerint?**  
A: Teljes mértékben. Meghatározhatja a munkanapokat, beállíthatja az egyedi munkahétet, hozzáadhat ünnepnapokat, és akár több naptárat is létrehozhat egyetlen projektfájlban.

**Q: Nyújt az Aspose.Tasks for Java támogatást a hibaelhárításhoz és segítségnyújtáshoz?**  
A: Igen, segítséget kaphat az Aspose.Tasks közösségi fórumon [itt](https://forum.aspose.com/c/tasks/15).

**Q: Van ingyenes próba verzió az Aspose.Tasks for Java-hoz?**  
A: Igen, egy teljes funkcionalitású ingyenes próba elérhető [itt](https://releases.aspose.com/).

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks for Java-hoz?**  
A: Ideiglenes licenceket a Aspose weboldalán kérhet [itt](https://purchase.aspose.com/temporary-license/).

---

**Utolsó frissítés:** 2026-02-05  
**Tesztelve ezzel:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}