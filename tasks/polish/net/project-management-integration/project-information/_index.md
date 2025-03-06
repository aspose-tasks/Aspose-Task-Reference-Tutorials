---
title: Wyodrębnij informacje o projekcie MS w Aspose.Tasks
linktitle: Wyodrębnianie informacji o projekcie w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak bez wysiłku wyodrębnić informacje MS Project za pomocą Aspose.Tasks dla .NET. Zapoznaj się z naszym obszernym samouczkiem.
type: docs
weight: 20
url: /pl/net/project-management-integration/project-information/
---
## Wstęp
Czy chcesz efektywnie wyodrębniać informacje z plików Microsoft Project za pomocą Aspose.Tasks dla .NET? W tym samouczku przeprowadzimy Cię krok po kroku przez ten proces. Zanim jednak zagłębimy się w szczegóły implementacji, upewnijmy się najpierw, że masz wszystko, czego potrzebujesz.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
### 1. Aspose.Tasks dla .NET
 Upewnij się, że zainstalowałeś bibliotekę Aspose.Tasks dla .NET. Jeśli jeszcze tego nie zrobiłeś, możesz pobrać go ze strony[Aspose.Tasks dla witryny .NET](https://releases.aspose.com/tasks/net/).
### 2. Poświadczenia dla SharePoint
Będziesz potrzebować poświadczeń, aby uzyskać dostęp do SharePoint, w którym przechowywane są Twoje pliki MS Project. Upewnij się, że masz następujące informacje:
- Adres domeny SharePoint
- Nazwa użytkownika
- Hasło
## Importowanie przestrzeni nazw
Po ustaleniu wymagań wstępnych nadszedł czas na zaimportowanie niezbędnych przestrzeni nazw do projektu.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Podzielmy teraz proces wyodrębniania informacji MS Project na wiele etapów.
## Krok 1: Podaj dane uwierzytelniające
Najpierw musisz podać swoje poświadczenia programu SharePoint, aby uzyskać dostęp do serwera Project Server.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Krok 2: Zainicjuj Menedżera serwera projektu
 Następnie zainicjuj a`ProjectServerManager` instancję z podanymi poświadczeniami.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Krok 3: Pobierz listę projektów
Teraz możesz pobrać listę projektów z serwera Project Server.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Krok 4: Wydrukuj informacje o projekcie
Na koniec przejrzyj listę projektów i wydrukuj zawarte w nich informacje.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się wyodrębniać informacje MS Project przy użyciu Aspose.Tasks dla .NET. Dzięki tej wiedzy możesz teraz bezproblemowo zintegrować tę funkcjonalność z aplikacjami .NET.
## Często zadawane pytania
### P1: Czy mogę używać Aspose.Tasks dla .NET z dowolną wersją Microsoft Project?
Odp.: Tak, Aspose.Tasks dla .NET obsługuje różne wersje Microsoft Project, w tym 2003, 2007, 2010, 2013, 2016 i 2019.
### P2: Czy Aspose.Tasks dla .NET jest kompatybilny zarówno z platformami Windows, jak i Linux?
Odp.: Tak, Aspose.Tasks dla .NET jest kompatybilny zarówno z platformami Windows, jak i Linux, dzięki czemu jest wszechstronny w różnych środowiskach programistycznych.
### P3: Czy mogę wyodrębnić zależności zadań za pomocą Aspose.Tasks dla .NET?
Odp.: Absolutnie! Aspose.Tasks dla .NET zapewnia solidną funkcjonalność umożliwiającą wyodrębnienie nie tylko podstawowych informacji o projekcie, ale także zależności zadań i innych skomplikowanych szczegółów.
### P4: Czy Aspose.Tasks dla .NET oferuje wsparcie techniczne?
 Odp.: Tak, możesz uzyskać pomoc techniczną dla Aspose.Tasks dla .NET poprzez[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), gdzie możesz zadawać pytania i szukać pomocy ekspertów.
### P5: Czy mogę wypróbować Aspose.Tasks dla .NET przed zakupem?
 Odp.: Oczywiście! Możesz skorzystać z bezpłatnej wersji próbnej Aspose.Tasks dla .NET w witrynie[strona z wydaniami](https://releases.aspose.com/), dzięki czemu możesz zapoznać się z jego funkcjami przed podjęciem decyzji o zakupie.