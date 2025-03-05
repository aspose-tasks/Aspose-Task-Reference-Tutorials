---
title: Master MS Project Sazby s Aspose.Tasks
linktitle: Sběr sazeb v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak spravovat sazby v souborech MS Project pomocí Aspose.Tasks pro .NET. Návod krok za krokem pro efektivní správu zdrojů.
type: docs
weight: 11
url: /cs/net/rate-recurring-tasks/rate-collection/
---
## Úvod
Vítejte v našem tutoriálu o správě sazeb v MS Project pomocí Aspose.Tasks pro .NET! V této příručce vás provedeme procesem práce se sazbami ve vašich souborech MS Project pomocí Aspose.Tasks. Ať už jste zkušený vývojář nebo s vývojem .NET teprve začínáte, tento tutoriál vám poskytne podrobné pokyny, jak efektivně zacházet s cenami ve vašich projektech.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:
### 1. Visual Studio nainstalováno
Ujistěte se, že máte v systému nainstalované Visual Studio. Můžete si jej stáhnout z webu, pokud jste tak ještě neučinili.
### 2. Aspose.Tasks pro .NET
 Stáhněte a nainstalujte knihovnu Aspose.Tasks for .NET z[webová stránka](https://releases.aspose.com/tasks/net/).
### 3. Základní znalost C# a .NET
Seznamte se s programovacím jazykem C# a základy .NET frameworku, abyste lépe porozuměli příkladům kódu v tomto kurzu.
## Importovat jmenné prostory
Ve svém projektu C# importujte potřebné jmenné prostory pro použití funkcí Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Nyní si každý příklad rozdělíme do několika kroků:
## Krok 1: Načtěte soubor MS Project
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Zde vytvoříme nový`Project` objekt načtením existujícího souboru MS Project.
## Krok 2: Přidejte zdroj a nastavte práci a sazby
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Do projektu přidáme nový zdroj, nastavíme jeho typ jako práci, množství práce a standardní sazbu.
## Krok 3: Přidejte sazby do zdroje
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Ke zdroji přidáváme sazby s uvedením data zahájení a ukončení, standardní sazby a formátu sazby.
## Krok 4: Tisk informací o sazbách
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
Tento krok vytiskne informace o sazbách spojených se zdrojem.
## Krok 5: Aktualizujte sazbu
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Aktualizujeme datum ukončení konkrétní sazby.
## Krok 6: Odstraňte sazby
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Tento krok odstraní všechny sazby určitého typu.
## Krok 7: Opakujte zbývající sazby
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Nakonec iterujeme přes zbývající sazby po odstranění.
## Závěr
Na závěr vám tento tutoriál poskytl komplexního průvodce správou sazeb v souborech MS Project pomocí Aspose.Tasks for .NET. Dodržováním podrobných pokynů uvedených v tomto kurzu můžete efektivně spravovat sazby ve svých projektech a zajistit tak přesnou správu zdrojů.
## FAQ
### Otázka: Mohu používat Aspose.Tasks pro .NET s jiným softwarem pro správu projektů?
Odpověď: Ano, Aspose.Tasks for .NET podporuje integraci s různými software pro řízení projektů, včetně MS Project, Primavera a dalších.
### Otázka: Je Aspose.Tasks for .NET kompatibilní s různými verzemi souborů MS Project?
Odpověď: Aspose.Tasks for .NET samozřejmě podporuje práci se soubory MS Project různých verzí, čímž zajišťuje flexibilitu a kompatibilitu.
### Otázka: Nabízí Aspose.Tasks pro .NET dokumentaci a podporu?
 Odpověď: Ano, komplexní dokumentaci a přístup k fórům podpory najdete na Aspose.Tasks[webová stránka](https://reference.aspose.com/tasks/net/).
### Otázka: Mohu vyzkoušet Aspose.Tasks pro .NET před nákupem?
Odpověď: Ano, můžete využít bezplatnou zkušební verzi Aspose.Tasks for .NET a vyhodnotit její funkce a kompatibilitu s vašimi požadavky.
### Otázka: Jak si mohu zakoupit licenci pro Aspose.Tasks pro .NET?
 A: Můžete si zakoupit licenci pro Aspose.Tasks pro .NET z[webová stránka](https://purchase.aspose.com/temporary-license/)která poskytuje flexibilní možnosti licencování podle vašich potřeb.