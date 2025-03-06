---
title: Mester kiterjesztett attribútum-definíciók MS Project az Aspose.Tasks-ban
linktitle: Kiterjesztett attribútum-definíciók gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti a kiterjesztett attribútumdefiníciókat a Microsoft Projectben az Aspose.Tasks for .NET használatával. Könnyedén testreszabhatja és javíthatja projektadatait.
weight: 14
url: /hu/net/tasks-project-management/extended-attribute-definition-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mester kiterjesztett attribútum-definíciók MS Project az Aspose.Tasks-ban

## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan dolgozhatunk kiterjesztett attribútum-definíciókkal a Microsoft Projectben az Aspose.Tasks for .NET használatával. A kiterjesztett attribútumok rugalmas módot kínálnak a projektadatok testreszabására és javítására, lehetővé téve a felhasználók számára, hogy az alapértelmezésben biztosított szabványos mezőkön túl további mezőket is hozzáadjanak. Az Aspose.Tasks segítségével könnyedén kezelheti ezeket a kiterjesztett attribútumokat, hogy testre szabhassa projektmenedzsment igényeit.
## Előfeltételek
Mielőtt folytatná, győződjön meg arról, hogy a következő előfeltételek telepítve vannak:
- [.NET Framework](https://dotnet.microsoft.com/download)
-  Aspose.Tasks .NET könyvtárhoz. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).

## Névterek importálása
Először is importálnia kell a szükséges névtereket az Aspose.Tasks osztályok és metódusok eléréséhez a .NET-projektben. Kovesd ezeket a lepeseket:
## 1. lépés: Nyissa meg a .NET-projektet
Nyissa meg .NET-projektjét a kívánt IDE-ben, például a Visual Studio-ban.
## 2. lépés: Adja hozzá az Aspose.Tasks névteret
Adja hozzá a következő sort a kódfájl elejéhez az Aspose.Tasks névtér importálásához:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Most bontsuk le a megadott kódpéldákat több lépésre az átfogó megértés érdekében:
## 1. lépés: Töltse be a projektfájlt
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## 2. lépés: Törölje a meglévő kiterjesztett attribútumdefiníciókat (opcionális)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## 3. lépés: Hozzon létre és adjon hozzá kiterjesztett attribútumdefiníciót egy feladathoz
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## 4. lépés: Ismételje meg a feladat kiterjesztett attribútumait
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## 5. lépés: Hozzon létre és adjon hozzá kiterjesztett attribútumdefiníciót egy erőforráshoz
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## 6. lépés: Szúrjon be egy erőforrás-bővített attribútum-definíciót
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## 7. lépés: Távolítsa el a kiterjesztett attribútumot index szerint
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Következtetés
Ebben az oktatóanyagban a Microsoft Project kiterjesztett attribútumdefinícióival való munka alapjait ismertetjük az Aspose.Tasks for .NET használatával. Ezen lépések követésével hatékonyan kezelheti és testreszabhatja a kiterjesztett attribútumokat a projektmenedzsment követelményeinek megfelelően.
## GYIK
### K: Módosíthatom a meglévő kiterjesztett attribútumdefiníciókat?
V: Igen, igényei szerint módosíthatja a meglévő kiterjesztett attribútumdefiníciókat, vagy újakat hozhat létre.
### K: A Microsoft Project minden verziója támogatja a kiterjesztett attribútumokat?
V: Igen, a Microsoft Project legtöbb verziója támogatja a kiterjesztett attribútumokat, beleértve a legújabbakat is.
### K: Használhatok kiterjesztett attribútumokat egyéni mezők kiszámításához?
V: Természetesen a kiterjesztett attribútumok használhatók egyéni mezők kiszámítására az Ön által meghatározott feltételek alapján.
### K: Az Aspose.Tasks kompatibilis más .NET keretrendszerekkel?
V: Az Aspose.Tasks kompatibilis a különböző .NET-keretrendszerekkel, rugalmasságot és egyszerű integrációt biztosítva.
### K: Hol találok további forrásokat és támogatást az Aspose.Tasks számára?
 V: Meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) támogatásért, és fedezze fel a dokumentációt[itt](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
