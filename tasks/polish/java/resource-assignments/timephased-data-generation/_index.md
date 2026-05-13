---
date: 2026-01-10
description: Dowiedz się, jak zmienić kontur i wygenerować dane czasowe dla przydziałów
  zasobów przy użyciu Aspose.Tasks dla Javy, zwiększając efektywność zarządzania projektami.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak zmienić kontur w Aspose.Tasks dla danych czasowo‑fazowych
url: /pl/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zmienić kontur w Aspose.Tasks dla danych czasowych

## Wprowadzenie
W tym samouczku dowiesz się **jak zmienić kontur** dla przydziału zasobów i wygenerować dane czasowe przy użyciu Aspose.Tasks dla Javy. Dane czasowe ukazują rozkład pracy w czasie trwania projektu, umożliwiając precyzyjne dostosowanie harmonogramów, zrównoważenie obciążeń i podejmowanie decyzji opartych na danych.

## Szybkie odpowiedzi
- **Co to jest kontur?** Kontur pracy definiuje, jak wysiłek jest rozłożony w czasie trwania zadania (np. Płaski, Żółw, Dzwon).  
- **Dlaczego zmienić kontur?** Aby odzwierciedlić realistyczne wzorce pracy, takie jak przydzielanie wysiłku na początek lub koniec.  
- **Jakiej biblioteki wymaga?** Aspose.Tasks dla Javy (dowolna aktualna wersja).  
- **Czy potrzebna jest licencja?** Tak, ważna licencja Aspose.Tasks jest wymagana do użytku produkcyjnego.  
- **Czy mogę zobaczyć wyniki w konsoli?** Przykład wypisuje daty rozpoczęcia i wartości dla każdego segmentu czasowego.

## Co oznacza „jak zmienić kontur”?
Zmiana konturu oznacza aktualizację właściwości `WORK_CONTOUR` obiektu `ResourceAssignment`. Aspose.Tasks obsługuje kilka predefiniowanych konturów (Flat, Turtle, Bell itp.), które wpływają na sposób przydzielania pracy w czasie.

## Dlaczego używać Aspose.Tasks do generowania danych czasowych?
- **Dokładne raportowanie:** Eksport precyzyjnego rozkładu pracy dla narzędzi raportujących.  
- **Planowanie scenariuszy:** Testowanie różnych konturów bez modyfikacji pierwotnego harmonogramu.  
- **Automatyzacja:** Integracja z pipeline'ami CI w celu automatycznej weryfikacji stanu projektu.

## Prerequisites
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania:
1. Java Development Kit (JDK): Upewnij się, że masz zainstalowany JDK w systemie. Możesz pobrać i zainstalować JDK z [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Biblioteka Aspose.Tasks dla Javy: Musisz posiadać bibliotekę Aspose.Tasks dla Javy. Możesz ją pobrać ze [website](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
First, let's import the necessary packages to work with Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Krok 1: Odczyt pliku źródłowego MPP
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Krok 2: Pobranie zadania i przydziału zasobu
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Jak zmienić kontur – Płaski (domyślny)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – Żółw
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – Załadowany od tyłu
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – Załadowany od przodu
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – Dzwon
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – Wczesny szczyt
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – Późny szczyt
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – Podwójny szczyt
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Typowe problemy i wskazówki
- **Kontur nie aktualizuje się?** Upewnij się, że wywołujesz `firstRA.set(Asn.WORK_CONTOUR, …)` *przed* pobraniem danych czasowych.
- **Nieoczekiwane wartości?** Sprawdź, czy daty rozpoczęcia i zakończenia zadania są poprawnie ustawione w źródłowym pliku MPP.
- **Wskazówka dotycząca wydajności:** Ponownie używaj tej samej instancji `Project` przy iteracji przez wiele konturów, aby uniknąć niepotrzebnego I/O plików.

## FAQ
### Czy mogę używać Aspose.Tasks z innymi bibliotekami Javy?
Tak, Aspose.Tasks może być integrowany z innymi bibliotekami Javy w celu rozszerzenia możliwości zarządzania projektami.

### Czy Aspose.Tasks jest odpowiedni dla dużych projektów korporacyjnych?
Zdecydowanie, Aspose.Tasks jest zaprojektowany do obsługi projektów każdej wielkości, w tym dużych inicjatyw korporacyjnych.

### Czy Aspose.Tasks zapewnia obsługę różnych formatów plików projektowych?
Tak, Aspose.Tasks obsługuje różnorodne formaty, takie jak MPP, XML i MPX.

### Czy mogę dostosować kontury pracy do wymagań mojego projektu?
Tak, możesz definiować niestandardowe kontury pracy, aby dopasować je do konkretnych potrzeb harmonogramowania.

### Czy istnieje forum społeczności, gdzie mogę uzyskać pomoc w sprawie Aspose.Tasks?
Tak, możesz odwiedzić [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) aby uzyskać wsparcie i dyskusje.

---

**Last Updated:** 2026-01-10  
**Testowano z:** Aspose.Tasks dla Javy (najnowsze wydanie)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}