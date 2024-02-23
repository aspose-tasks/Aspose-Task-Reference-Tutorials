---
title: Master Timephased Data Handling s Aspose.Tasks pro .NET
linktitle: Zpracování časově uspořádaných dat v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Prozkoumejte Aspose.Tasks for .NET, abyste mohli bez námahy zpracovávat časově uspořádaná data, vylepšit plánování projektů a optimalizovat správu zdrojů. #Zadejte #Úkoly #MS Project
type: docs
weight: 14
url: /cs/net/text-view-configuration/timephased-data/
---
## Úvod
Ve světě projektového řízení je efektivní nakládání s časově uspořádanými daty zásadní pro alokaci zdrojů, odhad nákladů a celkové plánování projektu. Aspose.Tasks for .NET poskytuje výkonné řešení pro bezproblémovou práci s vlastními časově uspořádanými daty. Tento tutoriál vás provede procesem zpracování časově uspořádaných dat pomocí Aspose.Tasks, což vám umožní optimalizovat správu zdrojů ve vašich projektech.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Základní porozumění konceptům projektového řízení.
-  Nainstalované Aspose.Tasks pro .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/net/).
- Editor kódu, jako je Visual Studio, pro implementaci poskytnutých příkladů.
## Importovat jmenné prostory
Ve svém projektu .NET se ujistěte, že jste importovali potřebné jmenné prostory, abyste mohli využívat funkce Aspose.Tasks. Na začátek souboru kódu přidejte následující řádky:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Nyní si uvedený příklad rozdělíme do několika kroků, které vás provedou zpracováním časově uspořádaných dat pomocí Aspose.Tasks:
## Krok 1: Nastavte projekt
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Zde inicializujeme nový projekt a nastavíme jeho režim výpočtu.
## Krok 2: Definujte zdroje a úkoly
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Vytvořte pracovní a nákladové zdroje a také úkol pro simulaci struktury projektu.
## Krok 3: Přiřaďte zdroje k úkolu
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Přidělte úkolu práci a nákladové zdroje.
## Krok 4: Přidejte vlastní časově uspořádaná data
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Podobné kroky pro costAssignment
costAssignment.TimephasedData.Clear();
```
Přidejte vlastní časově uspořádaná data pro přiřazení práce i nákladů.
## Krok 5: Zobrazte časově uspořádaná data
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Zobrazte relevantní informace o každém časovém vstupu dat
    }
}
```
Nakonec zobrazte časově uspořádaná data pro každé přiřazení.
#
## Závěr
Efektivní zpracování časově uspořádaných dat v Aspose.Tasks otevírá nové možnosti pro podrobné plánování projektů a řízení zdrojů. Podle tohoto podrobného průvodce jste se naučili, jak manipulovat s časově uspořádanými daty tak, aby vyhovovaly specifickým potřebám vašich projektů.
## Často kladené otázky
### Mohu používat Aspose.Tasks for .NET s jinými nástroji pro řízení projektů?
Aspose.Tasks je primárně určen pro vývoj .NET. Jeho funkcionality však mohou doplňovat různé nástroje projektového řízení.
### Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro .NET?
 Ano, můžete vyzkoušet bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Jak mohu získat podporu pro Aspose.Tasks pro .NET?
 navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)za podporu komunity.
### Co je to dočasná licence a jak ji mohu získat?
 Přečtěte si o dočasných licencích[tady](https://purchase.aspose.com/temporary-license/).
### Kde najdu dokumentaci k Aspose.Tasks pro .NET?
 Viz komplexní[dokumentace](https://reference.aspose.com/tasks/net/) pro podrobné informace.