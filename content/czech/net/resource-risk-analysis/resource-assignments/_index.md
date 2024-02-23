---
title: Zpracování přiřazení zdrojů MS Project v Aspose.Tasks
linktitle: Zpracování přiřazení zdrojů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně zacházet s přiřazením zdrojů MS Project pomocí Aspose.Tasks for .NET. Tento souhrn poskytuje vývojářům podrobné pokyny.
type: docs
weight: 11
url: /cs/net/resource-risk-analysis/resource-assignments/
---
## Úvod
V tomto tutoriálu se ponoříme do toho, jak efektivně zpracovávat přiřazení zdrojů aplikace Microsoft Project pomocí Aspose.Tasks for .NET. Aspose.Tasks je výkonné API, které umožňuje vývojářům programově manipulovat se soubory Microsoft Project. Podle těchto kroků se naučíte, jak efektivně spravovat přiřazení prostředků ve vašich aplikacích .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:

## Importovat jmenné prostory
Nejprve musíte importovat potřebné jmenné prostory, abyste mohli využívat funkce Aspose.Tasks ve vašem projektu .NET. To zahrnuje:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
Nyní rozeberme poskytnutý příklad do několika kroků, abychom komplexně pochopili, jak zacházet s přiřazením prostředků MS Project pomocí Aspose.Tasks.
## Krok 1: Nastavte projekt a nastavení kalendáře
Chcete-li začít, vytvořte novou instanci projektu a nastavte nastavení kalendáře projektu:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## Krok 2: Přidejte úkol do projektu
Dále přidejte nový úkol do kořenového úkolu projektu:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## Krok 3: Vytvořte přiřazení zdrojů a vygenerujte časově uspořádaná data
Nyní vytvořte nové přiřazení zdrojů pro úkol a vygenerujte časově uspořádaná data:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## Krok 4: Rozdělte úkol
Rozdělte úkol na více částí zadáním data zahájení a ukončení:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## Krok 5: Nastavte pracovní obrys
Nastavte typ pracovního obrysu pro přiřazení:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## Krok 6: Uložte projekt
Nakonec uložte soubor projektu s provedenými změnami:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Závěr
Závěrem lze říci, že zpracování přiřazení zdrojů Microsoft Project pomocí Aspose.Tasks for .NET je jednoduchý proces. Podle kroků uvedených v tomto kurzu můžete efektivně spravovat přiřazení prostředků ve vašich aplikacích .NET.
## FAQ
### Dokáže Aspose.Tasks zvládnout složité projektové struktury?
Ano, Aspose.Tasks poskytuje komplexní funkce pro efektivní zpracování složitých projektových struktur.
### Je Aspose.Tasks kompatibilní s různými verzemi Microsoft Project?
Ano, Aspose.Tasks podporuje různé verze Microsoft Project a zajišťuje kompatibilitu v různých prostředích.
### Mohu přizpůsobit přiřazení zdrojů na základě konkrétních požadavků?
Aspose.Tasks rozhodně nabízí rozsáhlé možnosti přizpůsobení pro přiřazení zdrojů, aby vyhovovaly specifickým potřebám projektu.
### Podporuje Aspose.Tasks export dat projektu do jiných formátů?
Ano, Aspose.Tasks umožňuje export projektových dat do různých formátů, jako jsou mimo jiné XML, PDF a HTML.
### Je pro uživatele Aspose.Tasks k dispozici technická podpora?
Ano, Aspose poskytuje specializovanou technickou podporu prostřednictvím svého fóra a dalších kanálů, aby pomohla uživatelům s jakýmikoli dotazy nebo problémy.