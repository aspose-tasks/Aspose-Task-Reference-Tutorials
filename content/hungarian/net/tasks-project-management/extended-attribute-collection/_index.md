---
title: MS Project Attributes Collection kezelése az Aspose.Tasks alkalmazásban
linktitle: A kiterjesztett attribútumgyűjtemény kezelése az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti hatékonyan az MS Project kiterjesztett attribútumait az Aspose.Tasks for .NET használatával. Zökkenőmentesen kezelheti a feladatattribútumokat lépésről lépésre.
type: docs
weight: 12
url: /hu/net/tasks-project-management/extended-attribute-collection/
---
## Bevezetés
Hatékonyan szeretné kezelni az MS Project kiterjesztett attribútumait az Aspose.Tasks for .NET használatával? Ebben az oktatóanyagban lépésről lépésre végigvezetjük a folyamaton. Merüljünk el!
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
1. Visual Studio: Telepítse a Visual Studio-t a rendszerére.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET webhelyet innen[itt](https://releases.aspose.com/tasks/net/).
3. C# alapismeretek: Ismerkedjen meg a C# programozási nyelv alapjaival.

## Névterek importálása
Kezdje a szükséges névterek importálásával a projektbe:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## 1. lépés: Töltse be a projektfájlt
Először töltse be az MS Project fájlt a következő kódrészlet segítségével:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## 2. lépés: A feladat és a kiterjesztett attribútumok elérése
Egy adott feladat elérése és kiterjesztett attribútumai:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## 3. lépés: Törölje a kiterjesztett attribútumokat
Szükség esetén törölje a meglévő kiterjesztett attribútumokat:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## 4. lépés: Hozzon létre kiterjesztett attribútum-definíciókat
Hozzon létre definíciókat az új kiterjesztett attribútumokhoz:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## 5. lépés: Ismételje meg a feladat kiterjesztett attribútumait
Ismétlés a feladat kiterjesztett attribútumain keresztül:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## 6. lépés: Adjon hozzá kiterjesztett attribútumokat
Új kiterjesztett attribútumok hozzáadása a feladathoz:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## 7. lépés: A kiterjesztett attribútumok használata
Szükség szerint hajtson végre műveleteket a kiterjesztett attribútumokon.
## 8. lépés: Távolítsa el a kiterjesztett attribútumokat
Távolítsa el a kiterjesztett attribútumokat index alapján vagy feltételesen:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## 9. lépés: Attribútumok másolása egy másik feladathoz
Attribútumok másolása egy másik feladathoz ugyanazon vagy különböző projekten belül:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Következtetés
Az MS Project kiterjesztett attribútumgyűjteményeinek kezelése zökkenőmentessé válik az Aspose.Tasks for .NET segítségével. Az oktatóanyagban ismertetett lépések követésével hatékonyan kezelheti a kiterjesztett attribútumokat, javítva ezzel a projektkezelési képességeit.
## GYIK
### K: Manipulálhatom a kiterjesztett attribútumokat több projektben?
V: Igen, az Aspose.Tasks for .NET használatával kiterjesztett attribútumokat másolhat a feladatok között a különböző projektekben.
### K: Vannak korlátozások a feladatonkénti kiterjesztett attribútumok számára?
V: Az Aspose.Tasks for .NET nem szab eredendő korlátozásokat a feladatonkénti kiterjesztett attribútumok számára.
### K: Létrehozhatok egyéni kiterjesztett attribútummezőket?
V: Abszolút! Az Aspose.Tasks for .NET lehetővé teszi egyéni kiterjesztett attribútummezők meghatározását a projekt követelményeihez igazítva.
### K: Az Aspose.Tasks for .NET támogatja a különféle verziójú MS Project fájlok olvasását és írását?
V: Igen, az Aspose.Tasks for .NET támogatja az MS Project fájlformátumokat a különböző verziókban.
### K: Elérhető az Aspose.Tasks próbaverziója .NET-hez?
 V: Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).