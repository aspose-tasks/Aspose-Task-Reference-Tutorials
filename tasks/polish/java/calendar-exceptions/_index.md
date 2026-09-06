---
date: 2026-08-18
description: Bezproblemowo twórz niestandardowe wyjątki kalendarza, integruj kalendarz
  MS Project oraz zarządzaj, definiuj, obsługuj i pobieraj wyjątki kalendarza w projektach
  Java przy użyciu Aspose.Tasks. Usprawnij przepływy pracy projektu dla efektywnego
  zarządzania projektami.
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
lastmod: 2026-08-18
linktitle: Wyjątki kalendarza
og_description: Dowiedz się, jak tworzyć wyjątki kalendarza, zarządzać kalendarzem
  projektu i ustawiać dni wolne od pracy w Javie przy użyciu Aspose.Tasks. Szybki
  przewodnik dla programistów.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Jak tworzyć wyjątki kalendarza przy użyciu Aspose.Tasks dla Javy
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: Jak tworzyć wyjątki kalendarza przy użyciu Aspose.Tasks dla Javy
url: /pl/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak tworzyć wyjątki kalendarza w Aspose.Tasks dla Javy

## Wprowadzenie

`Aspose.Tasks` jest biblioteką Java, która umożliwia programowe tworzenie, manipulację i konwersję plików Microsoft Project. W tym samouczku dowiesz się, jak **tworzyć wyjątki kalendarza** — niestandardowe okresy niepracujące, które nadpisują domyślny kalendarz projektu. Precyzyjna kontrola nad dniami pracującymi i niepracującymi jest niezbędna do dokładnego prognozowania harmonogramu, przydzielania zasobów i spełniania wymogów regionalnych świąt. Po zakończeniu tego przewodnika będziesz także wiedział, jak **zintegrować kalendarz MS Project** w swojej aplikacji Java oraz pobierać lub modyfikować jego wyjątki.

## Szybkie odpowiedzi
- **Co mogę osiągnąć?** Utworzyć, zmodyfikować i pobrać niestandardowe wyjątki kalendarza w projektach Java.  
- **Jakiej biblioteki wymagana jest?** Aspose.Tasks for Java (latest stable release).  
- **Czy potrzebuję licencji?** Tak, ważna licencja Aspose.Tasks jest wymagana do użytku produkcyjnego.  
- **Czy mogę pracować z plikami MS Project?** Oczywiście – możesz importować, edytować i eksportować dane kalendarza MS Project.  
- **Czy potrzebna jest specjalna konfiguracja?** Wystarczy dodać plik Aspose.Tasks JAR do classpath i zaimportować odpowiednie klasy.

## Jak tworzyć niestandardowe wyjątki kalendarza w Aspose.Tasks dla Javy?

Klasa `Project` reprezentuje plik Microsoft Project i zapewnia dostęp do jego zawartości. Obiekt `Calendar` definiuje godziny pracy i niepracujące dla projektu. Metoda `addException()` dodaje nowy wyjątek kalendarza do kalendarza.

Załaduj docelowy projekt przy użyciu `Project project = new Project("example.mpp")`, uzyskaj jego obiekt `Calendar` i wywołaj `addException()` z żądanym zakresem dat oraz ustawieniami czasu pracy. Ten dwustopniowy wzorzec tworzy nowy wyjątek natychmiast i zachowuje go po zapisaniu projektu. Dla powtarzających się świąt skonfiguruj `RecurrencePattern` na wyjątku przed zapisem.

Tworzenie wyjątków kalendarza w ten sposób pozwala **ustawiać dni niepracujące** precyzyjnie, niezależnie od tego, czy są to jednorazowe przestoje, czy roczne święta. Po dodaniu wyjątku możesz wywołać `project.save("updated.mpp")`, aby zapisać zmiany na dysku.

### Przegląd kroków
1. Załaduj plik projektu.  
2. Pobierz lub utwórz instancję `Calendar`.  
3. Zdefiniuj zakres dat wyjątku i czas pracy.  
4. (Opcjonalnie) Skonfiguruj powtarzalność dla rocznych świąt.  
5. Zapisz projekt.

## Zarządzaj wyjątkami kalendarza w Aspose.Tasks
[Learn how to add and remove calendar exceptions in Aspose.Tasks for Java efficiently](./add-remove/). Jeśli chodzi o zarządzanie projektami, elastyczność jest kluczowa. Aspose.Tasks umożliwia łatwe zarządzanie wyjątkami kalendarza, pozwalając na dynamiczne dostosowywanie harmonogramów projektów. Ten samouczek zapewnia przewodnik krok po kroku, dzięki czemu szybko opanujesz proces. Odkryj, jak z łatwością usprawnić przepływy pracy w zarządzaniu projektami.

## Definiuj dni tygodnia dla wyjątków kalendarza w Aspose.Tasks
[Master the art of defining weekdays for calendar exceptions in Java projects](./define-weekdays/) using Aspose.Tasks. Dokładne planowanie projektu wymaga skrupulatnej dbałości o szczegóły. Dzięki Aspose.Tasks możesz precyzyjnie definiować dni tygodnia dla wyjątków kalendarza, zapewniając, że projekty będą idealnie dopasowane do określonych terminów. Ten samouczek wyposaża Cię w wiedzę niezbędną do optymalizacji harmonogramu, dając kontrolę nad terminami projektów.

## Obsługuj wystąpienia w wyjątkach kalendarza przy użyciu Aspose.Tasks
[Effectively handle calendar exceptions in Java projects](./handle-occurrences/) with Aspose.Tasks for Java. Zarządzanie projektami to dynamiczny proces, często wymagający dostosowań w odpowiedzi na nieprzewidziane zdarzenia. Aspose.Tasks umożliwia skuteczne radzenie sobie z wyjątkami kalendarza, zapewniając usprawnione podejście do zarządzania projektami. Naucz się, jak z łatwością zarządzać niepewnościami projektowymi dzięki temu szczegółowemu samouczkowi.

## Pobierz wyjątki kalendarza przy użyciu Aspose.Tasks
[Learn how to retrieve calendar exceptions from MS Project using Aspose.Tasks for Java](./retrieve/). Bezproblemowo integruj wyjątki kalendarza w proces zarządzania projektami przy użyciu Aspose.Tasks. Ten samouczek prowadzi Cię krok po kroku przez proces pobierania wyjątków kalendarza, zapewniając płynną i efektywną integrację w Twoich projektach. Odkryj możliwości Aspose.Tasks, aby wzmocnić swoje zdolności zarządzania projektami.

## Jak zintegrować kalendarz MS Project z Aspose.Tasks?

Klasa `Project` ładuje plik Microsoft Project, udostępniając jego kalendarze oraz inne dane projektu. Zaimportuj istniejący plik MS Project używając `new Project("source.mpp")`; biblioteka automatycznie ładuje jego domyślny kalendarz oraz wszelkie niestandardowe wyjątki. Następnie możesz odczytać, zmodyfikować lub scalić te wyjątki przed zapisaniem projektu z powrotem na dysk. Takie podejście pozwala **modyfikować dane kalendarza MS Project** programowo, bez ręcznej edycji w interfejsie MS Project.

## Typowe przypadki użycia
- **Holiday scheduling** – Zdefiniuj święta narodowe jako dni niepracujące w wielu projektach.  
- **Shift work** – Ustaw niestandardowe tygodnie pracy dla zespołów pracujących w niestandardowych harmonogramach.  
- **Project phase gating** – Zablokuj okresy, w których nie powinno być planowanej pracy, np. okna konserwacyjne.  
- **Legacy migration** – Importuj kalendarze ze starszych plików MS Project i dostosuj je programowo.

## Wskazówki i najlepsze praktyki
- **Pro tip:** Zawsze pobieraj istniejący kalendarz przed dodaniem nowych wyjątków, aby uniknąć duplikatów.  
- **Warning:** Zmiana kalendarza, który jest już przypisany do zadań, może przesunąć terminy zadań; przelicz harmonogram po modyfikacjach.  
- **Performance:** Grupuj wiele aktualizacji wyjątków w jednej transakcji, aby zmniejszyć obciążenie I/O plików. Aspose.Tasks przetwarza pliki do 500 MB bez ładowania całego dokumentu do pamięci, obsługując ponad 50 wywołań API związanych z kalendarzem na sekundę na typowym sprzęcie serwerowym.

## Samouczki dotyczące wyjątków kalendarza
### [Zarządzaj wyjątkami kalendarza w Aspose.Tasks](./add-remove/)
Dowiedz się, jak efektywnie dodawać i usuwać wyjątki kalendarza w Aspose.Tasks dla Javy. Ulepszaj przepływy pracy w zarządzaniu projektami bez wysiłku.
### [Zdefiniuj dni tygodnia dla wyjątków kalendarza w Aspose.Tasks](./define-weekdays/)
Dowiedz się, jak definiować dni tygodnia dla wyjątków kalendarza w projektach Java przy użyciu Aspose.Tasks, aby zapewnić dokładne planowanie projektu.
### [Obsługuj wystąpienia w wyjątkach kalendarza przy użyciu Aspose.Tasks](./handle-occurrences/)
Dowiedz się, jak skutecznie obsługiwać wyjątki kalendarza w projektach Java przy użyciu Aspose.Tasks dla Javy. Usprawnij teraz proces zarządzania projektami.
### [Pobierz wyjątki kalendarza przy użyciu Aspose.Tasks](./retrieve/)
Dowiedz się, jak pobrać wyjątki kalendarza z MS Project przy użyciu Aspose.Tasks dla Javy. Samouczek krok po kroku zapewniający płynną integrację.

## Najczęściej zadawane pytania

**Q: Czy mogę modyfikować wyjątki kalendarza po opublikowaniu projektu?**  
A: Tak. Użyj API add‑remove i define‑weekdays, aby zaktualizować kalendarz, a następnie ponownie zapisz plik projektu.

**Q: Czy Aspose.Tasks obsługuje powtarzające się wyjątki (np. każdy pierwszy poniedziałek miesiąca)?**  
A: Zdecydowanie. Samouczek „handle occurrences” opisuje, jak ustawić powtarzalne wzorce.

**Q: Jak zapewnić, że mój niestandardowy kalendarz jest używany przez wszystkie zadania w projekcie?**  
A: Przypisz kalendarz do domyślnego kalendarza projektu lub wyraźnie ustaw go w właściwości `Calendar` każdego zadania.

**Q: Czy można scalić kalendarze z wielu plików MS Project?**  
A: Tak. Pobierz każdy kalendarz, połącz ich wyjątki programowo, a następnie przypisz scalony kalendarz do docelowego projektu.

**Q: Jakiej wersji Aspose.Tasks wymagana jest do tych funkcji?**  
A: Wszystkie funkcje są dostępne w bieżącej stabilnej wersji Aspose.Tasks dla Javy (2025.x).

---

**Ostatnia aktualizacja:** 2026-08-18  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz kalendarz projektu Aspose – Zdefiniuj dni tygodnia dla wyjątków kalendarza](/tasks/java/calendar-exceptions/define-weekdays/)
- [Pobierz wyjątki kalendarza przy użyciu Aspose.Tasks – samouczek asp tasks java](/tasks/java/calendar-exceptions/retrieve/)
- [Utwórz wyjątek kalendarza Aspose dla Javy](/tasks/java/calendar-exceptions/add-remove/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}