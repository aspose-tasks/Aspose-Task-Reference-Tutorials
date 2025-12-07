---
date: 2025-12-07
description: Dowiedz się, jak zapisać plik projektu, tworzyć i odczytywać formuły
  MS Project oraz dodawać formuły pól niestandardowych przy użyciu Aspose.Tasks dla
  Javy.
language: pl
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Zapisz plik projektu i twórz formuły MS Project przy użyciu Aspose.Tasks
url: /java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz plik projektu i twórz formuły MS Project przy użyciu Aspose.Tasks

## Wprowadzenie
W dziedzinie zarządzania projektami skuteczne przetwarzanie danych jest kluczowe. Aspose.Tasks for Java to solidne rozwiązanie, które umożliwia manipulację i wyodrębnianie danych z plików Microsoft Project. Jedną z potężnych funkcji, które oferuje, jest możliwość zapisywania i odczytywania formuł MS Project. **Nauczysz się także, jak *zapisz plik projektu* po zastosowaniu tych formuł**, zapewniając, że zmiany zostaną zachowane do dalszej analizy. Ten samouczek poprowadzi Cię przez proces wykorzystania tej funkcjonalności w celu usprawnienia zadań zarządzania projektami.

## Szybkie odpowiedzi
- **Co robi „save project file”?** Zapisuje wszystkie zmiany w pamięci do pliku .mpp na dysku.  
- **Czy mogę dodać formuły pól niestandardowych?** Tak – możesz utworzyć pole niestandardowe i przypisać formułę, np. „double task cost”.  
- **Czy potrzebna jest licencja do uruchomienia kodu?** Bezpłatna wersja próbna działa w celach oceny; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Które IDE jest najlepsze?** Dowolne IDE Java (IntelliJ IDEA, Eclipse, VS Code) skompiluje przykład.  
- **Czy API jest kompatybilne z najnowszą wersją MS Project?** Aspose.Tasks obsługuje wszystkie najnowsze formaty .mpp.

## Co oznacza „save project file” w Aspose.Tasks?
Zapisanie pliku projektu oznacza utrwalenie bieżącego stanu obiektu `Project` — w tym zadań, zasobów i wszelkich niestandardowych formuł — w fizycznym pliku Microsoft Project (`.mpp`). Operacja ta jest niezbędna po modyfikacji danych, takich jak dodanie pola niestandardowego czy zmiana kosztów zadania.

## Dlaczego dodać pole niestandardowe i utworzyć formułę pola niestandardowego?
Dodanie pola niestandardowego daje elastyczny kontener na dodatkowe informacje, które nie są objęte domyślnymi polami. Przypisując formułę — np. **double task cost** — automatyzujesz obliczenia, zmniejszasz liczbę błędów ręcznych i utrzymujesz spójność danych harmonogramu.

## Prerequisites
Przed przystąpieniem do tego samouczka upewnij się, że spełniasz następujące wymagania:

1. **Java Development Kit (JDK)** – Java 8 lub nowszy zainstalowany na twoim komputerze.  
2. **Aspose.Tasks for Java** – Pobierz i zainstaluj z [here](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Wybierz preferowane IDE do programowania w Javie (IntelliJ IDEA, Eclipse, VS Code, itp.).  

## Importowanie pakietów
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Krok 1: Ustaw katalog danych
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Zdefiniuj folder, w którym znajdują się Twoje pliki MS Project. To miejsce, z którego załadujesz plik źródłowy i w którym później **zapisz plik projektu**.

## Krok 2: Załaduj plik projektu
```java
Project project = new Project(dataDir + "project.mpp");
```
Wczytaj istniejący plik Microsoft Project do obiektu `Project`, aby móc odczytać lub zmodyfikować jego zawartość.

## Krok 3: Dodaj pole niestandardowe i utwórz formułę pola niestandardowego
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
W tym kroku **dodaj pole niestandardowe** „Double Costs” i **utwórz formułę pola niestandardowego**, która mnoży `[Cost]` zadania przez 2, skutecznie **double task cost**. Metoda `setFormula` osadza obliczenie bezpośrednio w pliku projektu.

## Krok 4: Dodaj zadanie i ustaw koszt
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Utwórz nowe zadanie, a następnie przypisz koszt bazowy `100`. Po zapisaniu projektu, pole niestandardowe automatycznie wyświetli `200` dzięki wcześniej zdefiniowanej formule.

## Krok 5: Zapisz plik projektu
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Na koniec **zapisz plik projektu** ze wszystkimi modyfikacjami. Metoda `save` zapisuje zaktualizowany projekt, w tym nowe pole niestandardowe i jego wyliczone wartości, do `saved.mpp`.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **Formuła nie zastosowana** | Pole niestandardowe nie zostało dodane do kolekcji `ExtendedAttributes` projektu. | Upewnij się, że `project.getExtendedAttributes().add(attr);` jest wywołane przed zapisem. |
| **Plik nie znaleziony** | Nieprawidłowa ścieżka `dataDir`. | Sprawdź, czy ciąg katalogu kończy się separatorem ścieżki (`/` lub `\\`). |
| **Koszt wyświetla się jako 0** | Koszt zadania nie został ustawiony przed zapisem. | Wywołaj `task.set(Tsk.COST, ...)` przed `project.save`. |

## Najczęściej zadawane pytania
**Q:** Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami MS Project?  
**A:** Tak, Aspose.Tasks obsługuje szeroki zakres wersji MS Project, od starszych formatów .mpp po najnowsze wydania.

**Q:** Czy mogę zintegrować Aspose.Tasks z istniejącym projektem Java?  
**A:** Oczywiście. API zostało zaprojektowane z myślą o płynnej integracji; wystarczy dodać plik JAR Aspose.Tasks do ścieżki klas projektu.

**Q:** Czy istnieją ograniczenia co do typów formuł, które mogę tworzyć?  
**A:** Biblioteka obsługuje większość natywnej składni formuł MS Project, w tym operacje arytmetyczne, logiczne oraz wbudowane funkcje. Bardziej złożone funkcje niestandardowe mogą wymagać obejść.

**Q:** Czy Aspose.Tasks wspiera wdrożenia wieloplatformowe?  
**A:** Tak, biblioteka działa na każdej platformie obsługującej Javę, w tym Windows, Linux i macOS.

**Q:** Jak mogę uzyskać wsparcie techniczne dla Aspose.Tasks?  
**A:** Odwiedź [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy społeczności lub otwórz zgłoszenie wsparcia, jeśli posiadasz licencję komercyjną.

## Zakończenie
W tym samouczku omówiliśmy, jak **zapisz plik projektu**, **dodaj pole niestandardowe** oraz **utwórz formułę pola niestandardowego**, która **double task cost** przy użyciu Aspose.Tasks for Java. Postępując zgodnie z tymi krokami, możesz automatyzować obliczenia, wzbogacać dane projektu i zapewnić, że wszystkie zmiany zostaną zachowane do przyszłych raportów i analiz.

---

**Last Updated:** 2025-12-07  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}