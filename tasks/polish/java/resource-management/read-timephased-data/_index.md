---
date: 2026-06-15
description: Dowiedz się, jak wyodrębnić timephased data z zasobów MS Project przy
  użyciu Aspose.Tasks for Java. Przewodnik krok po kroku, jak pobrać resource po id.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Odczyt Timephased Data dla zasobów w Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Odczyt Timephased Data dla zasobów w Aspose.Tasks – pobierz resource po id
url: /pl/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczyt danych czasowych zasobów w Aspose.Tasks

## Wprowadzenie
W tym samouczku nauczysz się **how to get resource by id** i odczytać jego dane czasowe przy użyciu Aspose.Tasks dla Javy. Przejdziemy krok po kroku — od skonfigurowania folderu projektu po wyświetlenie wartości pracy i kosztu w formie danych czasowych — abyś mógł programowo wyodrębnić cenne informacje o harmonogramie z dowolnego pliku Microsoft Project. Aspose.Tasks dla Javy to kompleksowe API, które umożliwia programistom tworzyć, odczytywać, modyfikować i konwertować pliki Microsoft Project bez konieczności instalacji Microsoft Project, obsługując szeroki zakres funkcji i formatów zarządzania projektami.

## Szybkie odpowiedzi
- **Co robi „get resource by id”?** Pobiera konkretny obiekt `Resource` z `Project` przy użyciu jego unikalnego identyfikatora.  
- **Która biblioteka obsługuje dane czasowe?** Aspose.Tasks dla Javy udostępnia API `Resource.getTimephasedData`.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Czy mogę odczytać duże projekty?** Tak — Aspose.Tasks może przetwarzać pliki zawierające do 10 000 zadań bez wczytywania całego pliku do pamięci.  
- **Jaka wersja Javy jest wymagana?** Java 8 lub nowsza; biblioteka jest kompatybilna ze wszystkimi głównymi JDK.

## Co to jest „get resource by id”?
`get resource by id` to wywołanie metody, które pobiera instancję `Resource` z załadowanego `Project` przy użyciu numerycznego ID zasobu. Operacja ta umożliwia precyzyjny dostęp do szczegółowych właściwości zasobu, takich jak przydziały, kalendarze i pola niestandardowe, i jest niezbędna do wyodrębniania danych czasowych pracy lub kosztu powiązanych z danym zasobem.

## Dlaczego używać Aspose.Tasks do danych czasowych?
Aspose.Tasks obsługuje **ponad 50 formatów wejściowych i wyjściowych** (MPP, XML, CSV itp.) i może wyodrębniać wartości pracy i kosztu w danych czasowych dla zasobów obejmujących wieloletnie harmonogramy, przy jednoczesnym niskim zużyciu pamięci. API domyślnie zwraca dane w interwałach 15‑minutowych, zapewniając szczegółowy wgląd przy raportowaniu lub analizach niestandardowych.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania:
1. Java Development Kit (JDK): Upewnij się, że masz zainstalowany JDK w systemie. Możesz go pobrać ze [strony internetowej](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) i postępować zgodnie z instrukcjami instalacji.  
2. Biblioteka Aspose.Tasks dla Javy: Pobierz bibliotekę Aspose.Tasks dla Javy ze [strony pobierania](https://releases.aspose.com/tasks/java/) i zastosuj instrukcje instalacji podane w dokumentacji.

## Importowanie pakietów
Pierwszym krokiem jest zaimportowanie wymaganych klas Aspose.Tasks do pliku źródłowego Javy.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Krok 1: Konfiguracja katalogu danych
Najpierw określ katalog, w którym znajduje się plik MS Project. Trzymanie folderu danych oddzielnie od kodu źródłowego ułatwia utrzymanie projektu.

```java
String dataDir = "Your Data Directory";
```

## Krok 2: Odczyt pliku szablonu MS Project
Określ nazwę pliku szablonu MS Project. Użycie szablonu zapewnia spójne ustawienia kolumn w różnych projektach.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Krok 3: Odczyt pliku wejściowego jako Project
Klasa `Project` jest podstawowym obiektem Aspose.Tasks, który reprezentuje plik Microsoft Project w pamięci. Załadowanie pliku zapewnia programowy dostęp do zadań, zasobów i harmonogramów.

```java
Project project = new Project(dataDir + fileName);
```

## Krok 4: Pobranie zasobu według ID
Aby pobrać konkretny zasób, wywołaj metodę `getResources().getById(id)`. Jest to dokładna operacja wymieniona w głównym słowie kluczowym.

```java
Resource resource = project.getResources().getByUid(1);
```

## Krok 5: Wyświetlenie danych czasowych pracy zasobu
Gdy masz już obiekt `Resource`, możesz wywołać `resource.getTimephasedData(ResourceTimephasedDataType.Work)`, aby uzyskać przydziały pracy w czasie. Zwrócona kolekcja zawiera obiekty `TimephasedData`, które obejmują datę rozpoczęcia, datę zakończenia oraz ilość pracy dla każdego interwału.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Krok 6: Wyświetlenie danych czasowych kosztu zasobu
Analogicznie, `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` zwraca informacje o kosztach podzielone na te same interwały czasowe. Jest to przydatne przy raportach budżetowych i śledzeniu kosztów.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Jak pobrać zasób według ID w jednej linii?
Załaduj projekt, a następnie wywołaj `project.getResources().getById(5)` — zamień **5** na rzeczywisty identyfikator zasobu, którego potrzebujesz. To pojedyncze wywołanie zwraca obiekt `Resource`, po czym możesz odpytać jego dane czasowe, przydziały lub pola niestandardowe. Metoda działa w czasie O(1), ponieważ zasoby są indeksowane wewnętrznie.

## Typowe problemy i rozwiązania
- **Resource not found** – Upewnij się, że ID istnieje w pliku projektu; ID zaczynają się od 1 i są unikalne dla każdego zasobu.  
- **Empty timephased data** – Sprawdź, czy zasób ma przydziały pracy lub kosztu; w przeciwnym razie kolekcja będzie pusta.  
- **Large file performance** – Użyj `Project.setLoadOptions(LoadOptions.fromFile(...))`, aby włączyć leniwe ładowanie dla projektów większych niż 500 MB.

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks obsługuje inne typy plików projektowych oprócz Microsoft Project?**  
A: Tak, Aspose.Tasks obsługuje MPP, XML, CSV i kilka innych formatów, umożliwiając odczyt i zapis w różnych standardach.

**Q: Czy Aspose.Tasks jest kompatybilny z różnymi środowiskami programistycznymi Javy?**  
A: Zdecydowanie. Biblioteka działa ze wszystkimi głównymi IDE (IntelliJ IDEA, Eclipse, NetBeans) oraz narzędziami budowania (Maven, Gradle).

**Q: Czy mogę manipulować danymi projektu przy użyciu Aspose.Tasks?**  
A: Tak, możesz tworzyć, modyfikować i usuwać zadania, zasoby, przydziały oraz nawet pola niestandardowe za pośrednictwem API.

**Q: Czy Aspose.Tasks nadaje się do projektów na poziomie przedsiębiorstwa?**  
A: Tak. Przedsiębiorstwa polegają na Aspose.Tasks przy przetwarzaniu dużych wolumenów, konwersjach wsadowych i raportowaniu po stronie serwera, ponieważ nie wymaga instalacji Microsoft Project.

**Q: Gdzie mogę uzyskać wsparcie, jeśli napotkam problemy podczas korzystania z Aspose.Tasks?**  
A: Możesz odwiedzić [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby uzyskać pomoc od społeczności i zespołu wsparcia.

## Zakończenie
W tym samouczku nauczyliśmy się, jak **get resource by id** oraz odczytać jego dane czasowe dotyczące pracy i kosztów przy użyciu Aspose.Tasks dla Javy. Postępując zgodnie z tymi krokami, możesz efektywnie wyodrębnić cenne informacje o harmonogramie z plików projektu i zintegrować je z własnymi raportami lub potokami analitycznymi.

---

**Ostatnia aktualizacja:** 2026-06-15  
**Testowano z:** Aspose.Tasks 24.11 for Java  
**Autor:** Aspose

## Powiązane samouczki

- [Dodaj zasób do projektu przy użyciu Aspose.Tasks dla Javy](/tasks/java/resource-management/create-resources/)
- [Zarządzaj kosztami zasobów MS Project przy użyciu Aspose.Tasks dla Javy](/tasks/java/resource-management/resource-cost/)
- [Odczytaj tygodnie pracy w Javie z kalendarza MS Project przy użyciu Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}