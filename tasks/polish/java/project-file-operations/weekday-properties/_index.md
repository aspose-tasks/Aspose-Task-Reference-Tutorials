---
date: 2026-03-29
description: Dowiedz się, jak zmienić liczbę dni w miesiącu i zarządzać innymi właściwościami
  dni tygodnia w Aspose.Tasks for Java. Dostosuj daty rozpoczęcia tygodnia, modyfikuj
  kalendarz projektu i zapisz projekt jako XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Zmieniaj dni w miesiącu przy użyciu właściwości dni tygodnia Aspose.Tasks
url: /pl/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zmień liczbę dni w miesiącu przy użyciu właściwości dni tygodnia Aspose.Tasks

## Wprowadzenie
Aspose.Tasks for Java pozwala **zmienić liczbę dni w miesiącu** i precyzyjnie dostroić inne ustawienia dni tygodnia bez konieczności instalacji Microsoft Project. Niezależnie od tego, czy dopasowujesz kalendarz projektu do niestandardowego miesiąca fiskalnego, czy po prostu musisz zmienić dzień rozpoczęcia tygodnia, ten samouczek przeprowadzi Cię przez najczęstsze scenariusze — pobieranie bieżącego dnia rozpoczęcia tygodnia, dostosowywanie daty rozpoczęcia tygodnia, modyfikowanie kalendarza projektu oraz zapisywanie projektu jako XML.

## Szybkie odpowiedzi
- **Czy mogę zmienić liczbę dni w miesiącu?** Tak, użyj `Prj.DAYS_PER_MONTH` na obiekcie `Project`.  
- **Jak dostosować datę rozpoczęcia tygodnia?** Ustaw `Prj.WEEK_START_DAY` na wartość `DayType` (np. `DayType.Monday`).  
- **Jakiego formatu mogę użyć do eksportu projektu?** Przykład zapisuje plik jako XML z `SaveFileFormat.Xml`.  
- **Czy wymagana jest licencja do użytku produkcyjnego?** Ważna licencja Aspose.Tasks jest wymagana przy wdrożeniach nie‑ewaluacyjnych.  
- **Jakie IDE są obsługiwane?** Działa dowolne IDE Java, takie jak IntelliJ IDEA, Eclipse lub NetBeans.

## Co oznacza „zmiana liczby dni w miesiącu” w Aspose.Tasks?
Zmiana liczby dni w miesiącu oznacza aktualizację właściwości `Prj.DAYS_PER_MONTH` w instancji `Project`. Właściwość ta informuje silnik, ile dni roboczych ma uwzględniać w każdym miesiącu, co bezpośrednio wpływa na planowanie zadań i kalkulacje kosztów.

## Dlaczego modyfikować właściwości kalendarza projektu?
Dostosowanie kalendarza projektu — na przykład ustawienie innego dnia rozpoczęcia tygodnia lub zmiana liczby minut dziennie — pomaga:

- Dostosować harmonogramy do regionalnych tygodni pracy.  
- Modelować niestandardowe wzorce pracy (np. tygodnie czterodniowe).  
- Zapewnić dokładne raportowanie dla kontraktów korzystających z niestandardowych kalendarzy.

## Wymagania wstępne
- **Java Development Kit (JDK)** – Zainstaluj najnowszy JDK od Oracle.  
- **Aspose.Tasks for Java library** – Pobierz go z oficjalnej strony [here](https://releases.aspose.com/tasks/java/).  
- **IDE według wyboru** – IntelliJ IDEA, Eclipse lub NetBeans.

## Importowanie pakietów
Najpierw zaimportuj niezbędne klasy Aspose.Tasks:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: Załaduj plik projektu
Ładuje istniejący plik Microsoft Project (`project.mpp`) z określonego folderu.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Krok 2: Wyświetl właściwości dni tygodnia
Tutaj pobieramy i wyświetlamy bieżące ustawienia dni tygodnia, w tym **dzień rozpoczęcia tygodnia** i **liczbę dni w miesiącu**.

```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```

## Krok 3: Ustawianie właściwości dni tygodnia
W tym kroku **zmieniamy liczbę dni w miesiącu** na 24, ustawiamy rozpoczęcie tygodnia na poniedziałek oraz dostosowujemy liczbę minut dziennie/tygodniowo. Demonstracja, jak programowo **modyfikować kalendarz projektu**.

```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```

## Krok 4: Zapisz projekt
Zmodyfikowany projekt jest zapisywany w formacie **save project as XML**, co jest przydatne przy integracji z innymi narzędziami lub przy przechowywaniu w systemie kontroli wersji.

```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```

## Krok 5: Wyświetl wynik
Proste potwierdzenie, że operacje zakończyły się bez błędów.

```java
System.out.println("Process completed Successfully");
```

## Jak dostosować datę rozpoczęcia tygodnia
Jeśli Twoja organizacja używa kalendarza rozpoczynającego się od niedzieli, zamień `DayType.Monday` na `DayType.Sunday`. Używana jest ta sama właściwość (`Prj.WEEK_START_DAY`), co sprawia, że zmiana jest prosta.

## Jak pobrać dzień rozpoczęcia tygodnia
Możesz wywołać `project.get(Prj.WEEK_START_DAY)` w dowolnym momencie, aby **pobrać informację o dniu rozpoczęcia tygodnia**, jak pokazano w Kroku 2.

## Jak modyfikować kalendarz projektu
Poza dniem rozpoczęcia tygodnia, możesz również dostosować `Prj.MINUTES_PER_DAY` i `Prj.MINUTES_PER_WEEK`, aby odzwierciedlić niestandardowe godziny pracy lub wzorce zmian.

## Typowe problemy i rozwiązania
- **Nieprawidłowa wartość typu dnia** – Upewnij się, że używasz wyliczenia `DayType` (np. `DayType.Monday`).  
- **Błędy ścieżki pliku** – Sprawdź, czy `dataDir` kończy się odpowiednim separatorem plików (`/` lub `\`).  
- **Licencja nie ustawiona** – Jeśli pojawiają się ostrzeżenia licencyjne, zarejestruj licencję Aspose.Tasks przed utworzeniem obiektu `Project`.

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks for Java radzi sobie ze złożonymi strukturami projektów?**  
A: Tak, Aspose.Tasks for Java zapewnia kompleksowe wsparcie w obsłudze złożonych struktur projektów z łatwością.

**Q: Czy Aspose.Tasks for Java jest kompatybilny z różnymi wersjami plików Microsoft Project?**  
A: Absolutnie, Aspose.Tasks for Java obsługuje różne wersje plików Microsoft Project, zapewniając kompatybilność na różnych platformach.

**Q: Czy mogę zintegrować Aspose.Tasks for Java z istniejącymi aplikacjami Java?**  
A: Tak, Aspose.Tasks for Java oferuje płynną integrację, umożliwiając wzbogacenie aplikacji Java o potężne funkcje zarządzania projektami.

**Q: Czy Aspose.Tasks for Java zapewnia dokumentację i wsparcie?**  
A: Tak, możesz uzyskać dostęp do obszernej dokumentacji i wsparcia społecznościowego dla Aspose.Tasks for Java na ich [website](https://releases.aspose.com/).

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Tasks for Java?**  
A: Tak, możesz pobrać darmową wersję próbną Aspose.Tasks for Java z ich [website](https://reference.aspose.com/tasks/java/), aby wypróbować funkcje przed zakupem.

---

**Ostatnia aktualizacja:** 2026-03-29  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}