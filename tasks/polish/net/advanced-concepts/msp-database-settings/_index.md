---
date: 2026-03-14
description: Dowiedz się, jak określić schemat bazy danych dla bazy Microsoft Project
  przy użyciu Aspose.Tasks oraz jak importować dane projektu do aplikacji .NET.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Określ schemat bazy danych dla Project DB z Aspose.Tasks
url: /pl/net/advanced-concepts/msp-database-settings/
weight: 19
---

 Project Data => "Krok 3: Załaduj dane projektu"

- Step 4: Save Project Data => "Krok 4: Zapisz dane projektu"

- After running the code... => translation.

- Conclusion => "Podsumowanie"

- Frequently Asked Questions => "Najczęściej zadawane pytania"

- Q1 etc.

- Last Updated => "Ostatnia aktualizacja"

- Tested With => "Testowano z"

- Author => "Autor"

- Backtop button shortcode unchanged.

Make sure to keep markdown formatting.

Also note: "Pro tip:" inside blockquote. Keep blockquote.

Also note: "Q:" and "A:" lines. Keep.

Let's craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustawienia bazy danych Microsoft Project w Aspose.Tasks

## Wprowadzenie

Jeśli pracujesz z bazami danych Microsoft Project w aplikacjach .NET przy użyciu Aspose.Tasks, musisz **określić schemat bazy danych** i skonfigurować niezbędne ustawienia, aby **importować dane projektu** bezproblemowo. Ten samouczek poprowadzi Cię krok po kroku, pokazując **jak skonfigurować szczegóły połączenia**, **utworzyć ciąg połączenia .NET**, a na koniec **zapisać projekt jako MPP**.

## Szybkie odpowiedzi
- **Jaki jest główny cel?** Określenie schematu bazy danych i import bazy danych Project do aplikacji .NET.  
- **Jakiej biblioteki potrzebujesz?** Aspose.Tasks dla .NET.  
- **Jak połączyć się z Project Server?** Tworząc prawidłowy ciąg połączenia SQL i używając `MspDbSettings`.  
- **Jaki format pliku jest tworzony?** Plik MPP zapisywany przy użyciu `SaveFileFormat.Mpp`.  
- **Czy mogę zmienić nazwę schematu?** Tak, ustaw właściwość `Schema` w `MspDbSettings`.

## Jak określić schemat bazy danych dla Project DB

Zrozumienie, dlaczego możesz potrzebować **określić schemat bazy danych**, jest kluczowe. W wielu środowiskach korporacyjnych baza danych Project Server znajduje się pod niestandardowym schematem (np. `dbo`, `psdata`). Ustawiając schemat explicite, zapewniasz, że Aspose.Tasks odwołuje się do właściwych tabel, co zapobiega błędom w czasie wykonywania i gwarantuje prawidłowy import danych.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz następujące elementy:

1. Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks z [tutaj](https://releases.aspose.com/tasks/net/).  
2. Dostęp do bazy danych Microsoft Project: Musisz mieć dostęp do bazy danych Microsoft Project, z której chcesz importować dane.  

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

Zbuduj ciąg połączenia do swojej bazy danych Microsoft Project. To miejsce, w którym **tworzysz .NET connection string** i definiujesz, jak **połączyć się z Project Server**.

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

> **Wskazówka:** Sprawdź dwukrotnie wartości `DataSource` i `InitialCatalog`; muszą one odpowiadać adresowi Twojego serwera oraz nazwie opublikowanej bazy danych.

## Krok 2: Skonfiguruj MspDbSettings

Utwórz instancję `MspDbSettings`, przekaż ciąg połączenia i **określ schemat bazy danych**, ustawiając właściwość `Schema`. Dzięki temu Aspose.Tasks będzie wiedział, którego schematu używać.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Tutaj podajemy również GUID projektu, który identyfikuje konkretny projekt, który chcesz załadować.

## Krok 3: Załaduj dane projektu

Zainicjuj obiekt `Project` przy użyciu skonfigurowanych ustawień. Ten krok efektywnie **importuje dane projektu** z bazy danych do obiektu .NET.

```csharp
var project = new Project(settings);
```

## Krok 4: Zapisz dane projektu

Na koniec zapisz załadowany projekt do pliku MPP na dysku. To demonstruje **zapis projektu jako MPP** przy użyciu API Aspose.Tasks.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Po uruchomieniu kodu znajdziesz plik `ImportProjectDataFromDatabase_out.mpp` w katalogu wyjściowym, gotowy do otwarcia w Microsoft Project.

## Podsumowanie

W tym samouczku nauczyłeś się, jak **określić schemat bazy danych** dla bazy Microsoft Project, **skonfigurować połączenie**, **importować dane projektu** oraz **zapisać projekt jako MPP** przy użyciu Aspose.Tasks dla .NET. Te kroki umożliwiają płynną integrację danych Project Server z własnymi aplikacjami, pomagając budować solidne rozwiązania do zarządzania projektami.

## Najczęściej zadawane pytania

### Q1: Czy mogę używać Aspose.Tasks z różnymi wersjami baz danych Microsoft Project?
A1: Tak, Aspose.Tasks obsługuje różne wersje baz danych Microsoft Project, zapewniając elastyczność integracji.

### Q2: Jak mogę rozwiązać problemy z połączeniem do bazy danych?
A2: Upewnij się, że ciąg połączenia jest poprawnie skonfigurowany z odpowiednimi poświadczeniami i szczegółami bazy danych. Możesz także odwołać się do dokumentacji lub poszukać pomocy na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q3: Czy dostępna jest wersja próbna Aspose.Tasks?
A3: Tak, wersję próbną możesz pobrać [tutaj](https://releases.aspose.com/).

### Q4: Czy mogę dostosować schemat dla interakcji z bazą danych?
A4: Tak, możesz określić schemat dla obiektu `MspDbSettings` zgodnie ze strukturą Twojej bazy danych.

### Q5: Gdzie znajdę bardziej szczegółową dokumentację dotyczącą używania Aspose.Tasks?
A5: Kompleksową dokumentację możesz przeglądać [tutaj](https://reference.aspose.com/tasks/net/) – znajdziesz tam szczegółowe informacje o funkcjonalnościach Aspose.Tasks.

**P: Czy to podejście działa z bazami danych Azure SQL?**  
O: Zdecydowanie. Wystarczy dostosować `DataSource` do nazwy Twojego serwera Azure i upewnić się, że ustawienia TLS/SSL są włączone.

**P: Jak radzić sobie z dużymi bazami danych Project, które mogą przekroczyć limit czasu?**  
O: Zwiększ wartość `ConnectTimeout` w ciągu połączenia i rozważ ładowanie projektów partiami, jeśli to konieczne.

---

**Ostatnia aktualizacja:** 2026-03-14  
**Testowano z:** Aspose.Tasks 24.12 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}