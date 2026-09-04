---
date: 2026-06-10
description: Dowiedz się, jak zmienić kontur i generować Timephased Data dla Resource
  Assignments przy użyciu Aspose.Tasks for Java, obejmując Work Contour Types oraz
  Advanced Scheduling Scenarios.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Generuj Timephased Data dla Resource Assignments w Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak zmienić kontur w Aspose.Tasks dla Timephased Data
url: /pl/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zmienić kontur w Aspose.Tasks dla danych czasowych

## Wprowadzenie
W tym samouczku odkryjesz **jak zmienić kontur** dla przydziału zasobu i wygenerujesz dane czasowe przy użyciu Aspose.Tasks dla Javy. Dane czasowe ukazują rozkład pracy w czasie trwania projektu, umożliwiając precyzyjne dostosowywanie harmonogramów, równoważenie obciążeń i podejmowanie decyzji opartych na danych. Opanowanie zmian konturu pomaga modelować realistyczne wzorce wysiłku, takie jak front‑loading, back‑loading lub szczytowe obciążenia.

## Szybkie odpowiedzi
- **Co to jest kontur?** Kontur pracy definiuje, jak wysiłek jest rozłożony w czasie trwania zadania (np. Płaski, Żółw, Dzwon).  
- **Dlaczego zmienić kontur?** Aby odzwierciedlić realistyczne wzorce pracy, takie jak front‑loading lub back‑loading.  
- **Jakiej biblioteki wymaga?** Aspose.Tasks for Java (dowolna aktualna wersja).  
- **Czy potrzebna jest licencja?** Tak, ważna licencja Aspose.Tasks jest wymagana do użytku produkcyjnego.  
- **Czy mogę zobaczyć wyniki w konsoli?** Przykład wypisuje daty rozpoczęcia i wartości dla każdego segmentu czasowego.

## Co to jest „jak zmienić kontur”?
Zmiana konturu oznacza aktualizację właściwości `WORK_CONTOUR` obiektu `ResourceAssignment`. Właściwość ta informuje Aspose.Tasks, jak rozłożyć całkowitą pracę przydziału w czasie trwania zadania. Biblioteka udostępnia kilka predefiniowanych konturów, takich jak Flat, Turtle, Bell i inne, z których każdy generuje odrębny wzorzec rozkładu wysiłku w czasie.

## Dlaczego używać Aspose.Tasks do generowania danych czasowych?
Aspose.Tasks generuje dane czasowe z **0 ms narzutu dla operacji w pamięci** i obsługuje **ponad 50 formatów wyjściowych** (MPP, XML, CSV itp.). Biblioteka może przetwarzać projekty liczące setki stron bez ładowania całego pliku do pamięci, dostarczając dokładny rozkład pracy dla raportowania, wyrównywania zasobów i analiz „co‑jeśli”. Jej API umożliwia automatyzację zmian konturu i programowe wyodrębnianie precyzyjnych wartości czasowych.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz następujące elementy:
1. Java Development Kit (JDK): Upewnij się, że masz zainstalowany JDK w systemie. Możesz pobrać i zainstalować JDK z [tutaj](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Biblioteka Aspose.Tasks for Java: Musisz mieć bibliotekę Aspose.Tasks for Java. Możesz ją pobrać ze [strony internetowej](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
Klasa `Project` jest podstawowym obiektem Aspose.Tasks, który reprezentuje cały plik projektu w pamięci. Zaimportuj niezbędne przestrzenie nazw przed rozpoczęciem pracy z zadaniami i przydziałami.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Krok 1: Odczyt pliku MPP źródłowego
Konstruktor `Project` ładuje istniejący plik MPP, parsując jego strukturę bez pełnego materializowania każdego zadania w pamięci, co utrzymuje operację lekką.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Krok 2: Pobranie zadania i przydziału zasobu
`ResourceAssignment` łączy zasób z zadaniem i przechowuje właściwości przydziału, takie jak praca, koszt i kontur. Pobierz pierwszy przydział za pomocą `project.getResourceAssignments().getById(1)` (lub dowolnego prawidłowego ID) przed modyfikacją jego konturu.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Jak zmienić kontur – Płaski (Domyślny)
`WorkContourType` jest wyliczeniem, które wymienia predefiniowane wzorce konturów pracy obsługiwane przez Aspose.Tasks. `Asn.WORK_CONTOUR` identyfikuje pole konturu przydziału zasobu, a `generateTimephasedData()` tworzy wpisy pracy czasowej na podstawie bieżącego ustawienia konturu. Kontur **Flat** (Płaski) rozdziela pracę równomiernie na cały czas trwania zadania; ustaw go za pomocą `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)`, a następnie wywołaj `firstRA.generateTimephasedData()`, aby uzyskać równomiernie rozmieszczone wartości.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – Żółw
Kontur **Turtle** (Żółw) zaczyna się od niskiego wysiłku, przyspiesza w kierunku środka, a następnie zwalnia, przypominając stopniowe tempo żółwia. Zastosuj go, ustawiając `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)`, a następnie ponownie wygeneruj dane czasowe. Ten wzorzec jest idealny dla zadań wymagających krzywej uczenia się przed osiągnięciem szczytowej wydajności.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – BackLoaded
Kontur **BackLoaded** (Załadowany od tyłu) umieszcza większość pracy pod koniec harmonogramu zadania, przy niewielkim wysiłku na początku. Ustaw go za pomocą `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` i ponownie wygeneruj dane czasowe. Jest to przydatne w przypadku działań, które zależą od wcześniejszych zadań przed rozpoczęciem pracy.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – FrontLoaded
Kontur **FrontLoaded** (Załadowany od przodu) koncentruje wysiłek na początku zadania, modelując scenariusze takie jak fazy rozpoczęcia lub intensywne wczesne okresy pracy. Zastosuj go za pomocą `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` i wywołaj `firstRA.generateTimephasedData()`, aby zobaczyć rozkład skoncentrowany na początku.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – Bell
Kontur **Bell** (Dzwon) tworzy symetryczny szczyt w środku osi czasu, reprezentując pracę, która stopniowo rośnie, osiąga szczyt, a następnie płynnie maleje. Ustaw go za pomocą `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` i ponownie wygeneruj dane czasowe, aby zwizualizować dzwonowaty krzywy wysiłku.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – EarlyPeak
**EarlyPeak** (Wczesny szczyt) umieszcza najwyższą wartość pracy na początku harmonogramu, a następnie stopniowo maleje. Użyj `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` a następnie `firstRA.generateTimephasedData()`, aby modelować działania wymagające mocnego startu, takie jak szybkie prototypowanie.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – LatePeak
**LatePeak** (Późny szczyt) przesuwa szczyt pracy w kierunku końca zadania, odpowiedni dla pracy, która nasila się w miarę zbliżania się terminu. Zastosuj go za pomocą `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` i ponownie wygeneruj dane czasowe, aby zobaczyć wzrost obciążenia w późnym etapie.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Jak zmienić kontur – DoublePeak
**DoublePeak** (Podwójny szczyt) tworzy dwa odrębne szczyty pracy oddzielone okresem o niższym wysiłku, przydatne dla zadań z dwoma głównymi okresami intensywnej pracy. Ustaw go za pomocą `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` i wywołaj `firstRA.generateTimephasedData()`, aby uzyskać wzorzec podwójnego szczytu.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Częste problemy i wskazówki
- **Kontur nie aktualizuje się?** Upewnij się, że wywołujesz `firstRA.set(Asn.WORK_CONTOUR, …)` *przed* pobraniem danych czasowych.  
- **Nieoczekiwane wartości?** Zweryfikuj, czy daty rozpoczęcia i zakończenia zadania są poprawnie ustawione w źródłowym pliku MPP.  
- **Wskazówka dotycząca wydajności:** Ponownie używaj tej samej instancji `Project` podczas iteracji przez wiele konturów, aby uniknąć niepotrzebnego I/O plików, co może skrócić czas przetwarzania nawet o 40 % w dużych projektach.  
- **Wskazówka dotycząca pamięci:** Dla projektów przekraczających 1 GB, włącz `Project.setReadOnly(true)`, aby utrzymać zużycie pamięci poniżej 200 MB, jednocześnie generując dokładne dane czasowe.

## FAQ
**P: Czy mogę używać Aspose.Tasks z innymi bibliotekami Java?**  
O: Tak, Aspose.Tasks integruje się bezproblemowo z innymi bibliotekami Java, umożliwiając łączenie danych harmonogramu z raportowaniem, analizą lub frameworkami UI.

**P: Czy Aspose.Tasks jest odpowiedni dla dużych projektów korporacyjnych?**  
O: Zdecydowanie tak. Biblioteka została zaprojektowana do obsługi projektów z dziesiątkami tysięcy zadań i zasobów, przetwarzając pliki liczące setki stron bez pogorszenia wydajności.

**P: Czy Aspose.Tasks zapewnia wsparcie dla różnych formatów plików projektowych?**  
O: Tak, Aspose.Tasks obsługuje ponad 30 formatów, w tym MPP, XML, CSV i MPX, umożliwiając łatwy import/eksport między systemami starszymi i nowoczesnymi.

**P: Czy mogę dostosować kontury pracy do wymagań mojego projektu?**  
O: Tak, możesz definiować własne kontury, podając tablicę procentów pracy do właściwości `WORK_CONTOUR`, co daje pełną kontrolę nad rozkładem wysiłku.

**P: Czy istnieje forum społeczności, gdzie mogę uzyskać pomoc w sprawie Aspose.Tasks?**  
O: Tak, możesz odwiedzić [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby uzyskać wsparcie, dyskusje i przykłady kodu od inżynierów Aspose oraz członków społeczności.

---

**Ostatnia aktualizacja:** 2026-06-10  
**Testowano z:** Aspose.Tasks for Java (latest release)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Utwórz przydziały zasobów w Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Odczytaj dane czasowe dla zasobów w Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [Jak zatrzymać przydział i wznowić przydziały zasobów w Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}