---
date: 2026-03-27
description: Dowiedz się, jak wyeksportować plik MPP do formatu SVG w Javie przy użyciu
  Aspose.Tasks. Przewodnik krok po kroku, przykłady kodu i wskazówki, jak szybko zapisać
  projekt jako SVG.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak wyeksportować MPP do SVG w Javie przy użyciu Aspose.Tasks
url: /pl/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wyeksportować MPP do SVG w Javie

## Eksport MPP do SVG – Wprowadzenie
W tym samouczku dowiesz się, jak **wyeksportować MPP do plików SVG** przy użyciu Aspose.Tasks for Java. Konwersja pliku Microsoft Project (MPP) na obraz Scalable Vector Graphics (SVG) pozwala osadzać wysokiej jakości, niezależne od rozdzielczości diagramy bezpośrednio w stronach internetowych, raportach lub pulpitach nawigacyjnych. Przeprowadzimy Cię przez niezbędną konfigurację, pokażemy dokładny kod, którego potrzebujesz, i wyjaśnimy każdy krok, abyś mógł pewnie **zapisać projekt jako SVG** w swoich aplikacjach.

## Szybkie odpowiedzi
- **Co oznacza „eksport MPP do SVG”?**  
  Konwertuje plik Microsoft Project (.mpp) na obraz SVG, który może być wyświetlany w dowolnej przeglądarce bez utraty jakości.  
- **Która biblioteka obsługuje konwersję?**  
  Aspose.Tasks for Java udostępnia jednowierszową metodę `save`, wykonującą konwersję.  
- **Czy potrzebna jest licencja?**  
  Tymczasowa licencja jest wymagana do użytku komercyjnego; dostępna jest darmowa wersja próbna.  
- **Jakie są wymagania wstępne?**  
  Java JDK 8+ oraz plik JAR Aspose.Tasks for Java.  
- **Jak długo trwa konwersja?**  
  Zazwyczaj mniej niż sekunda dla standardowych plików projektu.

## Co to jest „eksport MPP do SVG”?
Eksportowanie MPP do SVG oznacza pobranie wizualnej reprezentacji harmonogramu projektu — zadań, osi czasu i zasobów — i zapisanie jej jako pliku SVG. SVG jest oparty na XML, lekki i doskonale skalowalny na wyświetlaczach o wysokiej rozdzielczości.

## Dlaczego eksportować MPP do SVG przy użyciu Aspose.Tasks?
- **Brak wymogu instalacji Microsoft Project** – biblioteka działa niezależnie.  
- **Pełna wierność** – wykresy, paski Gantta i kamienie milowe zachowują swoje style.  
- **Wieloplatformowość** – uruchom kod na Windows, Linux lub macOS.  
- **Jednowierszowe API** – jedno wywołanie zapisuje projekt jako SVG, naturalnie wpasowując się w istniejące potoki Java.

## Wymagania wstępne
- **Java Development Kit (JDK)** – wersja 8 lub nowsza. Pobierz ze strony Oracle.  
- **Aspose.Tasks for Java** – pobierz bibliotekę ze strony **[tutaj](https://releases.aspose.com/tasks/java/)**.  

## Importowanie pakietów
Najpierw zaimportuj potrzebne klasy. Blok importu pozostaje niezmieniony.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Krok 1: Definiowanie katalogu danych
Określ, gdzie znajduje się Twój plik źródłowy MPP i gdzie zostanie zapisany plik SVG.

```java
String dataDir = "Your Data Directory";
```

> **Wskazówka:** Użyj ścieżki bezwzględnej lub ścieżki względnej względem folderu zasobów projektu, aby uniknąć `FileNotFoundException`.

## Krok 2: Ładowanie pliku MPP
Utwórz instancję `Project`, ładując istniejący plik Microsoft Project.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Ten wiersz odczytuje *HomeMovePlan.mpp* z folderu określonego wcześniej.

## Krok 3: Zapis projektu jako SVG
Teraz możesz **wyeksportować MPP do SVG** jednym poleceniem.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Metoda zapisuje `project5.svg` w tym samym katalogu. Powstały plik SVG można otworzyć w dowolnej nowoczesnej przeglądarce lub osadzić bezpośrednio w HTML.

## Typowe przypadki użycia
- **Pulpity projektowe** – osadzaj interaktywne wykresy Gantta w portalach internetowych bez konieczności instalacji Microsoft Project po stronie klienta.  
- **Automatyczne raportowanie** – generuj obrazy SVG w locie dla raportów PDF lub HTML.  
- **Współpraca między zespołami** – udostępniaj wizualny harmonogram interesariuszom, którzy potrzebują jedynie przeglądarki, aby go zobaczyć.

## Typowe problemy i rozwiązania
| Problem | Powód | Rozwiązanie |
|-------|--------|-----|
| **Plik nie znaleziony** | Nieprawidłowa ścieżka `dataDir` | Sprawdź, czy łańcuch katalogu kończy się separatorem (`/` lub `\\`). |
| **Pusty wynik SVG** | Projekt załadowany bez widoków | Upewnij się, że plik MPP zawiera widok wykresu Gantta przed zapisem. |
| **Wyjątek licencyjny** | Brak ważnej licencji | Zastosuj tymczasową licencję używając `License.setLicense("path/to/license.xml")` przed wywołaniem `save`. |

## Najczęściej zadawane pytania

**P: Czy Aspose.Tasks for Java jest kompatybilny ze wszystkimi wersjami plików Microsoft Project?**  
O: Tak, obsługuje formaty MPP, MPT i XML od starszych po najnowsze wydania Project.

**P: Czy mogę dostosować wygląd wyjściowego pliku SVG?**  
O: Oczywiście. Użyj `SvgOptions`, aby ustawić czcionki, kolory i opcje układu przed wywołaniem `save`.

**P: Czy Aspose.Tasks for Java wymaga licencji do użytku komercyjnego?**  
O: Tak, do produkcji wymagana jest ważna licencja. Tymczasową licencję można uzyskać **[tutaj](https://purchase.aspose.com/temporary-license/)**.

**P: Czy mogę wypróbować Aspose.Tasks for Java przed zakupem?**  
O: Tak, dostępna jest darmowa wersja próbna **[tutaj](https://purchase.aspose.com/buy)**.

**P: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks for Java?**  
O: Odwiedź forum społeczności **[tutaj](https://forum.aspose.com/c/tasks/15)**, aby zadawać pytania i dzielić się opinią.

## Podsumowanie
Teraz wiesz, jak **wyeksportować MPP do SVG** w Javie i efektywnie **zapisać projekt jako SVG** przy użyciu Aspose.Tasks. Ta funkcjonalność pozwala integrować bogate wizualizacje projektów w portalach internetowych, pulpitach raportowych lub w dowolnym miejscu, gdzie potrzebna jest skalowalna grafika. Eksperymentuj z `SvgOptions`, aby dopracować wyjście, a będziesz miał potężne narzędzie w swoim zestawie programistycznym.

---

**Ostatnia aktualizacja:** 2026-03-27  
**Testowano z:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}