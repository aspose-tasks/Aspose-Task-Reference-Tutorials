---
date: 2026-01-15
description: „Dowiedz się, jak zapisać projekt jako PDF oraz renderować widoki Wykorzystanie
  zasobów i Arkusz w MS Project przy użyciu Aspose.Tasks dla Javy. Skorzystaj z naszego
  krok po kroku przewodnika, aby bez wysiłku wyeksportować projekt do formatu PDF.”
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Zapisz projekt jako PDF – renderuj wykorzystanie zasobów i widok arkusza w
  Aspose.Tasks
url: /pl/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz projekt jako PDF – renderowanie widoku Wykorzystania zasobów i widoku Arkusza w Aspose.Tasks

## Wprowadzenie
W tym samouczku dowiesz się, jak **zapisz projekt jako PDF** przy renderowaniu widoków Wykorzystania zasobów i Arkusza pliku Microsoft Project. Niezależnie od tego, czy potrzebujesz wygenerować drukowalny raport dla interesariuszy, czy przekonwertować pliki MPP na format uniwersalnie czytelny, Aspose.Tasks for Java upraszcza proces — nie wymaga instalacji Microsoft Project.

## Szybkie odpowiedzi
- **Co robi „zapisz projekt jako pdf”?** Konwertuje plik Project (MPP) na dokument PDF, zachowując wybrany widok.  
- **Który widok może być wyeksportowany?** Wykorzystanie zasobów, Arkusz, Gantt, Wykorzystanie zadań i inne.  
- **Czy mogę zmienić skalę czasu w PDF?** Tak — dostępne opcje to Days, ThirdsOfMonths i Months.  
- **Czy potrzebna jest instalacja Microsoft Project?** Nie, Aspose.Tasks działa niezależnie.  
- **Czy wymagana jest licencja do użytku produkcyjnego?** Tak, do użytku nie‑trial wymagana jest licencja komercyjna.

## Co to jest „zapisz projekt jako PDF”?
Zapisanie projektu jako PDF tworzy statyczną, wysokiej rozdzielczości reprezentację wybranego widoku Project. Jest to idealne rozwiązanie do udostępniania klientom, archiwizacji lub drukowania bez ujawniania pierwotnego pliku projektu.

## Dlaczego używać Aspose.Tasks do eksportu projektu do PDF?
- **Brak zewnętrznych zależności** – działa na każdej platformie obsługującej Java.  
- **Precyzyjna kontrola** – możesz wybrać widok, skalę czasu i układ.  
- **Wysoka wierność** – PDF odzwierciedla wygląd oryginalnego widoku Project.  
- **Gotowość do automatyzacji** – integruj z pipeline’ami CI, usługami raportowania lub konwerterami wsadowymi.

## Wymagania wstępne
Zanim przejdziesz dalej, upewnij się, że masz:

1. **Java Development Kit (JDK)** – zalecana najnowsza wersja.  
2. **Aspose.Tasks for Java** – pobierz ze [strony pobierania](https://releases.aspose.com/tasks/java/).  

## Importowanie pakietów
Najpierw zaimportuj niezbędne klasy do swojego projektu Java:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Przewodnik krok po kroku

### Krok 1: Odczytaj projekt źródłowy
Wczytaj plik MPP, który chcesz przekonwertować.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Krok 2: Zdefiniuj SaveOptions z wymaganą skalą czasu (Eksport projektu do PDF)
Skonfiguruj opcje eksportu PDF i ustaw pożądaną skalę czasu.  
*Tutaj używamy **Days** jako przykładu.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Krok 3: Ustaw format prezentacji na ResourceUsage
Wybierz widok, który chcesz renderować. W tym przypadku widok **Resource Usage**.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Krok 4: Zapisz projekt (konwersja MPP do PDF)
Wykonaj konwersję i wygeneruj plik PDF.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Krok 5: Renderuj widoki dla innych ustawień skali czasu (Zmieniona skala czasu w PDF)
Powtórz poprzednie kroki, aby uzyskać PDF‑y z różnymi skalami czasu, takimi jak **ThirdsOfMonths** i **Months**.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Typowe problemy i rozwiązania
- **Błędy „plik nie znaleziony”** – sprawdź, czy `dataDir` wskazuje prawidłowy folder i czy nazwa pliku MPP jest dokładnie taka sama.  
- **Pusty wynik PDF** – upewnij się, że `PresentationFormat` odpowiada widokowi zawierającemu dane (np. ResourceUsage).  
- **Nieprawidłowa skala czasu** – sprawdź, czy `options.setTimescale()` jest wywoływane przed każdym `project.save()`.

## Najczęściej zadawane pytania

### Czy Aspose.Tasks może renderować inne widoki oprócz Wykorzystania zasobów i Arkusza?
Aspose.Tasks obsługuje renderowanie różnych widoków, takich jak wykres Gantt, Wykorzystanie zadań oraz widoki kalendarza, między innymi.

### Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?
Tak, Aspose.Tasks obsługuje szeroką gamę formatów plików Microsoft Project, w tym MPP, MPT i formaty XML.

### Czy mogę dostosować wygląd renderowanych widoków przy użyciu Aspose.Tasks?
Oczywiście! Aspose.Tasks oferuje rozbudowane opcje dostosowywania wyglądu i układu renderowanych widoków, aby spełnić Twoje konkretne wymagania.

### Czy Aspose.Tasks wymaga zainstalowanego Microsoft Project w systemie?
Nie, Aspose.Tasks jest biblioteką samodzielną i nie wymaga instalacji Microsoft Project do działania.

### Czy wsparcie techniczne jest dostępne dla użytkowników Aspose.Tasks?
Tak, użytkownicy Aspose.Tasks mogą korzystać ze wsparcia technicznego poprzez [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-01-15  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

---