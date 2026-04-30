---
date: 2026-04-30
description: Dowiedz się, jak ustawiać linię bazową i efektywnie manipulować liniami
  bazowymi projektu przy użyciu Aspose.Tasks dla .NET.
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Różne typy linii bazowych w Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak ustawić linię bazową w Aspose.Tasks – Różne typy linii bazowych
url: /pl/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Różne typy linii bazowych w Aspose.Tasks

## Wprowadzenie

W zarządzaniu projektami, **jak ustawić linię bazową** prawidłowo może decydować o różnicy między projektem, który pozostaje na właściwej drodze, a tym, który wymyka się kontroli. Aspose.Tasks dla .NET udostępnia w pełni funkcjonalne API do tworzenia, aktualizacji i porównywania linii bazowych, umożliwiając **śledzenie postępu projektu** względem pierwotnego planu. W tym samouczku nauczysz się, jak ustawić linię bazową, pracować z wieloma typami linii bazowych oraz wykorzystać dane do analizy **linii bazowej vs rzeczywisty harmonogram** twojego projektu.

## Szybkie odpowiedzi
- **Co to jest linia bazowa?** Migawka harmonogramu, kosztów i danych pracy wykonana w określonym momencie projektu.  
- **Ile linii bazowych może przechowywać Aspose.Tasks?** Do 11 odrębnych linii bazowych na projekt.  
- **Dlaczego ustawiać linię bazową?** Aby porównać rzeczywistą wydajność z pierwotnym planem i zidentyfikować odchylenia.  
- **Czy potrzebna jest licencja, aby wypróbować?** Dostępna jest darmowa wersja próbna; licencja jest wymagana do użytku produkcyjnego.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co to jest „jak ustawić linię bazową” w Aspose.Tasks?
Ustawienie linii bazowej oznacza wywołanie metody `SetBaseline` na obiekcie `Project`. API pozwala wybrać spośród kilku wartości `BaselineType` (Baseline, Baseline1 … Baseline10), aby móc zachować historyczne migawki w miarę rozwoju projektu.

## Dlaczego zarządzać liniami bazowymi projektu?
- **Mierzenie odchyleń:** Szybko zobacz, czy zadania są przed czy po harmonogramie.  
- **Kontrola kosztów:** Porównaj koszt linii bazowej z rzeczywistymi wydatkami.  
- **Raportowanie interesariuszom:** Eksportuj dane linii bazowej do PDF, XLSX lub innych formatów w celu klarownej komunikacji.  
- **Planowanie scenariuszy:** Przechowuj wiele linii bazowych, aby ocenić harmonogramy „co‑by‑było”.

## Prerequisites

### 1. Znajomość C# i .NET Framework
Podstawowa znajomość klas C#, metod i koncepcji programowania obiektowego jest wymagana.

### 2. Instalacja Aspose.Tasks dla .NET
Upewnij się, że biblioteka została dodana do projektu. Możesz ją pobrać ze [strony Aspose.Tasks](https://releases.aspose.com/tasks/net/) lub zainstalować przez NuGet.

### 3. Zintegrowane środowisko programistyczne (IDE)
Visual Studio (lub dowolne kompatybilne IDE) jest zalecane do pisania, kompilacji i debugowania kodu C#.

## Importowanie przestrzeni nazw

Zanim rozpoczniemy pracę z Aspose.Tasks w naszym projekcie C#, musimy zaimportować niezbędne przestrzenie nazw, aby uzyskać dostęp do wymaganych klas i metod. Postępuj zgodnie z poniższymi krokami:

```csharp

```

Teraz, gdy skonfigurowaliśmy wymagania wstępne i zaimportowaliśmy niezbędne przestrzenie nazw, przejdźmy do ustawiania różnych typów linii bazowych przy użyciu Aspose.Tasks dla .NET. Rozbijemy każdy przykład na kilka kroków dla jasności i łatwości zrozumienia.

## Jak ustawić linię bazową w Aspose.Tasks

### Krok 1: Załaduj plik projektu
Najpierw musimy załadować plik projektu, do którego zamierzamy ustawić linię bazową. Ten krok obejmuje inicjalizację obiektu `Project` i załadowanie pliku projektu. Oto jak to zrobić:

```csharp
var project = new Project("Project2.mpp");
```

### Krok 2: Ustaw linię bazową
Po załadowaniu projektu możemy przystąpić do ustawienia linii bazowej. Linie bazowe zapewniają migawkę początkowego harmonogramu projektu, która służy jako punkt odniesienia do porównań w trakcie postępu projektu. Użyj metody `SetBaseline`, aby ustawić linię bazową. Na przykład, aby ustawić linię bazową dla całego projektu, użyj wyliczenia `BaselineType.Baseline`:

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### Krok 3: Praca z liniami bazowymi projektu
Po ustawieniu linii bazowej możesz pracować z różnymi polami linii bazowych projektu, aby dokładnie analizować i śledzić postęp projektu. Ten krok obejmuje dostęp do danych linii bazowej, takich jak daty rozpoczęcia, daty zakończenia, trwania i koszty. Tutaj możesz wykorzystać bogaty zestaw funkcji udostępnionych przez Aspose.Tasks do manipulacji danymi linii bazowej zgodnie z Twoimi wymaganiami.

## Typowe problemy i rozwiązania
- **Linia bazowa nie zastosowana:** Upewnij się, że plik projektu został zapisany po wywołaniu `SetBaseline`. Użyj `project.Save("output.mpp");`, jeśli musisz zachować zmiany.  
- **Konflikt wielu linii bazowych:** Przy ustawianiu więcej niż jednej linii bazowej, określ właściwy `BaselineType` (np. `Baseline1`, `Baseline2`).  
- **Niezgodność wersji:** Zweryfikuj, czy wersja DLL Aspose.Tasks odpowiada docelowej wersji środowiska .NET.

## Najczęściej zadawane pytania

**P:** Czy mogę ustawić wiele linii bazowych dla jednego projektu przy użyciu Aspose.Tasks dla .NET?  
**O:** Tak, Aspose.Tasks pozwala ustawić do 11 linii bazowych dla projektu, zapewniając kompleksowe możliwości śledzenia.

**P:** Czy Aspose.Tasks jest kompatybilny z różnymi formatami plików projektów?  
**O:** Zdecydowanie! Aspose.Tasks obsługuje różne formaty plików projektów, takie jak MPP, XML i MPX, zapewniając kompatybilność na różnych platformach.

**P:** Jak mogę zwizualizować dane linii bazowej w moim projekcie?  
**O:** Możesz użyć Aspose.Tasks do eksportu danych projektu do popularnych formatów, takich jak PDF lub XLSX, co umożliwia łatwą wizualizację i udostępnianie informacji o linii bazowej.

**P:** Czy Aspose.Tasks oferuje wsparcie przy integracji z narzędziami do zarządzania projektami?  
**O:** Aspose.Tasks udostępnia obszerne dokumentacje i fora wsparcia, aby pomóc programistom w płynnej integracji jego funkcji z popularnymi narzędziami i platformami do zarządzania projektami.

**P:** Czy mogę wypróbować Aspose.Tasks przed zakupem?  
**O:** Tak, możesz zapoznać się z Aspose.Tasks poprzez darmową wersję próbną dostępną na stronie internetowej, co pozwala na bezpośrednie przetestowanie jego możliwości.

---

**Ostatnia aktualizacja:** 2026-04-30  
**Testowano z:** Aspose.Tasks for .NET (latest stable release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}