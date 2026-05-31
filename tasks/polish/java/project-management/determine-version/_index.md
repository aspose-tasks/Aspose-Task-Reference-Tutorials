---
date: 2026-05-31
description: Dowiedz się, jak uzyskać wersję projektu i odczytać datę ostatniego zapisu
  z plików MS Project przy użyciu Aspose.Tasks dla Java. Przewodnik krok po kroku
  z przykładami kodu.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Określ wersję projektu za pomocą Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak uzyskać wersję projektu – Aspose Tasks Java Tutorial
url: /pl/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak uzyskać wersję projektu – Samouczek Aspose Tasks Java

W tym **samouczku Aspose Tasks Java** dowiesz się **jak uzyskać wersję projektu** pliku Microsoft Project oraz jak **pobrać datę ostatniego zapisu** przy użyciu biblioteki Aspose.Tasks dla Javy. Znajomość wersji pliku i znacznika czasu zapisu pomaga unikać problemów z kompatybilnością, egzekwować polityki migracji i prowadzić dokładne dzienniki audytu. Przejdziemy przez każdy krok — od konfiguracji środowiska po wyświetlenie wersji i daty — abyś mógł zintegrować to sprawdzenie w dowolnej aplikacji Java z pewnością.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Określenie wersji pliku MS Project oraz daty ostatniego zapisu przy użyciu Aspose.Tasks dla Javy.  
- **Czy muszę mieć zainstalowany Microsoft Project?** Nie, Aspose.Tasks działa niezależnie od Microsoft Project.  
- **Jakie formaty plików są obsługiwane?** Pliki Project oparte na XML, takie jak MPP i XML, są w pełni obsługiwane.  
- **Jak długo trwa implementacja?** Około 5‑10 minut dla podstawowego sprawdzenia wersji.  
- **Czy wymagana jest licencja?** Darmowa wersja próbna działa w ocenie; licencja komercyjna jest wymagana w środowisku produkcyjnym.

## Czym jest samouczek Aspose Tasks Java?
`Aspose.Tasks` Java tutorial jest zwięzłym, praktycznym przewodnikiem, który demonstruje, jak programowo współdziałać z danymi Microsoft Project. Pokazuje, jak odczytywać, modyfikować i analizować informacje o projekcie bez konieczności instalacji Microsoft Project na serwerze. Dodatkowo obejmuje ładowanie plików, dostęp do właściwości i zapisywanie zmian, umożliwiając programistom efektywną automatyzację zadań zarządzania projektami.

## Dlaczego używać Aspose.Tasks do określenia wersji projektu?
Aspose.Tasks zapewnia **dokładne metadane wersji** oraz **znaczniki czasu ostatniego zapisu**, działając na każdym systemie operacyjnym obsługującym Javę. Przetwarza pliki do **500 stron w mniej niż 2 sekundy** na standardowym procesorze 2,5 GHz, co czyni go idealnym rozwiązaniem do automatyzacji wsadowej i scenariuszy migracji na dużą skalę.

## Wymagania wstępne
Before we begin, ensure you have:

1. **Java Development Kit (JDK)** – wersja 8 lub nowsza.  
2. **Aspose.Tasks for Java JAR** – pobierz ze [strony internetowej](https://releases.aspose.com/tasks/java/) i dodaj do classpath swojego projektu.  
3. **Plik MS Project** – plik Project oparty na XML (np. `input.xml`), który chcesz przeanalizować.  

> **Wskazówka:** Przechowuj plik Project w dedykowanym folderze `data`, aby utrzymać porządek w ścieżkach i uniknąć przypadkowego nadpisania.

## Importowanie pakietów
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Jak ustawić katalog projektu
Aby poprawnie zlokalizować pliki projektu, utwórz dedykowany katalog w strukturze aplikacji i przechowuj w nim wszystkie pliki wejściowe. Dzięki temu kod pozostaje przejrzysty i unika błędów związanych ze ścieżkami podczas ładowania plików. Użyj czytelnej nazwy zmiennej dla ścieżki katalogu, która może być absolutna lub względna względem katalogu głównego projektu.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Zastąp `"Your Data Directory"` ścieżką absolutną lub względną, w której znajduje się `input.xml`.

## Jak załadować projekt
`Project` jest podstawowym obiektem Aspose.Tasks, który reprezentuje plik Microsoft Project w pamięci, dając dostęp do wszystkich właściwości i kolekcji projektu. Po utworzeniu instancji `Project` możesz odpytywać jej pola, iterować po zadaniach lub modyfikować dane przed zapisaniem pliku z powrotem na dysk.

```java
Project project = new Project(dataDir + "input.xml");
```

Jeśli Twój plik ma inną nazwę, odpowiednio dostosuj `"input.xml"`.

## Jak określić wersję projektu
`Prj.SAVE_VERSION` jest właściwością wskazującą numer wersji Microsoft Project, która zapisała plik. `Prj.LAST_SAVED` przechowuje datę i godzinę ostatniego zapisu pliku. `Prj.SAVE_VERSION` zwraca numeryczną wersję aplikacji Microsoft Project, która zapisała plik (np. 12 dla Project 2010). `Prj.LAST_SAVED` podaje dokładną datę i godzinę ostatniej operacji zapisu.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

## Jak wyświetlić wynik
Po pobraniu informacji o wersji i dacie ostatniego zapisu zazwyczaj chcesz je wypisać na konsolę lub do pliku dziennika. Użyj `System.out.println`, aby wyświetlić wartości, formatując datę w razie potrzeby. Potwierdza to pomyślne wyodrębnienie i zapewnia natychmiastową informację zwrotną podczas programowania lub w skryptach automatycznych.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Typowe problemy i rozwiązania
| Problem | Powód | Rozwiązanie |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | Nie znaleziono pliku lub niepoprawna ścieżka | Zweryfikuj `dataDir` i nazwę pliku; użyj ścieżki absolutnej do testów. |
| Nieoczekiwana liczba wersji (np. 0) | Ładowanie pliku XML, który nie jest projektem | Upewnij się, że plik jest prawidłowym plikiem Microsoft Project (MPP/XML). |
| Wyjątek licencyjny | Używanie wersji próbnej bez ważnej licencji w produkcji | Zastosuj licencję Aspose.Tasks (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Tasks z innymi językami programowania?**  
A: Tak, Aspose.Tasks obsługuje .NET, Javę i C++ oraz inne.

**Q: Czy Aspose.Tasks jest odpowiedni dla projektów na dużą skalę?**  
A: Zdecydowanie; może przetwarzać projekty o setkach stron w ciągu kilku sekund bez ładowania całego pliku do pamięci.

**Q: Czy mogę dostosować dane projektu przy użyciu Aspose.Tasks?**  
A: Tak, możesz modyfikować zadania, zasoby, kalendarze i dowolny inny element projektu za pośrednictwem API.

**Q: Czy Aspose.Tasks wymaga instalacji Microsoft Project?**  
A: Nie, biblioteka działa niezależnie i nie wymaga Microsoft Project na maszynie hosta.

**Q: Czy dostępne jest wsparcie techniczne dla Aspose.Tasks?**  
A: Tak, pomoc można uzyskać na forum Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

**Dodatkowe pytania i odpowiedzi**

**Q: Jak pobrać inne właściwości projektu (np. autor, firma)?**  
A: Użyj `project.get(Prj.AUTHOR)` lub `project.get(Prj.COMPANY)` w taki sam sposób, jak pobierasz wersję.

**Q: Czy mogę sprawdzić wersję pliku MPP (binarny)?**  
A: Tak, Aspose.Tasks ładuje pliki `.mpp` bezpośrednio; właściwość `Prj.SAVE_VERSION` działa również dla formatów binarnych.

**Q: Czy istnieje sposób, aby programowo zaktualizować starszy plik projektu do nowszej wersji?**  
A: Załaduj starszy plik, a następnie zapisz go przy użyciu `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks zapisuje plik w najnowszym formacie domyślnie.

## Zakończenie
Teraz opanowałeś **sposób uzyskania wersji projektu** oraz **pobrania daty ostatniego zapisu** z plików MS Project przy użyciu Aspose.Tasks dla Javy. Włącz te fragmenty kodu do potoków automatyzacji, narzędzi raportujących lub narzędzi migracyjnych, aby mieć pewność, że zawsze znasz dokładną wersję Project, z którą pracujesz.

---

**Ostatnia aktualizacja:** 2026-05-31  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Ustaw datę rozpoczęcia projektu w MS Project przy użyciu Aspose.Tasks dla Java](/tasks/java/project-properties/write-project-info/)
- [Odczytaj bazę danych Microsoft Project przy użyciu Aspose.Tasks dla Java](/tasks/java/project-data-reading/read-project-database/)
- [Zapisz projekt jako szablon, CSV i tekst przy użyciu Aspose.Tasks dla Java](/tasks/java/project-file-operations/save-csv-text-template/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}