---
date: 2026-03-29
description: Dowiedz się, jak ustawić słowa kluczowe i datę utworzenia w projekcie
  MPP przy użyciu Aspose.Tasks for Java. Przewodnik krok po kroku z przykładami kodu.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak ustawić słowa kluczowe w podsumowaniu projektu MPP za pomocą Aspose.Tasks
url: /pl/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić słowa kluczowe w podsumowaniu projektu MPP przy użyciu Aspose.Tasks

## Wprowadzenie
W tym samouczku odkryjesz **jak ustawić słowa kluczowe** oraz inne informacje podsumowujące dla pliku projektu MPP przy użyciu Aspose.Tasks for Java. Niezależnie od tego, czy musisz osadzić dane autora, numery wersji, czy niestandardową datę utworzenia, ten przewodnik przeprowadzi Cię przez dokładne kroki, wraz z gotowym do uruchomienia kodem. Po zakończeniu będziesz w stanie ustawić słowa kluczowe, ustawić datę utworzenia java i odczytać dane z pliku.

## Szybkie odpowiedzi
- **Jakiej biblioteki użyto?** Aspose.Tasks for Java  
- **Główny cel?** Ustawienie słów kluczowych, informacji o autorze i daty utworzenia w pliku MPP  
- **Ile kroków kodu?** Trzy proste bloki kodu (inicjalizacja, zapis, odczyt)  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji  
- **Obsługiwana wersja Java?** Java 8 i wyższe  

## Co to jest „jak ustawić słowa kluczowe” w pliku MPP?
Słowa kluczowe to pola metadanych przechowywane wewnątrz pliku Microsoft Project (MPP). Pomagają kategoryzować projekty, umożliwiają szybkie wyszukiwanie i dostarczają informacji kontekstowych dla narzędzi downstream. Aspose.Tasks udostępnia właściwość `Prj.KEYWORDS`, co ułatwia programowe zapisywanie lub aktualizowanie tej wartości.

## Dlaczego używać Aspose.Tasks for Java do ustawiania słów kluczowych i daty utworzenia?
* **Pełna kompatybilność .MPP** – działa ze wszystkimi formatami Project 2007‑2023.  
* **Brak wymogu instalacji COM lub Office** – czysta Java, idealna dla środowisk serwerowych.  
* **Bogate API** – oprócz słów kluczowych możesz ustawić autora, wersję, komentarze i daty w jednym wywołaniu.  
* **Zoptymalizowana wydajność** – szybki odczyt/zapis nawet dla dużych plików projektów.

## Prerequisites
1. **Java Development Kit (JDK)** – zainstalowany JDK 8 lub nowszy.  
2. **Aspose.Tasks for Java** – pobierz najnowszy JAR z [tutaj](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans lub dowolny edytor, który preferujesz.

## Importowanie pakietów
Najpierw zaimportuj potrzebne klasy. Te importy dają dostęp do obiektu `Project`, wyliczenia `Prj` dla pól podsumowania oraz wyliczenia `SaveFileFormat` do zapisu.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Krok 1: Konfiguracja projektu i definiowanie informacji podsumowujących
Utwórz instancję `Project`, a następnie użyj metody `set`, aby zapisać żądane metadane. Zauważ, że **ustawiamy słowa kluczowe** i **ustawiamy datę utworzenia java** przy użyciu obiektu `Calendar`.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Krok 2: Zapis informacji podsumowujących projektu
Po wypełnieniu pól, zachowaj zmiany. Tutaj zapisujemy projekt jako XML dla łatwej inspekcji, ale możesz również zapisać go ponownie jako MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Krok 3: Odczyt informacji podsumowujących projektu
Aby zweryfikować, że metadane zostały zapisane poprawnie, wczytaj ponownie plik i odczytaj każdą właściwość. Ten krok pokazuje, że **jak ustawić słowa kluczowe** naprawdę działa od początku do końca.

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **NullPointerException przy `project.get(Prj.CREATION_DATE)`** | Kalendarz nigdy nie został ustawiony przed zapisem. | Upewnij się, że wywołujesz `project.set(Prj.CREATION_DATE, cal.getTime())` przed `save()`. |
| **Słowa kluczowe nie pojawiają się w interfejsie Microsoft Project** | Plik został zapisany jako XML i otwarty bezpośrednio w Project. | Zapisz ponownie jako MPP (`SaveFileFormat.MPP`) lub otwórz XML poprzez *Import* w Project. |
| **Wartości daty przesunięte o strefę czasową** | Java `Date` zawiera informacje o strefie czasowej. | Użyj `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))`, jeśli potrzebujesz dat w UTC. |

## Często zadawane pytania

**Q: Czy mogę używać Aspose.Tasks for Java z innymi bibliotekami Java?**  
A: Tak, Aspose.Tasks for Java może być płynnie zintegrowany z innymi bibliotekami Java, aby rozszerzyć możliwości zarządzania projektami.

**Q: Czy dostępna jest wersja próbna Aspose.Tasks for Java?**  
A: Tak, możesz pobrać darmową wersję próbną z [tutaj](https://releases.aspose.com/).

**Q: Jak często aktualizowane jest Aspose.Tasks for Java?**  
A: Aspose.Tasks for Java jest regularnie aktualizowane, aby zapewnić kompatybilność z najnowszymi wersjami Java i plików Microsoft Project.

**Q: Czy mogę dalej dostosować informacje podsumowujące projekt?**  
A: Oczywiście, Aspose.Tasks for Java oferuje szerokie możliwości dostosowywania informacji podsumowujących projekt zgodnie z Twoimi konkretnymi wymaganiami.

**Q: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks for Java?**  
A: Wsparcie możesz uzyskać na forum społeczności Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

---

**Ostatnia aktualizacja:** 2026-03-29  
**Testowano z:** Aspose.Tasks for Java 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}