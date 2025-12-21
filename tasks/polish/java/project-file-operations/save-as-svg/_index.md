---
date: 2025-12-21
description: Dowiedz się, jak tworzyć pliki SVG z plików MPP w Javie i zapisywać projekt
  jako SVG przy użyciu biblioteki Aspose.Tasks. Przewodnik krok po kroku z przykładami
  kodu.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak utworzyć SVG z pliku MPP w Javie przy użyciu Aspose.Tasks
url: /pl/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć SVG z MPP w Javie

## Wprowadzenie
W tym samouczku nauczysz się, jak **tworzyć SVG z MPP** przy użyciu Aspose.Tasks for Java. Konwersja pliku Microsoft Project (MPP) do skalowalnej grafiki wektorowej (SVG) pozwala osadzić wysokiej jakości, niezależne od rozdzielczości diagramy bezpośrednio w stronach internetowych, raportach lub pulpitach nawigacyjnych. Przeprowadzimy Cię przez niezbędną konfigurację, pokażemy dokładny kod, którego potrzebujesz, i wyjaśnimy każdy krok, abyś mógł pewnie **zapisać projekt jako SVG** w swoich aplikacjach.

## Szybkie odpowiedzi
- **Co oznacza „create SVG from MPP”?**  
  Konwertuje plik Microsoft Project (.mpp) na obraz SVG, który może być wyświetlany w dowolnej przeglądarce bez utraty jakości.  
- **Która biblioteka obsługuje konwersję?**  
  Aspose.Tasks for Java udostępnia jednowierszową metodę `save`, aby wykonać konwersję.  
- **Czy potrzebna jest licencja?**  
  Wymagana jest tymczasowa licencja do użytku komercyjnego; dostępna jest darmowa wersja próbna.  
- **Jakie są wymagania wstępne?**  
  Java JDK 8+ oraz plik JAR Aspose.Tasks for Java.  
- **Jak długo trwa konwersja?**  
  Zazwyczaj mniej niż sekunda dla standardowych plików projektu.

## Co to jest „create SVG from MPP”?
Tworzenie SVG z pliku MPP oznacza eksportowanie wizualnej reprezentacji harmonogramu projektu — zadań, osi czasu i zasobów — do formatu Scalable Vector Graphics. SVG jest oparty na XML, jest lekki i doskonale skalowalny na wyświetlaczach o wysokiej rozdzielczości.

## Dlaczego używać Aspose.Tasks do zapisywania projektu jako SVG?
- **Nie wymaga instalacji Microsoft Project** – biblioteka działa niezależnie.  
- **Pełna wierność** – wykresy, paski Gantta i kamienie milowe zachowują swoje style.  
- **Cross‑platform** – uruchamiaj kod na Windows, Linux lub macOS.  
- **Łatwa integracja** – jednowierszowe wywołanie API naturalnie wpasowuje się w istniejące potoki Java.

## Wymagania wstępne
- **Java Development Kit (JDK)** – wersja 8 lub nowsza. Pobierz ze strony Oracle.  
- **Aspose.Tasks for Java** – pobierz bibliotekę z oficjalnej strony pobierania **[here](https://releases.aspose.com/tasks/java/)**.  

## Importowanie pakietów
Najpierw zaimportuj klasy, które będą potrzebne. Blok importu pozostaje niezmieniony.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Krok 1: Zdefiniuj katalog danych
Określ, gdzie znajduje się źródłowy plik MPP i gdzie zostanie zapisany plik SVG.

```java
String dataDir = "Your Data Directory";
```

> **Wskazówka:** Użyj ścieżki bezwzględnej lub ścieżki względnej względem folderu zasobów projektu, aby uniknąć `FileNotFoundException`.

## Krok 2: Załaduj plik MPP
Utwórz instancję `Project`, ładując istniejący plik Microsoft Project.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Ten wiersz odczytuje *HomeMovePlan.mpp* z folderu, który zdefiniowałeś wcześniej.

## Krok 3: Zapisz projekt jako SVG
Teraz możesz **zapisać projekt jako SVG** za pomocą jednego polecenia.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Metoda zapisuje `project5.svg` w tym samym katalogu. Powstały plik SVG można otworzyć w dowolnej nowoczesnej przeglądarce lub osadzić bezpośrednio w HTML.

## Typowe problemy i rozwiązania
| Problem | Powód | Rozwiązanie |
|---------|-------|-------------|
| **Plik nie znaleziony** | Nieprawidłowa ścieżka `dataDir` | Sprawdź, czy ciąg katalogu kończy się separatorem (`/` lub `\\`). |
| **Pusty wynik SVG** | Projekt załadowany bez widoków | Upewnij się, że plik MPP zawiera widok wykresu Gantta przed zapisem. |
| **Wyjątek licencyjny** | Nie zastosowano ważnej licencji | Zastosuj tymczasową licencję używając `License.setLicense("path/to/license.xml")` przed wywołaniem `save`. |

## Najczęściej zadawane pytania

**P: Czy Aspose.Tasks for Java jest kompatybilny ze wszystkimi wersjami plików Microsoft Project?**  
O: Tak, obsługuje formaty MPP, MPT i XML od starszych po najnowsze wersje Project.

**P: Czy mogę dostosować wygląd wyjściowego SVG?**  
O: Oczywiście. Użyj `SvgOptions`, aby ustawić czcionki, kolory i opcje układu przed wywołaniem `save`.

**P: Czy Aspose.Tasks for Java wymaga licencji do użytku komercyjnego?**  
O: Tak, do produkcji wymagana jest ważna licencja. Tymczasową licencję możesz uzyskać **[here](https://purchase.aspose.com/temporary-license/)**.

**P: Czy mogę wypróbować Aspose.Tasks for Java przed zakupem?**  
O: Tak, dostępna jest darmowa wersja próbna **[here](https://purchase.aspose.com/buy)**.

**P: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks for Java?**  
O: Odwiedź forum społeczności **[here](https://forum.aspose.com/c/tasks/15)**, aby zadawać pytania i dzielić się opinią.

## Podsumowanie
Teraz wiesz, jak **tworzyć SVG z MPP** w Javie i efektywnie **zapisać projekt jako SVG** przy użyciu Aspose.Tasks. Ta funkcja pozwala integrować bogate wizualizacje projektów w portalach internetowych, pulpitach raportowych lub w każdym miejscu, gdzie potrzebna jest skalowalna grafika. Eksperymentuj z `SvgOptions`, aby dopracować wyjście, a będziesz mieć potężne narzędzie w swoim zestawie programistycznym.

---

**Ostatnia aktualizacja:** 2025-12-21  
**Testowane z:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}