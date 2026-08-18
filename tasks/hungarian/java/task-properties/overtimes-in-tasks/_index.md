---
date: 2026-02-23
description: Ismerje meg, hogyan kezelheti a túlórát a projektfeladatokban az Aspose.Tasks
  for Java segítségével, beleértve a túlóra költségének kiszámítását és az erőforrás-nyilvántartás
  egyszerűsítését.
linktitle: Overtimes in Tasks with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan kezeljük a túlórát a feladatokban az Aspose.Tasks segítségével
url: /hu/java/task-properties/overtimes-in-tasks/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan kezeljük a túlórát a feladatokban az Aspose.Tasks segítségével

## Bevezetés
Ha azt keresi, **hogyan kezelje a túlórát** egy Microsoft Project fájlban, jó helyen jár. Ebben az oktatóanyagról megmutatjuk, hogyan teszi lehetővé az Aspose.Tasks for Java, hogy beolvassa, módosítsa és jelentse a feladatok túlórával kapcsolatos tulajdonságait, így pontosan tarthatja a menetrendet és a költségvetést.  

## Gyors válaszok
- **Mi a “túlóra” jelentése egy projektben?** A rendszeres kapacitáson felül eső extra munkaórák.  
- **Melyik API osztály biztosítja a túlóra adatokat?** `Task` a `Tsk` mezőgyűjteménnyel (pl. `Tsk.OVERTIME_COST`).  
- **Szükségem van licencre a minta futtatásához?** Igen, egy ideiglenes vagy teljes Aspose.Tasks licenc szükséges a termeléshez.  
- **Képes vagyok automatikusan kiszámítani a túlóra költségét?** Természetesen – kérje le a `Tsk.OVERTIME_COST` értéket és alkalmazza a költség‑arány logikáját.  
- **Kompatibilis-e a Java 17-tel?** Igen, az Aspose.Tasks for Java támogatja a Java 8-at és újabbakat.

## Mi a túlóra kezelése a projektfeladatokban?
A túlóra kezelése azt jelenti, hogy nyomon követi a további munkát és költséget, amely akkor keletkezik, amikor az erőforrások meghaladják a normál munkaidejüket. Ennek az adatnak a pontos rögzítése segít a költségvetés előrejelzésében, a menetrendek módosításában és a reális projektállapot jelentésében.

## Miért használja az Aspose.Tasks-et a túlórához?
* **Microsoft Project nélkül** – dolgozzon közvetlenül .MPP fájlokkal.  
* **Teljes hozzáférés a túlóra mezőkhöz** – a költség, munka és a százalékosan kész értékek a `Tsk` felsoroláson keresztül érhetők el.  
* **Programozott vezérlés** – beolvashatja, módosíthatja vagy kiszámíthatja a túlóra költségét manuális UI lépések nélkül.

## Előfeltételek
Mielőtt belemerülne az oktatóanyagba, győződjön meg róla, hogy a következő előfeltételek teljesülnek:
- Java fejlesztői környezet: Győződjön meg róla, hogy a gépén be van állítva egy Java fejlesztői környezet.  
- Aspose.Tasks for Java: Töltse le és telepítse az Aspose.Tasks könyvtárat. A könyvtárat és a dokumentációt [itt](https://reference.aspose.com/tasks/java/) találja.  
- Projektfájl: Készítsen elő egy projektfájlt (pl. TaskOvertimes.mpp), amellyel a tutorial során dolgozhat.

## Csomagok importálása
Java projektjében importálja a szükséges Aspose.Tasks csomagokat a funkciók kihasználásához. Adja hozzá a következő import utasításokat:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## 1. lépés: Új projekt létrehozása
Új projekt (vagy egy meglévő betöltése) létrehozása az első lépés minden elemzéshez. Ez kielégíti a másodlagos kulcsszót is **create new project**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```

## 2. lépés: Feladatok bejárása és a túlóra részleteinek kiírása
Most végigjárjuk minden felső szintű feladatot, megjelenítjük a túlóra információkat, és bemutatjuk, hogyan **kalkulálhatja a túlóra költségét** a `OVERTIME_COST` mező beolvasásával.

```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    // Set percent complete
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```

> **Tipp:** Az `OVERTIME_COST` értéket az Aspose.Tasks már kiszámítja az erőforrás túlóra rátája alapján. Ha egyedi számítást szeretne, szorozza meg az `OVERTIME_WORK` értéket a saját rátájával, és frissítse a mezőt a `tsk.set(Tsk.OVERTIME_COST, yourValue);` paranccsal.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **Null értékek a túlóra mezőkben** | Győződjön meg róla, hogy a forrás .MPP fájl valóban tartalmaz túlóra adatokat; ellenkező esetben a mezők `null` értéket adnak vissza. |
| **Helytelen költség módosítás után** | A túlóra munka vagy költség módosítása után hívja meg a `project.save()` metódust a változások mentéséhez. |
| **Licenc nem található** | Helyezze a `Aspose.Tasks.lic` fájlt a projekt gyökerébe, vagy állítsa be a licencet programozottan a projekt betöltése előtt. |

## Gyakran ismételt kérdések

**K: Az Aspose.Tasks alkalmas nagy léptékű projektmenedzsmentre?**  
A: Igen, az Aspose.Tasks úgy lett tervezve, hogy különböző méretű projekteket kezeljen, a kis kezdeményezésektől a nagy és összetett programokig.

**K: Integrálhatom az Aspose.Tasks-et más Java keretrendszerekkel?**  
A: Természetesen! Az Aspose.Tasks zökkenőmentesen integrálható a Spring, Jakarta EE és más Java ökoszisztémákkal, növelve ezzel a sokoldalúságát.

**K: Vannak licencelési szempontok az Aspose.Tasks használatával kapcsolatban?**  
A: Igen, a licenc részleteket és egy ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) talál.

**K: Hol kérhetek segítséget vagy vitathatom meg az Aspose.Tasks‑hez kapcsolódó kérdéseket?**  
A: Látogassa meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15), hogy a közösséggel kapcsolatba léphessen és támogatást kapjon.

**K: Elérhető ingyenes próbaverzió az Aspose.Tasks‑hez?**  
A: Igen, a ingyenes próbaverziót [itt](https://releases.aspose.com/) érheti el.

**K: Hogyan számolhatom ki egy adott erőforrás túlóra költségét?**  
A: Szerezze meg az erőforrás túlóra rátáját, szorozza meg az `OVERTIME_WORK` (órában) értékkel, és ha egyedi számítást szeretne, állítsa be az eredményt az `OVERTIME_COST` mezőbe.

## Következtetés
Az Aspose.Tasks for Java egyszerűsíti a projektfeladatok **túlóra kezelését**, közvetlen programozott hozzáférést biztosítva a fejlesztőknek a túlóra költség, munka és előrehaladás mutatókhoz. Ezt az útmutatót követve betölthet egy projektet, beolvashatja a túlóra részleteket, módosíthatja a százalékos értékeket, és akár egyedi túlóra költségeket is kiszámíthat – mindezt anélkül, hogy megnyitná a Microsoft Projectet.

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Tasks for Java (latest version)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}