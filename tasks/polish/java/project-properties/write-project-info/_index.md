---
date: 2025-12-31
description: Dowiedz się, jak ustawić datę rozpoczęcia projektu, zapisać informacje
  o projekcie i zapisać projekt jako XML przy użyciu Aspose.Tasks dla Javy.
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ustaw datę rozpoczęcia projektu w MS Project przy użyciu Aspose.Tasks dla Javy
url: /pl/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw datę rozpoczęcia projektu w MS Project przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
W tym samouczku dowiesz się, jak **set project start date** oraz zapisać dodatkowe informacje MS Project przy użyciu Aspose.Tasks dla Javy. Niezależnie od tego, czy automatyzujesz harmonogramy projektów, generujesz raporty, czy integrujesz dane Project z większym systemem, programowe sterowanie datą rozpoczęcia daje precyzyjną kontrolę nad Twoimi terminami. Przejdziemy krok po kroku — od konfiguracji środowiska po zapis zaktualizowanego projektu jako pliku XML — abyś mógł od razu zastosować te techniki.

## Szybkie odpowiedzi
- **What is the primary class for manipulating a project?** `Project` from the Aspose.Tasks library.  
- **How do I set the project start date?** Use `project.set(Prj.START_DATE, <date>)`.  
- **Can I also set the status date?** Yes, with `project.set(Prj.STATUS_DATE, <date>)`.  
- **Which format should I use to export the project?** Save as XML with `SaveFileFormat.Xml`.  
- **Do I need a license for production use?** A valid Aspose.Tasks license is required for full functionality.

## Co to jest **ustalona data rozpoczęcia projektu**?
Ustalenie daty rozpoczęcia projektu kalendarzowego, od którego zależą wszystkie zadania. Jest to punkt odniesienia dla obliczeń takich jak czas trwania skutków, skutki i skutki uboczne. Programowe ustawienie tej daty zapewnia spójność w wielu plikach błędów i błędów ręcznych.

## Po co używać Aspose.Tasks dla Java do pisania informacji o projekcie?
- **Pełne pokrycie API:** Odczytuj, modyfikuj i zapisuj każdą właściwość projektu bez konieczności instalowania programu Microsoft Project.
- **Wiele platform:** działa w systemach Windows, Linux i macOS.
- **Gotowość do automatyzacji:** Idealny do przetwarzania wsadowego, potoków CI lub usług zaplecza, które na bieżąco generują harmonogramy projektów.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz:

1. **Java Development Kit (JDK)** – dowolna nowsza wersja (zalecane 8+).
2. **Biblioteka Aspose.Tasks dla Javy** – pobierz ją [tutaj](https://releases.aspose.com/tasks/java/).
3. **Środowisko IDE** – IntelliJ IDEA, Eclipse lub Twój ulubiony edytor Javy.

## Importowanie pakietów
Najpierw zaimportuj niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Krok 1: Skonfiguruj katalog danych
Zdefiniuj katalog, w którym będą przechowywane dane projektu.
```java
String dataDir = "Your Data Directory";
```

## Krok 2: Utwórz instancję projektu
Zainicjuj nową instancję projektu.
```java
Project project = new Project();
```

## Krok 3: Ustaw właściwości informacji o projekcie
Tutaj ustawiamy **datę rozpoczęcia projektu**, harmonogram od początku i datę statusu — obejmując podstawowe i dodatkowe słowa kluczowe *zapisz informacje o projekcie* oraz *jak ustawić status*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Krok 4: Zapisz projekt jako XML
Na koniec zapisz zaktualizowany plik projektu. To pokazuje dodatkowe słowo kluczowe **zapisz projekt jako xml**.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Poprawka |
|-------|--------|-----|
| **Nieprawidłowa data rozpoczęcia** | Miesiąc kalendarzowy w Javie zaczyna się od zera. | Użyj `Calendar.JULY` (lub dodaj 1 do indeksu miesiąca) zgodnie z ilustracją. |
| **Plik nie został zapisany** | `dataDir` nie istnieje lub nie ma uprawnień do zapisu. | Utwórz katalog wcześniej lub wybierz ścieżkę z możliwością zapisu. |
| **Ostrzeżenie dotyczące licencji** | Uruchamianie bez licencji powoduje dodanie znaku wodnego. | Zastosuj prawidłową licencję Aspose.Tasks przed utworzeniem obiektu `Project`. |

## Nie zadawane pytania
### P: Czy mogę używać Aspose.Tasks dla Javy do odczytu plików MS Project?
O: Tak, Aspose.Tasks dla Javy zapewnia rozbudowane funkcje zarówno do odczytu, jak i zapisu plików MS Project.
### P: Czy Aspose.Tasks dla Javy jest wydany z następującymi wersjami MS Project?
O: Oczywiście, Aspose.Tasks dla Java obsługuje różne wersje MS Project, zapewniając kompatybilność z różnymi formatami plików.
### P: Czy rozwiązanie problemu wersji próbnej Aspose.Tasks dla Javy?
O: Chociaż wersja próbna umożliwia poznanie możliwości biblioteki, ma ona pewne ograniczenia, takie jak znaki wodne na plikach wyjściowych.
### P: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla Javy?
Odp.: Możesz zwrócić się o pomoc na forum społeczności Aspose.Tasks [tutaj] (https://forum.aspose.com/c/tasks/15).
### Q: Czy mogę kupić tymczasową odpowiedź na Aspose.Tasks dla Javy?
Odpowiedź: Tak, dostępne są licencje tymczasowe do użytku krótkoterminowego. Możesz go pobrać [tutaj](https://purchase.aspose.com/temporary-license/).

## Podsumowanie
Nauczyłeś się już, jak **ustawić datę rozpoczęcia projektu**, zapisać niezbędne informacje o projekcie i **zapisać projekt w formacie XML** za pomocą Aspose.Tasks dla Javy. Te elementy składowe umożliwiają automatyzację przepływów pracy związanych z zarządzaniem projektami, generowanie spójnych harmonogramów i integrację danych MS Project z aplikacjami Java.

---

**Ostatnia aktualizacja:** 2025-12-31
**Testowano z:** Aspose.Tasks dla Javy 24.12
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}