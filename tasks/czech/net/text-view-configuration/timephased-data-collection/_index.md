---
title: Zvládnutí časově uspořádaného sběru dat v Aspose.Tasks
linktitle: Sběr časově uspořádaných dat v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Prozkoumejte časově uspořádaný sběr dat v Aspose.Tasks pro .NET. Podrobný průvodce, často kladené dotazy a další. Vylepšete své schopnosti projektového řízení ještě dnes!
weight: 15
url: /cs/net/text-view-configuration/timephased-data-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zvládnutí časově uspořádaného sběru dat v Aspose.Tasks

## Úvod
Chcete využít sílu časově uspořádaných dat ve svých aplikacích .NET pomocí Aspose.Tasks? Už nehledejte! Tento komplexní průvodce vás provede procesem shromažďování časově uspořádaných dat pomocí Aspose.Tasks pro .NET a zajistí, že z této výkonné knihovny vytěžíte maximum.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1.  Aspose.Tasks for .NET Library: Stáhněte a nainstalujte knihovnu z[Aspose.Tasks .NET dokumentace](https://reference.aspose.com/tasks/net/).
2. Vývojové prostředí .NET: Ujistěte se, že máte nastavené funkční vývojové prostředí .NET.
3. Váš adresář dokumentů: Nahraďte zástupný symbol "Your Document Directory" ve fragmentech kódu cestou k adresáři vašeho dokumentu.
## Importovat jmenné prostory
Ve svém projektu .NET začněte importem potřebných jmenných prostorů, abyste mohli využít funkce Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Vytvořte projekt a zdroje
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Přidejte úkoly do projektu
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Nastavit vlastnosti úkolu...
var task2 = project.RootTask.Children.Add("Task 2");
// Nastavit vlastnosti úkolu 2...
```
## 3. Přiřaďte prostředky k úkolům
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Nastavit vlastnosti přiřazení...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
//Nastavit vlastnosti přiřazení2...
```
## 4. Práce s časově uspořádanými daty
```csharp
// Nastavte konturovaný pracovní obrys
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Zkontrolujte, zda je časově řízené shromažďování dat pouze pro čtení
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Vymazat vygenerovaná časově uspořádaná data
assignment.TimephasedData.Clear();
// Vytvářejte a přidávejte časově uspořádaná data
var td = new TimephasedData
{
    // Nastavit vlastnosti časově uspořádaných dat...
};
assignment.TimephasedData.Add(td);
// Přidejte seznam časově uspořádaných dat
var list = new List<TimephasedData>();
// Přidat do seznamu více časově uspořádaných datových položek...
assignment.TimephasedData.AddRange(list);
// Filtrujte časově uspořádaná data podle typu a období
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Tisknout filtrovaná časově uspořádaná data...
```
## 5. Manipulujte s časově uspořádanými daty
```csharp
// Přidejte nesprávnou časově uspořádanou datovou položku a poté ji odstraňte
var td4 = new TimephasedData
{
    // Nastavit špatné vlastnosti časově uspořádaných dat...
};
assignment.TimephasedData.Add(td4);
// Odstraňte nesprávnou časově uspořádanou datovou položku
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Opakujte všechny časově uspořádané položky
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Vytisknout podrobnosti o časově uspořádané položce...
}
```
## 6. Zkopírujte časově uspořádaná data do jiného přiřazení
```csharp
// Zkopírujte časově uspořádaná data do jiného úkolu
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Převeďte kolekci na prostý seznam
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Odeberte časově uspořádané datové položky jednu po druhé
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Závěr
Na závěr, tento tutoriál poskytuje podrobný návod na shromažďování časově uspořádaných dat pomocí Aspose.Tasks pro .NET. Dodržováním těchto kroků můžete tuto funkci bez problémů integrovat do svých projektů a umožnit tak efektivní sledování času a správu zdrojů.
## Často kladené otázky
### Mohu používat Aspose.Tasks for .NET s jinými nástroji pro řízení projektů?
Ano, Aspose.Tasks for .NET je navržen pro práci s oblíbenými nástroji pro řízení projektů a podporuje různé formáty souborů.
### Existuje nějaký limit na počet zdrojů a úkolů, které mohu spravovat pomocí Aspose.Tasks?
Aspose.Tasks zpracovává projekty různých velikostí a neexistuje žádný přísný limit na počet zdrojů a úkolů.
### Jak mohu získat podporu pro jakékoli problémy nebo dotazy související s Aspose.Tasks pro .NET?
 Pro podporu navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) spojit se s komunitou a získat pomoc.
### Mohu vyzkoušet Aspose.Tasks pro .NET před jeho zakoupením?
 Ano, funkce Aspose.Tasks pro .NET můžete prozkoumat přístupem na[zkušební verze zdarma](https://releases.aspose.com/).
### Kde si mohu zakoupit licenci pro Aspose.Tasks pro .NET?
Můžete si zakoupit licenci pro Aspose.Tasks pro .NET[tady](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
