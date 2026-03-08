---
date: 2026-03-08
description: Dowiedz się, jak importować plik projektu przy użyciu Aspose.Tasks dla
  .NET, w tym jak określić kodowanie pliku i efektywnie wczytać plik Microsoft Project.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Importuj plik projektu – Opcje ładowania w Aspose.Tasks
url: /pl/net/advanced-concepts/loading-options/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Importowanie pliku projektu – Opcje ładowania w Aspose.Tasks

## Wprowadzenie

Aspose.Tasks for .NET ułatwia **importowanie danych z pliku projektu** pochodzących z Microsoft Project, Primavera i innych formatów. Niezależnie od tego, czy musisz odczytać plik zabezpieczony hasłem, ustawić własne kodowanie, czy obsłużyć błędy parsowania, biblioteka daje precyzyjną kontrolę dzięki opcjom ładowania. W tym samouczku przeprowadzimy Cię przez najczęstsze scenariusze, abyś mógł pewnie **ładować obiekty plików Microsoft Project** w aplikacjach .NET.

## Szybkie odpowiedzi
- **Jaki jest podstawowy sposób importowania pliku projektu?** Użyj konstruktora `Project` z instancją `LoadOptions`.  
- **Czy mogę otwierać pliki zabezpieczone hasłem?** Tak — ustaw właściwość `Password` w `LoadOptions`.  
- **Jak określić kodowanie pliku?** Przypisz obiekt `Encoding` do `LoadOptions.Encoding`.  
- **Czy obsługa błędów jest konfigurowalna?** Oczywiście — podaj delegata do `LoadOptions.ErrorHandler`.  
- **Czy te opcje działają z plikami Primavera?** Tak, za pośrednictwem `PrimaveraReadOptions` wewnątrz `LoadOptions`.

## Wymagania wstępne

Zanim przejdziesz do kodu, upewnij się, że masz:

1. **Visual Studio** (lub dowolne preferowane środowisko IDE .NET).  
2. **Aspose.Tasks for .NET** – pobierz je ze [strony internetowej](https://releases.aspose.com/tasks/net/).  
3. Podstawową znajomość składni **C#** oraz struktury projektu.

Teraz, gdy wszystko jest gotowe, zaimportujmy wymagane przestrzenie nazw.

## Importowanie przestrzeni nazw

W swoim projekcie C# dodaj następujące dyrektywy `using`, aby klasy API były dostępne:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## Jak importować plik projektu z opcjami ładowania

Poniżej znajdują się cztery praktyczne przykłady obejmujące najczęstsze scenariusze ładowania.

### Krok 1: Ładowanie projektu zabezpieczonego hasłem

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### Krok 2: Ładowanie projektu Primavera z własnymi opcjami

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### Krok 3: **Określenie kodowania pliku** przy importowaniu pliku XER

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### Krok 4: Ładowanie projektu Primavera z własną obsługą błędów

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

Postępując zgodnie z tymi krokami, możesz precyzyjnie **importować dane z pliku projektu**, dostosować proces ładowania do własnych potrzeb i utrzymać aplikację w stabilnym stanie.

## Typowe problemy i wskazówki

- **Nieprawidłowe hasło** – właściwość `Password` spowoduje wyrzucenie wyjątku; sprawdź poprawność danych przed ładowaniem.  
- **Nieobsługiwane kodowanie** – upewnij się, że podana strona kodowa istnieje na docelowej maszynie (`Encoding.GetEncoding(1251)` działa dla cyrylicy).  
- **Brak opcji Primavera** – jeśli potrzebujesz zachować identyfikatory zadań (UID), ustaw `PreserveUids = true`; w przeciwnym razie mogą pojawić się duplikaty ID.  
- **Obsługa błędów zwracająca null** – zwrócenie `null` sygnalizuje parserowi pominięcie problematycznego elementu; dostosuj zachowanie w razie potrzeby.

## Najczęściej zadawane pytania

**P: Czy Aspose.Tasks for .NET jest kompatybilny ze wszystkimi wersjami Microsoft Project?**  
O: Tak, obsługuje szeroką gamę wersji Microsoft Project, dzięki czemu możesz **ładować formaty plików Microsoft Project** od starszych plików MPP po najnowsze formaty.

**P: Czy mogę integrować Aspose.Tasks for .NET z innymi bibliotekami firm trzecich?**  
O: Oczywiście. Biblioteka współpracuje bezproblemowo z innymi pakietami .NET, umożliwiając łączenie jej z frameworkami raportowania, interfejsu użytkownika czy dostępu do danych.

**P: Czy Aspose.Tasks for .NET udostępnia dokumentację i zasoby wsparcia?**  
O: Tak, możesz skorzystać z obszernej [dokumentacji](https://reference.aspose.com/tasks/net/) oraz uzyskać pomoc na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**P: Czy dostępne są opcje licencjonowania Aspose.Tasks for .NET?**  
O: Tak, możesz zapoznać się z różnymi opcjami licencjonowania, w tym wersjami próbnymi i licencjami tymczasowymi, na stronie [Aspose.Tasks](https://purchase.aspose.com/buy).

**P: Jak często publikowane są aktualizacje i nowe funkcje dla Aspose.Tasks for .NET?**  
O: Aspose.Tasks otrzymuje regularne aktualizacje, które wprowadzają nowe funkcje, poprawiają wydajność i zapewniają kompatybilność z najnowszymi wydaniami Microsoft Project.

---

**Ostatnia aktualizacja:** 2026-03-08  
**Testowane z:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}