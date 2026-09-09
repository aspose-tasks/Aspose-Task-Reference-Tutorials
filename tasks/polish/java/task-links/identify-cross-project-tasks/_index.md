---
date: 2026-09-09
description: Dowiedz się, jak zidentyfikować zadania międzyprojektowe przy użyciu
  Aspose.Tasks dla Java. Poznaj płynną integrację, efektywne zarządzanie i przykłady
  z rzeczywistego świata.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Zidentyfikuj zadania międzyprojektowe w Aspose.Tasks
og_description: Zidentyfikuj zadania międzyprojektowe w Aspose.Tasks dla Java. Dowiedz
  się, jak ustawić katalog dokumentów, pobrać identyfikatory zadań i efektywnie zarządzać
  powiązanymi projektami.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Zidentyfikuj zadania międzyprojektowe w Aspose.Tasks – przewodnik Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Zidentyfikuj zadania międzyprojektowe w Aspose.Tasks
url: /pl/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Identyfikowanie zadań międzyprojektowych w Aspose.Tasks

## Wprowadzenie
W tym samouczku nauczysz się **jak identyfikować zadania międzyprojektowe** przy użyciu Aspose.Tasks dla Javy. Niezależnie od tego, czy zarządzasz portfelem wzajemnie zależnych harmonogramów, czy musisz audytować zewnętrzne zależności, poniższe kroki pokażą, jak znaleźć zadania odwołujące się do innych plików projektów, pobrać ich identyfikatory i pracować z nimi programowo.

## Szybkie odpowiedzi
- **Co oznacza „identyfikowanie zadań międzyprojektowych”?** Oznacza to znajdowanie zadań, które odwołują się do zadań w innym pliku projektu lub są od nich zależne.  
- **Która metoda wypisuje ID zadania?** Użyj `externalTask.get(Tsk.ID)`, aby wypisać ID zadania.  
- **Jak ustawić katalog dokumentu?** Przypisz ścieżkę folderu do zmiennej typu `String` (np. `dataDir`).  
- **Która właściwość pobiera zadanie po UID?** Wywołaj `getChildren().getByUid(yourUid)`.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Tak, do komercyjnych wdrożeń wymagana jest ważna licencja Aspose.Tasks.

## Co oznacza „identyfikowanie zadań międzyprojektowych”?
Identyfikowanie zadań międzyprojektowych pozwala śledzić zależności pomiędzy zadaniami rozproszonymi w wielu plikach Microsoft Project. Znajdując zadania, które odwołują się do zewnętrznych harmonogramów lub są od nich zależne, możesz zrozumieć, jak elementy pracy współdziałają poza granicami projektów, zapobiegać podwójnemu wysiłkowi i utrzymywać dokładne terminy. Ta funkcja jest niezbędna w dużych portfelach, w których zadania są współdzielone lub zależą od zewnętrznych harmonogramów.

## Dlaczego używać Aspose.Tasks dla Javy?
Aspose.Tasks dla Javy obsługuje **ponad 50 formatów wejściowych i wyjściowych** (w tym MPP, MPX, XML i CSV) i może przetwarzać projekty zawierające **do 10 000 zadań** bez ładowania całego pliku do pamięci. Biblioteka działa na każdej platformie zgodnej z JVM, nie wymaga instalacji Microsoft Project i zapewnia pełny dostęp API do ID, UID, zewnętrznych ID oraz metadanych powiązań.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

- Środowisko programistyczne Java (JDK 8 lub wyższy).  
- Aspose.Tasks dla Javy zainstalowane. Możesz pobrać go **[tutaj](https://releases.aspose.com/tasks/java/)**.  
- Ważny plik licencji Aspose.Tasks, jeśli planujesz uruchamiać kod w środowisku produkcyjnym.

## Importowanie pakietów
Klasa `Project` reprezentuje plik Microsoft Project, `Task` reprezentuje pojedyncze zadanie, a `Tsk` dostarcza stałe pól zadania.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Krok 1: ustaw katalog dokumentu
Ciąg znaków `dataDir` przechowuje ścieżkę do folderu zawierającego Twoje pliki `.mpp`.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Krok 2: załaduj projekt zewnętrzny
`Project externalProject` ładuje wskazany plik projektu zewnętrznego do analizy.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Krok 3: pobierz zadanie zewnętrzne po UID
`externalProject.getChildren().getByUid(uid)` pobiera zadanie z kolekcji zadań projektu zewnętrznego przy użyciu jego unikalnego identyfikatora.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Krok 4: wypisz ID zadania (główny przypadek użycia)
`externalTask.get(Tsk.ID)` zwraca wewnętrzny ID przydzielony przez Aspose.Tasks dla danego zadania.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Krok 5: wypisz oryginalny (zewnętrzny) ID zadania
`externalTask.get(Tsk.ExternalID)` pobiera oryginalny ID zadania, jak zdefiniowano w pliku źródłowym projektu.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Powtórz powyższe kroki dla wszystkich dodatkowych zadań, które musisz śledzić pomiędzy projektami.

## Częste problemy i wskazówki
- **Błędy ścieżki** – Upewnij się, że `dataDir` kończy się odpowiednim separatorem plików (`/` lub `\\`).  
- **UID nie znaleziony** – Sprawdź, czy UID istnieje w projekcie zewnętrznym; użyj `externalProject.getRootTask().getChildren().size()`, aby wyświetlić dostępne UIDy.  
- **Wyjątki licencyjne** – Brak lub nieprawidłowa licencja spowoduje wyrzucenie wyjątku licencyjnego w czasie wykonywania.  
- **Duże projekty** – W projektach powyżej 5 000 zadań rozważ użycie `ProjectReader` z flagą `LoadOptions`, aby strumieniować dane i zmniejszyć zużycie pamięci.

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Tasks z innymi językami programowania?**  
O: Tak, Aspose.Tasks obsługuje wiele języków, w tym Java, .NET i inne.

**P: Gdzie mogę znaleźć szczegółową dokumentację Aspose.Tasks dla Javy?**  
O: Zapoznaj się z dokumentacją **[tutaj](https://reference.aspose.com/tasks/java/)**.

**P: Czy dostępna jest darmowa wersja próbna Aspose.Tasks dla Javy?**  
O: Tak, darmową wersję próbną możesz uzyskać **[tutaj](https://releases.aspose.com/)**.

**P: Jak mogę uzyskać tymczasową licencję na Aspose.Tasks?**  
O: Tymczasową licencję można uzyskać **[tutaj](https://purchase.aspose.com/temporary-license/)**.

**P: Potrzebujesz pomocy lub masz konkretne pytania?**  
O: Odwiedź forum wsparcia Aspose.Tasks **[tutaj](https://forum.aspose.com/c/tasks/15)**.

---

**Ostatnia aktualizacja:** 2026-09-09  
**Testowano z:** Aspose.Tasks for Java 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose

## Powiązane samouczki

- [Tworzenie zależności zadań w zarządzaniu projektami w Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Ustaw datę rozpoczęcia projektu i zarządzaj zadaniami nadrzędnymi i podrzędnymi w Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Tworzenie projektu MPP w Javie – Zmiana postępu zadania przy użyciu Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}