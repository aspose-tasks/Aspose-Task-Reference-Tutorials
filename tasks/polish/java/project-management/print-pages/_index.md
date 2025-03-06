---
title: Drukuj strony, aby oddzielić obraz w Aspose.Tasks
linktitle: Drukuj strony, aby oddzielić obraz w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak drukować strony w celu oddzielenia obrazów w Aspose.Tasks dla Java. Popraw wizualizację projektu dzięki temu przewodnikowi krok po kroku.
type: docs
weight: 22
url: /pl/java/project-management/print-pages/
---
## Wstęp
W tym samouczku przeprowadzimy Cię przez proces drukowania stron w celu oddzielenia obrazów przy użyciu Aspose.Tasks dla Java. Ta funkcjonalność może być szczególnie przydatna, gdy trzeba osobno wizualizować układy projektu lub krytyczne zadania.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany pakiet JDK. Można go pobrać z[Tutaj](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Biblioteka Aspose.Tasks for Java: Pobierz i dołącz bibliotekę Aspose.Tasks for Java do swojego projektu. Możesz to dostać od[Tutaj](https://releases.aspose.com/tasks/java/).

## Importuj pakiety
Pamiętaj, aby zaimportować niezbędne pakiety na początku pliku Java:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## Krok 1: Załaduj dane projektu
Najpierw załaduj dane projektu z pliku MPP:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## Krok 2: Ustaw opcje zapisywania obrazu
Zdefiniuj opcje zapisywania obrazu, w tym datę początkową, datę końcową, zadania krytyczne, legendę i linie siatki:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## Krok 3: Dostosuj linie siatki
Dostosuj linie siatki obrazu, określając typ, kolor i wzór:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## Krok 4: Zapisz obrazy
Zapisz układ projektu jako obrazy, zarówno jako pojedynczy plik, jak i osobne pliki:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## Wniosek
W tym samouczku pokazaliśmy, jak drukować strony w celu oddzielenia obrazów za pomocą Aspose.Tasks dla Java. Wykonując kroki opisane powyżej, możesz efektywnie wizualizować układy projektu i krytyczne zadania zgodnie ze swoimi wymaganiami.
## Często zadawane pytania
### P: Czy mogę dostosować format obrazu podczas zapisywania układów projektu?
 O: Tak, Aspose.Tasks for Java obsługuje różne formaty obrazów, takie jak PNG, JPEG, BMP itp. Możesz określić żądany format w`ImageSaveOptions` klasa.
### P: Czy Aspose.Tasks for Java jest kompatybilny z różnymi środowiskami programistycznymi Java?
Odp.: Tak, Aspose.Tasks for Java jest kompatybilny z większością środowisk programistycznych Java, w tym Eclipse, IntelliJ IDEA i NetBeans.
### P: Czy mogę zintegrować Aspose.Tasks for Java z moim projektem Maven lub Gradle?
O: Tak, możesz łatwo zintegrować Aspose.Tasks for Java ze swoim projektem Maven lub Gradle, dodając odpowiednią zależność w swoim`pom.xml` Lub`build.gradle` plik.
### P: Czy Aspose.Tasks for Java obsługuje eksport danych projektu do innych formatów niż obrazy?
O: Tak, Aspose.Tasks for Java obsługuje eksport danych projektu do różnych formatów, takich jak PDF, HTML, XLSX itp., zapewniając elastyczność w wizualizacji danych i raportowaniu.
### P: Czy jest dostępne wsparcie społeczności dla Aspose.Tasks dla Java?
 O: Tak, możesz znaleźć wsparcie społeczności, zadawać pytania i kontaktować się z innymi użytkownikami na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).