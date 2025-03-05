---
title: Generuj dane okresowe w Aspose.Tasks
linktitle: Generuj dane okresowe dla przydziałów zasobów w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak generować dane okresowe dla przydziałów zasobów za pomocą Aspose.Tasks dla Java. Popraw efektywność zarządzania projektami dzięki temu kompleksowemu przewodnikowi.
type: docs
weight: 24
url: /pl/java/resource-assignments/timephased-data-generation/
---
## Wstęp
W tym samouczku omówimy proces generowania danych okresowych dla przydziałów zasobów przy użyciu Aspose.Tasks dla Java. Dane okresowe zapewniają cenny wgląd w alokację zasobów w czasie w ramach projektu, pomagając kierownikom projektów w podejmowaniu świadomych decyzji.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany pakiet JDK. Możesz pobrać i zainstalować JDK z[Tutaj](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Biblioteka Aspose.Tasks dla Java: Musisz mieć bibliotekę Aspose.Tasks dla Java. Można go pobrać z[strona internetowa](https://releases.aspose.com/tasks/java/).

## Importuj pakiety
Najpierw zaimportujmy niezbędne pakiety do pracy z Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Krok 1: Przeczytaj źródłowy plik MPP
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Data Directory";
// Przeczytaj źródłowy plik MPP
Project project = new Project(dataDir + "project.mpp");
```
## Krok 2: Uzyskaj przydział zadań i zasobów
```java
// Zdobądź pierwsze zadanie projektu
Task task = project.getRootTask().getChildren().getById(1);
// Uzyskaj pierwsze przypisanie zasobu projektu
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Krok 3: Wygeneruj dane okresowe z płaskim konturem
```java
// Kontur płaski jest konturem domyślnym
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 4: Zmień kontur na żółwia
```java
// Zmień kontur na Żółwia
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 5: Zmień kontur na BackLoaded
```java
// Zmień kontur na BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 6: Zmień kontur na FrontLoaded
```java
// Zmień kontur na FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 7: Zmień kontur na Bell
```java
// Zmień kontur na Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 8: Zmień kontur na EarlyPeak
```java
// Zmień kontur na EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 9: Zmień kontur na LatePeak
```java
// Zmień kontur na LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Krok 10: Zmień kontur na DoublePeak
```java
// Zmień kontur na DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wniosek
tym samouczku omówiliśmy sposób generowania danych okresowych dla przydziałów zasobów przy użyciu Aspose.Tasks dla Java. Zrozumienie różnych schematów pracy może pomóc kierownikom projektów w skutecznym zarządzaniu alokacją zasobów i harmonogramem w ich projektach.
## Często zadawane pytania
### Czy mogę używać Aspose.Tasks z innymi bibliotekami Java?
Tak, Aspose.Tasks można zintegrować z innymi bibliotekami Java w celu zwiększenia możliwości zarządzania projektami.
### Czy Aspose.Tasks nadaje się do projektów korporacyjnych na dużą skalę?
Absolutnie Aspose.Tasks jest przeznaczony do obsługi projektów dowolnej wielkości, w tym projektów korporacyjnych na dużą skalę.
### Czy Aspose.Tasks zapewnia obsługę różnych formatów plików projektów?
Tak, Aspose.Tasks obsługuje różne formaty plików projektów, w tym MPP, XML i MPX.
### Czy mogę dostosować kontury pracy zgodnie z wymaganiami mojego projektu?
Tak, Aspose.Tasks pozwala użytkownikom definiować niestandardowe kontury pracy, aby odpowiadały ich konkretnym potrzebom projektowym.
### Czy istnieje forum społeczności, na którym mogę uzyskać pomoc dotyczącą Aspose.Tasks?
 Tak, możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za wsparcie i dyskusje.