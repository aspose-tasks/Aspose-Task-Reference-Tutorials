---
title: Skala szybkości odczytu i zapisu dla przydziałów zasobów w Aspose.Tasks
linktitle: Skala szybkości odczytu i zapisu dla przydziałów zasobów w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak skutecznie zarządzać skalą przydziału zasobów w Aspose.Tasks dla Java, korzystając z tego wszechstronnego samouczka.
weight: 20
url: /pl/java/resource-assignments/read-write-rate-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skala szybkości odczytu i zapisu dla przydziałów zasobów w Aspose.Tasks

## Wstęp
W tym samouczku zagłębimy się w zarządzanie skalą przydziału zasobów przy użyciu Aspose.Tasks dla Java, solidnej biblioteki do programowej pracy z plikami Microsoft Project. Wykonując poniższe kroki, będziesz mógł efektywnie manipulować ustawieniami skali szybkości przydziałów zasobów w aplikacjach Java.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Środowisko programistyczne Java: Upewnij się, że w systemie jest zainstalowany zestaw Java Development Kit (JDK).
2.  Aspose.Tasks for Java Library: Pobierz i zainstaluj bibliotekę Aspose.Tasks for Java z[Tutaj](https://releases.aspose.com/tasks/java/).

## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety, aby móc pracować z funkcjonalnościami Aspose.Tasks. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## Krok 1: Skonfiguruj swój projekt
Zacznij od skonfigurowania projektu Java i dołącz bibliotekę Aspose.Tasks do swoich zależności.
## Krok 2: Załaduj plik projektu
Załaduj plik projektu, z którym chcesz pracować, do aplikacji Java.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Krok 3: Dodaj zadanie
Dodaj nowe zadanie do swojego projektu.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Krok 4: Zdefiniuj zasoby
Zdefiniuj zasoby materialne i niematerialne oraz określ ich rodzaje.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Krok 5: Przypisz zasoby do zadania
Przypisz do zadania wcześniej zdefiniowane zasoby wraz z rodzajami skali stawek.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Krok 6: Zapisz projekt
Zapisz projekt ze zmodyfikowanymi przypisaniami zasobów.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Krok 7: Pobierz przypisania zasobów
Załaduj ponownie zapisany projekt i pobierz przydziały zasobów, aby zweryfikować ustawienia skali stawek.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Wniosek
Zarządzanie skalą przydziału zasobów w Aspose.Tasks dla Java jest kluczowe dla efektywnego zarządzania projektami. Postępując zgodnie z tym przewodnikiem krok po kroku, można bezproblemowo manipulować ustawieniami skali szybkości przydziałów zasobów w aplikacjach Java.
## Często zadawane pytania
### P1: Czy mogę używać Aspose.Tasks dla Java z dowolnym IDE Java?
O: Tak, Aspose.Tasks for Java jest kompatybilny ze wszystkimi głównymi środowiskami IDE Java, w tym IntelliJ IDEA, Eclipse i NetBeans.
### P2: Czy Aspose.Tasks obsługuje inne formaty plików oprócz MPP?
Odp.: Tak, Aspose.Tasks obsługuje różne formaty plików, w tym MPP, XML i HTML.
### P3: Czy Aspose.Tasks nadaje się do zarządzania projektami na poziomie przedsiębiorstwa?
Odpowiedź: Oczywiście, Aspose.Tasks oferuje kompleksowe funkcje do zarządzania projektami o dowolnej skali, dzięki czemu nadaje się do zarządzania projektami na poziomie przedsiębiorstwa.
### P4: Czy mogę bardziej dostosować przydział zasobów poza skalą stawek?
O: Tak, Aspose.Tasks zapewnia szerokie możliwości dostosowywania przydziału zasobów, w tym dostosowywania kosztów, pracy i czasu trwania.
### P5: Czy istnieje forum społecznościowe dla wsparcia Aspose.Tasks?
 O: Tak, możesz znaleźć wsparcie i kontaktować się z innymi użytkownikami na forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
