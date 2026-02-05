---
date: 2026-02-05
description: Dowiedz się, jak dodać święta do kalendarza, przypisać kalendarz do projektu
  i zapisać plik MS Project jako MPP przy użyciu Aspose.Tasks dla Javy.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Dodaj święta do kalendarza i zapisz jako MPP przy użyciu Aspose.Tasks
url: /pl/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj święta do kalendarza i zapisz jako MPP przy użyciu Aspose.Tasks

## Wprowadzenie

We współczesnym zarządzaniu projektami często trzeba **dodać święta do kalendarza** w plikach, utworzyć **kalendarz MS Project** i następnie udostępnić harmonogram w natywnym formacie MPP. Niezależnie od tego, czy konsolidujesz terminy z wielu źródeł, czy migrujesz starsze dane, programowe generowanie kalendarza eliminuje błędy ręczne i przyspiesza dostawę. Ten samouczek przeprowadzi Cię przez cały proces tworzenia kalendarza w MS Project, jego dostosowywania przy użyciu świąt, **przypisania kalendarza do projektu**, a w końcu **konwersji projektu do MPP** przy użyciu API Aspose.Tasks dla Javy.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Dodawanie świąt do kalendarza, przypisywanie go do projektu oraz zapisywanie wyniku jako plik MPP przy użyciu Aspose.Tasks dla Javy.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarcza do rozwoju; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Jakiej wersji Javy potrzebuję?** Java 8 lub wyższa (JDK 8+).  
- **Czy mogę dostosować kalendarz?** Tak – możesz dodać godziny pracy, wyjątki i święta.  
- **Ile czasu zajmuje implementacja?** Około 10‑15 minut dla podstawowego kalendarza.  

## Co to jest „create calendar MS Project”?

Tworzenie kalendarza MS Project oznacza programowe definiowanie dni roboczych, godzin i wyjątków, które sterują planowaniem zadań w pliku Microsoft Project. Korzystając z Aspose.Tasks możesz **java create project calendar**, modyfikować go i zapisywać zmiany bez konieczności otwierania interfejsu Microsoft Project.

## Dlaczego warto używać Aspose.Tasks do tego zadania?

- **Pełna kompatybilność .NET/Java** – działa na każdej platformie obsługującej Javę.  
- **Brak wymogu COM ani instalacji Office** – idealne do automatyzacji po stronie serwera i **automate schedule generation**.  
- **Bogate API** – obsługuje wszystkie właściwości kalendarza, w tym niestandardowe tygodnie pracy i święta.  
- **Bezpośredni eksport do MPP** – możesz **save project as MPP** bez pośrednich konwersji.

## Wymagania wstępne

1. **Java Development Kit (JDK) 8+** – upewnij się, że `java -version` zwraca 1.8 lub nowszą wersję.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR z [strony Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse lub dowolny edytor, którego używasz.  
4. **Podstawowa znajomość Javy** – znajomość klas, metod i operacji I/O.

## Jak dodać święta do kalendarza

Poniżej przechodzimy krok po kroku, od konfiguracji środowiska po zapis finalnego pliku MPP. Bloki kodu pozostają niezmienione w stosunku do oryginalnego samouczka; otaczające je wyjaśnienia zostały rozbudowane dla większej przejrzystości.

### Krok 1: Import wymaganych pakietów

Najpierw zaimportuj klasy Aspose.Tasks oraz narzędzia Javy.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Krok 2: Ustaw katalog danych

Zdefiniuj, gdzie będą znajdować się pliki szablonu wejściowego oraz pliki wyjściowe. Zamień symbol zastępczy na rzeczywistą ścieżkę na swoim komputerze.

```java
String dataDir = "Your Data Directory";
```

### Krok 3: Określ nazwy plików wejściowego i wyjściowego

Wczytamy istniejący plik MPP (lub pusty projekt) i zapisujemy wynik do nowego pliku.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Krok 4: Wczytaj projekt i dodaj nowy kalendarz

Utwórz instancję `Project` z pliku źródłowego i dodaj kalendarz o nazwie **„Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Krok 5: Dostosuj kalendarz (opcjonalnie)

Jeśli potrzebujesz konkretnych godzin pracy, świąt lub wyjątków, wywołaj własną metodę pomocniczą. Przykład używa `GetTestCalendar` jako symbolu zastępczego.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Wskazówka:** Możesz bezpośrednio manipulować `cal1.getWeekDays()`, aby ustawić godziny pracy dla każdego dnia tygodnia, lub użyć `cal1.getExceptions()`, aby **add holidays to calendar**.

### Krok 6: Przypisz kalendarz do projektu

Powiedz projektowi, aby używał nowo utworzonego kalendarza we wszystkich obliczeniach harmonogramu.

```java
project.set(Prj.CALENDAR, cal1);
```

### Krok 7: Zapisz projekt jako MPP

Teraz **convert project to MPP** poprzez zapis z opcją `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Krok 8: Potwierdź pomyślne zakończenie

Prosta wiadomość w konsoli informuje, że proces zakończył się bez błędów.

```java
System.out.println("Process completed Successfully");
```

## Typowe przypadki użycia

- **Automatyczne generowanie harmonogramu** dla powtarzalnych projektów (np. tygodniowe sprinty).  
- **Migracja starszych kalendarzy CSV lub Excel** do w pełni funkcjonalnego pliku MS Project.  
- **Raportowanie po stronie serwera**, gdzie usługa sieciowa zwraca plik MPP na żądanie.  

## Rozwiązywanie problemów i typowe pułapki

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| `NullPointerException` przy `project.save` | `dataDir` wskazuje na nieistniejący folder | Upewnij się, że katalog istnieje lub utwórz go programowo. |
| Kalendarz nie zastosowany do zadań | Zadania nadal odwołują się do domyślnego kalendarza | Po ustawieniu `Prj.CALENDAR` zaktualizuj także `Task.CALENDAR` każdego zadania, jeśli zostały wcześniej nadpisane. |
| Plik wyjściowy ma 0 KB | Brak uprawnień do zapisu | Uruchom JVM z odpowiednimi prawami systemowymi lub wybierz ścieżkę, do której można zapisywać. |

## Najczęściej zadawane pytania

**P: Czy Aspose.Tasks for Java jest kompatybilny z różnymi wersjami MS Project?**  
O: Tak, Aspose.Tasks for Java obsługuje szeroki zakres wersji MS Project, od Project 2007 aż po najnowsze wydania, zapewniając płynną kompatybilność.

**P: Czy mogę dostosować kalendarze do konkretnych wymagań projektu?**  
O: Oczywiście. Możesz definiować dni robocze, ustawiać niestandardowe tygodnie pracy, dodawać święta i nawet tworzyć wiele kalendarzy w jednym pliku projektu.

**P: Czy Aspose.Tasks for Java oferuje wsparcie techniczne i pomoc?**  
O: Tak, pomoc możesz uzyskać na forum społeczności Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

**P: Czy dostępna jest darmowa wersja próbna Aspose.Tasks for Java?**  
O: Tak, w pełni funkcjonalna wersja próbna jest dostępna [tutaj](https://releases.aspose.com/).

**P: Jak mogę uzyskać tymczasową licencję dla Aspose.Tasks for Java?**  
O: Tymczasowe licencje można zamówić na stronie Aspose [tutaj](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-02-05  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}