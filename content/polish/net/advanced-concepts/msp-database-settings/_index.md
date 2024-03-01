---
title: Ustawienia bazy danych Microsoft Project w Aspose.Tasks
linktitle: Ustawienia bazy danych Microsoft Project w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak skonfigurować ustawienia bazy danych Microsoft Project za pomocą Aspose.Tasks w celu bezproblemowej integracji z aplikacjami .NET.
type: docs
weight: 19
url: /pl/net/advanced-concepts/msp-database-settings/
---
## Wstęp

Jeśli pracujesz z bazami danych Microsoft Project w aplikacjach .NET przy użyciu Aspose.Tasks, musisz skonfigurować niezbędne ustawienia, aby bezproblemowo importować dane projektu. Ten samouczek przeprowadzi Cię przez proces krok po kroku.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

1.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks z[Tutaj](https://releases.aspose.com/tasks/net/).
2. Dostęp do bazy danych Microsoft Project: Powinieneś mieć dostęp do bazy danych Microsoft Project, z której możesz importować dane.

## Importuj przestrzenie nazw

Najpierw upewnij się, że zaimportowałeś niezbędne przestrzenie nazw do swojego projektu:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Krok 1: Utwórz ciąg połączenia

Skonstruuj parametry połączenia z bazą danych programu Microsoft Project. Oto przykład:

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

Pamiętaj, aby zastąpić wartości zastępcze rzeczywistymi poświadczeniami bazy danych.

## Krok 2: Skonfiguruj ustawienia MspDb

 Utwórz instancję`MspDbSettings` i określ ciąg połączenia wraz z identyfikatorem GUID projektu:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## Krok 3: Załaduj dane projektu

 Utwórz instancję a`Project` obiekt przy użyciu skonfigurowanych ustawień:

```csharp
var project = new Project(settings);
```

## Krok 4: Zapisz dane projektu

Zapisz załadowane dane projektu do pliku:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## Wniosek

W tym samouczku nauczyłeś się konfigurować ustawienia dostępu do baz danych Microsoft Project przy użyciu Aspose.Tasks dla .NET. Wykonując poniższe kroki, możesz bezproblemowo importować dane projektu do swoich aplikacji, ułatwiając efektywne zarządzanie projektami.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Tasks z różnymi wersjami baz danych Microsoft Project?

Odpowiedź 1: Tak, Aspose.Tasks obsługuje różne wersje baz danych Microsoft Project, umożliwiając elastyczność integracji.

### P2: Jak mogę rozwiązać problemy z połączeniem z bazą danych?

 Odpowiedź 2: Upewnij się, że parametry połączenia są poprawnie skonfigurowane z odpowiednimi poświadczeniami i szczegółami bazy danych. Możesz także zapoznać się z dokumentacją lub zwrócić się o pomoc do[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P3: Czy dostępna jest wersja próbna Aspose.Tasks?

 Odpowiedź 3: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej z[Tutaj](https://releases.aspose.com/).

### P4: Czy mogę dostosować schemat interakcji z bazą danych?

 O4: Tak, możesz określić schemat dla`MspDbSettings` obiekt zgodnie ze strukturą bazy danych.

### P5: Gdzie mogę znaleźć bardziej szczegółową dokumentację dotyczącą korzystania z Aspose.Tasks?

 Odpowiedź 5: Możesz zapoznać się z obszerną dokumentacją[Tutaj](https://reference.aspose.com/tasks/net/) aby uzyskać szczegółowy wgląd w funkcjonalności Aspose.Tasks.