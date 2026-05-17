---
date: 2026-02-10
description: Dowiedz się, jak uzyskać wartości walut, odczytać plik MS Project i konwertować
  plik projektu w Javie przy użyciu Aspose.Tasks. Przewodnik krok po kroku, jak wyodrębnić
  cyfry walutowe.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak uzyskać walutę z MS Project przy użyciu Aspose.Tasks
url: /pl/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak uzyskać walutę z MS Project przy użyciu Aspose.Tasks

## Wprowadzenie
Jeśli zastanawiasz się **jak uzyskać walutę** w pliku Microsoft Project, trafiłeś we właściwe miejsce. W tym obszernym samouczku dowiesz się **jak pracować z ms project currency** przy użyciu biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy tworzysz narzędzie raportujące, narzędzie migracyjne, czy po prostu potrzebujesz odczytać ustawienia waluty z **java project file**, ten przewodnik przeprowadzi Cię przez każdy krok — od załadowania pliku *.mpp* po wyodrębnienie cyfr waluty. Po zakończeniu będziesz pewnie obsługiwać dane walutowe ms project w własnych aplikacjach.

## Szybkie odpowiedzi
- **Jaką bibliotekę używać do odczytu plików MS Project?** Aspose.Tasks for Java.  
- **Ile linii kodu potrzeba, aby uzyskać cyfry waluty?** Zaledwie trzy zwięzłe linie po załadowaniu projektu.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do testów; licencja komercyjna jest wymagana w produkcji.  
- **Która wersja Javy jest wspierana?** Java 8 lub wyższa (dowolny JDK, który uruchamia Aspose.Tasks).  
- **Czy mogę pobrać inne właściwości projektu?** Tak — Aspose.Tasks udostępnia pełny zestaw pól Projektu (np. datę rozpoczęcia, stawki kosztów itp.).

## Co to jest waluta w ms project?
`ms project currency` odnosi się do precyzji liczbowej (liczby miejsc po przecinku), której Microsoft Project używa przy wyświetlaniu wartości pieniężnych. Jest przechowywana w pliku Projektu jako właściwość **CURRENCY_DIGITS** i określa, czy kwoty wyświetlane są jako liczby całkowite, z jednym, dwoma itp. miejscami po przecinku.

## Dlaczego używać Aspose.Tasks do obsługi waluty w ms project?
- **Brak wymogu instalacji Microsoft Project** – pracuj bezpośrednio z plikami *.mpp* na dowolnej platformie obsługującej Javę.  
- **Silne bezpieczeństwo typów** – API zwraca wartości silnie typowane, co zmniejsza błędy parsowania.  
- **Optymalizacja wydajności** – szybko wczytuj duże projekty i wyodrębniaj tylko potrzebne pola.  
- **Wieloplatformowość** – uruchamiaj na Windows, Linux lub macOS bez modyfikacji.

## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:

1. **Środowisko programistyczne Java** – zainstalowany i skonfigurowany JDK 8 lub nowszy.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR z oficjalnej strony: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Podstawowa znajomość Javy** – powinieneś swobodnie tworzyć projekt Java, dodawać zewnętrzne biblioteki i uruchamiać metodę `main`.  

## Importowanie pakietów
First, import the classes we’ll need.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: Definiowanie katalogu danych
Specify the folder that contains your **java project file** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Zastąp `"Your Data Directory"` absolutną lub względną ścieżką, w której znajduje się `project.mpp`.

## Krok 2: Załadowanie pliku MPP
Now we’ll see **how to load mpp** files using Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Upewnij się, że nazwa pliku jest dokładnie zgodna; w przeciwnym razie zostanie zgłoszony `IOException`.

## Krok 3: Pobranie cyfr waluty
With the project loaded, extracting the **ms project currency** digits is a one‑liner:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Wywołanie zwraca `Integer` reprezentujący liczbę miejsc po przecinku (np. `2` dla centów). Wartość jest wypisywana w konsoli, ale możesz ją także przechować w zmiennej do dalszego przetwarzania.

## Typowe problemy i wskazówki
- **Plik nie znaleziony** – sprawdź ponownie ścieżkę `dataDir` i upewnij się, że nazwa pliku jest poprawna, łącznie z rozszerzeniem `.mpp`.  
- **Nieobsługiwana wersja pliku** – Aspose.Tasks obsługuje formaty Project 2000‑2024; starsze lub uszkodzone pliki mogą wymagać konwersji.  
- **Licencja nie ustawiona** – podczas rozwoju wersja próbna działa, ale w produkcji musisz zastosować ważną licencję, aby uniknąć znaków wodnych wersji ewaluacyjnej.

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks obsługuje inne atrybuty Projektu oprócz cyfr waluty?**  
A: Tak, Aspose.Tasks oferuje szeroki zakres funkcjonalności umożliwiających manipulację różnymi aspektami plików Projektu, takimi jak zadania, zasoby i pola niestandardowe.

**Q: Czy Aspose.Tasks jest odpowiedni dla aplikacji na poziomie przedsiębiorstwa?**  
A: Zdecydowanie, Aspose.Tasks został zaprojektowany, aby sprostać wymaganiom projektów klasy enterprise, oferując wysoką wydajność i skalowalność.

**Q: Czy Aspose.Tasks wspiera rozwój wieloplatformowy?**  
A: Tak, możesz używać Aspose.Tasks for Java na dowolnej platformie obsługującej środowisko uruchomieniowe Javy (Windows, Linux, macOS).

**Q: Czy mogę wypróbować Aspose.Tasks przed zakupem?**  
A: Tak, możesz pobrać darmową wersję próbną z [tutaj](https://releases.aspose.com/).

**Q: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks?**  
A: Wsparcie znajdziesz na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Podsumowanie
Teraz wiesz **jak uzyskać cyfry waluty** z pliku MS Project przy użyciu Aspose.Tasks dla Javy. Proces jest prosty: załaduj projekt, wywołaj `project.get(Prj.CURRENCY_DIGITS)` i użyj wyniku w swojej aplikacji. Śmiało eksploruj inne właściwości projektu według tego samego schematu i włącz tę logikę do większych rozwiązań raportujących lub migracyjnych.

---

**Ostatnia aktualizacja:** 2026-02-10  
**Testowano z:** Aspose.Tasks for Java (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}