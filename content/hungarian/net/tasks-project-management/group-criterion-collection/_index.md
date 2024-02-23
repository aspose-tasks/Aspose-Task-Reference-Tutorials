---
title: Kezelje az MS Project Group kritériumait az Aspose.Tasks segítségével
linktitle: Csoportkritérium-gyűjtemény kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti a Group Criterion MS Project gyűjteményét az Aspose.Tasks for .NET használatával. Lépésről lépésre útmutató fejlesztőknek.
type: docs
weight: 28
url: /hu/net/tasks-project-management/group-criterion-collection/
---
## Bevezetés
Az Aspose.Tasks for .NET egy hatékony API, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak Microsoft Project fájlokkal. Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet kezelni a Group Criterion gyűjteményt az MS Projectben az Aspose.Tasks segítségével.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:

1.  Aspose.Tasks for .NET: Győződjön meg arról, hogy az Aspose.Tasks könyvtár telepítve van a .NET projektben. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).

2. Microsoft Project File: Készítsen egy Microsoft Project fájlt (MPP) a használatra.

## Névterek importálása

Először is importálnia kell a szükséges névtereket a C# kódjába. Ez a lépés kulcsfontosságú az Aspose.Tasks által biztosított funkciók eléréséhez.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## 1. lépés: Töltse be a projektfájlt

 Inicializálás a`Project` objektumot az MPP fájl betöltésével. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## 2. lépés: Hozzáférés a csoportfeltételekhez

Keresse ki a csoportot a projektből, és érje el a kritériumait.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## 3. lépés: Ismétlés a csoportkritériumok felett

Lapozzon át a csoport minden feltételén, és jelenítse meg a tulajdonságait.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## 4. lépés: Csoportkritériumok törlése

Törölje a meglévő csoportfeltételeket, ha az nem csak olvasható.

```csharp
group.GroupCriteria.Clear();
```

## 5. lépés: Új kritériumok hozzáadása

Hozzon létre egy új csoportfeltételt, és adja hozzá a csoporthoz.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## 6. lépés: Másolja a kritériumokat egy másik csoportba

Másolja át a kritériumokat egyik csoportból a másikba.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan kezelheti a Group Criterion MS Project gyűjteményt az Aspose.Tasks for .NET használatával. Az alábbi lépések követésével hatékonyan módosíthatja a csoportfeltételeket a Microsoft Project fájljaiban programozottan.

## GYIK

### 1. kérdés: Az Aspose.Tasks kompatibilis a Microsoft Project összes verziójával?

V: Igen, az Aspose.Tasks támogatja a Microsoft Project különféle verziójú fájljait, beleértve a 2003-as, 2007-es, 2010-es, 2013-as és 2016-os verziókat.

### 2. kérdés: Alkalmazhatok több feltételt egyetlen csoportra?

V: Természetesen több feltételt is hozzáadhat egy csoporthoz úgy, hogy mindegyiket ismételgeti, és ennek megfelelően adja hozzá őket.

### 3. kérdés: Elérhető az Aspose.Tasks próbaverziója?

 V: Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját a webhelyről[itt](https://releases.aspose.com/).

### 4. kérdés: Hol találom az Aspose.Tasks dokumentációját?

 V: Tekintse meg a dokumentációt[itt](https://reference.aspose.com/tasks/net/).

### 5. kérdés: Hogyan kaphatok támogatást, ha bármilyen problémába ütközöm?

 V: Ha bármilyen kérdése van, vagy bármilyen problémája van, kérjen támogatást az Aspose.Tasks fórumon.[itt](https://forum.aspose.com/c/tasks/15).