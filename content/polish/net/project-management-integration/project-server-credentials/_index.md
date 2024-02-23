---
title: Zarządzanie poświadczeniami serwera MS Project w Aspose.Tasks
linktitle: Zarządzanie poświadczeniami serwera projektu w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak płynnie zarządzać poświadczeniami MS Project Server za pomocą Aspose.Tasks dla .NET. Zwiększ efektywność zarządzania projektami.
type: docs
weight: 22
url: /pl/net/project-management-integration/project-server-credentials/
---
## Wstęp
zarządzaniu projektami skuteczna koordynacja i płynna komunikacja mają kluczowe znaczenie dla pomyślnej realizacji projektu. Aspose.Tasks dla .NET zapewnia kompleksowe rozwiązanie do zarządzania poświadczeniami Microsoft Project Server, umożliwiając użytkownikom bezpieczny dostęp i manipulowanie danymi projektu. Ten samouczek omawia proces zarządzania poświadczeniami MS Project Server przy użyciu Aspose.Tasks dla .NET, prowadząc użytkowników przez każdy krok, aby zapewnić płynne działanie.
## Warunki wstępne
Przed wyruszeniem w podróż zarządzania poświadczeniami MS Project Server za pomocą Aspose.Tasks dla .NET upewnij się, że spełnione są następujące wymagania wstępne:
### 1. Instalacja Aspose.Tasks dla .NET
 Aby rozpocząć, pobierz i zainstaluj Aspose.Tasks dla .NET z dostarczonego oprogramowania[link do pobrania](https://releases.aspose.com/tasks/net/), Postępuj zgodnie z instrukcjami instalacji, aby bezproblemowo zintegrować bibliotekę ze środowiskiem .NET.
### 2. Dane dostępowe
Zbierz niezbędne dane uwierzytelniające wymagane do uzyskania dostępu do serwera MS Project. Obejmuje to adres domeny SharePoint, nazwę użytkownika i hasło powiązane z serwerem Project Server.

## Importuj przestrzenie nazw
W swoim projekcie .NET zaimportuj wymagane przestrzenie nazw, aby efektywnie wykorzystać funkcjonalności zapewniane przez Aspose.Tasks dla .NET.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## Krok 1: Zdefiniuj ścieżkę katalogu dokumentu
```csharp
String DataDir = "Your Document Directory";
```
## Krok 2: Ustaw adres domeny SharePoint, nazwę użytkownika i hasło
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## Krok 3: Utwórz poświadczenia serwera Project Server
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Krok 4: Załaduj plik projektu
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Krok 5: Zainicjuj Menedżera serwera projektu
```csharp
var manager = new ProjectServerManager(credentials);
```
## Krok 6: Utwórz nowy projekt
```csharp
manager.CreateNewProject(newProject);
```
## Krok 7: Pobierz listę projektów
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Krok 8: Iteruj po liście projektów
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Wniosek
Efektywne zarządzanie poświadczeniami serwera MS Project Server ma kluczowe znaczenie dla usprawnienia zarządzania projektami. Aspose.Tasks dla .NET upraszcza ten proces, zapewniając solidny zestaw funkcjonalności. Postępując zgodnie z przewodnikiem krok po kroku opisanym w tym samouczku, użytkownicy mogą bezproblemowo zintegrować Aspose.Tasks dla .NET ze swoimi projektami, zapewniając bezpieczny dostęp i manipulację danymi projektu.
## Często zadawane pytania
### P: Czy Aspose.Tasks for .NET jest kompatybilny ze wszystkimi wersjami Microsoft Project Server?
Odp.: Aspose.Tasks dla .NET został zaprojektowany tak, aby był kompatybilny z różnymi wersjami Microsoft Project Server, zapewniając użytkownikom wszechstronność i elastyczność.
### P: Czy mogę zintegrować Aspose.Tasks for .NET z moim istniejącym projektem .NET?
O: Tak, Aspose.Tasks for .NET można bezproblemowo zintegrować z istniejącymi projektami .NET, ułatwiając efektywne zarządzanie projektami.
### P: Czy Aspose.Tasks dla .NET zapewnia obsługę dostępu do zasobów projektu?
Odpowiedź: Oczywiście, Aspose.Tasks dla .NET oferuje kompleksowe wsparcie w zakresie dostępu do zasobów projektu i manipulowania nimi, zwiększając efektywność zarządzania projektami.
### P: Czy są dostępne opcje licencjonowania dla Aspose.Tasks dla .NET?
O: Tak, Aspose.Tasks dla .NET oferuje elastyczne opcje licencjonowania, w tym licencje tymczasowe do celów próbnych i licencje pełne do użytku komercyjnego.
### P: Gdzie mogę szukać pomocy lub wsparcia dla Aspose.Tasks dla .NET?
 Odp.: W przypadku jakichkolwiek pytań lub pomocy dotyczącej Aspose.Tasks dla .NET możesz odwiedzić forum pomocy technicznej pod adresem[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Kompletny kod źródłowy