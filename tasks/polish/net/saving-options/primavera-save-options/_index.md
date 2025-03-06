---
title: Zapisz opcje MS Project Primavera za pomocą Aspose.Tasks
linktitle: Opcje zapisu Primavera dla Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak bezproblemowo zapisywać opcje MS Project dla Primavera za pomocą Aspose.Tasks dla .NET. Postępuj zgodnie z naszym samouczkiem krok po kroku.
weight: 14
url: /pl/net/saving-options/primavera-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz opcje MS Project Primavera za pomocą Aspose.Tasks

## Wstęp
Aspose.Tasks dla .NET to potężna biblioteka, która umożliwia programistom płynną pracę z plikami Microsoft Project w aplikacjach .NET. Jedną z kluczowych funkcjonalności jakie oferuje jest możliwość zapisywania opcji MS Project dla popularnego oprogramowania do zarządzania projektami Primavera. W tym samouczku omówimy, jak to osiągnąć za pomocą Aspose.Tasks.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
- Podstawowa znajomość C# i frameworku .NET.
-  Aspose.Tasks dla .NET zainstalowany w Twoim środowisku programistycznym. Jeśli nie, możesz go pobrać[Tutaj](https://releases.aspose.com/tasks/net/).
- Przykładowy plik MS Project do eksperymentów.

## Importuj przestrzenie nazw
Najpierw zaimportujmy niezbędne przestrzenie nazw do naszego kodu C#:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Krok 1: Załaduj plik projektu MS
 Rozpocznij od załadowania pliku MS Project, z którym zamierzasz pracować, do aplikacji C#. Można to zrobić za pomocą`Project` klasa dostarczona przez Aspose.Tasks.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Krok 2: Zdefiniuj opcje zapisywania Primavera
Następnie utwórz opcje zapisu Primavera i dostosuj je do swoich wymagań. Ten krok obejmuje określenie parametrów, takich jak przedrostek, przyrostek, przyrost identyfikatora działania oraz możliwość zmiany numeracji identyfikatorów działań.
```csharp
var options = new PrimaveraSaveOptions
{
    ActivityIdPrefix = "TEST",
    ActivityIdSuffix = 10000,
    ActivityIdIncrement = 5,
    RenumberActivityIds = true
};
```
## Krok 3: Zapisz opcje MS Project dla Primavera
 Teraz, gdy załadowałeś plik projektu i zdefiniowałeś opcje zapisu Primavery, czas zapisać opcje Primavery. Użyj`Save` metoda podana przez`Project` class, przekazując żądaną ścieżkę pliku wyjściowego i opcje zapisu Primavera.
```csharp
project.Save(DataDir + "WorkWithPrimaveraSaveOptions_out.xer", options);
```

## Wniosek
Podsumowując, wykorzystanie Aspose.Tasks dla .NET umożliwia programistom płynne manipulowanie plikami MS Project, w tym zapisywanie opcji dla Primavera. Wykonując kroki opisane w tym samouczku, możesz efektywnie zintegrować tę funkcjonalność z aplikacjami .NET.
## Często zadawane pytania
### P: Czy mogę dostosować inne parametry oprócz identyfikatorów aktywności podczas zapisywania opcji MS Project dla Primavera?
O: Tak, Aspose.Tasks zapewnia szeroką gamę opcji dostosowywania, w tym alokację zasobów i planowanie zadań.
### P: Czy Aspose.Tasks obsługuje inne oprogramowanie do zarządzania projektami poza Primaverą?
O: Tak, Aspose.Tasks obsługuje różne formaty kompatybilne z popularnymi narzędziami do zarządzania projektami, takimi jak Oracle Primavera, Microsoft Project Server i nie tylko.
### P: Czy Aspose.Tasks nadaje się zarówno do projektów na małą skalę, jak i na poziomie przedsiębiorstwa?
O: Oczywiście, Aspose.Tasks został zaprojektowany, aby zaspokoić potrzeby programistów pracujących nad projektami dowolnej wielkości, oferując skalowalność i solidną wydajność.
### P: Czy mogę wypróbować Aspose.Tasks za darmo przed dokonaniem zakupu?
 Odp.: Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks ze strony[Tutaj](https://releases.aspose.com/) aby poznać jego funkcje i możliwości.
### P: Gdzie mogę uzyskać pomoc, jeśli napotkam problemy lub mam pytania podczas korzystania z Aspose.Tasks?
 Odp.: Możesz zwrócić się o pomoc do społeczności Aspose.Tasks i zespołu wsparcia na stronie[forum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
