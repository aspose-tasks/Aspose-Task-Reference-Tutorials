---
date: 2025-12-23
description: Tanulja meg, hogyan hozhat létre MPP összegzést és frissítheti a projekt
  szerzőjét az Aspose.Tasks for Java segítségével. Állítson be és kérjen le projektinformációkat
  könnyedén.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan hozzunk létre MPP összefoglalót és frissítsük a projekt szerzőjét az
  Aspose.Tasks segítségével
url: /hu/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Write MPP Project Summary in Aspose.Tasks

## Introduction
Ebben az útmutatóban **create MPP summary** információkat hozunk létre egy Microsoft Project fájlhoz, és megtanuljuk, hogyan **update project author** adatokat az Aspose.Tasks Java könyvtár segítségével. Akár projektmenedzsment eszközt építesz, akár jelentéskészítést automatizálsz, az összefoglaló tulajdonságok programozott vezérlése időt takarít meg, és biztosítja a konzisztenciát a projektjeidben.

## Quick Answers
- **Mit jelent a “create MPP summary”?** Azt jelenti, hogy beállítjuk a magas szintű projekt tulajdonságokat (szerző, revízió, kulcsszavak stb.), amelyek a Microsoft Project Projektösszefoglaló információk párbeszédablakában jelennek meg.  
- **Melyik könyvtár kezeli ezt?** Az Aspose.Tasks for Java egy folyékony API-t biztosít ezeknek a tulajdonságoknak az olvasásához és írásához.  
- **Szükségem van licencre?** Elérhető egy ingyenes próba, de a kereskedelmi licenc szükséges a termelési használathoz.  
- **Módosíthatom a szerzőt is a fájl mentése után?** Igen – a **project author** frissítéséhez meghívhatod a `project.set(Prj.AUTHOR, "New Author")` metódust, majd újra mentheted a fájlt.  
- **Milyen fájlformátumok támogatottak?** Mind az MPP, mind az XML (SaveFileFormat.Xml) teljes mértékben támogatott.

## What is create MPP summary?
Az MPP összefoglaló létrehozása magában foglalja a projekt metaadatainak (szerző, revíziószám, kulcsszavak, megjegyzések, létrehozási dátum és nyomtatási dátum) kitöltését. Ezek a metaadatok a Projektösszefoglaló információ rekordjában tárolódnak, és a Microsoft Project **File → Info** szakaszában jelennek meg.

## Why update project author?
A **project author** információjának pontos fenntartása elengedhetetlen az audit nyomvonalak, az együttműködés és a jelentéskészítés szempontjából. Ha több csapattag járul hozzá, előfordulhat, hogy **update project author** kell, hogy tükrözze a legújabb változásokat vagy helyesen hozzárendelje a munkát.

## Prerequisites
1. Java Development Kit (JDK) telepítve legyen a gépeden.  
2. Aspose.Tasks for Java – töltsd le [innen](https://releases.aspose.com/tasks/java/).  
3. Egy IDE, például IntelliJ IDEA, Eclipse vagy NetBeans.

## Import Packages
Firstly, import the necessary packages into your Java class:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Step 1: Set Up Project and Define Summary Information
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
A fenti kódban **create MPP summary** mezőket hozunk létre, például szerző, revízió és kulcsszavak. Később a **project author** is frissíthető a `project.set(Prj.AUTHOR, "New Name")` hívással.

## Step 2: Save Project Summary Information
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
A projekt mentése elmenti az összes, most definiált összefoglaló adatot.

## Step 3: Read Project Summary Information
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
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Ez a kódrészlet bemutatja, hogyan **read back** az összefoglaló információkat, megerősítve, hogy a **create MPP summary** művelet sikeres volt.

## Common Issues and Solutions
- **Null értékek olvasás után:** Győződj meg róla, hogy a projekt sikeresen mentésre került a újratöltés előtt. Ellenőrizd a fájl útvonalakat és a jogosultságokat.  
- **Dátumformátum eltérések:** A `project.get(Prj.CREATION_DATE)` egy `java.util.Date` objektumot ad vissza. Használj `SimpleDateFormat`-ot, ha egyedi megjelenítési formátumra van szükséged.  
- **Licenc nincs beállítva:** Érvényes licenc nélkül az Aspose.Tasks értékelő módban fut, és vízjelet helyezhet el. Regisztráld a licencet a kód elején.

## Frequently Asked Questions
**K: Használhatom az Aspose.Tasks for Java-t más Java könyvtárakkal?**  
V: Igen, az Aspose.Tasks for Java zökkenőmentesen integrálható más Java könyvtárakkal, hogy bővítse a projektmenedzsment képességeidet.

**K: Van elérhető próba verzió az Aspose.Tasks for Java-hoz?**  
V: Igen, letölthetsz egy ingyenes próba verziót [innen](https://releases.aspose.com/).

**K: Milyen gyakran frissül az Aspose.Tasks for Java?**  
V: Az Aspose.Tasks for Java rendszeresen frissül, hogy biztosítsa a kompatibilitást a legújabb Java és Microsoft Project fájlok verzióival.

**K: Tovább testreszabhatom a projektösszefoglaló információkat?**  
V: Természetesen, az Aspose.Tasks for Java kiterjedt lehetőségeket biztosít a projektösszefoglaló információk testreszabásához a saját igényeid szerint.

**K: Hol kaphatok támogatást az Aspose.Tasks for Java-hoz?**  
V: Támogatást kaphatsz az Aspose.Tasks közösségi fórumán [itt](https://forum.aspose.com/c/tasks/15).

## Conclusion
Ebben az útmutatóban bemutattuk, hogyan **create MPP summary** adatokat, **update project author**, és ellenőrizzük ezeket a változásokat az Aspose.Tasks for Java segítségével. Ezeknek a lépéseknek az automatizálásával teljes irányítást nyerhetsz a projekt metaadatok felett, ami robusztusabbá teszi az alkalmazásaidat és pontosabbá a projektjelentéseket.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}