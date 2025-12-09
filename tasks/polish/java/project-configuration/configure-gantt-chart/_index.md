---
date: 2025-12-09
description: Dowiedz się, jak ustawić katalog danych i skonfigurować widok wykresu
  Gantta w Aspose.Tasks przy użyciu Javy. Ten przewodnik pokazuje również, jak dostosować
  pola tabeli i krok po kroku konfigurować projekty Java z wykresem Gantta.
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ustaw katalog danych dla widoku wykresu Gantta w Aspose.Tasks
url: /pl/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw katalog danych dla widoku wykresu Gantta w Aspose.Tasks

## Wprowadzenie
W tym samouczku dowiesz się **jak ustawić katalog danych** i skonfigurować widok wykresu Gantta MS Project w projektach Aspose.Tasks przy użyciu Javy. Aspose.Tasks to solidne API Java, które umożliwia programowe manipulowanie plikami Microsoft Project. Po zakończeniu tego przewodnika będziesz w stanie **dostosować pola tabeli**, zmienić katalog danych oraz zwizualizować swój projekt dokładnie tak, jak tego potrzebujesz.

## Szybkie odpowiedzi
- **Jaki jest pierwszy krok?** Ustaw ścieżkę katalogu danych, w którym znajdują się pliki projektu.  
- **Która biblioteka jest wymagana?** Aspose.Tasks dla Javy (do pobrania ze strony oficjalnej).  
- **Czy mogę dodać własnetrybuty?** Tak – możesz definiować rozszerzone atrybuty i wyświetlać je na wykresie Gantta.  
- **Czy potrzebna jest licencja do testów?** Dostępna jest tymczasowa licencja do celów ewaluacyjnych.  
- **Które IDE działa najlepiej?** Każde IDE Java (IntelliJ IDEA, Eclipse, NetBeans) będzie odpowiednie.

## Co to jest „ustaw katalog danych” i dlaczego ma to znaczenie?
Ustawienie katalogu danych informuje Aspose.Tasks, gdzie ma odczytywać i zapisywać pliki projektu. Bez prawidłowej ścieżki API nie może zlokalizować plików `.mpp`, co prowadzi do błędów FileNotFound. Zdefiniowanie tego katalogu na początku kodu sprawia, że dalszy przepływ pracy jest czysty i powtarzalny.

## Dlaczego warto dostosować pola tabeli w wykresie Gantta?
Niestandardowe pola tabeli pozwalają wyświetlać dodatkowe informacje — takie jak własne atrybuty, dane zasobów czy notatki specyficzne dla projektu — bezpośrednio w widoku Gantta. Dzięki temu wykres jest bardziej informacyjny dla interesariuszy i zmniejsza potrzebę przełączania się między wieloma raportami.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Java Development Kit (JDK)** – dowolna aktualna wersja (8+).  
2. **Biblioteka Aspose.Tasks** – pobierz ją z [tutaj](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse lub dowolny edytor kompatybilny z Javą, którego używasz.

## Importowanie pakietów
Najpierw zaimportuj przestrzeń nazw Aspose.Tasks, aby móc pracować z jej klasami:

```java
import com.aspose.tasks.*;
```

## Przewodnik krok po kroku

### Krok 1: Konfiguracja katalogu danych
Zdefiniuj folder, który zawiera pliki projektu. To jest krok **ustaw katalog danych**, na którym koncentruje się samouczek.

```java
String dataDir = "Your Data Directory";
```

Zastąp `"Your Data Directory"` absolutną ścieżką do folderu, w którym znajduje się `project.mpp`.

### Krok 2: Załaduj plik projektu
Utwórz instancję `Project`, ładując istniejący plik Microsoft Project.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Krok 3: Dodaj nową aktywność
Wstaw nowe zadanie (aktywność) do korzenia projektu.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Krok 4: Zdefiniuj własny atrybut
Utwórz definicję własnego atrybutu, którą później możesz przypisać do zadań.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Krok 5: Dodaj własny atrybut do zadania
Przypisz nowo zdefiniowany atrybut do utworzonego zadania.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Krok 6: Dostosuj tabelę – **dostosuj pola tabeli**
Dodaj własny atrybut jako kolumnę w tabeli wykresu Gantta, określając szerokość, tytuł i wyrównanie.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Krok 7: Zapisz projekt
Zachowaj zmiany w nowym pliku, który można otworzyć w Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| **FileNotFoundException** podczas ładowania projektu | Ścieżka **ustaw katalog danych** jest nieprawidłowa lub brakuje końcowego ukośnika. | Sprawdź, czy `dataDir` wskazuje dokładnie na folder i zawiera odpowiedni separator (`/` lub `\\`). |
| Własny atrybut nie jest widoczny w widoku Gantta | Pole tabeli zostało dodane pod niewłaściwym indeksem lub szerokość kolumny jest zbyt mała. | Upewnij się, że `table.getTableFields().add(3, attrField);` używa prawidłowego indeksu i dostosuj `setWidth` w razie potrzeby. |
| LicenseException przy zapisie | Nie zastosowano ważnej licencji do użytku produkcyjnego. | Zastosuj tymczasową lub stałą licencję przed wywołaniem `project.save()`. |

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Tasks w innych językach programowania?**  
O: Tak, Aspose.Tasks jest dostępny dla wielu języków, w tym .NET, Java i C++.

**P: Czy dostępna jest darmowa wersja próbna Aspose.Tasks?**  
O: Tak, darmową wersję próbną można pobrać [tutaj](https://releases.aspose.com/).

**P: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks?**  
O: Wsparcie i pytania znajdziesz na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**P: Jak mogę kupić licencję na Aspose.Tasks?**  
O: Licencję można zakupić [tutaj](https://purchase.aspose.com/buy).

**P: Czy potrzebuję tymczasowej licencji do celów testowych?**  
O: Tak, tymczasową licencję można uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

## Zakończenie
Teraz wiesz, jak **ustawić katalog danych**, dodać nową aktywność, zdefiniować i dołączyć własny atrybut oraz **dostosować pola tabeli** w widoku wykresu Gantta przy użyciu Aspose.Tasks dla Javy. Te kroki dają pełną kontrolę nad sposobem wyświetlania danych projektu, czyniąc wykresy Gantta bardziej informacyjnymi i dopasowanymi do potrzeb interesariuszy.

---

**Ostatnia aktualizacja:** 2025-12-09  
**Testowane z:** Aspose.Tasks Java 24.12 (najnowsza)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}