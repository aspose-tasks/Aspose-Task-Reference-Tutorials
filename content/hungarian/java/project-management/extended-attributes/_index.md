---
title: Kezelje a kiterjesztett attribútumokat az Aspose.Tasks projektekben
linktitle: Kezelje a kiterjesztett attribútumokat az Aspose.Tasks projektekben
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan kezelheti hatékonyan a kiterjesztett attribútumokat az Aspose.Tasks projektekben a Java használatával. Lépésről lépésre útmutató a hatékony projektmenedzsmenthez.
type: docs
weight: 13
url: /hu/java/project-management/extended-attributes/
---
## Bevezetés
kiterjesztett attribútumok kezelése a projektmenedzsmentben kulcsfontosságú a projektadatok testreszabásához és javításához. Az Aspose.Tasks for Java robusztus eszközöket biztosít az MS Project fájlok kiterjesztett attribútumainak hatékony kezelésére. Ez az oktatóanyag lépésről lépésre végigvezeti Önt a folyamaton, biztosítva, hogy minden koncepciót alaposan megértsen.
## Előfeltételek
Mielőtt belevágna ebbe az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java programozási alapismeretek.
2. JDK (Java Development Kit) telepítve van a rendszerére.
3. Aspose.Tasks for Java könyvtár letöltve és beállítva a Java projektben.
## Csomagok importálása
Először is importáljuk a szükséges csomagokat a kezdéshez:
```java
import java.util.Date;
import com.aspose.tasks.*;
```
## 1. lépés: Adja meg az adatkönyvtárat
```java
String dataDir = "Your Data Directory";
```
 Biztosítsa a cserét`"Your Data Directory"` a projekt adatkönyvtárának elérési útjával.
## 2. lépés: Töltse be a projektfájlt
```java
Project prj = new Project(dataDir + "project5.mpp");
```
 Ez a sor betölti a nevű projektfájlt`"project5.mpp"`.
## 3. lépés: Nyissa meg a kiterjesztett attribútum-definíciókat
```java
ExtendedAttributeDefinitionCollection eads = prj.getExtendedAttributes();
```
Itt lekérjük a kiterjesztett attribútumdefiníciók gyűjteményét a projektből.
## 4. lépés: Hozzon létre kiterjesztett attribútum-definíciót
```java
ExtendedAttributeDefinition attributeDefinition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
```
 Ez a kódszegmens kiterjesztett attribútum-definíciót hoz létre a feladatokhoz, megadva az egyéni mezőtípust mint`Start` és attribútum neve as`"Start 7"`.
## 5. lépés: Adja hozzá a definíciót a projekthez
```java
prj.getExtendedAttributes().add(attributeDefinition);
eads.add(attributeDefinition);
```
Az újonnan létrehozott kiterjesztett attribútumdefiníciót hozzáadjuk a projekthez és az attribútumdefiníciók gyűjteményéhez is.
## 6. lépés: A feladat és a kiterjesztett attribútumok elérése
```java
Task tsk = prj.getRootTask().getChildren().getById(1);
ExtendedAttributeCollection eas = tsk.getExtendedAttributes();
```
Itt lekérünk egy feladatot a projektből és a hozzá tartozó kiterjesztett attribútumokat.
## 7. lépés: Hozzon létre kiterjesztett attribútumpéldányt
```java
ExtendedAttribute ea = attributeDefinition.createExtendedAttribute();
```
Ez a lépés létrehozza a kiterjesztett attribútum egy példányát a korábban meghatározott attribútumdefiníció alapján.
## 8. lépés: Állítsa be az attribútum értékét
```java
Date date = new Date();
ea.setDateValue(date);
```
Beállítjuk a kiterjesztett attribútum értékét, jelen esetben egy dátumértéket.
## 9. lépés: Adjon hozzá attribútumot a feladathoz
```java
eas.add(ea);
```
Végül hozzáadjuk a kiterjesztett attribútumot a feladathoz.
## 10. lépés: Projekt mentése
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
Ez a sor XML-fájlba menti a módosított projektet a hozzáadott kiterjesztett attribútummal.
## Következtetés
Ebben az oktatóanyagban megtanulta, hogyan kezelheti a kiterjesztett attribútumokat az Aspose.Tasks projektekben Java használatával. Ha követi ezeket a lépéseket, hatékonyan kezelheti az egyéni projektadatokat, javítva projektkezelési képességeit.
## GYIK
### K: Használhatom az Aspose.Tasks-t más programozási nyelvekkel?
V: Igen, az Aspose.Tasks több programozási nyelvet támogat, beleértve a Java, .NET és C nyelvet++.
### K: Elérhető az Aspose.Tasks ingyenes próbaverziója?
V: Igen, letölthet egy ingyenes próbaverziót az Aspose.Tasks webhelyről.
### K: Testreszabhatom a kiterjesztett attribútumtípusokat?
V: Természetesen az Aspose.Tasks lehetővé teszi egyedi kiterjesztett attribútumtípusok meghatározását a projekt igényeihez igazítva.
### K: Hogyan férhetek hozzá az Aspose.Tasks dokumentációjához?
 V: Az Aspose.Tasks webhelyen átfogó dokumentációt találhat[dokumentáció](https://reference.aspose.com/tasks/java/).
### K: Elérhető technikai támogatás az Aspose.Tasks felhasználók számára?
 V: Igen, az Aspose.Tasks fórumon keresztül elérheti a technikai támogatást[weboldal](https://forum.aspose.com/c/tasks/15).