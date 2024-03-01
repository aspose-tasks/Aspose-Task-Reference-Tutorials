---
title: Serwer Zapisz opcje MS Project dla Aspose.Tasks
linktitle: Opcje zapisu serwera Project dla Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zapisać opcje Microsoft Project dla Aspose.Tasks przy użyciu integracji z Project Server. Usprawnij przepływ pracy w zarządzaniu projektami.
type: docs
weight: 16
url: /pl/net/saving-options/project-server-save-options/
---
## Wstęp
W tym samouczku zajmiemy się zapisywaniem opcji programu Microsoft Project dla Aspose.Tasks przy użyciu programu Project Server. Aspose.Tasks to potężny interfejs API .NET, który umożliwia programistom programową pracę z plikami Microsoft Project. Wykorzystując możliwości Project Server, możemy bezproblemowo zintegrować Aspose.Tasks z naszymi przepływami pracy związanymi z zarządzaniem projektami. Ten samouczek przeprowadzi Cię przez proces krok po kroku.
## Warunki wstępne
Przed rozpoczęciem upewnij się, że spełnione są następujące wymagania wstępne:
1.  Aspose.Tasks dla .NET: Zainstaluj Aspose.Tasks dla .NET z[link do pobrania](https://releases.aspose.com/tasks/net/).
   
2. Dostęp do Project Server: Będziesz potrzebować poświadczeń dostępu i adresu URL swojej instancji Project Server. Jeśli go nie masz, możesz uzyskać bezpłatną wersję próbną od[Tutaj](https://releases.aspose.com/).
3. Plik Microsoft Project: Przygotuj plik Microsoft Project (.mpp), który chcesz zapisać za pomocą Aspose.Tasks.

## Importuj przestrzenie nazw
Najpierw musisz zaimportować niezbędne przestrzenie nazw do swojego projektu:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Krok 1: Zainicjuj projekt i poświadczenia
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://serwer_projektu.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Upewnij się, że wymieniłeś`"Your Document Directory"`, `URL`, `Domain`, `UserName` , I`Password` z Twoimi rzeczywistymi wartościami.
## Krok 2: Utwórz Menedżera serwera projektu
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Krok 3: Zdefiniuj opcje zapisywania
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Poprawić`ProjectGuid`, `ProjectName`, `Timeout` , I`PollingInterval` zgodnie z Twoimi wymaganiami.
## Krok 4: Zapisz projekt na serwerze
```csharp
manager.CreateNewProject(project, options);
```
Spowoduje to zapisanie projektu na serwerze Project Server z określonymi opcjami.

## Wniosek
W tym samouczku dowiedzieliśmy się, jak zapisać opcje Microsoft Project dla Aspose.Tasks przy użyciu integracji z Project Server. Wykonując te kroki, możesz bezproblemowo włączyć Aspose.Tasks do przepływów pracy związanych z zarządzaniem projektami, zwiększając wydajność i produktywność.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks z różnymi wersjami Microsoft Project?
O: Tak, Aspose.Tasks obsługuje różne wersje Microsoft Project, zapewniając kompatybilność w różnych środowiskach.
### P: Czy dostępna jest wersja próbna Aspose.Tasks?
 Odp.: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks z[Tutaj](https://releases.aspose.com/).
### P: Czy Aspose.Tasks obsługuje wielowątkowość?
O: Tak, Aspose.Tasks zaprojektowano tak, aby był bezpieczny dla wątków i umożliwiał równoczesny dostęp do danych projektu.
### P: Czy mogę dostosować opcje zapisywania podczas korzystania z integracji z serwerem Project Server?
O: Tak, możesz dostosować opcje zapisywania, takie jak nazwa projektu, limit czasu i interwał odpytywania, do własnych wymagań.
### P: Gdzie mogę znaleźć wsparcie dla Aspose.Tasks?
 Odp.: Wsparcie i pomoc można znaleźć na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).