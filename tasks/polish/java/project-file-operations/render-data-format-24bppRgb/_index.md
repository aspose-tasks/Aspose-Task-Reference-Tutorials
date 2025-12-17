---
date: 2025-12-17
description: Dowiedz się, jak zapisać projekt jako obraz i zmienić rozdzielczość obrazu
  w Javie przy użyciu Aspose.Tasks for Java. Ten przewodnik krok po kroku pokazuje
  renderowanie danych MS Project w formacie 24bppRgb.
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: Zapisz projekt jako obraz – format 24bppRgb w Aspose.Tasks
url: /pl/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz projekt jako obraz – format 24bppRgb w Aspose.Tasks

## Wprowadzenie
W tym samouczku dowiesz się, jak **zapisz projekt jako obraz** używając formatu pikseli 24bppRgb w Aspose.Tasks dla Javy. Renderowanie danych MS Project do obrazu jest przydatne, gdy potrzebujesz udostępnić wizualny zrzut harmonogramu, osadzić oś czasu w raporcie lub wygenerować miniatury dla portalu projektowego. Pokażemy także, jak **change image resolution java**, aby spełnić wymagania jakościowe.

## Szybkie odpowiedzi
- **Czy mogę renderować projekt do obrazu?** Tak, Aspose.Tasks umożliwia zapis projektu jako TIFF, PNG, JPEG itp.  
- **Jaki format pikseli zapewnia najlepszą głębię kolorów?** `Format24bppRgb` zapewnia obrazy w prawdziwych kolorach (24‑bit).  
- **Jak dostosować rozdzielczość obrazu?** Użyj `setHorizontalResolution` i `setVerticalResolution` w `ImageSaveOptions`.  
- **Czy potrzebuję licencji do produkcji?** Licencja komercyjna jest wymagana do użytku nie‑ewaluacyjnego.  
- **Czy jest to kompatybilne ze wszystkimi wersjami Java?** Działa z Java 8 i nowszymi.

## Czym jest „zapisz projekt jako obraz”?
Zapisanie projektu jako obrazu konwertuje wizualną reprezentację pliku Microsoft Project (`.mpp`) do formatu rastrowego (np. TIFF). Powstały plik może być wyświetlany w przeglądarkach, wstawiany do dokumentów lub drukowany bez konieczności posiadania oryginalnej aplikacji Project.

## Dlaczego używać formatu 24bppRgb?
Format pikseli 24bppRgb przechowuje każdy piksel z 8‑bitami dla czerwieni, zieleni i niebieskiego, zapewniając prawdziwą jakość kolorów bez kanału alfa. Jest to idealne rozwiązanie dla raportów o wysokiej klarowności, gdzie ważna jest wierność kolorów, przy jednoczesnym utrzymaniu rozsądnych rozmiarów plików w porównaniu z formatami 32‑bitowymi.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz następujące elementy:

1. **Java Development Kit (JDK)** – JDK 8 lub nowszy zainstalowany na Twoim komputerze.  
2. **Aspose.Tasks for Java** – Pobierz i zainstaluj z [here](https://releases.aspose.com/tasks/java/).  
3. **Podstawowa znajomość Javy** – Znajomość składni Javy i konfiguracji projektu ułatwi śledzenie fragmentów kodu.

## Importowanie pakietów
Najpierw zaimportuj wymagane klasy Aspose.Tasks do swojego projektu Java:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Przewodnik krok po kroku

### Krok 1: Definiowanie katalogu danych
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Zastąp `"Your Data Directory"` absolutną ścieżką, w której znajduje się Twój plik `.mpp`.

### Krok 2: Załaduj plik projektu
```java
Project project = new Project(dataDir + "project.mpp");
```
Ten wiersz odczytuje plik Microsoft Project (`project.mpp`) i tworzy obiekt `Project`, którym Aspose.Tasks może zarządzać.

### Krok 3: Skonfiguruj opcje zapisu obrazu
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
Tutaj ustawiamy format wyjściowy na TIFF, określamy rozdzielczość **72 dpi** (możesz zmienić te wartości, aby dopasować je do swoich potrzeb – to miejsce, w którym **change image resolution java**), oraz wybieramy format pikseli 24bppRgb dla obrazu w prawdziwych kolorach.

### Krok 4: Zapisz dane projektu jako obraz
```java
project.save(dataDir + "resFile.tif", options);
```
Metoda `save` zapisuje wyrenderowany obraz do `resFile.tif` przy użyciu wcześniej zdefiniowanych opcji.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| **Pusty obraz wyjściowy** | Widok projektu może być pusty. | Wywołaj `project.setDefaultView(ViewType.Gantt);` przed zapisem. |
| **Obraz o niskiej jakości** | Rozdzielczość ustawiona zbyt nisko. | Zwiększ `setHorizontalResolution` i `setVerticalResolution` (np. 150 dpi). |
| **Nieobsługiwany format pikseli** | Używana starsza wersja Aspose.Tasks. | Uaktualnij do najnowszej wersji Aspose.Tasks for Java. |

## Podsumowanie
Teraz wiesz, jak **zapisz projekt jako obraz** w formacie 24bppRgb i jak dostosować rozdzielczość przy użyciu Aspose.Tasks dla Javy. To podejście pozwala generować wyraźne, kolorowo‑dokładne wizualizacje harmonogramów projektów do udostępniania, raportowania lub archiwizacji.

## FAQ
### Q: Czy mogę renderować dane projektu w innych formatach obrazu?
A: Tak, Aspose.Tasks obsługuje renderowanie danych projektu w różnych formatach obrazu, takich jak PNG, JPEG, BMP itp.  
### Q: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami MS Project?
A: Tak, Aspose.Tasks wspiera wiele wersji MS Project, w tym 2003, 2007, 2010, 2013 i 2016.  
### Q: Czy mogę dostosować rozdzielczość i format pikseli renderowanego obrazu?
A: Tak, możesz dostosować rozdzielczość i format pikseli zgodnie z wymaganiami, używając Aspose.Tasks.  
### Q: Czy Aspose.Tasks wymaga licencji do użytku komercyjnego?
A: Tak, do komercyjnego użycia Aspose.Tasks wymagana jest licencja. Tymczasową licencję do testów możesz uzyskać [here](https://purchase.aspose.com/temporary-license/).  
### Q: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks?
A: Wsparcie dla Aspose.Tasks znajdziesz na [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}