---
title: Bezproblemowy odczyt danych online MS Project za pomocą Aspose.Tasks
linktitle: Odczytywanie danych projektu online w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak bez wysiłku czytać dane Microsoft Project Online za pomocą Aspose.Tasks dla Java. Zwiększ swoje możliwości zarządzania projektami.
type: docs
weight: 13
url: /pl/java/project-data-reading/read-project-online/
---
## Wstęp
dziedzinie zarządzania projektami wydajna obsługa danych Microsoft Project Online ma kluczowe znaczenie dla usprawnienia operacji. Aspose.Tasks dla Java zapewnia solidne rozwiązanie do łatwego odczytu takich danych. W tym samouczku szczegółowo opisano wykorzystanie Aspose.Tasks do płynnego uzyskiwania dostępu do danych MS Project Online i manipulowania nimi.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że posiadasz następujące elementy:
1. Zestaw Java Development Kit (JDK): zainstaluj pakiet JDK, aby kompilować i uruchamiać programy w języku Java.
2.  Aspose.Tasks dla biblioteki Java: Pobierz i dołącz bibliotekę Aspose.Tasks do swojego projektu Java. Można go nabyć od[Tutaj](https://releases.aspose.com/tasks/java/).
3. Konto Microsoft Project Online: Uzyskaj ważne poświadczenia umożliwiające dostęp do danych MS Project Online.
4. Adres domeny SharePoint: Adres domeny SharePoint, w której znajdują się dane MS Project Online.
5. Nazwa użytkownika i hasło: Poświadczenia umożliwiające uwierzytelnienie dostępu do MS Project Online.
## Importuj pakiety
W swoim projekcie Java zaimportuj niezbędne pakiety Aspose.Tasks, aby zapewnić bezproblemową integrację:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Krok 1: Ustaw adres domeny SharePoint, nazwę użytkownika i hasło
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 Zastępować`"https://contoso.sharepoint.com"` z adresem Twojej domeny SharePoint,`"admin@contoso.onmicrosoft.com"` z Twoją nazwą użytkownika i`"MyPassword"` swoim hasłem.
## Krok 2: Uwierzytelnij się przy użyciu poświadczeń serwera Project Server
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 Tworzyć`ProjectServerCredentials` obiekt z adresem domeny SharePoint, nazwą użytkownika i hasłem. Następnie zainicjuj`ProjectServerManager` z tymi referencjami.
## Krok 3: Pobierz listę projektów i wyświetl informacje
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 Wykonaj iterację po liście projektów uzyskanej z`reader.getProjectList()` i wyświetlaj szczegóły projektu, takie jak nazwa, data utworzenia i data ostatniego zapisania.
## Krok 4: Załaduj poszczególne projekty i liczbę zasobów wyjściowych
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 Dla każdego projektu załaduj go za pomocą`reader.getProject(p.getId())` i wypisz nazwę projektu wraz z liczbą powiązanych zasobów.

## Wniosek
Aspose.Tasks for Java upraszcza proces odczytu danych MS Project Online, oferując programistom potężny zestaw narzędzi usprawniających zadania związane z zarządzaniem projektami. Postępując zgodnie z tym samouczkiem, możesz efektywnie zintegrować Aspose.Tasks z aplikacjami Java, aby z łatwością uzyskać dostęp do danych projektu i manipulować nimi.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks for Java do modyfikowania danych MS Project Online?
O: Tak, Aspose.Tasks zapewnia szerokie możliwości nie tylko odczytywania, ale także programowego modyfikowania danych MS Project Online.
### P: Czy Aspose.Tasks obsługuje inne formaty plików do zarządzania projektami?
Odp.: Oczywiście, Aspose.Tasks obsługuje różne formaty plików, w tym MPP, XML i inne, zapewniając kompatybilność z różnorodnymi systemami zarządzania projektami.
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla Java?
 Odpowiedź: Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/) aby poznać funkcje i funkcjonalności Aspose.Tasks.
### P: Gdzie mogę znaleźć obszerną dokumentację Aspose.Tasks dla Java?
 Odp.: Możesz zapoznać się ze szczegółową dokumentacją[Tutaj](https://reference.aspose.com/tasks/java/)aby uzyskać kompleksowe wskazówki dotyczące wykorzystania Aspose.Tasks w projektach Java.
### P: Jakie opcje wsparcia są dostępne dla Aspose.Tasks dla Java?
 Odp.: Jeśli napotkasz jakiekolwiek problemy lub masz pytania, możesz zwrócić się o pomoc na forum społeczności Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).