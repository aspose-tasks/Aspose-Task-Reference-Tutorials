---
title: Konfigurálja a Gantt-diagram nézetet az Aspose.Tasks Projects programban
linktitle: Konfigurálja a Gantt-diagram nézetet az Aspose.Tasks Projects programban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan konfigurálhatja a Gantt MS Project Chart View nézetet az Aspose.Tasks programban Java használatával. Testreszabhatja a projektet, és lépésről lépésre megjelenítheti őket a Gantt-diagramon.
type: docs
weight: 10
url: /hu/java/project-configuration/configure-gantt-chart/
---
## Bevezetés
Ebből az oktatóanyagból megtudhatja, hogyan konfigurálhatja a Gantt MS Project Chart View nézetet Aspose.Tasks projektekben Java használatával. Az Aspose.Tasks egy hatékony Java API, amely lehetővé teszi a Microsoft Project fájlokkal való programozást. Ha követi ezeket a lépéseket, testreszabhatja a Gantt-diagram nézetet a projekt követelményei szerint.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a Java telepítve van a rendszeren.
2.  Aspose.Tasks könyvtár: Töltse le és telepítse az Aspose.Tasks könyvtárat. Letöltheti innen[itt](https://releases.aspose.com/tasks/java/).
3. Integrált fejlesztői környezet (IDE): Válasszon egy IDE-t, amelyet választott. Ez az oktatóanyag az IntelliJ IDEA-t használja, de bármilyen IDE-t használhat, amivel kényelmes.
## Csomagok importálása
Először is importálnia kell a szükséges csomagokat az Aspose.Tasks használatához a Java projektben. Adja hozzá a következő importálási utasításokat a Java fájlhoz:
```java
import com.aspose.tasks.*;
```
Most bontsuk le a Gantt MS Project Chart View konfigurálásának folyamatát lépésről lépésre:
## 1. lépés: Állítsa be a Data Directory-t
```java
String dataDir = "Your Data Directory";
```
 Cserélje ki`"Your Data Directory"` a projekt adatkönyvtárának elérési útjával.
## 2. lépés: Töltse be a projektfájlt
```java
Project project = new Project(dataDir + "project.mpp");
```
Töltse be projektfájlját (`project.mpp` ebben a példában) segítségével`Project` osztály az Aspose.Tasks.
## 3. lépés: Új tevékenység hozzáadása
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 Hozzon létre egy új feladatot a projektben a`Task` osztályba, és add hozzá a gyökérfeladat gyermekeihez.
## 4. lépés: Egyéni attribútum meghatározása
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 Határozzon meg egy új egyéni attribútumot a`ExtendedAttributeDefinition`osztályba, és adja hozzá a projekt kiterjesztett attribútumaihoz.
## 5. lépés: Adjon hozzá egyéni attribútumot a feladathoz
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Adja hozzá az egyéni attribútumot a létrehozott feladathoz a`createExtendedAttribute` módszer.
## 6. lépés: Táblázat testreszabása
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
Testreszabhatja a táblázatot a megadott szélességű, cím és igazítású szövegattribútummező hozzáadásával.
## 7. lépés: Projekt mentése
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Mentse a projektet a konfigurált Gantt MS Project Chart View segítségével. Az eredményül kapott fájl megnyitható a Microsoft Project 2010 programban.
## Következtetés
Gratulálunk! Sikeresen konfigurálta a Gantt MS Project Chart View nézetet az Aspose.Tasks projektekben Java használatával. Most már testreszabhatja a projekt attribútumait, és megjelenítheti őket a Gantt-diagramon a projekt igényei szerint.
## GYIK
### K: Használhatom az Aspose.Tasks-t más programozási nyelvekkel?
V: Igen, az Aspose.Tasks több programozási nyelvhez is elérhető, beleértve a .NET-t, a Java-t és a C-t.++.
### K: Elérhető az Aspose.Tasks ingyenes próbaverziója?
 V: Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
### K: Hol találok támogatást az Aspose.Tasks számára?
V: Támogatást találhat és kérdéseket tehet fel a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).
### K: Hogyan vásárolhatok licencet az Aspose.Tasks számára?
 V: Vásárolhat licencet a következőtől[itt](https://purchase.aspose.com/buy).
### K: Szükségem van ideiglenes licencre tesztelés céljából?
 V: Igen, ideiglenes engedélyt szerezhet a következőtől[itt](https://purchase.aspose.com/temporary-license/).