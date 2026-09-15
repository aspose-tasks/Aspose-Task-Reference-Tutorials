---
date: 2026-09-14
description: Dowiedz się, jak uzyskać walutę w MS Project i odczytać właściwości projektu
  w Javie przy użyciu Aspose.Tasks. Przewodnik krok po kroku, jak wyodrębnić cyfry
  waluty z pliku MPP.
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Jak uzyskać walutę z MS Project przy użyciu Aspose.Tasks
og_description: Dowiedz się, jak uzyskać walutę w MS Project i odczytać właściwości
  projektu w Javie przy użyciu Aspose.Tasks. Skorzystaj z tego zwięzłego samouczka
  Java, aby wyodrębnić cyfry waluty z pliku MPP.
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Jak uzyskać walutę w MS Project przy użyciu Aspose.Tasks – przewodnik Java
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Jak uzyskać walutę w MS Project przy użyciu Aspose.Tasks
url: /pl/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak uzyskać walutę projektu MS przy użyciu Aspose.Tasks

## Wprowadzenie
Jeśli zastanawiasz się **jak uzyskać informacje o walucie projektu MS** z pliku Microsoft Project, trafiłeś we właściwe miejsce. W tym obszernym samouczku odkryjesz **jak pracować z wartościami waluty projektu MS** przy użyciu biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy tworzysz narzędzie raportujące, narzędzie migracyjne, czy po prostu potrzebujesz odczytać ustawienia waluty z **pliku projektu java**, ten przewodnik przeprowadzi Cię przez każdy krok — od załadowania pliku *.mpp* po wyodrębnienie cyfr waluty. Po zakończeniu będziesz pewnie obsługiwać dane waluty projektu MS w swoich aplikacjach.

## Szybkie odpowiedzi
- **Jaką bibliotekę odczytuje pliki MS Project?** Aspose.Tasks for Java.  
- **Ile linii kodu potrzebnych jest do uzyskania cyfr waluty?** Tylko trzy zwięzłe linie po załadowaniu projektu.  
- **Czy potrzebuję licencji do rozwoju?** Darmowa wersja próbna działa w testach; licencja komercyjna jest wymagana w produkcji.  
- **Jaką wersję Javy obsługuje?** Java 8 lub wyższą (dowolny JDK, który uruchamia Aspose.Tasks).  
- **Czy mogę pobrać inne właściwości projektu?** Tak – Aspose.Tasks udostępnia pełny zestaw pól projektu (np. datę rozpoczęcia, stawki kosztów itp.).

## Czym jest waluta projektu MS?
Właściwość `ms project currency` określa liczbę miejsc dziesiętnych, które Microsoft Project używa przy wyświetlaniu wartości pieniężnych. Jest ona przechowywana w pliku projektu jako pole **CURRENCY_DIGITS** i decyduje, czy kwoty wyświetlane są jako liczby całkowite, z jednym miejscem po przecinku, dwoma miejscami itp. To ustawienie bezpośrednio wpływa na raporty budżetowe, zestawienia kosztów oraz wszelkie interfejsy użytkownika pokazujące dane finansowe, co czyni je niezbędnym dla dokładnej wymiany danych.

## Dlaczego używać Aspose.Tasks do obsługi waluty projektu MS?
Aspose.Tasks pozwala wyodrębnić cyfry waluty bez instalowania Microsoft Project i robi to z wydajnością klasy korporacyjnej. Biblioteka obsługuje **ponad 30 lat wersji plików Project** — od Project 2000 do Project 2024 — obejmując ponad **150 odrębnych schematów plików**. Załadowanie projektu o 500 stronach zazwyczaj zajmuje mniej niż **2 sekundy** na standardowym serwerze, a możesz zapytać tylko o potrzebne pola, utrzymując zużycie pamięci poniżej **50 MB** nawet dla największych harmonogramów.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz następujące elementy:

1. **Środowisko programistyczne Java** – zainstalowany i skonfigurowany JDK 8 lub nowszy.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR z oficjalnej strony: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Podstawowa znajomość Javy** – powinieneś swobodnie tworzyć projekt Java, dodawać zewnętrzne biblioteki i uruchamiać metodę `main`.  

## Importowanie pakietów
Najpierw zaimportuj klasy, które będą potrzebne.  
Zaimportuj klasę `Project` oraz powiązane narzędzia z biblioteki Aspose.Tasks.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: określ katalog danych
Określ folder, który zawiera Twój **java project file** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Zastąp `"Your Data Directory"` absolutną lub względną ścieżką, w której znajduje się `project.mpp`.

## Krok 2: załaduj plik mpp  
Teraz zobaczymy **jak załadować pliki mpp** przy użyciu Aspose.Tasks.  
Klasa `Project` reprezentuje plik Microsoft Project i zapewnia dostęp do jego właściwości.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Upewnij się, że nazwa pliku jest dokładnie taka sama; w przeciwnym razie zostanie zgłoszony `IOException`.

## Krok 3: pobierz cyfry waluty  
Po załadowaniu projektu wyodrębnienie **ms project currency** cyfr jest jednowierszowe:  
Metoda `getCurrencyDigits()` zwraca liczbę miejsc dziesiętnych zdefiniowanych dla wartości pieniężnych.  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Wywołanie zwraca `Integer` reprezentujący liczbę miejsc dziesiętnych (np. `2` dla centów). Wartość jest wypisywana na konsolę, ale możesz ją także przechować w zmiennej do dalszego przetwarzania.

## Typowe problemy i wskazówki
- **Plik nie znaleziony** – sprawdź dokładnie ścieżkę `dataDir` i upewnij się, że nazwa pliku jest poprawna, łącznie z rozszerzeniem `.mpp`.  
- **Nieobsługiwana wersja pliku** – Aspose.Tasks obsługuje formaty Project 2000‑2024; starsze lub uszkodzone pliki mogą wymagać konwersji.  
- **Licencja nie ustawiona** – w trakcie rozwoju wersja próbna działa, ale w produkcji musisz zastosować ważną licencję, aby uniknąć znaków wodnych oceny.

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks może obsługiwać inne atrybuty projektu oprócz cyfr waluty?**  
A: Tak, Aspose.Tasks oferuje szeroki zakres funkcjonalności do manipulacji różnymi aspektami plików Project, takimi jak zadania, zasoby i pola niestandardowe.

**Q: Czy Aspose.Tasks jest odpowiedni dla aplikacji klasy enterprise?**  
A: Absolutnie, Aspose.Tasks został zaprojektowany tak, aby sprostać wymaganiom projektów klasy enterprise, oferując wysoką wydajność i skalowalność.

**Q: Czy Aspose.Tasks wspiera rozwój wieloplatformowy?**  
A: Tak, możesz używać Aspose.Tasks for Java na dowolnej platformie obsługującej środowisko Java Runtime (Windows, Linux, macOS).

**Q: Czy mogę wypróbować Aspose.Tasks przed zakupem?**  
A: Tak, możesz pobrać darmową wersję próbną ze [strony wydawniczej Aspose](https://releases.aspose.com/).

**Q: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks?**  
A: Wsparcie znajdziesz na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Last updated:** 2026-09-14  
**Tested with:** Aspose.Tasks for Java (latest at time of writing)  
**Author:** Aspose

## Powiązane samouczki

- [java project properties – Wyodrębnij symbol waluty z MPP przy użyciu Aspose.Tasks for Java](/tasks/java/currency/currency-symbols/)
- [Jak pobrać walutę z MS Project przy użyciu Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Project Properties Java – Odczytaj metadane przy użyciu Aspose.Tasks](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}