---
date: 2026-04-06
description: Dowiedz się, jak usunąć wszystkie linie bazowe i zarządzać kolekcjami
  linii bazowych w Aspose.Tasks dla .NET, korzystając z przykładów kodu krok po kroku.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Usuń wszystkie linie bazowe przy użyciu kolekcji Baseline w Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Usuń wszystkie linie bazowe przy użyciu kolekcji Baseline w Aspose.Tasks
url: /pl/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Usuń wszystkie linie bazowe przy użyciu kolekcji Baseline w Aspose.Tasks

## Wprowadzenie

Aspose.Tasks for .NET pozwala na manipulację plikami Microsoft Project bezpośrednio z aplikacji .NET. Jedną z najpotężniejszych funkcji jest możliwość **usunięcia wszystkich linii bazowych** dla zasobu, co jest niezbędne, gdy trzeba zresetować dane śledzenia projektu lub rozpocząć nowy okres linii bazowej. W tym samouczku przeprowadzimy Cię przez cały proces — od załadowania pliku projektu po usunięcie każdej linii bazowej powiązanej z określonym zasobem — używając jasnych, konwersacyjnych wyjaśnień i gotowego do uruchomienia kodu C#.

## Szybkie odpowiedzi
- **Co robi „delete all baselines”?** Usuwa każdy zapisany rekord linii bazowej dla wybranego zasobu, czyszcząc historyczne dane kosztów i pracy.  
- **Dlaczego mógłbym tego potrzebować?** Aby zresetować śledzenie po dużej zmianie w projekcie lub gdy oryginalne linie bazowe nie są już istotne.  
- **Która biblioteka zapewnia tę funkcjonalność?** Aspose.Tasks for .NET.  
- **Czy potrzebna jest licencja?** Wymagana jest ważna licencja Aspose.Tasks do użytku produkcyjnego; dostępna jest bezpłatna wersja próbna.  
- **Czy kod jest kompatybilny z .NET 6+?** Tak, API działa z .NET Framework 4.5+, .NET Core 3.1+ oraz .NET 5/6.

## Czym jest linia bazowa i dlaczego usuwać wszystkie linie bazowe?

Linia bazowa przechowuje pierwotny plan kosztów, pracy i harmonogramu w określonym momencie. W trakcie trwania projektu możesz tworzyć kilka linii bazowych (Baseline 1, Baseline 2, itp.), aby porównywać rzeczywisty postęp z różnymi snapshotami planowania. Jednak w niektórych sytuacjach — takich jak zmiana zakresu projektu lub nowy start — utrzymywanie tych historycznych linii bazowych może wprowadzać zamieszanie. Usunięcie wszystkich linii bazowych daje czystą kartę, umożliwiając ustawienie nowych linii bazowych odzwierciedlających aktualną rzeczywistość.

## Wymagania wstępne

Przed przystąpieniem do kodu upewnij się, że masz:

1. **Visual Studio** – dowolna aktualna edycja (Community, Professional lub Enterprise).  
2. **Aspose.Tasks for .NET** – pobierz go z [download link](https://releases.aspose.com/tasks/net/).  
3. **Podstawowa znajomość C#** – powinieneś być pewny w używaniu zmiennych, pętli i wyjścia konsoli.  
4. **Plik Microsoft Project** (`.mpp`) – w przykładach zostanie użyty przykładowy plik o nazwie *WorkWithBaselineCollection.mpp*.

## Importowanie przestrzeni nazw

Najpierw wprowadź niezbędne przestrzenie nazw, aby kompilator wiedział, gdzie znaleźć używane klasy.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Krok 1: Załaduj plik projektu

Zaczynamy od załadowania istniejącego pliku Project. Dostosuj `DataDir`, aby wskazywał na folder zawierający Twój plik `.mpp`.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Krok 2: Pobierz docelowy zasób

Dla demonstracji pobieramy zasób o UID = 1. W rzeczywistym scenariuszu znajdziesz zasób po nazwie lub innym identyfikatorze.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Krok 3: Wyświetl istniejące informacje o liniach bazowych

Przed usunięciem czegokolwiek przydatne jest zobaczenie, które linie bazowe są aktualnie przypisane do zasobu. Daje to pewność, że usuwasz właściwe dane.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Krok 4: Iteruj przez wszystkie linie bazowe

Tutaj przechodzimy przez każdą linię bazową, wypisując kluczowe metryki, takie jak koszt, praca i wartość uzyskaną (BCWP/BCWS). Ten krok jest opcjonalny, ale przydatny do logowania lub celów audytowych.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Usuń wszystkie linie bazowe

Teraz wykonujemy podstawową akcję: **delete all baselines** dla wybranego zasobu. Najpierw kopiujemy kolekcję do listy, aby uniknąć modyfikacji kolekcji podczas iteracji, a następnie usuwamy każdą linię bazową pojedynczo.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Po uruchomieniu tego bloku, `resource.Baselines.Count` będzie równe `0`, potwierdzając, że wszystkie rekordy linii bazowych zostały usunięte.

## Typowe problemy i wskazówki

- **NullReferenceException** – Upewnij się, że plik projektu rzeczywiście zawiera zasób, który chcesz wybrać; w przeciwnym razie `GetByUid` zwróci `null`.  
- **Licensing** – Bez ważnej licencji Aspose.Tasks zobaczysz znak wodny w wyjściu i ograniczoną funkcjonalność.  
- **Performance** – W przypadku bardzo dużych projektów rozważ iterację przy użyciu `Parallel.ForEach`, aby przyspieszyć proces usuwania, ale pamiętaj, że podstawowa kolekcja nie jest bezpieczna wątkowo.

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks radzi sobie z dużymi plikami projektu?**  
A: Tak, Aspose.Tasks jest zoptymalizowany pod kątem wydajności i może efektywnie przetwarzać pliki `.mpp` o rozmiarze kilku gigabajtów.

**Q: Czy biblioteka jest kompatybilna ze wszystkimi wersjami Microsoft Project?**  
A: Aspose.Tasks obsługuje Project 2000 do Project 2024, obejmując zarówno starsze formaty `.mpp`, jak i nowsze pliki oparte na XML.

**Q: Czy mogę dostosować linie bazowe przed ich usunięciem?**  
A: Oczywiście. Możesz odczytać lub zmodyfikować dowolną właściwość linii bazowej (koszt, praca, daty) przed podjęciem decyzji o jej usunięciu.

**Q: Czy Aspose.Tasks działa na platformach chmurowych?**  
A: Tak, API działa w każdym środowisku zgodnym z .NET, w tym Azure App Service, AWS Lambda (przez .NET Core) i kontenerach Docker.

**Q: Gdzie mogę poprosić społeczność o pomoc?**  
A: Odwiedź [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15), aby połączyć się z innymi programistami i personelem Aspose.

## Podsumowanie

W tym przewodniku pokazaliśmy, jak **delete all baselines** z zasobu przy użyciu Aspose.Tasks for .NET. Postępując zgodnie z kodem krok po kroku, możesz zresetować dane linii bazowych, utrzymać śledzenie projektu w czystości i przygotować harmonogram do nowego cyklu planowania. Śmiało eksperymentuj z tworzeniem nowych linii bazowych po usunięciu, aby zobaczyć, jak biblioteka aktualizuje plik projektu.

---

**Ostatnia aktualizacja:** 2026-04-06  
**Testowano z:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}