---
title: Határozza meg az MS Project verzióját az Aspose.Tasks segítségével
linktitle: Határozza meg a projekt verzióját az Aspose.Tasks segítségével
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan határozhatja meg programozottan az MS Project fájlok verzióját az Aspose.Tasks for Java segítségével. Lépésről lépésre útmutató kódpéldákkal.
weight: 12
url: /hu/java/project-management/determine-version/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Határozza meg az MS Project verzióját az Aspose.Tasks segítségével

## Bevezetés
Ez az oktatóanyag végigvezeti Önt az Aspose.Tasks for Java használatán, amellyel lépésről lépésre meghatározhatja az MS Project fájl verzióját. Az Aspose.Tasks egy hatékony Java API, amely lehetővé teszi a fejlesztők számára, hogy a Microsoft Project telepítése nélkül kezeljék a Microsoft Project fájlokat.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren.
2.  Aspose.Tasks for Java JAR fájl: Töltse le az Aspose.Tasks for Java könyvtárat a[weboldal](https://releases.aspose.com/tasks/java/) és adja hozzá a Java projekthez.
3. MS Project File: Készítsen elő egy MS Project fájlt (XML formátum) tesztelésre.

## Csomagok importálása
Mielőtt belemerülnénk a kódba, importáljuk a szükséges csomagokat:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## 1. lépés: Állítsa be a projektet
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Data Directory";
```
 Cserélje ki`"Your Data Directory"` az MS Project fájlt tartalmazó könyvtár elérési útjával.
## 2. lépés: Töltse be a projektet
```java
Project project = new Project(dataDir + "input.xml");
```
 Cserélje ki`"input.xml"` az MS Project fájl nevével.
## 3. lépés: Határozza meg a projekt verzióját
```java
//Projektverzió tulajdonság megjelenítése
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Ez a kódrészlet lekéri és kinyomtatja az MS Project fájl verzióját és utolsó mentési dátumát.
## 4. lépés: Eredmény megjelenítése
```java
//Konverzió eredményének megjelenítése.
System.out.println("Process completed Successfully");
```
Ez a sor a folyamat befejezését jelzi.

## Következtetés
Ebben az oktatóanyagban megtanulta, hogyan határozhatja meg az MS Project fájl verzióját az Aspose.Tasks for Java segítségével. A lépésenkénti útmutató követésével hatékonyan, probléma nélkül dolgozhat az MS Project fájlokkal Java-alkalmazásaiban.

## GYIK
### K: Használhatom az Aspose.Tasks-t más programozási nyelvekkel?
V: Igen, az Aspose.Tasks több programozási nyelvet támogat, beleértve a .NET-et, a Java-t és a C-t++.
### K: Az Aspose.Tasks alkalmas nagyszabású projektekre?
V: Természetesen az Aspose.Tasks-t úgy tervezték, hogy bármilyen méretű projektet könnyedén kezeljen.
### K: Testreszabhatom a projekt adatait az Aspose.Tasks segítségével?
V: Igen, az Aspose.Tasks segítségével kezelheti a projektadatokat, módosíthatja a feladatokat, az erőforrásokat és még sok mást.
### K: Az Aspose.Tasks használatához szükséges a Microsoft Project telepítése?
V: Nem, az Aspose.Tasks függetlenül működik, és nem szükséges a Microsoft Project telepítése.
### K: Elérhető technikai támogatás az Aspose.Tasks számára?
 V: Igen, technikai támogatást kaphat az Aspose.Tasks fórumon a címen[itt](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
