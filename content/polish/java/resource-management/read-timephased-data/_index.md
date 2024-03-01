---
title: Przeczytaj dane okresowe dotyczące zasobów w Aspose.Tasks
linktitle: Przeczytaj dane okresowe dotyczące zasobów w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak wyodrębnić dane okresowe z zasobów MS Project za pomocą Aspose.Tasks dla Java. Samouczek krok po kroku.
type: docs
weight: 15
url: /pl/java/resource-management/read-timephased-data/
---
## Wstęp
W tym samouczku przeprowadzimy Cię przez proces odczytywania danych okresowych dla zasobów MS Project przy użyciu Aspose.Tasks dla Java. Ta biblioteka zapewnia zaawansowane funkcje do programowego zarządzania plikami Microsoft Project.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK w swoim systemie. Można go pobrać z[strona internetowa](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) i postępuj zgodnie z instrukcją instalacji.
2.  Biblioteka Aspose.Tasks for Java: Pobierz bibliotekę Aspose.Tasks for Java z witryny[strona pobierania](https://releases.aspose.com/tasks/java/) i postępuj zgodnie z instrukcjami instalacji zawartymi w dokumentacji.

## Importuj pakiety
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Krok 1: Skonfiguruj katalog danych
Najpierw zdefiniuj katalog, w którym znajduje się plik MS Project.
```java
String dataDir = "Your Data Directory";
```
## Krok 2: Przeczytaj plik szablonu projektu MS Project
Określ nazwę pliku szablonu MS Project.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Krok 3: Przeczytaj plik wejściowy jako projekt
Przeczytaj plik wejściowy za pomocą Aspose.Tasks i załaduj go jako obiekt projektu.
```java
Project project = new Project(dataDir + fileName);
```
## Krok 4: Uzyskaj zasób według identyfikatora
Pobierz żądany zasób z projektu według jego unikalnego identyfikatora (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Krok 5: Wydrukuj dane okresowe dotyczące pracy z zasobami
Wydrukuj dane okresowe dotyczące pracy zasobów.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Krok 6: Wydrukuj dane okresowe dotyczące kosztów zasobów
Wydrukuj dane okresowe dotyczące kosztów zasobów.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Wniosek
W tym samouczku nauczyliśmy się czytać dane okresowe dla zasobów MS Project za pomocą Aspose.Tasks dla Java. Wykonując poniższe kroki, możesz efektywnie i programowo wyodrębnić cenne informacje z plików projektu.
## Często zadawane pytania
### Czy Aspose.Tasks może obsługiwać inne typy plików projektu oprócz Microsoft Project?
Tak, Aspose.Tasks obsługuje różne formaty plików, w tym MPP, XML i CSV.
### Czy Aspose.Tasks jest kompatybilny z różnymi środowiskami programistycznymi Java?
Tak, Aspose.Tasks jest kompatybilny ze wszystkimi głównymi środowiskami IDE i frameworkami Java.
### Czy mogę manipulować danymi projektu za pomocą Aspose.Tasks?
Absolutnie Aspose.Tasks zapewnia rozbudowane interfejsy API do tworzenia, modyfikowania i analizowania danych projektu.
### Czy Aspose.Tasks nadaje się do projektów na poziomie przedsiębiorstwa?
Tak, Aspose.Tasks jest szeroko stosowany w środowiskach korporacyjnych ze względu na jego niezawodność i skalowalność.
### Gdzie mogę znaleźć pomoc, jeśli napotkam problemy podczas korzystania z Aspose.Tasks?
 Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) o pomoc ze strony społeczności i zespołu wsparcia.