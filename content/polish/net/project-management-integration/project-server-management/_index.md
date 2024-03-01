---
title: Zarządzanie serwerem MS Project Server za pomocą Aspose.Tasks
linktitle: Zarządzanie serwerem projektów za pomocą Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Odblokuj płynne zarządzanie MS Project Server za pomocą Aspose.Tasks dla .NET. Automatyzuj zadania projektowe bez wysiłku.
type: docs
weight: 23
url: /pl/net/project-management-integration/project-server-management/
---
## Wstęp
tym samouczku zagłębimy się w zarządzanie MS Project Server przy użyciu Aspose.Tasks dla .NET. Aspose.Tasks to potężna biblioteka, która umożliwia programistom programową pracę z plikami Microsoft Project, umożliwiając bezproblemową integrację i manipulowanie danymi projektu.
## Warunki wstępne
Zanim zagłębimy się w zarządzanie MS Project Server za pomocą Aspose.Tasks, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
1. Microsoft Project Server: Potrzebujesz dostępu do instancji Microsoft Project Server, w której masz uprawnienia administracyjne lub przynajmniej uprawnienia do tworzenia projektów i zarządzania nimi.
2.  Biblioteka Aspose.Tasks dla .NET: Upewnij się, że pobrałeś i zainstalowałeś bibliotekę Aspose.Tasks dla .NET. Można go pobrać z[strona internetowa](https://releases.aspose.com/tasks/net/).
3. Poświadczenia: Uzyskaj niezbędne poświadczenia, aby uwierzytelnić się w instancji MS Project Server. Zwykle obejmuje to nazwę użytkownika i hasło.
## Importuj przestrzenie nazw
Zanim zaczniesz, upewnij się, że zaimportowałeś wymagane przestrzenie nazw do swojego kodu C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## Krok 1: Skonfiguruj dane uwierzytelniające
Najpierw musisz skonfigurować dane uwierzytelniające, aby połączyć się z instancją MS Project Server. Obejmuje to adres domeny, nazwę użytkownika i hasło.
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## Krok 2: Załaduj projekt
Następnie załaduj plik MS Project, którym chcesz zarządzać za pomocą Aspose.Tasks.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## Krok 3: Utwórz Menedżera serwera projektu
 Utwórz instancję a`ProjectServerManager` obiekt przy użyciu wcześniej zdefiniowanych poświadczeń.
```csharp
var manager = new ProjectServerManager(credentials);
```
## Krok 4: Zdefiniuj opcje zapisywania
Zdefiniuj dowolne opcje zapisywania swojego projektu. Można na przykład ustawić limit czasu operacji.
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## Krok 5: Utwórz lub zaktualizuj projekt
Na koniec utwórz lub zaktualizuj projekt na serwerze MS Project.
```csharp
manager.CreateNewProject(project, options);
```
Gratulacje! Pomyślnie zarządzałeś MS Project Server przy użyciu Aspose.Tasks dla .NET.

## Wniosek
W tym samouczku omówiliśmy, jak programowo zarządzać MS Project Server przy użyciu Aspose.Tasks dla .NET. Dzięki podanym krokom możesz bezproblemowo zintegrować Aspose.Tasks z aplikacjami .NET, aby zautomatyzować zadania zarządzania projektami na MS Project Server.
## Często zadawane pytania
### P: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project Server?
O: Aspose.Tasks obsługuje integrację z różnymi wersjami Microsoft Project Server, zapewniając kompatybilność w różnych środowiskach.
### P: Czy mogę wykonywać operacje zbiorcze na projektach przy użyciu Aspose.Tasks?
O: Tak, Aspose.Tasks umożliwia wykonywanie operacji zbiorczych, takich jak tworzenie, aktualizowanie i usuwanie projektów na MS Project Server.
### P: Czy Aspose.Tasks zapewnia wsparcie w zakresie planowania projektów i zarządzania zasobami?
Odpowiedź: Oczywiście, Aspose.Tasks oferuje kompleksowe wsparcie w zakresie planowania projektów, alokacji zasobów i funkcji zarządzania zadaniami.
### P: Czy można zautomatyzować zadania raportowania za pomocą Aspose.Tasks?
O: Tak, Aspose.Tasks umożliwia automatyzację generowania niestandardowych raportów na podstawie danych projektu, ułatwiając efektywne monitorowanie i analizę projektu.
### P: Czy mogę wypróbować Aspose.Tasks przed zakupem?
 Odp.: Tak, możesz poznać możliwości Aspose.Tasks, korzystając z bezpłatnej wersji próbnej z poziomu[strona internetowa](https://purchase.aspose.com/temporary-license/).