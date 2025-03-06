---
title: Wyodrębnij informacje z nagłówka i stopki za pomocą Aspose.Tasks
linktitle: Informacje nagłówka i stopki w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak wyodrębnić informacje nagłówka i stopki z plików MS Project za pomocą Aspose.Tasks dla .NET. Rozwiązanie łatwe, wydajne i przyjazne dla programistów.
weight: 29
url: /pl/net/tasks-project-management/header-footer-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wyodrębnij informacje z nagłówka i stopki za pomocą Aspose.Tasks

## Wstęp
Aspose.Tasks dla .NET to potężna biblioteka, która pozwala programistom z łatwością manipulować plikami Microsoft Project. W tym samouczku nauczymy się pobierać informacje z nagłówka i stopki z plików MS Project za pomocą Aspose.Tasks.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Visual Studio: Zainstaluj Visual Studio w swoim systemie.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość języka C#: Znajomość języka programowania C#.

## Importuj przestrzenie nazw
Najpierw musisz zaimportować niezbędne przestrzenie nazw do projektu C#. Umożliwi to dostęp do klas i metod udostępnianych przez bibliotekę Aspose.Tasks.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Krok 1: Zainicjuj obiekt projektu
 Aby rozpocząć, musisz zainicjować plik a`Project` obiekt poprzez załadowanie istniejącego pliku MS Project.
```csharp
// Ścieżka do katalogu dokumentów.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Krok 2: Pobierz informacje o nagłówku i stopce
 Po załadowaniu pliku projektu możesz pobrać informacje o nagłówku i stopce za pomocą metody`PageInfo` nieruchomość.
```csharp
var info = project.DefaultView.PageInfo;
// Informacje nagłówkowe
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Informacje w stopce
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Wykonując te proste kroki, możesz łatwo pobrać informacje o nagłówkach i stopkach z plików MS Project przy użyciu Aspose.Tasks dla .NET.

## Wniosek
tym samouczku omówiliśmy, jak wyodrębnić informacje z nagłówka i stopki z plików MS Project za pomocą Aspose.Tasks dla .NET. Ta potężna biblioteka upraszcza pracę z plikami projektu w aplikacjach C#, zapewniając programistom niezawodne narzędzia do manipulacji.
### Często zadawane pytania
### Czy mogę modyfikować informacje w nagłówku i stopce za pomocą Aspose.Tasks?
Tak, możesz programowo modyfikować informacje nagłówka i stopki za pomocą Aspose.Tasks dla .NET.
### Czy Aspose.Tasks obsługuje inne formaty plików projektów oprócz MS Project?
Tak, Aspose.Tasks obsługuje różne formaty plików projektów, w tym MPP, XML i MPX.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?
 Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks ze strony[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dokumentację dla Aspose.Tasks?
 Możesz znaleźć dokumentację Aspose.Tasks[Tutaj](https://reference.aspose.com/tasks/net/).
### Jak mogę uzyskać wsparcie dla Aspose.Tasks?
 Możesz uzyskać pomoc dotyczącą Aspose.Tasks odwiedzając stronę[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
