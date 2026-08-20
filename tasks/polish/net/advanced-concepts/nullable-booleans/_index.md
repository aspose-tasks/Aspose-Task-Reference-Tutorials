---
date: 2026-03-14
description: Dowiedz się, jak używać nullable bool w Aspose.Tasks dla .NET, w tym
  konwertować wartości nullable bool oraz ustawiać właściwości nullable bool.
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak używać wartości boolowskich dopuszczających null w Aspose.Tasks
url: /pl/net/advanced-concepts/nullable-booleans/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać nullable Boolean w Aspose.Tasks

W tym samouczku pokażemy **jak używać nullable** Booleanów podczas pracy z API Aspose.Tasks .NET. Nullable Booleany dają trzy możliwe stany — `true`, `false` lub *undefined* — co jest szczególnie przydatne w ustawieniach na poziomie projektu, które mogą nie być wyraźnie określone. Zobaczysz, jak tworzyć, konwertować i **ustawiać nullable Boolean** wartości oraz dlaczego prawidłowe obsługiwanie nullable Booleanów może zapobiec nieoczekiwanemu zachowaniu w aplikacjach planistycznych.

## Szybkie odpowiedzi
- **What is a nullable boolean?** Typ, który może przyjąć `true`, `false` lub być niezdefiniowany.  
- **Why use nullable booleans in Aspose.Tasks?** Pozwalają reprezentować opcjonalne właściwości projektu bez zgadywania wartości domyślnej.  
- **How to convert a nullable boolean to a regular bool?** Użyj konwersji niejawnej lub najpierw sprawdź `IsDefined`.  
- **What is the primary class?** `NullableBool` w przestrzeni nazw `Aspose.Tasks`.  
- **Do I need a license?** Tak, ważna licencja Aspose.Tasks jest wymagana do użytku produkcyjnego.

## Co to jest Nullable Boolean?

Nullable Boolean (`NullableBool`) rozszerza zwykły typ `bool` o flagę *IsDefined*. Gdy `IsDefined` jest `false`, wartość jest uznawana za niezdefiniowaną, co pozwala odróżnić „false” od „not set”.

## Dlaczego obsługiwać Nullable Boolean w ustawieniach projektu?

Wiele opcji projektu — takich jak **ActualsInSync** lub **HonorConstraints** — jest opcjonalnych. Użycie zwykłego `bool` zmusza do wyboru `true` lub `false`, co może nieumyślnie nadpisać intencję użytkownika. Poprzez **obsługę nullable Boolean**, zachowujesz pierwotny stan i unikasz przypadkowych zmian konfiguracji.

## Wymagania wstępne

1. **Visual Studio** (lub dowolne IDE zgodne z .NET).  
2. **Aspose.Tasks for .NET** – pobierz go z [here](https://releases.aspose.com/tasks/net/).

## Importowanie przestrzeni nazw

Najpierw zaimportuj wymagane przestrzenie nazw:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

Teraz przejdźmy przez każdy przykład krok po kroku.

## Praca z `NullableBool`

### Krok 1: Utwórz nową instancję `Project`.

```csharp
var project = new Project();
```

### Krok 2: Zainstaluj obiekt `NullableBool` z określonymi wartościami.

```csharp
var actualsInSync = new NullableBool(false, false);
```

### Krok 3: Sprawdź wartość i status zdefiniowania obiektu `NullableBool`.

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### Krok 4: **Ustaw nullable Boolean** w projekcie.

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### Krok 5: Zainstaluj kolejny obiekt `NullableBool` z pojedynczą wartością.

```csharp
var honorConstraints = new NullableBool(true);
```

### Krok 6: Wyświetl reprezentację tekstową obiektu `NullableBool`.

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### Krok 7: Użyj instancji `NullableBool`, ustawiając ją w projekcie.

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## Porównywanie instancji `NullableBool`

### Krok 1: Zainstaluj dwa obiekty `NullableBool`.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Krok 2: Sprawdź reprezentację tekstową każdego obiektu `NullableBool`.

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### Krok 3: Implicytna konwersja do `bool` i wydrukuj wynik.

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### Krok 4: Porównaj dwa obiekty `NullableBool` pod kątem równości.

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## Pobieranie kodu hash `NullableBool`

### Krok 1: Zainstaluj dwa obiekty `NullableBool`.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Krok 2: Wydrukuj kod hash dla każdego obiektu `NullableBool`.

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## Częste pułapki i wskazówki

- **Never assume a nullable boolean is defined.** Zawsze sprawdzaj `IsDefined` przed użyciem `Value`.  
- **Converting to a regular bool** bez sprawdzenia może rzucić wyjątek, jeśli wartość jest niezdefiniowana. Używaj konwersji niejawnej tylko wtedy, gdy masz pewność, że jest zdefiniowana.  
- **When setting project properties**, użyj metody `Set` z `NullableBool`, aby zachować stan niezdefiniowany, jeśli to konieczne.

## Najczęściej zadawane pytania

**Q: What is a nullable boolean?**  
A: Nullable Boolean może reprezentować `true`, `false` lub stan niezdefiniowany, umożliwiając trzy odrębne wyniki.

**Q: How can I convert a nullable boolean to a regular bool safely?**  
A: Najpierw sprawdź `IsDefined`, potem użyj właściwości `Value` lub polegaj na konwersji niejawnej, gdy masz pewność, że jest zdefiniowany.

**Q: Why should I use nullable booleans instead of plain bools in Aspose.Tasks?**  
A: Pozwalają zachować opcjonalne ustawienia projektu niezmienione, zapobiegając przypadkowym nadpisaniom.

**Q: Can I set a nullable boolean to be undefined?**  
A: Tak — użyj konstruktora, który przyjmuje tylko flagę zdefiniowania, np. `new NullableBool(false, false)`.

**Q: Where can I find further documentation on Aspose.Tasks for .NET?**  
A: Szczegółową dokumentację znajdziesz [here](https://reference.aspose.com/tasks/net/).

---

**Ostatnia aktualizacja:** 2026-03-14  
**Testowano z:** Aspose.Tasks for .NET (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}