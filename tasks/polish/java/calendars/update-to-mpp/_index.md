---
date: 2025-12-03
description: Dowiedz się, jak tworzyć kalendarz w MS Project, konwertować projekt
  do formatu MPP i bez wysiłku zapisywać projekt MPP przy użyciu Aspose.Tasks dla
  języka Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Utwórz kalendarz w MS Project i zapisz jako MPP przy użyciu Aspose.Tasks
url: /pl/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kalendarz MS Project i zapisz jako MPP przy użyciu Aspose.Tasks

## Wprowadzenie

We współczesnym zarządzaniu projektami często trzeba **create calendar MS Project** pliki i następnie udostępniać je w natywnym formacie MPP. Niezależnie od tego, czy konsolidujesz harmonogramy z wielu źródeł, czy migrujesz starsze dane, możliwość programowego generowania kalendarza oszczędza czas i eliminuje błędy ręczne. Ten samouczek przeprowadzi Cię przez cały proces tworzenia kalendarza w MS Project, jego dostosowywania oraz ostatecznie **convert[ing] project to MPP** przy użyciu Aspose.Tasks Java API.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Tworzenie kalendarza w MS Project i zapisywanie go jako plik MPP przy użyciu Aspose.Tasks dla Javy.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarczy do rozwoju; licencja komercyjna jest wymagana w produkcji.  
- **Jakiej wersji Javy wymaga?** Java 8 lub wyższa (JDK 8+).  
- **Czy mogę dostosować kalendarz?** Tak – możesz dodać godziny pracy, wyjątki i święta.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego kalendarza.

## Co to jest „create calendar MS Project”?

Tworzenie kalendarza MS Project oznacza programowe definiowanie dni roboczych, godzin i wyjątków, które sterują harmonogramowaniem zadań w pliku Microsoft Project. Korzystając z Aspose.Tasks możesz budować, modyfikować i zapisywać te kalendarze bez konieczności otwierania interfejsu Microsoft Project.

## Dlaczego warto używać Aspose.Tasks do tego zadania?

- **Full .NET/Java compatibility** – działa na każdej platformie obsługującej Javę.  
- **No COM or Office installation needed** – idealne do automatyzacji po stronie serwera.  
- **Rich API** – obsługuje wszystkie właściwości kalendarza, w tym niestandardowe tygodnie pracy i święta.  
- **Direct MPP output** – możesz **save project MPP** bez pośrednich konwersji.

## Wymagania wstępne

1. **Java Development Kit (JDK) 8+** – upewnij się, że `java -version` zwraca 1.8 lub nowszą wersję.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR ze [strony Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse lub dowolny edytor, którego używasz.  
4. **Podstawowa znajomość Javy** – znajomość klas, metod i operacji I/O.

## Przewodnik krok po kroku

### Krok 1: Importowanie wymaganych pakietów

Najpierw zaimportuj klasy Aspose.Tasks oraz narzędzia Javy.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Krok 2: Ustawienie katalogu danych

Zdefiniuj, gdzie będą przechowywane szablony wejściowe i pliki wyjściowe. Zastąp symboliczny placeholder rzeczywistą ścieżką na swoim komputerze.

```java
String dataDir = "Your Data Directory";
```

### Krok 3: Definiowanie nazw plików wejściowych i wyjściowych

Wczytamy istniejący plik MPP (lub pusty projekt) i zapisujemy wynik do nowego pliku.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Krok 4: Załadowanie projektu i dodanie nowego kalendarza

Utwórz instancję `Project` z pliku źródłowego i dodaj kalendarz o nazwie **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Krok 5: Dostosowanie kalendarza (opcjonalnie)

Jeśli potrzebujesz konkretnych godzin pracy, świąt lub wyjątków, wywołaj własną metodę pomocniczą. Przykład używa `GetTestCalendar` jako symbolicznego placeholdera.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** Możesz bezpośrednio manipulować `cal1.getWeekDays()`, aby ustawić godziny pracy dla każdego dnia tygodnia.

### Krok 6: Przypisanie kalendarza do projektu

Powiedz projektowi, aby używał nowo utworzonego kalendarza we wszystkich obliczeniach harmonogramu.

```java
project.set(Prj.CALENDAR, cal1);
```

### Krok 7: Zapisz projekt jako MPP

Teraz **convert project to MPP** poprzez zapisanie go z opcją `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Krok 8: Potwierdzenie pomyślnego zakończenia

Prosta wiadomość w konsoli informuje, że proces zakończył się bez błędów.

```java
System.out.println("Process completed Successfully");
```

## Typowe przypadki użycia

- **Automated schedule generation** dla powtarzalnych projektów (np. tygodniowe sprinty).  
- **Migrating legacy CSV or Excel calendars** do w pełni funkcjonalnego pliku MS Project.  
- **Server‑side reporting**, w którym usługa sieciowa zwraca plik MPP na żądanie.  

## Rozwiązywanie problemów i typowe pułapki

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| `NullPointerException` on `project.save` | `dataDir` wskazuje na nieistniejący folder | Upewnij się, że katalog istnieje lub utwórz go programowo. |
| Calendar not applied to tasks | Zadania nadal odwołują się do domyślnego kalendarza | Po ustawieniu `Prj.CALENDAR` zaktualizuj także `Task.CALENDAR` każdego zadania, jeśli zostały wcześniej nadpisane. |
| Output file is 0 KB | Brak uprawnień do zapisu | Uruchom JVM z odpowiednimi prawami systemowymi lub wybierz ścieżkę, do której można zapisywać. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks for Java jest kompatybilny z różnymi wersjami MS Project?**  
A: Tak, Aspose.Tasks for Java obsługuje szeroki zakres wersji MS Project, od Project 2007 aż po najnowsze wydanie, zapewniając płynną kompatybilność.

**Q: Czy mogę dostosować kalendarze do konkretnych wymagań projektu?**  
A: Oczywiście. Możesz definiować dni robocze, ustawiać niestandardowe tygodnie pracy, dodawać święta oraz tworzyć wiele kalendarzy w jednym pliku projektu.

**Q: Czy Aspose.Tasks for Java oferuje wsparcie w rozwiązywaniu problemów?**  
A: Tak, pomoc możesz uzyskać na forum społeczności Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Tasks for Java?**  
A: Tak, w pełni funkcjonalna wersja próbna jest dostępna [tutaj](https://releases.aspose.com/).

**Q: Jak mogę uzyskać tymczasową licencję na Aspose.Tasks for Java?**  
A: Tymczasowe licencje można zamówić poprzez stronę Aspose [tutaj](https://purchase.aspose.com/temporary-license/).

**Ostatnia aktualizacja:** 2025-12-03  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}