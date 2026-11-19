---
date: 2026-11-19
description: Dowiedz się, jak utworzyć custom calendar Java przy użyciu Aspose.Tasks.
  Ten przewodnik pokazuje, jak definiować working days, ustawiać working hours i modyfikować
  kalendarze MS Project programowo.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: Kalendarze
og_description: Dowiedz się, jak utworzyć custom calendar Java z Aspose.Tasks. Opanuj
  definiowanie working days, ustawianie working hours oraz efektywne modyfikowanie
  kalendarzy MS Project.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Jak utworzyć custom calendar Java z Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: Jak utworzyć custom calendar Java z Aspose.Tasks
url: /pl/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalendarze

## Wprowadzenie

Jeśli jesteś programistą Java, który chce **tworzyć niestandardowe rozwiązania kalendarza Java**, trafiłeś we właściwe miejsce. To centrum gromadzi wszystkie samouczki Aspose.Tasks for Java, które pokazują, jak **zdefiniować dni robocze w MS Project**, **ustawić godziny pracy w MS Project** oraz programowo dostosować ustawienia kalendarza. Niezależnie od tego, czy budujesz nowy silnik harmonogramowania, czy rozszerzasz istniejący plan, opanowanie tych interfejsów API daje Ci precyzyjną kontrolę nad wzorcami dni roboczych, świętami i niestandardowymi zmianami — bez konieczności otwierania interfejsu MS Project UI.

## Szybkie odpowiedzi
- **Jaki jest główny cel definiowania dni roboczych?**  
  Aby poinformować MS Project, które dni są dniami roboczymi i jakie są ich godziny pracy.  
- **Która biblioteka obsługuje definiowanie dni roboczych w Javie?**  
  Aspose.Tasks for Java zapewnia płynne API do manipulacji kalendarzem.  
- **Czy potrzebuję licencji?**  
  Darmowa licencja ewaluacyjna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę zdefiniować wiele kalendarzy dla różnych zespołów?**  
  Tak – każdy projekt może zawierać kilka kalendarzy, każdy z własnymi ustawieniami dni roboczych.  
- **Czy istnieje przykładowy projekt, od którego można rozpocząć?**  
  Samouczek „Define Weekdays in Calendar” zamieszczony poniżej zawiera gotowy do uruchomienia przykład.

## Jak utworzyć niestandardowy kalendarz Java?

Załaduj projekt, utwórz lub pobierz kalendarz, dodaj definicje dni roboczych i zapisz plik — wszystko w kilku wywołaniach API. To podejście eliminuje ręczne kroki w interfejsie, pozwala automatyzować tworzenie kalendarzy w dziesiątkach projektów i zapewnia spójne wzorce dni roboczych w całej organizacji.

## Co to jest klasa Project?

Klasa `Project` jest centralnym obiektem do ładowania, edytowania i zapisywania plików MS Project. Przechowuje kolekcje zadań, zasobów i kalendarzy, udostępniając metody, które pozwalają programowo odczytywać i modyfikować każdy aspekt projektu. Korzystając z tej klasy, możesz uzyskać dostęp do kolekcji kalendarzy projektu, dostosować godziny pracy i zapisać zmiany z powrotem do pliku MPP lub XML.

## Jak zdefiniować dni robocze w kalendarzach MS Project?

Klasa `Project` reprezentuje plik MS Project i zapewnia dostęp do jego struktur danych. Obiekt `Calendar` przechowuje definicje czasu pracy oraz wyjątki dla projektu. Załaduj swój projekt przy pomocy `new Project("myproject.mpp")`, pobierz (lub utwórz) obiekt `Calendar`, a następnie wywołaj `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. Ten pojedynczy wiersz tworzy wpis dnia roboczego poniedziałku z 8‑godzinną zmianą. Powtórz dla pozostałych dni, a na koniec zapisz projekt przy pomocy `project.save("updated.mpp")`. Ten zwięzły wzorzec pozwala definiować, modyfikować lub usuwać dni robocze w kilku wywołaniach API, eliminując potrzebę ręcznej interakcji z UI.

## Co to jest obiekt WeekDay?

Obiekt `WeekDay` reprezentuje pojedynczy wpis dnia tygodnia w kalendarzu. Przechowuje informację, czy dzień jest roboczy, przedziały czasu pracy dla tego dnia oraz flagi domyślnego zachowania. Możesz dołączyć jeden lub więcej przedziałów `WorkingTime`, aby modelować podzielone zmiany, ustawić dzień jako niepracujący lub odziedziczyć domyślne ustawienia z kalendarza nadrzędnego.

## Jak zdefiniować dni robocze w MS Project?

Definiujesz dni robocze, dodając obiekty `WeekDay` do kolekcji `WeekDays` kalendarza. Każdy `WeekDay` określa, czy dzień jest roboczy oraz przedziały czasu uznawane za czas pracy. Na przykład, aby uczynić sobotę półdniem, dodaj `WeekDay` z pojedynczym `WorkingTime` od 10:00 do 14:00. API automatycznie aktualizuje obliczenia harmonogramu projektu.

## Jak ustawić godziny pracy w MS Project?

Ustaw godziny pracy, tworząc jeden lub więcej przedziałów `WorkingTime` dla każdego `WeekDay`. `WorkingTime` przyjmuje wartości godziny‑start, minuty‑start, godziny‑koniec i minuty‑koniec. Możesz przypisać wiele przedziałów do jednego dnia, aby modelować podzielone zmiany (np. 08:00‑12:00 i 13:00‑17:00). Po skonfigurowaniu wszystkich dni roboczych wywołaj `project.save(...)`, aby zapisać zmiany.

## Dlaczego używać Aspose.Tasks for Java do definiowania dni roboczych?

- **Pełna kontrola API** – Brak ograniczeń UI; możesz programowo tworzyć, modyfikować lub usuwać wpisy dni roboczych.  
- **Cross‑platform** – Działa w każdym środowisku kompatybilnym z JVM, od aplikacji desktopowych po usługi w chmurze.  
- **Precyzja** – Ustaw różne godziny pracy dla każdego dnia tygodnia, dodawaj wyjątki na święta i synchronizuj kalendarze w wielu projektach.  
- **Wydajność** – Przetwarzaj projekty z ponad 500 zadaniami i kalendarze zawierające ponad 100 tygodni bez ładowania całego UI, osiągając czasy konwersji poniżej 2 sekund na standardowym serwerze 2,5 GHz (twierdzenie oparte na benchmarku Aspose).  
- **Szerokie wsparcie formatów** – Aspose.Tasks obsługuje ponad 30 API związanych z kalendarzem i może importować/eksportować do ponad 20 formatów plików, umożliwiając płynną integrację z istniejącymi pipeline’ami danych projektowych.

## Wymagania wstępne
- Java 8 lub nowsza zainstalowana.  
- Biblioteka Aspose.Tasks for Java (pobrana ze strony Aspose lub dodana przez Maven/Gradle).  
- Ważna licencja Aspose.Tasks (licencja ewaluacyjna działa do nauki).  

## Zarządzanie właściwościami kalendarza MS Project w Aspose.Tasks

Odblokuj pełny potencjał zarządzania właściwościami kalendarza MS Project w Javie przy użyciu Aspose.Tasks. Nasz samouczek przeprowadzi Cię przez zawiłości zarządzania kalendarzem, oferując cenne wskazówki dotyczące dostosowywania i optymalizacji. Od dostosowywania godzin pracy po definiowanie specjalnych dat, opanujesz wszystko.

Gotowy, aby przejąć kontrolę nad harmonogramami projektu? [Poznaj samouczek tutaj](./properties/).

## Tworzenie kalendarzy MS Project przy użyciu Aspose.Tasks

Bez wysiłku usprawnij zarządzanie projektem poprzez tworzenie kalendarzy MS Project przy użyciu Aspose.Tasks for Java. Nasz samouczek upraszcza proces, zapewniając możliwość skonfigurowania kalendarzy dopasowanych do unikalnych potrzeb Twojego projektu. Zrób pierwszy krok w kierunku efektywnego planowania i organizacji projektu.

Gotowy, aby tworzyć kalendarze z łatwością? [Sprawdź samouczek](./create/).

## Definiowanie dni roboczych w kalendarzu za pomocą Aspose.Tasks

Dostosuj swoje kalendarze MS Project, definiując dni robocze przy użyciu Aspose.Tasks for Java. Ten samouczek prowadzi Cię przez proces dopasowywania dni roboczych i godzin, oferując elastyczność niezbędną do skutecznego zarządzania projektem. Spraw, aby Twoje kalendarze pracowały dla Ciebie.

Gotowy, aby łatwo definiować dni robocze? [Rozpocznij tutaj](./define-weekdays/).

Podczas przeglądania tych samouczków odkryjesz dodatkowe tematy, takie jak wyodrębnianie godzin pracy, tworzenie standardowego kalendarza, odczytywanie tygodni pracy oraz aktualizacja kalendarzy do formatu MPP. Każdy samouczek został przygotowany, aby dostarczyć praktycznej wiedzy, zapewniając możliwość bezpośredniego zastosowania tego, czego się nauczysz, w projektach Java.

## Pobieranie godzin pracy z kalendarza przy użyciu Aspose.Tasks

Uprość zadania zarządzania projektem, wyodrębniając godziny pracy z kalendarzy MS Project przy użyciu Aspose.Tasks for Java. Ten samouczek wyposaża Cię w umiejętności niezbędne do efektywnej optymalizacji harmonogramów projektu.

Gotowy, aby łatwo wyodrębnić godziny pracy? [Poznaj samouczek](./working-hours/).

## Tworzenie standardowego kalendarza w Aspose.Tasks

Rozwiń możliwości zarządzania projektem, ucząc się, jak stworzyć standardowy kalendarz MS Project w Javie przy użyciu Aspose.Tasks. Ten samouczek krok po kroku zapewnia możliwość wdrożenia ustandaryzowanego podejścia do harmonogramów projektu.

Gotowy, aby stworzyć standardowy kalendarz? [Sprawdź samouczek](./make-standard/).

## Odczytywanie tygodni pracy z kalendarza MS Project przy użyciu Aspose.Tasks

Uzyskaj kompleksowy wgląd w odczytywanie tygodni pracy z kalendarzy MS Project przy użyciu Aspose.Tasks for Java. Ten samouczek oferuje szczegółowe instrukcje, umożliwiając skuteczne zarządzanie harmonogramami projektu.

Gotowy, aby łatwo odczytać tygodnie pracy? [Rozpocznij tutaj](./read-work-weeks/).

## Aktualizacja kalendarzy MS Project do formatu MPP przy użyciu Aspose.Tasks

Bez wysiłku zaktualizuj kalendarze MS Project do formatu MPP przy użyciu Aspose.Tasks for Java. Ten samouczek zapewnia płynne podejście, aby Twoje dane projektowe były w odpowiednim formacie zapewniającym optymalną kompatybilność.

Gotowy, aby zaktualizować kalendarze do formatu MPP? [Poznaj samouczek](./update-to-mpp/).

Odblokuj pełny potencjał Aspose.Tasks for Java i podnieś swoje umiejętności zarządzania projektami. Każdy samouczek został zaprojektowany z myślą o programistach na każdym poziomie, zapewniając płynne doświadczenie edukacyjne. Zanurz się i zrewolucjonizuj swoją podróż w zarządzaniu projektami Java już dziś!

## Samouczki dotyczące kalendarzy
### [Zarządzanie właściwościami kalendarza MS Project w Aspose.Tasks](./properties/)
Learn how to manage MS Project calendar properties in Java using Aspose.Tasks. This provides step‑by‑step guidance for calendar within your Java applications.
### [Tworzenie kalendarzy MS Project przy użyciu Aspose.Tasks](./create/)
Learn how to create MS Project calendars using Aspose.Tasks for Java. Streamline project management with ease.
### [Definiowanie dni roboczych w kalendarzu za pomocą Aspose.Tasks](./define-weekdays/)
Learn how to define weekdays in MS Project calendar using Aspose.Tasks for Java. Customize working days and timings effortlessly.
### [Pobieranie godzin pracy z kalendarza przy użyciu Aspose.Tasks](./working-hours/)
Extract working hours from MS Project calendars easily with Aspose.Tasks for Java. Simplify project management tasks.
### [Tworzenie standardowego kalendarza w Aspose.Tasks](./make-standard/)
Learn how to create a standard MS Project calendar in Java using Aspose.Tasks. Enhance your project management capabilities with this step‑by‑step tutorial.
### [Odczytywanie tygodni pracy z kalendarza MS Project przy użyciu Aspose.Tasks](./read-work-weeks/)
Learn how to read work weeks from MS Project calendar using Aspose.Tasks for Java. Get step‑by‑step instructions in this comprehensive tutorial.
### [Aktualizacja kalendarzy MS Project do formatu MPP bez wysiłku przy użyciu Aspose.Tasks for Java](./update-to-mpp/)
Learn how to update MS Project calendars to MPP format effortlessly using Aspose.Tasks for Java.

## Najczęściej zadawane pytania

**Q: Czy mogę definiować różne godziny pracy dla każdego dnia tygodnia?**  
A: Tak. Aspose.Tasks pozwala ustawić godziny rozpoczęcia i zakończenia indywidualnie dla poniedziałku aż do niedzieli.

**Q: Jak radzić sobie z świętami lub dniami niepracującymi?**  
A: Po zdefiniowaniu dni roboczych możesz dodać wyjątki (daty), aby oznaczyć święta lub niestandardowe okresy niepracujące.

**Q: Czy można skopiować definicję dnia roboczego z jednego kalendarza do drugiego?**  
A: Oczywiście. Możesz pobrać obiekt `WeekDay` z istniejącego kalendarza i dodać go do innej instancji kalendarza.

**Q: Czy muszę ponownie załadować projekt po aktualizacji dni roboczych?**  
A: Nie. Zmiany są stosowane bezpośrednio do obiektu `Project` w pamięci; wystarczy zapisać projekt po zakończeniu.

**Q: Jakiej wersji Aspose.Tasks potrzebuję do manipulacji dniami roboczymi?**  
A: Wszystkie recent versions (20.10 i późniejsze) obsługują pełne API dni roboczych. Zalecamy użycie najnowszej stabilnej wersji dla najlepszej wydajności.

---

**Last Updated:** 2026-11-19  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Related Tutorials

- [Dodaj kalendarz do projektu przy użyciu Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Określ dni robocze i godziny pracy z Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Utwórz niestandardowe wyjątki kalendarza przy użyciu Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}