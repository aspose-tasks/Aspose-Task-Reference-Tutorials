---
title: Zarządzaj kodami konspektu projektu w Aspose.Tasks dla .NET
linktitle: Zarządzanie kodami konspektu w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naucz się zarządzać kodami konspektu MS Project za pomocą Aspose.Tasks dla .NET. Uprość organizację projektu bez wysiłku.
weight: 10
url: /pl/net/outline-code-page-settings/outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zarządzaj kodami konspektu projektu w Aspose.Tasks dla .NET

## Wstęp
W tym samouczku omówimy, jak zarządzać kodami konspektu programu Microsoft Project za pomocą Aspose.Tasks dla .NET. Kody konspektu to niestandardowe pola w programie Microsoft Project, które umożliwiają użytkownikom kategoryzację i organizowanie zadań według określonych kryteriów. Aspose.Tasks upraszcza proces programowego czytania i manipulowania tymi kodami konspektu.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1.  Biblioteka Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[strona internetowa](https://releases.aspose.com/tasks/net/).
2. Środowisko programistyczne: Skonfiguruj odpowiednie środowisko programistyczne dla programowania .NET, takie jak Visual Studio.
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie korzystna dla zrozumienia przykładów kodu.

## Importowanie przestrzeni nazw
Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw do projektu C#. Umożliwia to dostęp do klas i metod udostępnianych przez bibliotekę Aspose.Tasks.
1. Otwórz program Visual Studio: Uruchom środowisko IDE programu Visual Studio.
2. Utwórz nowy projekt: Rozpocznij nowy projekt C# lub otwórz istniejący, w którym zamierzasz używać Aspose.Tasks.
3. Dodaj odwołanie do Aspose.Tasks: Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań, wybierz „Zarządzaj pakietami NuGet”, wyszukaj „Aspose.Tasks” i zainstaluj najnowszą wersję.
4. Importuj przestrzeń nazw Aspose.Tasks: Na górze pliku C# dodaj następującą dyrektywę using:
```csharp
using Aspose.Tasks;
using System;

```
## Krok 1: Zdefiniuj katalog dokumentów
Najpierw ustaw ścieżkę do katalogu zawierającego plik MS Project.
```csharp
String DataDir = "Your Document Directory";
```
 Zastępować`"Your Document Directory"` z rzeczywistą ścieżką do pliku projektu.
## Krok 2: Załaduj plik projektu
 Utwórz instancję nowego`Project` obiekt poprzez załadowanie pliku MS Project.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Spowoduje to inicjowanie obiektu projektu z określonym plikiem.
## Krok 3: Przeczytaj kody konspektu
Iteruj po wszystkich zadaniach w projekcie i pobieraj ich kody konspektu.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
Ten fragment kodu przegląda każde zadanie, sprawdza, czy zawiera kody konspektu i wyświetla szczegółowe informacje, takie jak identyfikator pola, identyfikator wartości i identyfikator wartości dla każdego kodu konspektu powiązanego z zadaniem.

## Wniosek
Podsumowując, Aspose.Tasks dla .NET zapewnia potężne możliwości programowego zarządzania kodami konspektu Microsoft Project. Wykonując kroki opisane w tym samouczku, możesz efektywnie czytać i manipulować kodami konspektu w plikach MS Project przy użyciu języka C#.
## Często zadawane pytania
### P: Czy mogę modyfikować kody konspektu za pomocą Aspose.Tasks?
O: Tak, możesz programowo modyfikować kody konspektu za pomocą Aspose.Tasks dla .NET. Po prostu uzyskaj dostęp do kodów konspektu zadań i w razie potrzeby zaktualizuj ich wartości.
### P: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project?
Odp.: Aspose.Tasks obsługuje szeroką gamę wersji Microsoft Project, w tym 2003, 2007, 2010, 2013, 2016 i 2019.
### P: Czy Aspose.Tasks wymaga licencji do użytku komercyjnego?
Odp.: Tak, do komercyjnego wykorzystania Aspose.Tasks wymagana jest ważna licencja. Licencję można uzyskać ze strony internetowej Aspose.
### P: Czy mogę wypróbować Aspose.Tasks przed zakupem?
Odp.: Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks ze strony internetowej, aby ocenić jej funkcje i możliwości.
### P: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks?
 Odp.: Możesz uzyskać pomoc dotyczącą Aspose.Tasks, odwiedzając forum pod adresem[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Kompletny kod źródłowy
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
