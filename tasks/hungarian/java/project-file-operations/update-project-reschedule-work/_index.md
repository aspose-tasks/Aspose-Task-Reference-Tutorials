---
title: Frissítse és ütemezze át az MS Projectet az Aspose.Tasks-ban
linktitle: Frissítse a projektet és ütemezze át a befejezetlen munkákat az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan frissítheti és ütemezheti át programozottan az MS Project fájlokat az Aspose.Tasks for Java használatával.
weight: 23
url: /hu/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Frissítse és ütemezze át az MS Projectet az Aspose.Tasks-ban

## Bevezetés
A Microsoft Project egy széles körben használt projektmenedzsment szoftver, amely lehetővé teszi a felhasználók számára a feladatok, erőforrások és idővonalak hatékony kezelését. Az Aspose.Tasks for Java hatékony API-készletet biztosít a Microsoft Project fájlok programozott kezeléséhez. Ebben az oktatóanyagban megtudjuk, hogyan frissítheti az MS Project fájlokat, és hogyan ütemezheti át a befejezetlen munkákat az Aspose.Tasks for Java segítségével.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. Java Development Kit (JDK) telepítve a rendszerére.
2.  Aspose.Tasks a Java könyvtárhoz. Letöltheti innen[itt](https://releases.aspose.com/tasks/java/).
3. A Java programozási nyelv alapvető ismerete.

## Csomagok importálása
Először importálja a szükséges csomagokat a Java kódba:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## 1. lépés: Állítsa be a projektet
Inicializáljon egy új Project objektumot, és határozzon meg benne feladatokat azok időtartamával és függőségeivel együtt.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Határozza meg a feladatokat és azok időtartamát
// ...
// Határozza meg a feladatfüggőségeket
// ...
// Mentse el a projekt kezdeti állapotát
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## 2. lépés: Frissítse a projektmunkát
Frissítse a projektmunkát, hogy egy bizonyos dátumig befejezettként jelölje meg.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Mentse el a frissített projektet
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## 3. lépés: ütemezze át a befejezetlen munkát
Ütemezze át a befejezetlen munkákat úgy, hogy egy meghatározott dátum után kezdjék el.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Mentse el az átütemezett projektet
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet frissíteni az MS Project fájlokat, és átütemezni a befejezetlen munkákat az Aspose.Tasks for Java használatával. Ez különösen hasznos lehet olyan forgatókönyvekben, amikor a projekt ütemezését az előrehaladás vagy a változó prioritások alapján módosítani kell.

## GYIK
### K: Az Aspose.Tasks for Java kezelheti az összetett projektstruktúrákat?
V: Igen, az Aspose.Tasks for Java robusztus API-kat biztosít a feladatok, függőségek, erőforrások és egyéb projektelemek hatékony kezeléséhez.
### K: Elérhető az Aspose.Tasks for Java próbaverziója?
 V: Igen, ingyenes próbaverziót kaphat a webhelyen[itt](https://releases.aspose.com/).
### K: Hogyan kaphatok támogatást az Aspose.Tasks for Java számára?
 V: Meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) bármilyen segítségért vagy kérdésért.
### K: Vásárolhatok ideiglenes licencet az Aspose.Tasks for Java számára?
 V: Igen, ideiglenes licencek megvásárolhatók[itt](https://purchase.aspose.com/temporary-license/).
### K: Hol találom az Aspose.Tasks for Java részletes dokumentációját?
 V: Tekintse meg a dokumentációt[itt](https://reference.aspose.com/tasks/java/) átfogó útmutatókért és API-referenciákért.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
