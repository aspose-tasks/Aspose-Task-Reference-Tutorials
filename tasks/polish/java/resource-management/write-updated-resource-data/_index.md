---
date: 2026-01-15
description: Dowiedz się, jak dodać zasób do projektu, zaktualizować dane zasobu i
  zapisać projekt jako MPP przy użyciu Aspose.Tasks for Java.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Dodaj zasób do projektu przy użyciu Aspose.Tasks dla Javy
url: /pl/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj zasób do projektu przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
W tym praktycznym samouczku dowiesz się **jak dodać zasób do projektu** programowo przy użyciu API Aspose.Tasks dla Javy. Przeprowadzimy Cię przez ładowanie istniejącego pliku MS Project XML, wstawianie nowego zasobu, aktualizację jego właściwości oraz w końcu **zapisanie projektu jako MPP**. Po zakończeniu będziesz mieć jasny, powtarzalny wzorzec, który możesz wstawić do dowolnego narzędzia raportującego lub automatyzującego opartego na Javie.

## Szybkie odpowiedzi
- **Co oznacza „dodaj zasób do projektu”?** Tworzy nowy wpis zasobu (osoby, sprzęt, materiały) w pliku Microsoft Project.  
- **Która biblioteka to obsługuje?** Aspose.Tasks dla Javy – nie wymaga zainstalowanego Microsoft Project.  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Czy mogę konwertować XML na MPP?** Tak – załaduj plik XML i **zapisz projekt jako MPP** używając `project.save(...)`.  
- **Jakiej wersji Javy potrzebuję?** Java 6 lub nowsza (zalecana Java 8+).

## Co to jest „dodaj zasób do projektu”?
Dodanie zasobu do projektu oznacza wstawienie nowego wiersza w tabeli Zasoby pliku MS Project. Wiersz ten przechowuje informacje takie jak nazwa, stawki kosztowe, grupa oraz pola niestandardowe, do których zadania mogą się odwoływać później.

## Dlaczego warto używać Aspose.Tasks dla Javy?
- **Brak zależności od Microsoft Project** – działa na każdym systemie operacyjnym i serwerze CI.  
- **Pełna wierność** – zachowuje wszystkie natywne funkcje Project przy konwersji między formatami.  
- **Bogate API** – umożliwia odczyt, zapis i manipulację zadaniami, zasobami, kalendarzami i nie tylko.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. Zainstalowany Java Development Kit (JDK) 8 lub nowszy.  
2. Bibliotekę Aspose.Tasks dla Javy – pobierz ją [tutaj](https://releases.aspose.com/tasks/java/).  
3. Podstawową znajomość składni Javy oraz konfiguracji projektu Maven/Gradle.

## Importowanie pakietów
Dodaj wymagane klasy Aspose.Tasks do swojego pliku źródłowego Java:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: Konfiguracja katalogu danych
Zdefiniuj, gdzie będą znajdować się pliki źródłowe XML oraz wynikowe pliki MPP:

```java
String dataDir = "Your Data Directory";
```

## Krok 2: Określenie plików wejściowych i wyjściowych
Wskaż plik XML, który chcesz przekonwertować (**konwertuj XML na MPP**) oraz docelowy plik MPP, który będzie zawierał nowy zasób:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Krok 3: Ładowanie projektu
Utwórz obiekt `Project` z źródła XML:

```java
Project project = new Project(file);
```

## Krok 4: Dodanie zasobu i ustawienie atrybutów
Tutaj **dodajemy zasób do projektu** i konfigurujemy jego stawki oraz grupę:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*Pro tip:* Możesz powtarzać wywołanie `add` w pętli, aby **zaktualizować wiele zasobów** w jednym uruchomieniu.

## Krok 5: Zapis projektu
Na koniec **zapisz projekt jako MPP**, aby utrwalić zmiany:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Zakończenie
Właśnie nauczyłeś się **jak dodać zasób do projektu**, zaktualizować jego właściwości oraz **zapisz projekt jako MPP** przy użyciu Aspose.Tasks dla Javy. To podejście jest idealne dla zautomatyzowanych potoków raportowania, masowych importów zasobów lub każdego scenariusza, w którym trzeba manipulować plikami MS Project bez aplikacji desktopowej.

## Najczęściej zadawane pytania

**Q1: Czy mogę zaktualizować wiele zasobów w tym samym projekcie przy użyciu Aspose.Tasks dla Javy?**  
A: Tak, iteruj po `project.getResources()` lub wywołuj `add` wielokrotnie, ustawiając pola każdego zasobu według potrzeb.

**Q2: Czy Aspose.Tasks obsługuje inne formaty plików poza MS Project?**  
A: Oczywiście – obsługiwane są XML, MPP, MPX, Primavera i wiele innych.

**Q3: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami Javy?**  
A: Biblioteka działa z Java 6 i nowszymi; Java 8+ jest zdecydowanie zalecana dla najlepszej wydajności.

**Q4: Czy mogę wykonywać inne operacje na plikach MS Project przy użyciu Aspose.Tasks?**  
A: Tak, możesz odczytywać/zapisywać zadania, kalendarze, przydziały, pola niestandardowe oraz generować raporty.

**Q5: Gdzie mogę znaleźć dodatkową pomoc lub wsparcie dla Aspose.Tasks?**  
A: Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby uzyskać pomoc od społeczności i oficjalne wsparcie.

---

**Ostatnia aktualizacja:** 2026-01-15  
**Testowano z:** Aspose.Tasks dla Javy 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}