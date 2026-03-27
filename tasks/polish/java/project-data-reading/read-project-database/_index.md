---
date: 2026-02-18
description: Dowiedz się, jak zapisać projekt jako PDF i odczytać bazę danych Microsoft
  Project przy użyciu Aspose.Tasks for Java, a także połączyć się z Project Server,
  przekonwertować projekt na HTML i wyeksportować projekt do XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Zapisz projekt jako PDF i odczytaj bazę danych projektu przy użyciu Aspose.Tasks
  dla Javy
url: /pl/java/project-data-reading/read-project-database/
weight: 12
---

 **bold**.

Proceed similarly for other sections.

Tables: keep content but translate Issue, Typical Cause, Fix headings and entries.

Need to translate FAQ questions and answers.

Also translate "Last Updated", "Tested With", "Author".

Make sure not to translate URLs.

Also code block placeholders remain.

Let's craft translation.

Be careful with bullet lists.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz projekt jako PDF i odczytaj bazę danych Microsoft Project przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
W tym samouczku dowiesz się, jak **odczytać bazę danych Microsoft Project** bezpośrednio z serwera Microsoft Project Server, a następnie **zapisać projekt jako PDF** przy użyciu API Aspose.Tasks dla Javy. Niezależnie od tego, czy musisz generować raporty, migrować dane, czy integrować informacje o projekcie w własnych aplikacjach, ten przewodnik poprowadzi Cię przez każdy krok — od skonfigurowania połączenia z bazą danych po eksport projektu do PDF, XML lub HTML. Po zakończeniu będziesz posiadać solidne, gotowe do produkcji rozwiązanie, które działa bez instalacji Microsoft Project na maszynie hosta.

## Szybkie odpowiedzi
- **Co robi Aspose.Tasks?** Udostępnia czysto‑Java API do odczytu, zapisu i manipulacji plikami oraz bazami danych Microsoft Project.  
- **Czy potrzebny jest zainstalowany Microsoft Project?** Nie, Aspose.Tasks działa niezależnie od Microsoft Project.  
- **Jakiego typu bazy danych są obsługiwane?** Microsoft SQL Server (backend Project Server).  
- **Czy mogę eksportować do innych formatów?** Tak, oprócz PDF możesz zapisywać do XML, HTML, CSV i innych.  
- **Jakie są główne wymagania wstępne?** JDK, biblioteka Aspose.Tasks dla Javy, sterownik JDBC dla SQL Server oraz dane uwierzytelniające **do połączenia z Project Server**.

## Co oznacza „odczytać bazę danych Microsoft Project”?
Odczytanie bazy danych Microsoft Project oznacza połączenie się z repozytorium SQL Server serwera Project, wyodrębnienie przechowywanych danych projektowych i załadowanie ich do obiektu `Project`, którym Aspose.Tasks może zarządzać. Takie podejście jest idealne do automatycznego raportowania, migracji danych lub własnych analiz.

## Dlaczego warto używać Aspose.Tasks dla Javy?
- **Brak zależności od Microsoft Project** – działa na dowolnym serwerze lub w środowisku CI.  
- **Bogaty model obiektowy** – programistyczny dostęp do zadań, zasobów, przydziałów, kalendarzy i pól niestandardowych.  
- **Wiele opcji eksportu** – PDF, XML, HTML, PNG itp., przy użyciu jednego wywołania API.  
- **Wysoka wydajność** – zoptymalizowane pod kątem dużych projektów korporacyjnych.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. Działające środowisko programistyczne Java (JDK 8 lub nowszy).  
2. Bibliotekę Aspose.Tasks dla Javy dodaną do ścieżki klas projektu.  
3. Dane uwierzytelniające dostęp do bazy danych SQL serwera Project Server (nazwa serwera, port, nazwa bazy, nazwa użytkownika, hasło) **do połączenia z Project Server**.  
4. Sterownik Microsoft JDBC dla SQL Server (np. `sqljdbc4.jar`).  

## Importowanie pakietów
Najpierw zaimportuj klasy, które będą potrzebne. Lista obejmuje podstawowe klasy Aspose.Tasks oraz standardowe utilitety Javy.

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
Ustanowienie niezawodnego połączenia jest podstawą odczytu danych projektowych. Upewnij się, że instancja SQL Server jest dostępna z hosta Javy i że używany login ma uprawnienia **SELECT** do schematu Project Server.

## Krok 1: Konfiguracja połączenia z bazą danych
Utwórz instancję `MspDbSettings`, która przechowuje łańcuch połączenia JDBC. Zastąp wartości zastępcze rzeczywistymi danymi serwera.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Wskazówka:** Przechowuj łańcuch połączenia w bezpiecznym pliku konfiguracyjnym lub zmiennej środowiskowej, zamiast wpisywać poświadczenia na stałe w kodzie.

## Krok 2: Dodanie sterownika JDBC
Załaduj sterownik Microsoft SQL Server JDBC w czasie wykonywania, aby JVM mógł komunikować się z bazą danych.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Ostrzeżenie:** Upewnij się, że wersja sterownika odpowiada wersji Twojego SQL Servera. Użycie niekompatybilnego sterownika może spowodować niepowodzenie połączenia.

## Krok 3: Odczyt danych projektu
Zainicjuj obiekt `Project`, przekazując `MspDbSettings`. Aspose.Tasks automatycznie pobierze dane projektu z bazy.

```java
Project project = new Project(settings);
```

W tym miejscu możesz eksplorować obiekt `project` — wyświetlać listę zadań, zasobów lub modyfikować pola według potrzeb.

## Krok 4: Zapis projektu jako PDF
Wyeksportuj załadowany projekt do wybranego formatu pliku. Poniższy przykład zapisuje projekt jako **PDF**, co jest idealne dla raportów do druku. Możesz także **wyeksportować projekt do XML** lub **przekonwertować projekt na HTML**, zmieniając wartość wyliczenia `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Jeśli wolisz XML, po prostu zamień `SaveFileFormat.Pdf` na `SaveFileFormat.Xml`. Dla wyjścia HTML użyj `SaveFileFormat.Html`.

## Typowe problemy i rozwiązania
| Problem | Typowa przyczyna | Rozwiązanie |
|---------|------------------|-------------|
| **Przekroczenie limitu czasu połączenia** | Nieprawidłowy serwer/port lub zapora blokuje połączenie | Sprawdź adres serwera, otwórz port 1433 i przetestuj łączność prostym programem JDBC. |
| **Błąd uwierzytelniania** | Nieprawidłowa nazwa użytkownika/hasło lub SQL Server nie jest skonfigurowany do uwierzytelniania SQL | Użyj prawidłowego loginu SQL lub włącz tryb mieszany (mixed‑mode) na serwerze. |
| **Sterownik nie został znaleziony** | Plik JAR sterownika nie znajduje się w classpath | Upewnij się, że `addJDBCDriver` wskazuje na właściwy plik `.jar` i że ścieżka używa podwójnych backslashów (`\\`). |
| **Pusty projekt po załadowaniu** | Brak wystarczających uprawnień do odczytu tabel Project Server | Przyznaj loginowi prawa SELECT do schematu bazy danych Project Server. |

## Najczęściej zadawane pytania

**P: Czy Aspose.Tasks może odczytywać dane projektowe z innych baz danych niż Microsoft Project?**  
O: Tak, Aspose.Tasks obsługuje odczyt danych projektowych z różnych źródeł, w tym plików XML, Primavera oraz baz danych Microsoft Project.

**P: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami Microsoft Project?**  
O: Tak, Aspose.Tasks został zaprojektowany tak, aby działać z wieloma wersjami Microsoft Project, zapewniając płynną integrację.

**P: Czy mogę modyfikować dane projektu przed jego zapisaniem?**  
O: Oczywiście, Aspose.Tasks udostępnia rozbudowane API do dodawania zadań, aktualizacji zasobów i ustawiania właściwości projektu przed eksportem.

**P: Czy Aspose.Tasks obsługuje wiele formatów wyjściowych?**  
O: Tak, możesz zapisywać projekty jako PDF, XML, HTML, CSV, PNG, JPEG i inne.

**P: Gdzie mogę znaleźć dodatkowe wsparcie lub pomoc dotyczącą Aspose.Tasks?**  
O: Po dodatkową pomoc odwiedź forum Aspose.Tasks lub zapoznaj się z dokumentacją dostępną na stronie [here](https://forum.aspose.com/c/tasks/15).

## Zakończenie
Korzystając z tego przewodnika krok po kroku, teraz wiesz, jak **odczytać bazę danych Microsoft Project**, **zapisać projekt jako PDF** oraz eksportować go do innych formatów przy użyciu Aspose.Tasks dla Javy. To podejście eliminuje zależność od Microsoft Project, usprawnia automatyczne raportowanie i otwiera drzwi do potężnych, własnych integracji.

---

**Ostatnia aktualizacja:** 2026-02-18  
**Testowano z:** Aspose.Tasks dla Javy 24.5 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}