---
date: 2026-03-29
description: Tanulja meg, hogyan állíthat be kulcsszavakat és létrehozási dátumot
  Java-ban egy MPP projektben az Aspose.Tasks for Java használatával. Lépésről lépésre
  útmutató kódrészletekkel.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan állítsuk be a kulcsszavakat az MPP projekt összefoglalóban az Aspose.Tasks
  segítségével
url: /hu/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a kulcsszavakat az MPP projekt összefoglalóban az Aspose.Tasks segítségével

## Bevezetés
Ebben az útmutatóban megtudja, **hogyan állítsuk be a kulcsszavakat** és egyéb összefoglaló információkat egy MPP projektfájlhoz az Aspose.Tasks for Java használatával. Akár szerzői adatokat, revíziószámokat vagy egy egyedi létrehozási dátumot szeretne beágyazni, ez az útmutató lépésről lépésre végigvezeti a pontos lépéseken, kész‑kód példákkal. A végére képes lesz kulcsszavakat beállítani, a Java létrehozási dátumot beállítani, és visszaolvasni az adatokat a fájlból.

## Gyors válaszok
- **Melyik könyvtárat használják?** Aspose.Tasks for Java  
- **Elsődleges cél?** Kulcsszavak, szerzői információk és létrehozási dátum beállítása egy MPP fájlban  
- **Hány kódlépés van?** Három egyszerű kódrészlet (inicializálás, mentés, olvasás)  
- **Szükség van licencre?** Egy ingyenes próba működik fejlesztéshez; a gyártási környezethez kereskedelmi licenc szükséges  
- **Támogatott Java verzió?** Java 8 és újabb  

## Mi az a „hogyan állítsuk be a kulcsszavakat” egy MPP fájlban?
A kulcsszavak metaadatmezők, amelyek a Microsoft Project (MPP) fájlban tárolódnak. Segítenek a projektek kategorizálásában, gyors keresést tesznek lehetővé, és kontextuális információkat nyújtanak az azt követő eszközök számára. Az Aspose.Tasks a `Prj.KEYWORDS` tulajdonságot teszi elérhetővé, ami egyszerűvé teszi ennek az értéknek a programozott írását vagy frissítését.

## Miért használjuk az Aspose.Tasks for Java-t a kulcsszavak és a létrehozási dátum beállításához?
* **Teljes .MPP kompatibilitás** – minden Project 2007‑2023 formátummal működik.  
* **Nincs szükség COM vagy Office telepítésre** – tiszta Java, tökéletes szerver‑oldali környezetekhez.  
* **Gazdag API** – a kulcsszavak mellett szerzőt, revíziót, megjegyzéseket és dátumokat is beállíthat egyetlen hívással.  
* **Teljesítmény‑optimalizált** – gyors olvasás/írás még nagy projektfájlok esetén is.  

## Előfeltételek
1. **Java Development Kit (JDK)** – JDK 8 vagy újabb telepítve.  
2. **Aspose.Tasks for Java** – töltse le a legújabb JAR-t innen: [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans, vagy bármely kedvelt szerkesztő.  

## Csomagok importálása
Először importálja a szükséges osztályokat. Ezek az importok hozzáférést biztosítanak a `Project` objektumhoz, a `Prj` felsoroláshoz az összefoglaló mezőkhöz, és a `SaveFileFormat` enumhoz a mentéshez.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## 1. lépés: Projekt beállítása és összefoglaló információk meghatározása
Hozzon létre egy `Project` példányt, majd használja a `set` metódust a kívánt metaadatok írásához. Figyelje meg, hogyan **állítjuk be a kulcsszavakat** és **állítjuk be a Java létrehozási dátumot** egy `Calendar` objektummal.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## 2. lépés: Projekt összefoglaló információk mentése
A mezők kitöltése után mentse el a változásokat. Itt a projektet XML formátumban mentjük a könnyű ellenőrzés érdekében, de vissza is menthető MPP formátumba.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## 3. lépés: Projekt összefoglaló információk olvasása
Annak ellenőrzésére, hogy a metaadatok helyesen íródtak-e, töltse be újra a fájlt, és olvassa vissza minden tulajdonságot. Ez a lépés bemutatja, hogy a **hogyan állítsuk be a kulcsszavakat** valóban végponttól‑végpontig működik.

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **NullPointerException on `project.get(Prj.CREATION_DATE)`** | A naptár soha nem lett beállítva mentés előtt. | Győződjön meg róla, hogy a `project.set(Prj.CREATION_DATE, cal.getTime())` hívást a `save()` előtt végzi. |
| **Keywords not appearing in Microsoft Project UI** | A fájlt XML-ként mentették, és közvetlenül a Projectben nyitották meg. | Mentse vissza MPP‑ként (`SaveFileFormat.MPP`), vagy nyissa meg az XML-t a *Import* funkcióval a Projectben. |
| **Date values shifted by timezone** | A Java `Date` időzóna információt tartalmaz. | Használja a `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` beállítást, ha UTC dátumokra van szükség. |

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.Tasks for Java-t más Java könyvtárakkal?**  
A: Igen, az Aspose.Tasks for Java zökkenőmentesen integrálható más Java könyvtárakkal a projektmenedzsment képességek bővítése érdekében.

**Q: Elérhető-e próba verzió az Aspose.Tasks for Java-hoz?**  
A: Igen, letölthet egy ingyenes próba verziót innen: [here](https://releases.aspose.com/).

**Q: Milyen gyakran frissül az Aspose.Tasks for Java?**  
A: Az Aspose.Tasks for Java rendszeresen frissül, hogy biztosítsa a kompatibilitást a legújabb Java és Microsoft Project fájlok verzióival.

**Q: További testreszabhatom a projekt összefoglaló információkat?**  
A: Természetesen, az Aspose.Tasks for Java kiterjedt lehetőségeket kínál a projekt összefoglaló információk testreszabására az Ön specifikus igényei szerint.

**Q: Hol kaphatok támogatást az Aspose.Tasks for Java-hoz?**  
A: Támogatást kaphat az Aspose.Tasks közösségi fórumon [here](https://forum.aspose.com/c/tasks/15).

---

**Legutóbb frissítve:** 2026-03-29  
**Tesztelve:** Aspose.Tasks for Java 24.11 (legújabb a írás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}