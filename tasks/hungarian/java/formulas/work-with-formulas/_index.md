---
date: 2025-12-07
description: Tanulja meg, hogyan **hozzon létre tesztprojektet** és **adjon hozzá
  egyéni mezőt**, miközben a Microsoft Project fájlokat manipulálja az Aspose.Tasks
  for Java segítségével.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tesztprojekt létrehozása és képletek használata az Aspose.Tasks for Java-val
url: /hu/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tesztprojekt létrehozása és képletek használata az Aspose.Tasks for Java-val

## Introduction
Ebben az útmutatóban **tesztprojekt** fájlokat hozunk létre, egy egyéni mezőt adunk hozzá, és az MS Project képletekkel dolgozunk az Aspose.Tasks Java könyvtár segítségével. Az Aspose.Tasks egyszerűvé teszi a **Microsoft Project** adatok programozott manipulálását – legyen szó ütemtervek generálásáról, dátumok számításáról vagy jelentések automatizálásáról. A leírás végére egy futtatható példát kap, amely meghatároz egy kiterjesztett attribútumot, beállít egy feladat határidejét képlettel, és MPP fájlként menti a projektet.

## Quick Answers
- **What does the tutorial cover?** Tesztprojekt létrehozása, egyéni mező hozzáadása, kiterjesztett attribútum definiálása, és feladat határidejének beállítása képlettel.  
- **Which library is required?** Aspose.Tasks for Java (legújabb verzió).  
- **Do I need a license?** Fejlesztéshez egy ingyenes próba verzió elegendő; termeléshez licenc szükséges.  
- **What IDE can I use?** Bármely Java IDE (IntelliJ IDEA, Eclipse, VS Code), amely támogatja a JDK 8+ verziót.  
- **How long does the implementation take?** Körülbelül 10‑15 perc a kód másolásához és futtatásához.

## What is a “Test Project” in Aspose.Tasks?
A **testprojekt** egy könnyű Microsoft Project fájl, amelyet programozottan hozunk létre a funkciók bemutatására vagy ellenőrzésére. Minimális feladat-, erőforrás- és egyéni mezőkészletet tartalmaz, amelyet a valós projektadatok érintése nélkül manipulálhat.

## Why Use Aspose.Tasks to Manipulate Microsoft Project?
- **Full API coverage** – minden Project, Task és Resource tulajdonsághoz hozzáférés.  
- **No Office installation required** – szervereken, CI pipeline-okon és Docker konténerekben is működik.  
- **Cross‑platform** – Windows, Linux és macOS rendszereken fut ugyanazzal a Java kóddal.  
- **Robust formula engine** – dátumok, időtartamok és egyéni mezők közvetlen számítása a projektfájlban.

## Prerequisites
Mielőtt elkezdené, győződjön meg róla, hogy a következők rendelkezésre állnak:

- **Java Development Kit (JDK) 8+** – letölthető az Oracle weboldaláról vagy az OpenJDK‑ból.  
- **Aspose.Tasks for Java** – a legújabb JAR letölthető a [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) oldalról, és hozzáadható a projekt classpath‑éhez vagy Maven/Gradle függőségekhez.

## Import Packages
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Step‑by‑Step Guide

### Step 1: Create a Test Project with a Field
Kezdjük a **tesztprojekt** létrehozásával és egy egyéni mező hozzáadásával, amely később a képlet eredményét tárolja.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` egy segédmetódus, amely egy minimális ütemtervet épít fel, és regisztrál egy kiterjesztett attribútumot a képlet hozzárendeléséhez.

### Step 2: Define an Extended Attribute (Add Custom Field)
Ezután **definiáljuk a kiterjesztett attribútumot** – lényegében az egyéni mezőt – és adunk neki egy barátságos alias‑t. Itt történik a **custom field** logika hozzáadása.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** teszi a mezőt olvashatóvá a Projectben.  
- **Formula** kiszámítja a napok számát a feladat *Finish* dátuma és a *Deadline* között.

### Step 3: Set Deadline for a Task (Add Deadline Task & Set Task Deadline)
Most **határidő feladat** adatokat adunk hozzá a *Deadline* tulajdonság beállításával egy adott feladatra.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- A `Calendar` példány pontosan meghatározza a határidő időpontját.  
- `set(Tsk.DEADLINE, …)` **sets task deadline** a kiválasztott feladatra.

### Step 4: Save the Project (Manipulate Microsoft Project File)
Végül **manipuláljuk a Microsoft Project** fájlt a változások MPP fájlba mentésével.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Megnyithatja a `SaveFile.mpp` fájlt a Microsoft Projectben, hogy lássa az egyéni mezőt, a képlet eredményét és a határidőt a menetrendben.

## Common Issues and Solutions
| Probléma | Megoldás |
|----------|----------|
| **Formula not evaluating** | Győződjön meg arról, hogy az attribútum `Formula` karakterlánca a helyes mezőneveket használja (pl. `[Deadline]`, `[Finish]`). |
| **Task not found** | Ellenőrizze, hogy a feladat ID (`1` a példában) létezik; a `project.getRootTask().getChildren().size()` segítségével hibakereshet. |
| **License exception** | Alkalmazzon érvényes Aspose.Tasks licencet az API‑metódusok meghívása előtt (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Igen, az Aspose.Tasks API‑kat biztosít .NET, Java és egyéb platformok számára, így **manipulálhatja a Microsoft Project** fájlokat a választott nyelven.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Természetesen. Töltsön le egy teljes funkcionalitású próbaverziót a [Aspose.Tasks download page](https://releases.aspose.com/) oldalról.

**Q: Where can I find detailed documentation for Aspose.Tasks?**  
A: A hivatalos dokumentáció a [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/) oldalon érhető el.

**Q: How can I get support for Aspose.Tasks?**  
A: Látogassa meg az [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) oldalt, ahol kérdéseket tehet fel és tapasztalatokat oszthat meg a közösséggel.

**Q: Do I need a temporary license for evaluation?**  
A: Ideiglenes licenc áll rendelkezésre rövid távú teszteléshez; igényelheti [itt](https://purchase.aspose.com/temporary-license/).

---

**Legutóbb frissítve:** 2025-12-07  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12 (a legújabb a kiadás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}