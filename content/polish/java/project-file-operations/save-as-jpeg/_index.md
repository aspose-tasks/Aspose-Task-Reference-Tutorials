---
title: Konwertuj projekt MS jako JPEG w Aspose.Tasks
linktitle: Zapisz projekt jako JPEG w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak łatwo konwertować pliki Microsoft Project na obrazy JPEG za pomocą Aspose.Tasks dla Java. Zwiększ swoją produktywność.
type: docs
weight: 20
url: /pl/java/project-file-operations/save-as-jpeg/
---
## Wstęp
W tym samouczku dowiemy się, jak zapisać plik Microsoft Project jako obraz JPEG przy użyciu Aspose.Tasks dla Java. Może to być szczególnie przydatne przy udostępnianiu wizualizacji projektów lub integrowaniu danych projektu z raportami lub prezentacjami.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowana Java. Możesz pobrać i zainstalować najnowszą wersję ze strony[witryna internetowa Java](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks dla Java: Pobierz i skonfiguruj Aspose.Tasks dla Java, postępując zgodnie z instrukcjami podanymi w[dokumentacja](https://reference.aspose.com/tasks/java/).

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety do pliku Java:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## Krok 1: Zdefiniuj katalog danych
Ustaw ścieżkę do katalogu danych, w którym znajduje się plik MS Project.
```java
String dataDir = "Your Data Directory";
```
## Krok 2: Załaduj plik projektu MS
Załaduj plik MS Project za pomocą Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## Krok 3: Skonfiguruj jakość JPEG (opcjonalnie)
 Jeśli chcesz dostosować jakość JPEG, możesz to ustawić za pomocą`ImageSaveOptions` klasa. Jakość waha się od 0 do 100.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Ustaw jakość JPEG na 50
```
## Krok 4: Zapisz projekt jako JPEG
Zapisz plik MS Project jako obraz JPEG.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Wniosek
tym samouczku nauczyliśmy się, jak zapisać plik Microsoft Project jako obraz JPEG przy użyciu Aspose.Tasks dla Java. Ta funkcja pozwala na łatwe udostępnianie i integrowanie danych projektu z różnymi dokumentami i prezentacjami.
## Często zadawane pytania
### P: Czy mogę dostosować jakość obrazu JPEG?
 Odp.: Tak, możesz dostosować jakość za pomocą`setJpegQuality()` metoda, w zakresie od 0 do 100.
### P: Co się stanie, jeśli nie określę jakości JPEG?
Odp.: Jeśli nie określisz jakości, zostanie użyta jakość domyślna.
### P: Czy korzystanie z Aspose.Tasks dla Java jest bezpłatne?
 O: Aspose.Tasks for Java to biblioteka komercyjna, ale możesz poznać jej funkcje w ramach bezpłatnej wersji próbnej. Odwiedzić[bezpłatna strona próbna](https://releases.aspose.com/) po więcej informacji.
### P: Gdzie mogę uzyskać pomoc dotyczącą Aspose.Tasks dla Java?
Odp.: Możesz uzyskać pomoc na forum społeczności Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).
### P: Czy mogę kupić tymczasową licencję na Aspose.Tasks?
 Odpowiedź: Tak, możesz kupić tymczasową licencję od[Tutaj](https://purchase.aspose.com/temporary-license/).