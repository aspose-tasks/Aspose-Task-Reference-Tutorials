---
title: Opcje ładowania w Aspose.Tasks
linktitle: Opcje ładowania w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak wykorzystać moc Aspose.Tasks dla .NET, aby efektywnie zarządzać dokumentami Microsoft Project, korzystając ze wskazówek krok po kroku.
type: docs
weight: 16
url: /pl/net/advanced-concepts/loading-options/
---
## Wstęp

Aspose.Tasks dla .NET to potężna biblioteka, która pozwala programistom programowo manipulować dokumentami Microsoft Project. Niezależnie od tego, czy chcesz tworzyć, czytać, pisać czy konwertować pliki projektu, Aspose.Tasks zapewnia szeroką gamę funkcji usprawniających Twoje zadania. W tym samouczku zagłębimy się w podstawy korzystania z Aspose.Tasks dla .NET, dzieląc kluczowe procesy na proste, wykonalne kroki.

## Warunki wstępne

Zanim zagłębisz się w Aspose.Tasks dla .NET, upewnij się, że masz skonfigurowane następujące wymagania wstępne:

1. Visual Studio: Zainstaluj Visual Studio lub dowolne inne wybrane IDE.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[strona internetowa](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#.

Skoro już omówiliśmy wymagania wstępne, przyjrzyjmy się najważniejszym przestrzeniom nazw i zapoznajmy się z przewodnikiem krok po kroku.

## Importowanie przestrzeni nazw

swoim projekcie C# zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.Tasks:

1. Aspose.Tasks: Ta przestrzeń nazw udostępnia podstawowe klasy i interfejsy do pracy z dokumentami projektu.

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

Podzielmy teraz różne zadania na przewodniki krok po kroku.

## Krok 1: Ładowanie projektów chronionych hasłem

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Zainicjuj FileStream, aby załadować plik projektu
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Utwórz instancję LoadOptions
        var options = new LoadOptions
        {
            Password = "password" // Ustaw hasło
        };

        // Załaduj projekt z określonymi opcjami
        var project = new Project(stream, options);

        // Wyświetl nazwę projektu
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

## Krok 2: Ładowanie projektów Primavera z opcjami niestandardowymi

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Utwórz instancję LoadOptions
    var loadOptions = new LoadOptions();

    // Skonfiguruj opcje czytania Primavera
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Ustaw identyfikator UID projektu
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Ustaw opcje czytania Primavera
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Załaduj projekt Primavera z określonymi opcjami
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Wyświetl nazwę projektu
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Wykonaj dalsze operacje na wczytanym projekcie
}
```

## Krok 3: Określanie kodowania pliku

```csharp
public void SpecifyFileEncoding()
{
    // Utwórz instancję LoadOptions
    LoadOptions lo = new LoadOptions();

    // Określ kodowanie podczas otwierania projektu z pliku Primavera XER
    lo.Encoding = Encoding.GetEncoding(1251);

    // Załaduj projekt z określonym kodowaniem
    var project = new Project("encoding1251.xer", lo);

    // Wykonaj dalsze operacje na wczytanym projekcie
}
```

## Krok 4: Ładowanie projektów Primavera z obsługą błędów

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Utwórz instancję LoadOptions
    var loadOptions = new LoadOptions();

    // Skonfiguruj opcje czytania Primavera
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Ustaw identyfikator UID projektu
    };

    // Ustaw opcje czytania Primavera
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //Ustaw niestandardową obsługę błędów
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Załaduj projekt Primavera z określonymi opcjami i obsługą błędów
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Wykonaj dalsze operacje na wczytanym projekcie
}

// Niestandardowa metoda obsługi błędów
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Zaimplementuj niestandardową logikę obsługi błędów
}
```

Wykonując te kroki, możesz efektywnie wykorzystać opcje ładowania w Aspose.Tasks dla .NET, aby manipulować dokumentami projektu zgodnie z własnymi wymaganiami.

## Wniosek

W tym samouczku omówiliśmy podstawy pracy z opcjami ładowania w Aspose.Tasks dla .NET. Od ładowania projektów chronionych hasłem po określanie niestandardowej obsługi błędów — opanowanie tych technik umożliwi wydajne zarządzanie plikami projektów w aplikacjach .NET.

## Często zadawane pytania

### P1: Czy Aspose.Tasks for .NET jest kompatybilny ze wszystkimi wersjami Microsoft Project?

O1: Tak, Aspose.Tasks dla .NET obsługuje różne wersje Microsoft Project, zapewniając kompatybilność w różnych środowiskach.

### P2: Czy mogę zintegrować Aspose.Tasks dla .NET z bibliotekami innych firm?

Odpowiedź 2: Oczywiście, Aspose.Tasks dla .NET bezproblemowo integruje się z innymi bibliotekami .NET, oferując zwiększoną funkcjonalność i elastyczność.

### P3: Czy Aspose.Tasks dla .NET zapewnia dokumentację i zasoby wsparcia?

 A3: Tak, możesz odwołać się do kompleksowości[dokumentacja](https://reference.aspose.com/tasks/net/) i uzyskaj dostęp do wsparcia poprzez[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P4: Czy dostępne są opcje licencjonowania dla Aspose.Tasks dla .NET?

 Odpowiedź 4: Tak, możesz poznać różne opcje licencjonowania, w tym bezpłatne wersje próbne i licencje tymczasowe, na stronie[Witryna Aspose.Tasks](https://purchase.aspose.com/buy).

### P5: Jak często są wydawane aktualizacje i nowe funkcje dla Aspose.Tasks dla .NET?

O5: Aspose.Tasks dla .NET otrzymuje regularne aktualizacje i ulepszenia funkcji, aby zapewnić optymalną wydajność i kompatybilność z rozwijającymi się technologiami.