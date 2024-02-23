---
title: Konfigurálja az MS Project XLSX beállításait az Aspose.Tasks for .NET-ben
linktitle: Konfigurálja az XLSX-beállításokat az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan konfigurálhatja az MS Project XLSX beállításait az Aspose.Tasks for .NET-ben. Könnyedén testreszabhatja az oszlopokat, a kódolást és még sok mást.
type: docs
weight: 11
url: /hu/net/file-format-options/configuring-xlsx-options/
---
## Bevezetés
A Microsoft Project (MS Project) egy hatékony eszköz a projektmenedzsmenthez, az Aspose.Tasks for .NET pedig zökkenőmentes integrációt biztosít az MS Project fájlokkal való programozott munkavégzéshez. Ebben az oktatóanyagban végigvezetjük az MS Project XLSX beállításainak konfigurálását az Aspose.Tasks for .NET használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
### 1. Aspose.Tasks for .NET telepítve
 Győződjön meg arról, hogy az Aspose.Tasks for .NET telepítve van a fejlesztői környezetében. Ha nem, akkor letöltheti a[Aspose.Tasks for .NET letöltési oldal](https://releases.aspose.com/tasks/net/).
### 2. A C# és a .NET-keretrendszer alapvető ismerete
Ennek az oktatóanyagnak a követéséhez a C# programozási nyelv és a .NET keretrendszer ismerete szükséges.
### 3. Microsoft Project File
Készítsen egy Microsoft Project-fájlt (MPP), amelyet konfigurálni szeretne, és XLSX-fájlként szeretne menteni.

## Névterek importálása
A kezdéshez importálja a szükséges névtereket:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## 1. lépés: Töltse be a projektet
```csharp
var project = new Project("YourProjectFile.mpp");
```
Töltse be a konfigurálni kívánt Microsoft Project fájlt.
## 2. lépés: Adja meg az XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Hozzon létre egy példányt a`XlsxOptions` az XLSX formátumban történő mentés beállításainak konfigurálásához.
## 3. lépés: Adjon hozzá Gantt-diagramoszlopokat
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Adja hozzá a kívánt Gantt-diagram oszlopokat a lehetőségekhez.
## 4. lépés: Erőforrásnézet oszlopok hozzáadása
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Adja meg a kívánt oszlopokat az erőforrásnézethez a lehetőségek között.
## 5. lépés: Hozzárendelés nézet oszlopok hozzáadása
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Adja hozzá a kívánt oszlopokat a hozzárendelési nézethez a beállításokban.
## 6. lépés: Állítsa be a kódolást
```csharp
options.Encoding = Encoding.Unicode;
```
Állítsa be a kimeneti fájl kódolását.
## 7. lépés: Mentse el a projektet XLSX néven
```csharp
project.Save("OutputFile.xlsx", options);
```
Mentse a projektet a konfigurált beállításokkal XLSX-fájlként.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell konfigurálni az MS Project XLSX beállításait az Aspose.Tasks for .NET használatával. Az alábbi lépések követésével testreszabhatja a kimeneti formátumot igényei szerint, növelve ezzel a projektmenedzsment munkafolyamatának rugalmasságát és használhatóságát.
## GYIK

### K: Beállíthatok-e különálló oszlopokat a Gantt-diagram, az erőforrás-nézet és a hozzárendelés nézet számára?

V: Igen, az Aspose.Tasks for .NET segítségével az egyes nézetekhez függetlenül testreszabhatja az oszlopokat.

### K: Elérhető-e próbaverzió az Aspose.Tasks .NET-hez való megvásárlása előtt?

 V: Igen, letölthet egy ingyenes próbaverziót a webhelyről[Aspose.Tasks .NET kiadásokhoz oldal](https://releases.aspose.com/).

### K: Hogyan kaphatok támogatást, ha a megvalósítás során bármilyen problémám vagy kérdéseim vannak?

 V: Meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) segítségért a közösségtől és az Aspose ügyfélszolgálati csapatától.

### K: Létrehozhatok XLSX fájlokat az Aspose.Tasks for .NET segítségével nem Windows platformokon?

V: Az Aspose.Tasks for .NET elsősorban Windows-platformokhoz készült, de megtekintheti más platformok kompatibilitási lehetőségeit is.

### K: Vannak-e ideiglenes licenclehetőségek tesztelési célból?

 V: Igen, ideiglenes engedélyt kaphat a[Az Aspose.Tasks ideiglenes licenc oldala](https://purchase.aspose.com/temporary-license/).