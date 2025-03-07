---
title: Adjon hozzá kiterjesztett attribútumokat a Tasks-hoz az Aspose.Tasks-ban
linktitle: Adjon hozzá kiterjesztett attribútumokat a Tasks-hoz az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Fedezze fel az Aspose.Tasks Java erejét a Microsoft Project fájlok kiterjesztett attribútumokkal történő testreszabásában. Növelje projektmenedzsment képességeit könnyedén.
weight: 11
url: /hu/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adjon hozzá kiterjesztett attribútumokat a Tasks-hoz az Aspose.Tasks-ban

## Bevezetés
projektmenedzsment képességek fejlesztése kulcsfontosságú a hatékony feladatkövetéshez és erőforrás-kezeléshez. Az Aspose.Tasks for Java hatékony megoldást kínál a Java fejlesztők számára a Microsoft Project fájlok zökkenőmentes kezeléséhez. Ebben az oktatóanyagban megvizsgáljuk, hogyan adhatunk kibővített attribútumokat a feladatokhoz az Aspose.Tasks for Java használatával, amely lehetővé teszi a projektadatok testreszabását és rendszerezését az Ön egyedi igényei szerint.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Java programozási alapismeretek.
-  Aspose.Tasks for Java könyvtár telepítve. Letöltheti a[weboldal](https://releases.aspose.com/tasks/java/).
- Java Integrated Development Environment (IDE) telepítve a rendszerére.
## Csomagok importálása
Java projektjében importálja a szükséges csomagokat az Aspose.Tasks funkciók eléréséhez:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Most bontsuk le az egyes példákat több lépésre:
## 1. Egyszerű szöveg attribútum hozzáadása
1. Állítsa be a dokumentumkönyvtár elérési útját:
```java
String dataDir = "Your Document Directory";
```
2. Hozzon létre egy új projektet:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Hozzon létre egy kiterjesztett attribútum-definíciót a Text1 típushoz:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Adja hozzá a definíciót a projekt Kiterjesztett Attribútumok gyűjteményéhez:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Adjon hozzá egy feladatot a projekthez:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Hozzon létre egy kiterjesztett attribútumot az attribútum definíciójából:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Rendeljen értéket a generált kiterjesztett attribútumhoz:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Adja hozzá a kiterjesztett attribútumot a feladathoz:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Mentse el a projektet:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Szöveg attribútum hozzáadása keresési opcióval
Kövesse a fenti lépéseket, cserélje le a Text1-et Text2-re, és szabja testre a keresési értékeket.
## 3. Időtartam attribútum hozzáadása keresési opcióval
Kövesse a fenti lépéseket, a Szöveg1 szöveget Duration2-re cserélve, és testreszabva a keresési értékeket.
## Következtetés
Ennek a lépésenkénti útmutatónak a követésével megtanulta, hogyan használhatja az Aspose.Tasks for Java-t, hogy bővített attribútumokat adjon a Microsoft Project fájljaiban lévő feladatokhoz. Ez a testreszabás lehetővé teszi a projektmenedzsment megközelítésének testreszabását, növelve a rugalmasságot és a hatékonyságot.
## Gyakran Ismételt Kérdések
### K: Használhatom az Aspose.Tasks for Java-t más Java könyvtárakkal?
V: Igen, az Aspose.Tasks for Java zökkenőmentesen integrálható Java projektjeibe, és jól működik más Java könyvtárakkal.
### K: Az Aspose.Tasks for Java alkalmas nagyméretű projektmenedzsment alkalmazásokhoz?
V: Természetesen az Aspose.Tasks for Java különböző méretű projektek kezelésére készült, beleértve a nagyszabású alkalmazásokat is.
### K: Vannak-e licencelési megfontolások az Aspose.Tasks for Java használatához kereskedelmi projektekben?
 V: Igen, feltétlenül tekintse át a következő oldalon található licencinformációkat[Aspose.Tasks webhely](https://purchase.aspose.com/buy).
### K: Hogyan kaphatok támogatást vagy segítséget az Aspose.Tasks for Java-hoz?
 V: Látogassa meg a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) közösségi támogatásra és beszélgetésekre.
### K: Kipróbálhatom az Aspose.Tasks for Java programot vásárlás előtt?
 V: Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
