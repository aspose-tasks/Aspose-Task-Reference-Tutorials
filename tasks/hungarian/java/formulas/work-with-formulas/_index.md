---
date: 2026-10-05
description: Ismerje meg, hogyan hozhat létre tesztprojektet és számíthatja ki a napok
  számát a dátumok között az Aspose.Tasks for Java használatával, adjon hozzá egy
  custom field-et, és kezelje hatékonyan az MPP fájlokat.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Képletek használata az Aspose.Tasks-ben
og_description: Tesztprojekt létrehozása és napok számítása a dátumok között az Aspose.Tasks
  for Java használatával. Ez az útmutató bemutatja, hogyan adjon hozzá egy custom
  field-et, állítson be task deadlines-et, és mentse a projektet MPP file-ként.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Tesztprojekt létrehozása és napok számítása a dátumok között
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Tesztprojekt létrehozása és napok számítása a dátumok között
url: /hu/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tesztprojekt létrehozása és napok számítása dátumok között

Ebben az útmutatóban **tesztprojektet hoz létre** és **napok számítását végzi dátumok között** egy egyéni mező hozzáadásával, egy kiterjesztett attribútum meghatározásával, és egy Microsoft Project képlet alkalmazásával az Aspose.Tasks Java könyvtáron keresztül. Akár ütemterveket kell generálnia, határidőket számítania, vagy jelentéseket automatizálnia, az Aspose.Tasks lehetővé teszi a Project adatok programozott manipulálását asztali telepítés nélkül, több mint 50 bemeneti és kimeneti formátumot támogat, és több száz oldalas fájlokat kezel memóriahatékony módban.

## Gyors válaszok
- **Mi a tutorial tartalma?** Bemutatja, hogyan hozhat létre egy tesztprojektet, definiáljon egy kiterjesztett attribútumot, állítson be egy feladat határidejét, és használjon képletet a napok számításához dátumok között.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (legújabb verzió).  
- **Szükségem van licencre?** Egy ingyenes próba verzió fejlesztéshez megfelelő; a termeléshez kereskedelmi licenc szükséges.  
- **Milyen IDE-t használhatok?** Bármely Java IDE (IntelliJ IDEA, Eclipse, VS Code), amely támogatja a JDK 8+ verziót.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc a kód másolásához és futtatásához.

## Mi a „napok számítása dátumok között” az Aspose.Tasks-ben?
Az Aspose.Tasks-ben a képlet egy karakterlánc, amely hivatkozhat feladatmezőkre és számításokat végezhet. A `[Deadline] - [Finish]` a képletszintaxis, amelyet az Aspose.Tasks használ a két dátummező közötti napok számának numerikus különbségének visszaadásához. Az eredmény numerikus értékként tárolódik, amely egész napokat képvisel, és megjeleníthető egy egyéni mezőben vagy felhasználható további számításokban.

## Miért használja az Aspose.Tasks-et a napok számításához dátumok között?
Az Aspose.Tasks **teljes API lefedettséget** biztosít minden Project, Task és Resource tulajdonsághoz, Windows, Linux és macOS rendszereken fut, és **nem igényel Microsoft Project vagy Office** telepítést. A motor **500+ feladatot** képes feldolgozni kevesebb, mint egy másodperc alatt tipikus szerverhardveren, így ideális CI csővezetékekhez, Docker konténerekhez és nagy mennyiségű kötegelt feldolgozáshoz.

## Hogyan állítsunk be határidőt egy feladathoz
A java.util.Calendar egy Java osztály, amely egy adott időpontot reprezentál. Határidőt úgy állít be, hogy egy `java.util.Calendar` értéket ad a feladat `Tsk.DEADLINE` mezőjéhez. A Calendar példány létrehozása után állítsa be az év, hónap és nap értékeket a kívánt határidőre, majd hívja a `task.set(Tsk.DEADLINE, calendar);` metódust. A határidő a projektfájlban tárolódik, és használható képletekben, például `[Deadline] - [Finish]`.

## Hogyan definiáljunk kiterjesztett attribútumot
A kiterjesztett attribútum egy egyéni mező, amely a képlet eredményét tárolja. Egyszer hozza létre, adjon neki barátságos álnevet, és csatolja a `[Deadline] - [Finish]` kifejezést, hogy minden feladat automatikusan kiszámíthassa az intervallumot. Létrehozható a `ExtendedAttribute` példányosításával, az Alias beállításával, a képlet hozzárendelésével, és a projekt gyűjteményéhez való hozzáadásával.

## Előfeltételek
Before you start, make sure you have the following:

- **Java Development Kit (JDK) 8+** – töltse le az Oracle weboldaláról vagy használja az OpenJDK-t.  
- **Aspose.Tasks for Java** – szerezze be a legújabb JAR-t a [Aspose.Tasks for Java letöltési oldalról](https://releases.aspose.com/tasks/java/), és adja hozzá a projekt classpath-hez vagy Maven/Gradle függőségekhez.

## Csomagok importálása
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Tesztprojekt létrehozása egy egyéni mezővel
Először **tesztprojektet hozunk létre** és hozzáadunk egy egyéni mezőt, amely később a képlet eredményét tárolja.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tipp:* `CreateTestProjectWithCustomField()` egy segédmetódus, amely egy minimális ütemtervet épít fel és regisztrál egy kiterjesztett attribútumot, amely készen áll a képlet hozzárendelésére.

### 2. lépés: Kiterjesztett attribútum definiálása (egyéni mező hozzáadása)
Ezután **kiterjesztett attribútumot definiálunk** – lényegében az egyéni mezőt – és adunk neki egy barátságos álnevet. Itt történik a **egyéni mező** logikájának hozzáadása.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** a mezőt olvashatóvá teszi a Projectben.  
- **Formula** kiszámítja a napok számát egy feladat *Finish* dátuma és a *Deadline* között – a *napok számítása dátumok között* lényege.

### 3. lépés: Határidő beállítása egy feladathoz (határidő feladat hozzáadása és feladat határidő beállítása)
Most **határidő feladat** adatokat adunk hozzá a *Deadline* tulajdonság egy adott feladatra történő beállításával.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- A `Calendar` példány határozza meg a pontos határidő pillanatát.  
- `set(Tsk.DEADLINE, …)` **beállítja a feladat határidejét** a kiválasztott feladatra.

### 4. lépés: Projekt mentése (Microsoft Project fájl manipulálása)
Végül **manipuláljuk a Microsoft Project-et** a változások MPP fájlba mentésével.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Megnyithatja a `SaveFile.mpp` fájlt a Microsoft Projectben, hogy lássa az egyéni mezőt, a képlet eredményét és a határidőt a menetrendben.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **Képlet nem értékelődik** | Győződjön meg róla, hogy az attribútum `Formula` karakterlánca helyes mezőneveket használ (pl. `[Deadline]`, `[Finish]`). |
| **Feladat nem található** | Ellenőrizze, hogy a feladat azonosító (`1` a példában) létezik; használja a `project.getRootTask().getChildren().size()`-t a hibakereséshez. |
| **Licenc kivétel** | Alkalmazzon érvényes Aspose.Tasks licencet, mielőtt bármely API metódust meghívna (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Gyakran ismételt kérdések

**K: Használhatom az Aspose.Tasks-et más programozási nyelvekkel?**  
V: Igen, az Aspose.Tasks API-kat biztosít .NET, Java és más platformok számára, lehetővé téve a Microsoft Project fájlok manipulálását a választott nyelven.

**K: Elérhető ingyenes próba verzió az Aspose.Tasks-hez?**  
V: Természetesen. Töltse le a teljes funkcionalitású próbaverziót a [Aspose.Tasks letöltési oldalról](https://releases.aspose.com/).

**K: Hol találok részletes dokumentációt az Aspose.Tasks-hez?**  
V: A hivatalos dokumentáció a [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/) oldalon érhető el.

**K: Hogyan kaphatok támogatást az Aspose.Tasks-hez?**  
V: Látogasson el az [Aspose.Tasks fórumra](https://forum.aspose.com/c/tasks/15), hogy kérdéseket tegyen fel és tapasztalatokat osszon meg a közösséggel.

**K: Szükségem van ideiglenes licencre az értékeléshez?**  
V: Ideiglenes licenc áll rendelkezésre rövid távú teszteléshez; kérhet egyet a [temporary license request page](https://purchase.aspose.com/temporary-license/) oldalon.

---

**Utoljára frissítve:** 2026-10-05  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Hogyan hozzunk létre MPP fájlt – Üres projekt létrehozása és mentése MPP formátumban az Aspose.Tasks segítségével](/tasks/java/project-configuration/create-save-mpp/)
- [Projekt kezdő dátum beállítása MS Projectben az Aspose.Tasks for Java használatával](/tasks/java/project-properties/write-project-info/)
- [Kiterjesztett attribútum létrehozása Java-ban az Aspose.Tasks segítségével](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}