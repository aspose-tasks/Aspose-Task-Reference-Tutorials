---
title: Przeczytaj MS Project z Primavera za pomocą Aspose.Tasks dla Java
linktitle: Przeczytaj projekt z Primavera w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak bezproblemowo czytać pliki MS Project z Primavera XML za pomocą Aspose.Tasks dla Java. Zwiększ efektywność zarządzania projektami.
type: docs
weight: 20
url: /pl/java/project-management/read-primavera/
---
## Wstęp
zarządzaniu projektami interoperacyjność między różnymi platformami oprogramowania ma kluczowe znaczenie dla płynnego przepływu pracy. Aspose.Tasks dla Java zapewnia solidną funkcjonalność do odczytu plików Microsoft Project z Primavera XML. Ten samouczek poprowadzi Cię przez proces odczytywania plików MS Project z Primavera przy użyciu Aspose.Tasks dla Java, umożliwiając efektywne sprawdzenie właściwości specyficznych dla zadań Primavera.
## Warunki wstępne
Przed kontynuowaniem upewnij się, że masz zainstalowane i skonfigurowane następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK w swoim systemie.
2.  Aspose.Tasks dla Java: Pobierz i zainstaluj Aspose.Tasks dla Java z[Tutaj](https://releases.aspose.com/tasks/java/).

## Importuj pakiety
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Krok 1: Skonfiguruj katalog danych
```java
String dataDir = "Your Data Directory";
```
 Pamiętaj o wymianie`"Your Data Directory"` z rzeczywistą ścieżką do katalogu danych.
## Krok 2: Przeczytaj projekt z Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Pamiętaj o wymianie`"PrimaveraProject.xml"` z rzeczywistą nazwą pliku XML Primavera.
## Krok 3: Iteruj po zadaniach i pobieraj właściwości specyficzne dla Primavery
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Ten kod iteruje po każdym zadaniu w projekcie, drukując odpowiednie właściwości specyficzne dla Primavery.

## Wniosek
tym samouczku nauczyłeś się czytać pliki MS Project z Primavera XML przy użyciu Aspose.Tasks dla Java. Ta funkcjonalność umożliwia bezproblemową integrację i analizę danych projektowych na różnych platformach, zwiększając ogólną efektywność zarządzania projektami.
## Często zadawane pytania
### P: Czy mogę modyfikować właściwości zadań specyficzne dla Primavery przy użyciu Aspose.Tasks for Java?
O: Tak, Aspose.Tasks for Java udostępnia interfejsy API umożliwiające modyfikowanie właściwości zadań specyficznych dla Primavery w razie potrzeby.
### P: Czy Aspose.Tasks for Java obsługuje odczytywanie plików projektów w innych formatach?
O: Tak, Aspose.Tasks for Java obsługuje odczytywanie różnych formatów plików projektów, w tym MPP, XML i Primavera XML.
### P: Czy Aspose.Tasks for Java jest odpowiedni dla aplikacji do zarządzania projektami na poziomie przedsiębiorstwa?
O: Oczywiście, Aspose.Tasks dla Java oferuje solidne funkcje i skalowalność, dzięki czemu nadaje się do aplikacji do zarządzania projektami na poziomie przedsiębiorstwa.
### P: Czy mogę wyodrębnić informacje o zasobach z projektów Primavera przy użyciu Aspose.Tasks dla Java?
O: Tak, Aspose.Tasks for Java pozwala wyodrębnić informacje o zasobach wraz ze szczegółami zadań z projektów Primavera.
### P: Gdzie mogę znaleźć dodatkowe wsparcie lub dokumentację dla Aspose.Tasks dla Java?
 O: Obszerną dokumentację i dostęp do forów pomocy technicznej można znaleźć na stronie[Aspose.Tasks dla dokumentacji Java](https://reference.aspose.com/tasks/java/) strona.