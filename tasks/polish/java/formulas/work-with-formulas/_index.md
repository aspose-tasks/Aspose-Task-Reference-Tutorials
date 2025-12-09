---
date: 2025-12-07
description: Dowiedz się, jak **utworzyć projekt testowy** i **dodać pole niestandardowe**,
  manipulując plikami Microsoft Project przy użyciu Aspose.Tasks dla Javy.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Utwórz projekt testowy i użyj formuł z Aspose.Tasks dla Javy
url: /pl/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz projekt testowy i używaj formuł z Aspose.Tasks dla Javy

## Wprowadzenie
W tym samouczku **utworzysz pliki projektu testowego**, dodasz pole niestandardowe i będziesz pracować z formułami MS Project przy użyciu biblioteki Aspose.Tasks dla Javy. Aspose.Tasks ułatwia **manipulowanie danymi Microsoft Project** programowo — niezależnie od tego, czy potrzebujesz generować harmonogramy, obliczać daty czy automatyzować raportowanie. Po zakończeniu przewodnika będziesz mieć działający przykład, który definiuje rozszerzony atrybut, ustawia termin (deadline) dla zadania i zapisuje projekt jako plik MPP.

## Szybkie odpowiedzi
- **Co obejmuje samouczek?** Tworzenie projektu testowego, dodawanie pola niestandardowego, definiowanie rozszerzonego atrybutu oraz ustawianie terminu zadania przy użyciu formuły.  
- **Jakiej biblioteki wymaga?** Aspose.Tasks dla Javy (najnowsza wersja).  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja jest wymagana w produkcji.  
- **Jakiego IDE mogę używać?** Dowolne IDE Java (IntelliJ IDEA, Eclipse, VS Code), które obsługuje JDK 8+.  
- **Jak długo trwa implementacja?** Około 10‑15 minut na skopiowanie kodu i jego uruchomienie.

## Co to jest „Projekt testowy” w Aspose.Tasks?
**Projekt testowy** to lekki plik Microsoft Project tworzony programowo w celu demonstracji lub weryfikacji funkcjonalności. Zawiera minimalny zestaw zadań, zasobów i pól niestandardowych, które można manipulować bez wpływu na rzeczywiste dane projektu.

## Dlaczego używać Aspose.Tasks do manipulacji Microsoft Project?
- **Pełne pokrycie API** – dostęp do każdej właściwości Project, Task i Resource.  
- **Brak wymogu instalacji Office** – działa na serwerach, w pipeline’ach CI oraz kontenerach Docker.  
- **Cross‑platform** – działa na Windows, Linux i macOS przy użyciu tego samego kodu Java.  
- **Solidny silnik formuł** – oblicza daty, trwania i pola niestandardowe bezpośrednio w pliku projektu.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz następujące elementy:

- **Java Development Kit (JDK) 8+** – pobierz ze strony Oracle lub użyj OpenJDK.  
- **Aspose.Tasks for Java** – pobierz najnowszy plik JAR ze [strony pobierania Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/) i dodaj go do classpath projektu lub zależności Maven/Gradle.

## Importowanie pakietów
Najpierw zaimportuj klasy, których będziemy potrzebować:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Przewodnik krok po kroku

### Krok 1: Utwórz projekt testowy z polem niestandardowym
Zaczynamy od **utworzenia projektu testowego** i dodania pola niestandardowego, które później będzie przechowywać wynik naszej formuły.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` jest metodą pomocniczą, która tworzy minimalny harmonogram i rejestruje rozszerzony atrybut gotowy do przypisania formuły.

### Krok 2: Zdefiniuj rozszerzony atrybut (dodaj pole niestandardowe)
Następnie **definiujemy rozszerzony atrybut** – właściwie pole niestandardowe – i nadajemy mu przyjazny alias. To miejsce, w którym **dodajemy logikę pola niestandardowego**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** sprawia, że pole jest czytelne w Project.  
- **Formuła** oblicza liczbę dni pomiędzy datą *Finish* zadania a jego *Deadline*.

### Krok 3: Ustaw termin (deadline) dla zadania (dodaj zadanie deadline i ustaw termin zadania)
Teraz **dodajemy dane zadania deadline** ustawiając właściwość *Deadline* dla konkretnego zadania.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Instancja `Calendar` definiuje dokładny moment deadline.  
- `set(Tsk.DEADLINE, …)` **ustawia termin (deadline) zadania** dla wybranego zadania.

### Krok 4: Zapisz projekt (manipuluj plikiem Microsoft Project)
Na koniec **manipulujemy Microsoft Project**, zapisując zmiany do pliku MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Możesz otworzyć `SaveFile.mpp` w Microsoft Project, aby zobaczyć pole niestandardowe, wynik formuły i termin (deadline) odzwierciedlone w harmonogramie.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Formuła nie jest wyliczana** | Upewnij się, że ciąg `Formula` atrybutu używa prawidłowych nazw pól (np. `[Deadline]`, `[Finish]`). |
| **Zadanie nie znalezione** | Sprawdź, czy ID zadania (`1` w przykładzie) istnieje; użyj `project.getRootTask().getChildren().size()` do debugowania. |
| **Wyjątek licencyjny** | Zastosuj ważną licencję Aspose.Tasks przed wywołaniem jakichkolwiek metod API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Najczęściej zadawane pytania

P: Czy mogę używać Aspose.Tasks z innymi językami programowania?**  
O: Tak, Aspose.Tasks udostępnia API dla .NET, Java i innych platform, umożliwiając **manipulowanie plikami Microsoft Project** w wybranym języku.

**P: Czy dostępna jest darmowa wersja próbna Aspose.Tasks?**  
O: Oczywiście. Pobierz w pełni funkcjonalną wersję próbną ze [strony pobierania Aspose.Tasks](https://releases.aspose.com/).

**P: Gdzie mogę znaleźć szczegółową dokumentację Aspose.Tasks?**  
O: Oficjalna dokumentacja jest dostępna pod adresem [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**P: Jak mogę uzyskać wsparcie dla Aspose.Tasks?**  
O: Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby zadawać pytania i dzielić się doświadczeniami ze społecznością.

**P: Czy potrzebuję tymczasowej licencji do oceny?**  
O: Tymczasowa licencja jest dostępna do krótkoterminowych testów; możesz ją zamówić [tutaj](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2025-12-07  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}