---
date: 2026-10-31
description: Dowiedz się, jak zapisać projekt jako PDF i odczytać bazę danych Microsoft
  Project przy użyciu Aspose.Tasks dla Java, a także połączyć się z Project Server,
  przekonwertować projekt na HTML oraz wyeksportować projekt do XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Odczytywanie danych projektu z bazy danych Microsoft Project w Aspose.Tasks
og_description: Zapisz projekt jako PDF i odczytaj bazę danych Microsoft Project przy
  użyciu Aspose.Tasks dla Java. Dowiedz się, jak połączyć się z Project Server, wyeksportować
  do HTML, XML i CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Zapisz projekt jako PDF i odczytaj bazę danych Microsoft Project przy użyciu
  Aspose.Tasks dla Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Zapisz projekt jako PDF i odczytaj bazę danych Microsoft Project przy użyciu
  Aspose.Tasks dla Java
url: /pl/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz projekt jako PDF i odczytaj bazę danych Microsoft Project przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
W tym samouczku dowiesz się, jak **odczytać bazę danych Microsoft Project** bezpośrednio z Microsoft Project Server, a następnie **zapisać projekt jako PDF** przy użyciu API Aspose.Tasks Java. Niezależnie od tego, czy potrzebujesz generować raporty do druku, migrować starsze dane, czy osadzić informacje o projekcie w własnym portalu, ten przewodnik przeprowadzi Cię przez każdy krok — od konfiguracji połączenia JDBC po eksport projektu do PDF, XML lub HTML. Po zakończeniu będziesz mieć gotowe rozwiązanie produkcyjne, które działa na dowolnym serwerze Java bez instalacji Microsoft Project.

## Szybkie odpowiedzi
- **Co robi Aspose.Tasks?** Zapewnia czysto‑Java API do odczytu, zapisu i manipulacji plikami i bazami danych Microsoft Project.  
- **Czy muszę mieć zainstalowany Microsoft Project?** Nie, Aspose.Tasks działa niezależnie od Microsoft Project.  
- **Jakiego typu bazy danych są obsługiwane?** Microsoft SQL Server, backend Project Server.  
- **Czy mogę eksportować do innych formatów?** Tak — PDF, XML, HTML, CSV, PNG, JPEG i więcej.  
- **Jakie są główne wymagania wstępne?** JDK 8 lub nowszy, biblioteka Aspose.Tasks for Java, sterownik JDBC SQL Server oraz prawidłowe poświadczenia Project Server.

## Co oznacza „odczyt bazy danych Microsoft Project”?
Odczyt bazy danych Microsoft Project oznacza połączenie się z repozytorium SQL Server serwera Project, wyodrębnienie przechowywanych danych projektu i załadowanie ich do obiektu `Project`, który Aspose.Tasks może manipulować. Takie podejście jest idealne do automatycznego raportowania, migracji danych lub własnych analiz.

## Dlaczego używać Aspose.Tasks dla Javy?
Aspose.Tasks dla Javy pozwala pracować z danymi Microsoft Project bez potrzeby aplikacji desktopowej, oferując czysto‑Java rozwiązanie działające na każdej platformie. Dostarcza kompleksowy model obiektowy dla zadań, zasobów, kalendarzy i pól niestandardowych oraz radzi sobie z dużymi projektami korporacyjnymi, co czyni go idealnym do automatycznego raportowania, migracji i integracji.

- **Brak zależności od Microsoft Project** — działa na dowolnym serwerze lub w środowisku CI.  
- **Bogaty model obiektowy** — dostęp do zadań, zasobów, przydziałów, kalendarzy i pól niestandardowych programowo.  
- **Wiele opcji eksportu** — Aspose.Tasks obsługuje eksport do **ponad 20 formatów plików**, w tym PDF, XML, HTML, CSV, PNG i JPEG, jednym wywołaniem API.  
- **Wysoka wydajność** — biblioteka może przetworzyć projekty zawierające **do 10 000 zadań** w mniej niż minutę i strumieniuje dane, aby uniknąć ładowania całego pliku do pamięci.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

1. Działające środowisko programistyczne Java (JDK 8 lub nowszy).  
2. Bibliotekę Aspose.Tasks for Java dodaną do classpath projektu.  
3. Poświadczenia dostępu do bazy danych SQL serwera Project Server (nazwa serwera, port, nazwa bazy, nazwa użytkownika, hasło) w celu połączenia z Project Server.  
4. Sterownik Microsoft JDBC dla SQL Server (np. `sqljdbc4.jar`).  

## Importowanie pakietów
Najpierw zaimportuj potrzebne klasy. Lista obejmuje podstawowe klasy Aspose.Tasks oraz standardowe utilsy Javy.

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## Jak połączyć się z Project Server
Ustanowienie niezawodnego połączenia jest fundamentem odczytu danych projektu. Upewnij się, że instancja SQL Server jest dostępna z hosta Java i że używany login ma uprawnienia **SELECT** do schematu Project Server. Warto również sprawdzić opóźnienia sieciowe i skonfigurować wymagane ustawienia SSL, aby zapewnić bezpieczną komunikację.

## Krok 1: skonfiguruj połączenie z bazą danych
Klasa `MspDbSettings` enkapsuluje szczegóły połączenia JDBC potrzebne do uzyskania dostępu do bazy danych Microsoft Project Server. Utwórz instancję `MspDbSettings`, która przechowuje łańcuch połączenia JDBC. Zastąp wartości zastępcze rzeczywistymi danymi serwera.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Przechowuj łańcuch połączenia w bezpiecznym pliku konfiguracyjnym lub zmiennej środowiskowej zamiast wpisywać poświadczenia na stałe w kodzie.

## Krok 2: dodaj sterownik JDBC
Załaduj sterownik Microsoft SQL Server JDBC w czasie wykonywania, aby JVM mógł komunikować się z bazą danych.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** Upewnij się, że wersja sterownika odpowiada wersji Twojego SQL Servera. Użycie niekompatybilnego sterownika może spowodować błędy połączenia.

## Krok 3: odczytaj dane projektu
Klasa `Project` reprezentuje plik Microsoft Project załadowany do pamięci, udostępniając zadania, zasoby i przydziały. Utwórz obiekt `Project`, przekazując `MspDbSettings`. Aspose.Tasks automatycznie pobierze dane projektu z bazy.

```java
Project project = new Project(settings);
```

W tym miejscu możesz eksplorować obiekt `project` — wyświetlać listy zadań, zasobów lub modyfikować pola według potrzeb.

## Krok 4: zapisz projekt jako PDF
Wyliczenie `SaveFileFormat` definiuje format wyjściowy dla metody `Project.save`, np. PDF, XML lub HTML. Wyeksportuj załadowany projekt do wybranego formatu. Poniższy przykład zapisuje projekt jako **PDF**, co jest idealne dla raportów do druku. Możesz także **wyeksportować projekt do XML** lub **przekonwertować projekt na HTML**, zmieniając wartość wyliczenia `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Jeśli wolisz XML, po prostu zamień `SaveFileFormat.Pdf` na `SaveFileFormat.Xml`. Dla wyjścia HTML użyj `SaveFileFormat.Html`.

## Typowe problemy i rozwiązania
| Problem | Typowa przyczyna | Rozwiązanie |
|---------|------------------|-------------|
| **Przekroczenie limitu czasu połączenia** | Nieprawidłowy serwer/port lub blokada zapory | Sprawdź adres serwera, otwórz port 1435 (standardowo 1433) i przetestuj połączenie prostym programem testowym JDBC. |
| **Błąd uwierzytelniania** | Nieprawidłowa nazwa użytkownika/hasło lub SQL Server nie jest skonfigurowany do uwierzytelniania SQL | Użyj prawidłowego logowania SQL lub włącz uwierzytelnianie mieszane na serwerze. |
| **Sterownik nie znaleziony** | Plik JAR sterownika nie znajduje się w classpath | Upewnij się, że `addJDBCDriver` wskazuje na właściwy plik `.jar` i że ścieżka używa podwójnych backslashów (`\\`). |
| **Pusty projekt po załadowaniu** | Niewystarczające uprawnienia do odczytu tabel Project Server | Przyznaj loginowi uprawnienia SELECT na schemacie bazy danych Project Server. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks może być używany do odczytu danych projektu z innych baz danych niż Microsoft Project?**  
A: Tak, Aspose.Tasks obsługuje odczyt danych projektu z plików XML, baz danych Primavera oraz innych standardowych formatów projektowych.

**Q: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami Microsoft Project?**  
A: Tak, biblioteka działa z Microsoft Project 2007 aż po najnowsze wydania 2024, zapewniając płynną integrację we wszystkich wersjach.

**Q: Czy mogę modyfikować dane projektu przed ich zapisaniem?**  
A: Oczywiście, możesz dodawać, aktualizować lub usuwać zadania, zasoby i pola niestandardowe przy użyciu bogatego API przed eksportem.

**Q: Czy Aspose.Tasks obsługuje wiele formatów wyjściowych?**  
A: Tak, możesz zapisywać projekty jako PDF, XML, HTML, CSV, PNG, JPEG i inne — ponad 20 formatów łącznie.

**Q: Gdzie mogę znaleźć dodatkowe wsparcie lub pomoc w sprawie Aspose.Tasks?**  
A: Po dodatkową pomoc odwiedź forum Aspose.Tasks lub zapoznaj się z dokumentacją dostępną na stronie [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Podsumowanie
Korzystając z tego przewodnika krok po kroku, teraz wiesz, jak **odczytać bazę danych Microsoft Project**, **zapisać projekt jako PDF** oraz eksportować go do innych formatów przy użyciu Aspose.Tasks dla Javy. To podejście eliminuje zależność od Microsoft Project, upraszcza automatyczne raportowanie i otwiera drzwi do potężnych, własnych integracji.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Author:** Aspose

## Powiązane samouczki

- [Jak zapisać projekt jako PDF przy użyciu Aspose.Tasks – przewodnik eksportu](/tasks/java/project-file-operations/save-as-pdf/)
- [Zapisz projekt jako PDF – renderowanie arkusza zadań przy użyciu Aspose.Tasks dla Javy](/tasks/java/task-properties/render-task-sheet/)
- [Eksportuj projekt do PDF i zmniejsz odstęp między listą zadań a stopką w Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}