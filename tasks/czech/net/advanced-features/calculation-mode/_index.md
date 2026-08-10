---
date: 2026-03-24
description: Naučte se, jak nastavit režim výpočtu v Aspose.Tasks pro .NET, zahrnující
  automatický, manuální režim výpočtu a režim žádný pro správu závislostí úkolů.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Jak nastavit režim výpočtu v Aspose.Tasks pro .NET
url: /cs/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit režim výpočtu v Aspose.Tasks pro .NET

## Úvod

Aspose.Tasks pro .NET je výkonná API, která vám umožňuje programově pracovat se soubory Microsoft Project. Jedním z nejdůležitějších nastavení, na které narazíte, je **režim výpočtu**, který řídí, jak jsou aktualizovány data úkolů a harmonogramy projektu. V tomto tutoriálu se naučíte **jak nastavit výpočet**, prozkoumáte **automatický režim výpočtu**, **manuální režim výpočtu** a **režim žádného výpočtu** a uvidíte, jak tyto možnosti ovlivňují **správu závislostí úkolů**, **vytvoření data zahájení projektu** a **propojení vztahů ukončení‑na‑začátek úkolů**.

## Rychlé odpovědi
- **Co je režim výpočtu?** Určuje, zda jsou data úkolů přepočítávána automaticky, manuálně nebo vůbec.  
- **Proč používat manuální režim výpočtu?** Pro získání úplné kontroly nad tím, kdy se harmonogram obnoví, což je užitečné při hromadných aktualizacích.  
- **Který režim je výchozí?** Automatický režim výpočtu, který aktualizuje data okamžitě po změnách.  
- **Mohu režim změnit během běhu aplikace?** Ano — stačí nastavit vlastnost `CalculationMode` na objektu `Project`.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována platná licence Aspose.Tasks.

## Co je “jak nastavit výpočet” v Aspose.Tasks?
Nastavení režimu výpočtu je tak jednoduché, jako přiřadit hodnotu výčtu (`enum`) k vlastnosti `Project.CalculationMode`. Výčet poskytuje tři možnosti: `Automatic`, `Manual` a `None`. Volba správného režimu závisí na vašem pracovním postupu — zda chcete okamžité aktualizace, dávkové zpracování nebo úplnou kontrolu.

## Požadavky

1. **Visual Studio** — jakákoli recentní verze (2019, 2022 nebo novější).  
2. **Aspose.Tasks pro .NET** — stáhněte a nainstalujte knihovnu z [zde](https://releases.aspose.com/tasks/net/).  
3. **Základní znalost C#** — měli byste být schopni vytvářet konzolové aplikace a používat balíčky NuGet.

## Importovat jmenné prostory

Než začneme pracovat s Aspose.Tasks pro .NET, naimportujme potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;
```

## Jak nastavit režim výpočtu

Níže najdete krok‑za‑krokem příklady pro každý režim výpočtu. Kódové bloky zůstávají nezměněny oproti originálnímu tutoriálu; doprovodná vysvětlení byla rozšířena pro větší přehlednost.

### Použití automatického režimu výpočtu

Automatický režim přepočítává data okamžitě, kdykoli upravíte úkoly nebo odkazy.

#### Krok 1: Vytvořit novou instanci Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Krok 2: Nastavit datum zahájení projektu a přidat úkoly

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Krok 3: Propojit úkoly (ukončení‑na‑začátek)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Krok 4: Ověřit přepočítaná data

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Použití manuálního režimu výpočtu

Manuální režim vypíná automatické aktualizace a dává vám možnost provést dávkové změny před vynucením přepočtu.

#### Krok 1: Vytvořit novou instanci Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Krok 2: Nastavit datum zahájení projektu a přidat úkoly

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Krok 3: Ověřit vlastnosti úkolu

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Krok 4: Propojit úkoly a ověřit data (žádná automatická přepočet)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Použití režimu žádného výpočtu

Režim None vypíná všechny interní výpočty. Použijte jej, když potřebujete pouze číst nebo exportovat data bez jakýchkoli změn harmonogramu.

#### Krok 1: Vytvořit novou instanci Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Krok 2: Přidat nový úkol

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Krok 3: Ověřit vlastnosti úkolu (žádné automatické ID)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Časté problémy a řešení

| Problém | Proč se to děje | Oprava |
|---------|----------------|--------|
| Data se neaktualizují po propojení úkolů | Projekt je v režimu **Manual** nebo **None** | Nastavte `project.CalculationMode = CalculationMode.Automatic` nebo zavolejte `project.Calculate()` ručně |
| ID úkolů zůstávají na 0 | Použití režimu **None** zabraňuje generování ID | Přepněte do režimu **Automatic** nebo **Manual** a poté přepočítejte |
| Propojení selže s `ArgumentException` | Datum zahájení předchůdce je pozdější než následníka při použití režimu **Manual** bez přepočtu | Zajistěte správná data zahájení nebo přepočítejte po přidání odkazů |

## Často kladené otázky

**Q1: Mohu během běhu měnit režim výpočtu?**  
A1: Ano, můžete kdykoli v kódu změnit vlastnost `CalculationMode` a poté zavolat `project.Calculate()`, pokud potřebujete okamžitou aktualizaci.

**Q2: Podporuje Aspose.Tasks i jiné formáty souborů pro řízení projektů kromě Microsoft Project?**  
A2: Aspose.Tasks se primárně zaměřuje na formáty Microsoft Project, ale také podporuje Primavera P6 XML, Primavera DB a Asta Powerproject XML.

**Q3: Je Aspose.Tasks vhodný jak pro malé, tak pro enterprise‑úrovňové projekty?**  
A3: Rozhodně. API škáluje od jednoduchých seznamů úkolů po složité, vícefázové enterprise harmonogramy.

**Q4: Mohu integrovat Aspose.Tasks s jinými .NET knihovnami a frameworky?**  
A4: Ano, můžete kombinovat Aspose.Tasks s ASP.NET, WPF, Xamarin nebo jakoukoli jinou .NET technologií pro tvorbu bohatých řešení pro řízení projektů.

**Q5: Existuje komunitní fórum nebo podpora pro uživatele Aspose.Tasks?**  
A5: Ano, můžete navštívit [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) pro komunitní podporu a diskuze.

---

**Poslední aktualizace:** 2026-03-24  
**Testováno s:** Aspose.Tasks 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}