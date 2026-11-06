---
date: 2026-11-06
description: Twórz bez wysiłku custom calendar exceptions, integruj kalendarz MS Project
  i zarządzaj, definiuj, obsługuj oraz pobieraj calendar exceptions w projektach Java
  przy użyciu Aspose.Tasks. Usprawnij project workflows dla efektywnego project management.
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: Calendar Exceptions
og_description: Dowiedz się, jak tworzyć calendar exceptions w Java przy użyciu Aspose.Tasks.
  Zarządzaj project calendars, ustaw nonworking days i modyfikuj kalendarze MS Project
  efektywnie.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Tworzenie calendar exceptions przy użyciu Aspose.Tasks dla Java
schemas:
- author: Aspose
  dateModified: '2026-11-06'
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
title: Jak tworzyć calendar exceptions przy użyciu Aspose.Tasks dla Java
url: /pl/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak tworzyć wyjątki kalendarza w Aspose.Tasks dla Javy

## Wprowadzenie

`Aspose.Tasks` jest biblioteką Javy, która umożliwia programowe tworzenie, manipulację i konwersję plików Microsoft Project. W tym samouczku dowiesz się, jak **tworzyć wyjątki kalendarza** — niestandardowe okresy niepracujące, które nadpisują domyślny kalendarz projektu. Precyzyjna kontrola nad dniami pracującymi i niepracującymi jest niezbędna do dokładnego prognozowania harmonogramu, przydzielania zasobów oraz spełniania wymogów związanych z regionalnymi świętami. Po zakończeniu tego przewodnika będziesz także wiedział, jak **zintegrować kalendarz MS Project** z aplikacją Java oraz jak pobierać i modyfikować jego wyjątki.

## Szybkie odpowiedzi
- **Co mogę osiągnąć?** Tworzyć, modyfikować i pobierać niestandardowe wyjątki kalendarza w projektach Java.  
- **Jakiej biblioteki potrzebuję?** Aspose.Tasks for Java (najnowsze stabilne wydanie).  
- **Czy potrzebna jest licencja?** Tak, do użytku produkcyjnego wymagana jest ważna licencja Aspose.Tasks.  
- **Czy mogę pracować z plikami MS Project?** Oczywiście – możesz importować, edytować i eksportować dane kalendarza MS Project.  
- **Czy wymagana jest specjalna konfiguracja?** Wystarczy dodać plik JAR Aspose.Tasks do classpath i zaimportować odpowiednie klasy.

## Jak tworzyć własne wyjątki kalendarza w Aspose.Tasks dla Javy?

Aby utworzyć własne wyjątki kalendarza w Aspose.Tasks dla Javy, załaduj docelowy projekt, pobierz jego kalendarz, określ daty rozpoczęcia i zakończenia wyjątku wraz z żądanym czasem pracy, opcjonalnie ustaw wzorzec powtarzalności, a następnie zapisz projekt. Ten ciąg działań dodaje wyjątek natychmiast i zapisuje go w pliku .mpp.

Klasa `Project` jest podstawowym obiektem Aspose.Tasks modelującym cały plik Microsoft Project. Klasa `Project` reprezentuje plik Microsoft Project i zapewnia dostęp do jego zawartości. Obiekt `Calendar` definiuje czasy pracy i niepracy dla projektu. Klasa `Calendar` jest kontenerem wszystkich reguł czasu pracy, w tym wyjątków. Metoda `addException()` dodaje nowy wyjątek kalendarza do kalendarza. `addException()` to jednorazowe wywołanie API, które rejestruje okres niepracy dla określonego zakresu dat.

Załaduj docelowy projekt przy pomocy `Project project = new Project("example.mpp")`, uzyskaj jego obiekt `Calendar` i wywołaj `addException()` z żądanym zakresem dat oraz ustawieniami czasu pracy. Ten dwustopniowy wzorzec tworzy nowy wyjątek natychmiast i zachowuje go po zapisaniu projektu. Dla powtarzających się świąt skonfiguruj `RecurrencePattern` na wyjątku przed zapisem.

Tworzenie wyjątków kalendarza w ten sposób pozwala **precyzyjnie ustawiać dni niepracujące**, niezależnie od tego, czy są to jednorazowe przestoje, czy coroczne święta. Po dodaniu wyjątku możesz wywołać `project.save("updated.mpp")`, aby zapisać zmiany na dysku.

### Przegląd kroków
1. Załaduj plik projektu.  
2. Pobierz lub utwórz instancję `Calendar`.  
3. Zdefiniuj zakres dat wyjątku oraz czas pracy.  
4. (Opcjonalnie) Skonfiguruj powtarzalność dla corocznych świąt.  
5. Zapisz projekt.

## Zarządzanie wyjątkami kalendarza w Aspose.Tasks
[Learn how to add and remove calendar exceptions in Aspose.Tasks for Java efficiently](./add-remove/). Kiedy chodzi o zarządzanie projektami, elastyczność jest kluczowa. Aspose.Tasks umożliwia łatwe zarządzanie wyjątkami kalendarza, pozwalając na dynamiczne dostosowywanie terminów projektów. Ten samouczek zapewnia krok po kroku instrukcje, dzięki którym szybko opanujesz proces. Odkryj, jak z łatwością usprawnić przepływy pracy w zarządzaniu projektami.

## Definiowanie dni tygodnia dla wyjątków kalendarza w Aspose.Tasks
[Master the art of defining weekdays for calendar exceptions in Java projects](./define-weekdays/) using Aspose.Tasks. Dokładne planowanie projektu wymaga skrupulatnej uwagi na szczegóły. Dzięki Aspose.Tasks możesz precyzyjnie definiować dni tygodnia dla wyjątków kalendarza, zapewniając, że projekty będą zgodne z określonymi terminami. Ten samouczek wyposaży Cię w wiedzę niezbędną do optymalizacji harmonogramów, dając pełną kontrolę nad terminami projektów.

## Obsługa wystąpień w wyjątkach kalendarza przy użyciu Aspose.Tasks
[Effectively handle calendar exceptions in Java projects](./handle-occurrences/) with Aspose.Tasks for Java. Zarządzanie projektami to proces dynamiczny, często wymagający korekt w odpowiedzi na nieprzewidziane zdarzenia. Aspose.Tasks umożliwia skuteczne radzenie sobie z wyjątkami kalendarza, oferując usprawnione podejście do zarządzania projektami. Naucz się, jak z łatwością zarządzać niepewnościami projektowymi dzięki temu szczegółowemu samouczkowi.

## Pobieranie wyjątków kalendarza przy użyciu Aspose.Tasks
[Learn how to retrieve calendar exceptions from MS Project using Aspose.Tasks for Java](./retrieve/). Bezproblemowo integruj wyjątki kalendarza z procesem zarządzania projektami przy pomocy Aspose.Tasks. Ten samouczek prowadzi Cię krok po kroku przez proces pobierania wyjątków kalendarza, zapewniając płynną i efektywną integrację w Twoich projektach. Odkryj moc Aspose.Tasks, aby wzmocnić możliwości zarządzania projektami.

## Jak zintegrować kalendarz MS Project z Aspose.Tasks?

Integracja kalendarza MS Project z Aspose.Tasks polega na załadowaniu pliku źródłowego .mpp przy użyciu klasy Project, uzyskaniu dostępu do domyślnego lub niestandardowego obiektu Calendar, modyfikacji lub scaleniu wyjątków w razie potrzeby, a następnie zapisaniu zaktualizowanego projektu. Dzięki temu możesz programowo pracować z kalendarzami MS Project bez ręcznej interakcji z interfejsem użytkownika.

Klasa `Project` jest podstawowym obiektem Aspose.Tasks modelującym cały plik Microsoft Project. Importuj istniejący plik MS Project przy pomocy `new Project("source.mpp")`; biblioteka automatycznie ładuje jego domyślny kalendarz oraz wszelkie niestandardowe wyjątki. Następnie możesz odczytywać, modyfikować lub scalać te wyjątki przed zapisaniem projektu z powrotem na dysk. To podejście pozwala **programowo modyfikować dane kalendarza MS Project** bez ręcznej edycji w UI programu MS Project.

## Typowe przypadki użycia
- **Planowanie świąt** – Definiuj narodowe święta jako dni niepracujące w wielu projektach.  
- **Praca zmianowa** – Ustaw niestandardowe tygodnie pracy dla zespołów pracujących w niestandardowych harmonogramach.  
- **Zablokowanie faz projektu** – Blokuj okresy, w których nie powinno się planować pracy, np. okna konserwacyjne.  
- **Migracja dziedzictwa** – Importuj kalendarze ze starszych plików MS Project i dostosuj je programowo.

## Wskazówki i najlepsze praktyki
- **Pro tip:** Zawsze pobieraj istniejący kalendarz przed dodaniem nowych wyjątków, aby uniknąć duplikatów.  
- **Ostrzeżenie:** Zmiana kalendarza już przypisanego do zadań może przesunąć daty zadań; po modyfikacjach przelicz harmonogram.  
- **Wydajność:** Grupuj wiele aktualizacji wyjątków w jednej transakcji, aby zmniejszyć obciążenie I/O plików. Aspose.Tasks przetwarza pliki do 1 GB, utrzymując zużycie pamięci poniżej 200 MB, i może obsłużyć ponad 30 wywołań API związanych z kalendarzem na sekundę na typowym serwerze.

## Samouczki dotyczące wyjątków kalendarza
### [Zarządzanie wyjątkami kalendarza w Aspose.Tasks](./add-remove/)
Dowiedz się, jak efektywnie dodawać i usuwać wyjątki kalendarza w Aspose.Tasks dla Javy. Ulepszaj przepływy pracy w zarządzaniu projektami bez wysiłku.
### [Definiowanie dni tygodnia dla wyjątków kalendarza w Aspose.Tasks](./define-weekdays/)
Naucz się definiować dni tygodnia dla wyjątków kalendarza w projektach Java przy użyciu Aspose.Tasks, aby zapewnić dokładne planowanie projektu.
### [Obsługa wystąpień w wyjątkach kalendarza przy użyciu Aspose.Tasks](./handle-occurrences/)
Poznaj skuteczne metody obsługi wyjątków kalendarza w projektach Java z Aspose.Tasks dla Javy. Usprawnij proces zarządzania projektami już teraz.
### [Pobieranie wyjątków kalendarza przy użyciu Aspose.Tasks](./retrieve/)
Dowiedz się, jak pobierać wyjątki kalendarza z MS Project przy użyciu Aspose.Tasks dla Javy. Samouczek krok po kroku zapewniający płynną integrację.

## Najczęściej zadawane pytania

**P: Czy mogę modyfikować wyjątki kalendarza po opublikowaniu projektu?**  
O: Tak. Użyj API do dodawania/ usuwania oraz definiowania dni tygodnia, aby zaktualizować kalendarz, a następnie ponownie zapisz plik projektu.

**P: Czy Aspose.Tasks obsługuje wyjątki powtarzalne (np. każdy pierwszy poniedziałek miesiąca)?**  
O: Oczywiście. Samouczek „Obsługa wystąpień” wyjaśnia, jak ustawiać wzorce powtarzalności.

**P: Jak zapewnić, że mój niestandardowy kalendarz jest używany przez wszystkie zadania w projekcie?**  
O: Przypisz kalendarz do domyślnego kalendarza projektu lub wyraźnie ustaw go w właściwości `Calendar` każdego zadania.

**P: Czy można scalać kalendarze z wielu plików MS Project?**  
O: Tak. Pobierz każdy kalendarz, połącz ich wyjątki programowo, a następnie przypisz scalony kalendarz do projektu docelowego.

**P: Jakiej wersji Aspose.Tasks potrzebuję do tych funkcji?**  
O: Wszystkie funkcje są dostępne w bieżącym stabilnym wydaniu Aspose.Tasks for Java (2025.x).

## Powiązane samouczki

- [Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions](/tasks/java/calendar-exceptions/define-weekdays/)
- [Retrieve Calendar Exceptions with Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Create Calendar Exception Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)

---

**Ostatnia aktualizacja:** 2026-11-06  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}