---
date: 2026-03-27
description: Dowiedz się, jak używać Aspose i Aspose.Tasks do wyodrębniania szczegółów
  kalendarza projektu z plików Microsoft Project przy użyciu Javy. Przewodnik krok
  po kroku z przykładami kodu.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak używać Aspose.Tasks do pobierania informacji o kalendarzu MS Project
url: /pl/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać Aspose.Tasks do pobierania informacji o kalendarzu MS Project

## Wprowadzenie
W tym samouczku **dowiesz się, jak używać Aspose.Tasks**, aby programowo pobierać informacje o kalendarzu z plików Microsoft Project. Dostęp do danych kalendarza, takich jak dni robocze, godziny i wyjątki, jest niezbędny, gdy potrzebujesz **wyodrębnić kalendarz projektu** w celu raportowania, integracji lub własnej logiki harmonogramowania. Przejdźmy krok po kroku przez proces i zobacz dokładnie **jak używać Aspose**, aby wyciągnąć te dane z pliku *.mpp*.

## Szybkie odpowiedzi
- **Jakiej biblioteki używa ten samouczek?** Aspose.Tasks for Java.  
- **Jakie główne słowo kluczowe jest omawiane?** *how to use aspose*.  
- **Co możesz wyodrębnić?** Kalendarze projektu, w tym dni robocze i godziny.  
- **Czy potrzebna jest licencja?** Dostępna jest darmowa wersja próbna; licencja jest wymagana w środowisku produkcyjnym.  
- **Jaką wersję Javy obsługuje?** Java 8 lub wyższą.

## Czym jest Aspose.Tasks i dlaczego warto go używać?
Aspose.Tasks to potężne API Java, które pozwala programistom odczytywać, zapisywać i manipulować plikami Microsoft Project bez potrzeby posiadania samego Microsoft Project. Korzystając z Aspose.Tasks możesz **how to extract calendar** informacje, automatyzować obliczenia harmonogramów i integrować dane projektowe z innymi systemami przedsiębiorstwa — wszystko w czystym kodzie Java.

## Dlaczego wyodrębniać informacje o kalendarzu projektu?
Kalendarze projektu sterują datami zadań, przydziałami zasobów i ogólnymi obliczeniami harmonogramu. Wyodrębniając te dane możesz:
- Generowanie niestandardowych raportów odzwierciedlających rzeczywiste harmonogramy pracy.  
- Synchronizacja harmonogramów Microsoft Project z zewnętrznymi systemami (ERP, BI itp.).  
- Przeprowadzanie analiz „co‑jeśli” poprzez programowe modyfikowanie ustawień kalendarza.  
- **Wyodrębnić dane kalendarza MS Project** w celu migracji do innych narzędzi planistycznych.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz:

- Podstawową znajomość programowania w Javie.  
- Zainstalowany Java Development Kit (JDK) w systemie.  
- Bibliotekę Aspose.Tasks for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
Najpierw zaimportuj niezbędne klasy Aspose.Tasks do swojego projektu Java.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Krok 1: Ustaw katalog danych
Zdefiniuj folder, który zawiera Twój plik *.mpp*.

```java
String dataDir = "Your Data Directory";
```

Zastąp `"Your Data Directory"` absolutną ścieżką do folderu, w którym znajduje się **project.mpp**.

## Krok 2: Zdefiniuj jednostki czasu
Utwórz stałe, które pomogą przeliczyć wewnętrzną reprezentację czasu na czytelne godziny.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Wartości te są wyrażone w mikrosekundach, co jest sposobem, w jaki Aspose.Tasks przechowuje czas wewnętrznie.

## Krok 3: Utwórz instancję projektu
Załaduj plik Microsoft Project do obiektu `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Konstruktor `Project` parsuje plik *.mpp* i udostępnia wszystkie dane projektu, w tym kalendarze, poprzez API.

## Krok 4: Pobierz informacje o kalendarzach
Uzyskaj kolekcję kalendarzy zdefiniowanych w projekcie.

```java
CalendarCollection alCals = project.getCalendars();
```

Projekt może zawierać wiele kalendarzy (standardowy, zasobów i niestandardowe). Ta kolekcja daje dostęp do każdego z nich.

## Krok 5: Iteruj po kalendarzach
Przejdź przez każdy kalendarz, wyświetl jego UID, nazwę oraz dni robocze wraz z odpowiadającymi godzinami.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

Wewnętrzna pętla sprawdza każdy obiekt `WeekDay`. Jeśli dzień jest oznaczony jako roboczy, wypisuje typ dnia (Monday, Tuesday, …) wraz z obliczonymi godzinami pracy.

## Krok 6: Wyświetl komunikat o zakończeniu
Zasygnalizuj, że proces wyodrębniania został zakończony.

```java
System.out.println("Process completed Successfully");
```

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **Brak zwróconych kalendarzy** | Plik projektu może nie zawierać żadnych niestandardowych kalendarzy. | Sprawdź, czy *.mpp* rzeczywiście definiuje kalendarze lub otwórz go w Microsoft Project, aby to potwierdzić. |
| **Nieprawidłowe godziny pracy** | Stałe konwersji czasu są nieprawidłowe dla innej wersji Project. | Dostosuj `OneSec`, `OneMin`, `OneHour`, jeśli pracujesz z nowszą wersją Aspose.Tasks, która zmienia wewnętrzną jednostkę czasu. |
| **`NullPointerException` przy `cal.getName()`** | Niektóre obiekty kalendarza mogą być null. | Dodaj sprawdzenie null przed dostępem do właściwości (już pokazane). |

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Tasks w innych językach programowania?**  
A: Tak, Aspose.Tasks obsługuje wiele platform i języków programowania, w tym .NET, C++, Python i Java.

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Tasks?**  
A: Tak, możesz pobrać darmową wersję próbną [tutaj](https://releases.aspose.com/).

**Q: Jak mogę uzyskać wsparcie dla Aspose.Tasks?**  
A: Wsparcie możesz uzyskać na forum społeczności Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

**Q: Czy mogę kupić tymczasową licencję na Aspose.Tasks?**  
A: Tak, tymczasowe licencje są dostępne do zakupu [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Gdzie znajdę szczegółową dokumentację Aspose.Tasks?**  
A: Dokumentację możesz znaleźć [tutaj](https://reference.aspose.com/tasks/java/).

## Podsumowanie
Postępując zgodnie z tymi krokami, **teraz wiesz, jak używać Aspose.Tasks do wyodrębniania kalendarza projektu** z pliku MS Project przy użyciu Javy. Możesz zintegrować tę logikę z większymi aplikacjami, automatyzować raportowanie lub synchronizować harmonogramy z innymi systemami przedsiębiorstwa. Pamiętaj, że opanowanie **how to use aspose** otwiera drzwi do wielu zaawansowanych scenariuszy automatyzacji zarządzania projektami.

---

**Ostatnia aktualizacja:** 2026-03-27  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}