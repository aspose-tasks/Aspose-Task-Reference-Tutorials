---
title: Mentés CSV-ként, szövegként és sablonként az Aspose.Tasks-ban
linktitle: Mentés CSV-ként, szövegként és sablonként az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan menthet Microsoft Project fájlokat CSV, szöveg és sablon formátumban az Aspose.Tasks for Java segítségével.
type: docs
weight: 16
url: /hu/java/project-file-operations/save-csv-text-template/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet projektfájlokat menteni különböző formátumokban, például CSV, szöveg és sablon formájában az Aspose.Tasks for Java segítségével. Az Aspose.Tasks egy hatékony Java-könyvtár, amely lehetővé teszi a fejlesztők számára, hogy a Microsoft Project telepítése nélkül dolgozzanak Microsoft Project fájlokkal.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK) telepítve a rendszerére.
2.  Aspose.Tasks a Java könyvtárhoz letöltve és beállítva a Java projektben. Letöltheti innen[itt](https://releases.aspose.com/tasks/java/).
3. Java programozási nyelv alapismerete.

## Csomagok importálása
Először importálnia kell a szükséges csomagokat a Java fájlba:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Projekt mentése CSV-ként
Nézzük meg a projekt CSV formátumban történő mentéséhez szükséges lépéseket:
### 1. lépés: Töltse be a projektet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 2. lépés: Mentés CSV-ként
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Projekt mentése szövegként
Így mentheti el a projektet szövegként:
### 1. lépés: Töltse be a projektet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 2. lépés: Mentés szövegként
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Projekt mentése sablonként
A projekt sablonként történő mentése a következő lépéseket tartalmazza:
### 1. lépés: Töltse be a projektet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 2. lépés: Állítsa be a sablonbeállításokat
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### 3. lépés: Mentés sablonként
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan menthet Microsoft Project fájlokat CSV-ként, szövegként és sablonként az Aspose.Tasks for Java segítségével. Ezekkel az egyszerű lépésekkel hatékonyan kezelheti projektfájljait különböző formátumokban, javítva ezzel Java-fejlesztői hatékonyságát.
## GYIK
### K: Az Aspose.Tasks for Java kezelheti az összetett projektfájlokat?
V: Abszolút! Az Aspose.Tasks for Java könnyedén kezeli a különböző bonyolultságú projekteket, átfogó támogatást nyújtva a Microsoft Project fájlformátumokhoz.
### K: Elérhető az Aspose.Tasks for Java próbaverziója?
 V: Igen, letöltheti az Aspose.Tasks for Java ingyenes próbaverzióját a webhelyről[itt](https://releases.aspose.com/).
### K: Hol találok támogatást az Aspose.Tasks for Java számára?
 V: Meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) az Aspose.Tasks for Java kapcsán bármilyen segítségért vagy kérdésért.
### K: Vásárolhatok ideiglenes licencet az Aspose.Tasks for Java számára?
 V: Igen, vásárolhat ideiglenes licencet a következőtől[itt](https://purchase.aspose.com/temporary-license/), amely lehetővé teszi a könyvtárban rejlő teljes potenciál értékelését.
### K: Az Aspose.Tasks for Java kompatibilis a különböző operációs rendszerekkel?
V: Igen, az Aspose.Tasks for Java különféle operációs rendszerekkel kompatibilis, beleértve a Windowst, a macOS-t és a Linuxot.