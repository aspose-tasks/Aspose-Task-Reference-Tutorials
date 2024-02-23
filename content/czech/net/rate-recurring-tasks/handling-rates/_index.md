---
title: Manipulace s cenami MS Project pomocí Aspose.Tasks pro .NET
linktitle: Manipulační sazby v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Master správu MS Project Sazby s lehkostí pomocí Aspose.Tasks pro. NET. Efektivně automatizujte úkoly pro hladší projektové pracovní postupy.
type: docs
weight: 10
url: /cs/net/rate-recurring-tasks/handling-rates/
---
## Úvod
Vítejte v našem tutoriálu o manipulaci s cenami MS Project pomocí Aspose.Tasks pro .NET! V této příručce vás provedeme procesem krok za krokem a zajistíme, že budete moci efektivně spravovat sazby ve svých dokumentech MS Project. Aspose.Tasks for .NET poskytuje výkonné funkce pro programovou manipulaci se soubory MS Project, což vám umožňuje bez námahy zjednodušit úkoly řízení projektů.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1. Nainstalované Visual Studio: Ujistěte se, že máte v systému nainstalované Visual Studio.
2.  Knihovna Aspose.Tasks for .NET: Stáhněte a nainstalujte knihovnu Aspose.Tasks for .NET. Odkaz ke stažení najdete[tady](https://releases.aspose.com/tasks/net/).
3. Základní porozumění C#: Seznamte se se základy programovacího jazyka C#.
## Importovat jmenné prostory
Nejprve musíte do svého projektu C# importovat potřebné jmenné prostory. Tyto jmenné prostory budou poskytovat přístup ke třídám a metodám potřebným pro zpracování sazeb MS Project.
## Krok 1: Import jmenného prostoru Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;

```
Nyní si uvedený příklad rozdělíme do několika kroků a každý krok důkladně pochopíme.
## Krok 1: Načtěte soubor projektu
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 V tomto kroku načítáme existující soubor MS Project s názvem "Project1.mpp" pomocí`Project` třídy poskytuje Aspose.Tasks.
## Krok 2: Přidejte zdroj a nastavte práci
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Zde přidáme do projektu nový zdroj s názvem „Resource 1“ a nastavíme jeho typ jako „Work“. Definujeme také dobu trvání práce pro tento zdroj.
## Krok 3: Nastavte standardní sazbu
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
V tomto kroku nastavíme standardní sazbu za zdroj na 20 $ za hodinu.
## Krok 4: Definujte období sazby
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Zde definujeme období sazby pro zdroj. Sazba 1 je stanovena od 1. ledna 2019 do 11. listopadu 2019, přičemž jsou specifikovány standardní a přesčasové sazby.
## Krok 5: Přidejte další období sazby
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
V tomto posledním kroku přidáme další období sazby od 12. listopadu 2019 do 31. prosince 2019 s jinou standardní sazbou a definovanou cenou za použití.
Gratulujeme! Úspěšně jste zvládli sazby MS Project pomocí Aspose.Tasks pro .NET.
## Závěr
Správa sazeb MS Project pomocí programu může výrazně zlepšit pracovní tok řízení projektů. S Aspose.Tasks for .NET máte možnost efektivně automatizovat úlohy zpracování sazeb, čímž šetříte čas a zdroje.
## FAQ
### Otázka: Dokáže Aspose.Tasks zvládnout složité projektové struktury?
Odpověď: Ano, Aspose.Tasks poskytuje robustní funkce pro snadné zpracování složitých projektových struktur.
### Otázka: Je Aspose.Tasks kompatibilní se všemi verzemi souborů MS Project?
Odpověď: Aspose.Tasks podporuje různé verze souborů MS Project a zajišťuje kompatibilitu napříč různými platformami.
### Otázka: Mohu upravit stávající sazby v souboru MS Project pomocí Aspose.Tasks?
A: Rozhodně! Aspose.Tasks vám umožňuje upravovat stávající sazby, přidávat nové sazby a dynamicky je spravovat.
### Otázka: Nabízí Aspose.Tasks podporu pro vlastní výpočty sazeb?
Odpověď: Ano, můžete implementovat vlastní výpočty sazeb pomocí Aspose.Tasks, abyste splnili specifické požadavky projektu.
### Otázka: Je pro uživatele Aspose.Tasks k dispozici komunitní fórum nebo podpora?
 Odpověď: Ano, můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)vyhledat pomoc a komunikovat s ostatními uživateli.