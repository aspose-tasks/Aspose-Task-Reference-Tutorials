---
title: Ustawienia bazy danych w Aspose.Tasks
linktitle: Ustawienia bazy danych w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak importować projekty z bazy danych Primavera przy użyciu Aspose.Tasks dla .NET. Uzyskaj wskazówki krok po kroku w tym obszernym samouczku.
weight: 29
url: /pl/net/calendar-scheduling/database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustawienia bazy danych w Aspose.Tasks

## Wstęp

Aspose.Tasks dla .NET to potężna biblioteka, która umożliwia programistom pracę z plikami Microsoft Project w ich aplikacjach .NET. W tym samouczku skupimy się na importowaniu projektów z bazy danych Primavera przy użyciu Aspose.Tasks.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

- Podstawowa znajomość języka programowania C#.
- Program Visual Studio zainstalowany w systemie.
-  Zainstalowana biblioteka Aspose.Tasks dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).
- Dostęp do bazy danych Primavera wraz z niezbędnymi uprawnieniami.

## Importuj przestrzenie nazw

Najpierw musisz zaimportować niezbędne przestrzenie nazw do projektu C#. Te przestrzenie nazw zapewniają dostęp do klas i metod potrzebnych do pracy z Aspose.Tasks dla .NET.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Podzielmy teraz podany przykładowy kod na kilka kroków:

## Krok 1: Zdefiniuj ciąg połączenia

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 W tym kroku definiujemy parametry połączenia umożliwiające połączenie z bazą danych Primavera. Upewnij się, że wymieniłeś`DataDir` z katalogiem, w którym znajduje się plik bazy danych.

## Krok 2: Utwórz ustawienia bazy danych

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 Tutaj tworzymy instancję`PrimaveraDbSettings` class, przekazując parametry połączenia i identyfikator projektu jako parametry. Dostosuj identyfikator projektu zgodnie ze swoimi wymaganiami.

## Krok 3: Ustaw stałą nazwę dostawcy

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Określ niezmienną nazwę dostawcy. W tym przykładzie używamy SQLite, ale możesz go zmienić w zależności od dostawcy bazy danych.

## Krok 4: Załaduj projekt

```csharp
var project = new Project(settings);
```

 Stwórz nowy`Project` obiekt, przekazując ustawienia bazy danych jako parametr.

## Krok 5: Zapisz projekt

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Na koniec zapisz projekt w wybranej lokalizacji w określonym formacie pliku.

## Wniosek

W tym samouczku nauczyliśmy się, jak importować projekty z bazy danych Primavera za pomocą Aspose.Tasks dla .NET. Postępując zgodnie z podanymi krokami, możesz bezproblemowo zintegrować funkcję importowania projektów z aplikacjami .NET.

## Często zadawane pytania

### P1: Czy mogę importować projekty od różnych dostawców baz danych za pomocą Aspose.Tasks dla .NET?

O1: Tak, możesz importować projekty od różnych dostawców baz danych, odpowiednio dostosowując parametry połączenia i niezmienną nazwę dostawcy.

### P2: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla .NET?

 A2: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks dla .NET od[Tutaj](https://releases.aspose.com/).

### P3: Gdzie mogę znaleźć dokumentację Aspose.Tasks dla .NET?

 Odpowiedź 3: Możesz znaleźć dokumentację[Tutaj](https://reference.aspose.com/tasks/net/).

### P4: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?

 O4: Możesz uzyskać pomoc na forum społeczności Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).

### P5: Czy potrzebuję tymczasowej licencji, aby używać Aspose.Tasks dla .NET?

 Odpowiedź 5: Jeśli chcesz przetestować pełną funkcjonalność biblioteki, możesz uzyskać licencję tymczasową od[Tutaj](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
