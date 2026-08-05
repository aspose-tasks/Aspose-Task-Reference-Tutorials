---
date: 2026-02-13
description: Dowiedz się, jak obliczyć liczbę dni między datami, utworzyć projekt
  testowy i dodać własne pole, manipulując plikami Microsoft Project przy użyciu Aspose.Tasks
  for Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Oblicz dni pomiędzy datami przy użyciu Aspose.Tasks dla Javy
url: /pl/java/formulas/work-with-formulas/
weight: 11
---

FAQ: translate Q and A.

Make sure to keep markdown formatting.

Also at bottom: Last Updated, Tested With, Author.

Translate.

Now produce final.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obliczanie liczby dni między datami przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
W tym samouczku **obliczysz liczbę dni między datami**, tworząc projekt testowy, dodając pole niestandardowe i wykorzystując formuły Microsoft Project za pośrednictwem biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy potrzebujesz generować harmonogramy, wyliczać terminy, czy automatyzować raportowanie, Aspose.Tasks pozwala programowo manipulować danymi Project bez instalacji aplikacji desktopowej. Po zakończeniu przewodnika będziesz mieć działający przykład, który definiuje atrybut rozszerzony, ustawia termin zadania i zapisuje projekt jako plik MPP.

## Szybkie odpowiedzi
- **Co obejmuje samouczek?** Tworzenie projektu testowego, dodanie pola niestandardowego, zdefiniowanie atrybutu rozszerzonego oraz ustawienie terminu zadania przy użyciu formuły obliczającej liczbę dni między datami.  
- **Jakiej biblioteki potrzebujesz?** Aspose.Tasks dla Javy (najnowsza wersja).  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna działa w środowisku deweloperskim; licencja jest wymagana w produkcji.  
- **Jakie IDE można używać?** Dowolne IDE dla Javy (IntelliJ IDEA, Eclipse, VS Code) obsługujące JDK 8+.  
- **Jak długo trwa implementacja?** Około 10‑15 minut na skopiowanie kodu i uruchomienie go.

## Co oznacza „obliczanie liczby dni między datami” w Aspose.Tasks?
Obliczanie liczby dni między datami polega na użyciu formuły Project, która odejmuje jedno pole daty (np. **Finish**) od drugiego (np. **Deadline**) i zwraca różnicę liczbową w dniach. Jest to przydatne do śledzenia opóźnień w harmonogramie, mierzenia zapasu czasu lub generowania raportów niestandardowych.

## Dlaczego warto używać Aspose.Tasks do obliczania liczby dni między datami?
- **Pełne pokrycie API** – dostęp do każdej właściwości Project, Task i Resource.  
- **Brak wymogu instalacji Office** – działa na serwerach, w pipeline’ach CI i kontenerach Docker.  
- **Wieloplatformowość** – uruchamia się na Windows, Linux i macOS przy użyciu tego samego kodu Javy.  
- **Solidny silnik formuł** – pozwala definiować obliczenia takie jak `[Deadline] - [Finish]` bezpośrednio w pliku projektu.

## Jak ustawić termin (deadline) dla zadania
Ustawienie terminu jest pierwszym krokiem przed obliczeniem przedziału. Termin jest przechowywany w polu `Tsk.DEADLINE` zadania i może być przypisany przy użyciu instancji `java.util.Calendar`.

## Jak zdefiniować atrybut rozszerzony
Atrybut rozszerzony to pole niestandardowe, które będzie przechowywać wynik Twojej formuły. Definiujesz go raz, nadajesz mu alias dla czytelności, a następnie dołączasz formułę wykonującą odejmowanie dat.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz następujące elementy:

- **Java Development Kit (JDK) 8+** – pobierz ze strony Oracle lub użyj OpenJDK.  
- **Aspose.Tasks dla Javy** – pobierz najnowszy plik JAR ze [strony pobierania Aspose.Tasks dla Javy](https://releases.aspose.com/tasks/java/) i dodaj go do classpath projektu lub jako zależność Maven/Gradle.

## Importowanie pakietów
Najpierw zaimportuj klasy, które będą potrzebne:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Przewodnik krok po kroku

### Krok 1: Utwórz projekt testowy z polem niestandardowym
Zaczynamy od **utworzenia projektu testowego** i dodania pola niestandardowego, które później będzie przechowywać wynik formuły.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Wskazówka:* `CreateTestProjectWithCustomField()` to metoda pomocnicza, która buduje minimalny harmonogram i rejestruje atrybut rozszerzony gotowy do przypisania formuły.

### Krok 2: Zdefiniuj atrybut rozszerzony (dodaj pole niestandardowe)
Następnie **definiujemy atrybut rozszerzony** – w praktyce pole niestandardowe – i nadajemy mu przyjazny alias. To tutaj dodajemy logikę **dodawania pola niestandardowego**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** sprawia, że pole jest czytelne w Project.  
- **Formuła** oblicza liczbę dni między datą *Finish* a *Deadline* zadania – sedno *obliczania liczby dni między datami*.

### Krok 3: Ustaw termin (deadline) dla zadania (dodaj zadanie z terminem i ustaw termin zadania)
Teraz **dodajemy dane o terminie** poprzez ustawienie właściwości *Deadline* dla konkretnego zadania.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Instancja `Calendar` określa dokładny moment terminu.  
- `set(Tsk.DEADLINE, …)` **ustawia termin zadania** dla wybranego elementu.

### Krok 4: Zapisz projekt (manipulacja plikiem Microsoft Project)
Na koniec **manipulujemy plikiem Microsoft Project**, zapisując zmiany do pliku MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Możesz otworzyć `SaveFile.mpp` w Microsoft Project, aby zobaczyć pole niestandardowe, wynik formuły i ustawiony termin w harmonogramie.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|---------|-------------|
| **Formuła nie jest wyliczana** | Upewnij się, że ciąg `Formula` atrybutu używa poprawnych nazw pól (np. `[Deadline]`, `[Finish]`). |
| **Nie znaleziono zadania** | Sprawdź, czy identyfikator zadania (`1` w przykładzie) istnieje; użyj `project.getRootTask().getChildren().size()` do debugowania. |
| **Wyjątek licencyjny** | Zastosuj ważną licencję Aspose.Tasks przed wywołaniem jakichkolwiek metod API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Tasks w innych językach programowania?**  
O: Tak, Aspose.Tasks udostępnia API dla .NET, Javy i innych platform, umożliwiając **manipulację plikami Microsoft Project** w wybranym języku.

**P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?**  
O: Oczywiście. Pobierz w pełni funkcjonalną wersję próbną ze [strony pobierania Aspose.Tasks](https://releases.aspose.com/).

**P: Gdzie znajdę szczegółową dokumentację Aspose.Tasks?**  
O: Oficjalna dokumentacja znajduje się pod adresem [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**P: Jak mogę uzyskać wsparcie dla Aspose.Tasks?**  
O: Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby zadawać pytania i wymieniać doświadczenia z społecznością.

**P: Czy potrzebna jest tymczasowa licencja do oceny?**  
O: Tymczasowa licencja jest dostępna na krótkoterminowe testy; możesz ją zamówić [tutaj](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-02-13  
**Testowane z:** Aspose.Tasks dla Javy 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}