---
title: Zatrzymaj i wznów zadanie w Aspose.Tasks
linktitle: Zatrzymaj i wznów zadanie w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Odkryj moc Aspose.Tasks dla Java, korzystając z naszego przewodnika krok po kroku dotyczącego zatrzymywania i wznawiania zadań. Ulepsz zarządzanie projektami bezproblemowo!
weight: 30
url: /pl/java/task-properties/stop-resume-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zatrzymaj i wznów zadanie w Aspose.Tasks

## Wstęp
W dziedzinie programowania w języku Java efektywne zarządzanie zadaniami jest kluczowym aspektem realizacji projektu. Aspose.Tasks dla Java zapewnia solidne rozwiązanie do obsługi zadań dzięki zaawansowanym funkcjom. W tym samouczku zajmiemy się jedną konkretną funkcjonalnością - zatrzymywaniem i wznawianiem zadań. Postępując zgodnie z tym przewodnikiem krok po kroku, będziesz w stanie bezproblemowo zintegrować tę funkcję ze swoimi projektami Java.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
- Zainstalowano zestaw Java Development Kit (JDK) w systemie.
- Biblioteka Aspose.Tasks dla Java pobrana i dodana do Twojego projektu. Można go uzyskać od[Tutaj](https://releases.aspose.com/tasks/java/).
## Importuj pakiety
Aby rozpocząć proces, zaimportuj niezbędne pakiety do projektu Java:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```
## Krok 1: Inicjalizacja
 Zacznij od zainicjowania projektu i utworzenia pliku`ChildTasksCollector` instancję, aby zebrać wszystkie zadania.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Krok 2: Ustaw minimalną datę
Zdefiniuj minimalną datę, aby filtrować zadania, które należy zatrzymać lub wznowić.
```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```
## Krok 3: Zatrzymaj i wznów zadania
Iteruj między zadaniami, sprawdzając i drukując daty zatrzymania i wznowienia.
```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```
Powtórz te kroki w swoim projekcie Java, aby bezproblemowo zintegrować funkcję zatrzymywania i wznawiania za pomocą Aspose.Tasks dla Java.
## Wniosek
W tym samouczku omówiliśmy proces zatrzymywania i wznawiania zadań przy użyciu Aspose.Tasks dla Java. Wykonując kroki opisane powyżej, możesz zwiększyć możliwości zarządzania projektami i usprawnić realizację zadań.
## Często Zadawane Pytania
### Czy Aspose.Tasks dla Java nadaje się do projektów na dużą skalę?
Absolutnie! Aspose.Tasks for Java przeznaczony jest do obsługi projektów o różnej wielkości, zapewniając wydajność i niezawodność.
### Czy mogę dostosować datę zatrzymywania i wznawiania zadań?
Tak, podany przykład pozwala na elastyczność w ustalaniu minimalnego terminu zgodnie z wymaganiami projektu.
### Gdzie mogę znaleźć dodatkowe wsparcie dla Aspose.Tasks dla Java?
 Odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za wsparcie społeczności i dyskusje.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla Java?
 Tak, możesz uzyskać dostęp do[bezpłatna wersja próbna](https://releases.aspose.com/) aby zapoznać się z funkcjami przed dokonaniem zakupu.
### Jak mogę uzyskać tymczasową licencję na Aspose.Tasks dla Java?
 Możesz nabyć licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/) do celów testowych.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
