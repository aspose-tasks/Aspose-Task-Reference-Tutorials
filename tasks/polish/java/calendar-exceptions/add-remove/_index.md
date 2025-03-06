---
title: Zarządzaj wyjątkami kalendarza w Aspose.Tasks
linktitle: Dodawaj i usuwaj wyjątki kalendarza w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak efektywnie dodawać i usuwać wyjątki kalendarza w Aspose.Tasks dla Java. Ulepsz przepływ pracy w zarządzaniu projektami bez wysiłku.
weight: 10
url: /pl/java/calendar-exceptions/add-remove/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zarządzaj wyjątkami kalendarza w Aspose.Tasks


## Wstęp
W zarządzaniu projektami obsługa wyjątków w kalendarzach jest kluczowa dla dokładnego planowania zadań i zarządzania zasobami. Aspose.Tasks dla Java zapewnia zaawansowane funkcje umożliwiające łatwe dodawanie i usuwanie wyjątków kalendarza. W tym samouczku przeprowadzimy Cię krok po kroku przez ten proces.
#### Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany w systemie
- Biblioteka Aspose.Tasks dla Java pobrana i skonfigurowana w Twoim projekcie
- Podstawowa znajomość języka programowania Java i koncepcji zarządzania projektami

## Importuj pakiety
Po pierwsze, pamiętaj o zaimportowaniu niezbędnych pakietów do swojej klasy Java, aby efektywnie korzystać z funkcjonalności Aspose.Tasks.
```java
import com.aspose.tasks.*;
```
## Krok 1: Załaduj projekt i uzyskaj dostęp do kalendarza
Rozpocznij od załadowania pliku projektu i uzyskania dostępu do kalendarza, do którego chcesz dodać lub usunąć wyjątki.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```
## Krok 2: Usuń wyjątek
Aby usunąć istniejący wyjątek z kalendarza, sprawdź, czy są jakieś wyjątki, a następnie usuń żądany.
```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```
## Krok 3: Dodaj wyjątek
 Aby dodać nowy wyjątek do kalendarza, utwórz plik`CalendarException` obiektu i określić jego daty rozpoczęcia i zakończenia.
```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```
## Krok 4: Wyświetl wyjątki
Na koniec możesz wyświetlić dodane wyjątki w celu weryfikacji lub dalszego przetwarzania.
```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From" + calExc1.getFromDate().toString());
    System.out.println("To" + calExc1.getToDate().toString());
}
```

## Wniosek
Zarządzanie wyjątkami w kalendarzu jest niezbędne do dokładnego planowania projektu i alokacji zasobów. Dzięki Aspose.Tasks dla Java możesz bez wysiłku dodawać i usuwać wyjątki, aby zapewnić efektywne dotrzymanie harmonogramu projektu.

## Często zadawane pytania
### P: Czy mogę dodać wiele wyjątków do kalendarza za pomocą Aspose.Tasks dla Java?

Odp.: Tak, możesz dodać wiele wyjątków do kalendarza, przeglądając listę wyjątków i dodając każdy z osobna.

### P: Czy Aspose.Tasks for Java jest kompatybilny ze wszystkimi wersjami plików Microsoft Project?

Odp.: Aspose.Tasks dla Java zapewnia kompatybilność z różnymi wersjami plików Microsoft Project, zapewniając bezproblemową integrację z przepływami pracy związanymi z zarządzaniem projektami.

### P: Jak mogę obsłużyć powtarzające się wyjątki w kalendarzach projektów?

O: Aspose.Tasks dla Java oferuje solidne funkcje do obsługi powtarzających się wyjątków w kalendarzach projektów, umożliwiając łatwe definiowanie złożonych wzorców powtarzania.

### P: Czy dostępna jest wersja próbna Aspose.Tasks dla Java?

 O: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.Tasks dla Java z poziomu[strona internetowa](https://releases.aspose.com/) aby zapoznać się z jego funkcjami przed dokonaniem zakupu.

### P: Gdzie mogę szukać pomocy w przypadku jakichkolwiek problemów lub zapytań związanych z Aspose.Tasks dla Java?

 O: Możesz odwiedzić forum Aspose.Tasks dotyczące języka Java na stronie[strona internetowa](https://reference.aspose.com/tasks/java/) aby zwrócić się o pomoc do społeczności lub bezpośrednio skontaktować się z zespołem wsparcia w celu uzyskania spersonalizowanej pomocy.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
