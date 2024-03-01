---
title: Odczyt danych projektu z bazy danych MS Project w Aspose.Tasks
linktitle: Odczyt danych projektu z bazy danych Microsoft Project w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak czytać dane projektu z bazy danych Microsoft Project Database przy użyciu Aspose.Tasks dla Java. Przewodnik krok po kroku z przykładami kodu.
type: docs
weight: 12
url: /pl/java/project-data-reading/read-project-database/
---
## Wstęp
W tym samouczku dowiemy się, jak odczytać dane projektu z bazy danych Microsoft Project przy użyciu Aspose.Tasks dla języka Java. Aspose.Tasks to potężny interfejs API języka Java, który umożliwia programistom manipulowanie dokumentami programu Microsoft Project bez konieczności instalowania programu Microsoft Project. Wykonując kroki opisane w tym przewodniku, dowiesz się, jak efektywnie wyodrębnić dane projektu z bazy danych i zapisać je w żądanym formacie.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Podstawowa znajomość programowania w języku Java.
2. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
3. Biblioteka Aspose.Tasks dla Java pobrana i skonfigurowana w Twoim projekcie.

## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety:
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
## Krok 1: Skonfiguruj połączenie z bazą danych
W pierwszej kolejności należy skonfigurować połączenie z bazą danych Microsoft Project. Obejmuje to określenie adresu URL bazy danych, nazwy serwera, numeru portu, nazwy bazy danych, nazwy użytkownika i hasła.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## Krok 2: Dodaj sterownik JDBC
Następnie musisz dodać sterownik JDBC do swojego projektu. Driver ten ułatwia komunikację pomiędzy aplikacjami Java a bazą danych Microsoft SQL Server.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## Krok 3: Przeczytaj dane projektu
 Teraz utwórz`Project` obiektu i wczytaj dane projektu z bazy danych, korzystając z wcześniej zdefiniowanych ustawień.
```java
Project project = new Project(settings);
```
## Krok 4: Zapisz dane projektu
Na koniec zapisz dane projektu w żądanym formacie. W tym przykładzie zapisujemy go jako plik XML.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Gratulacje! Pomyślnie odczytałeś dane projektu z bazy danych Microsoft Project przy użyciu Aspose.Tasks for Java.

## Wniosek
tym samouczku omówiliśmy proces odczytywania danych projektu z bazy danych Microsoft Project przy użyciu Aspose.Tasks dla Java. Wykonując opisane kroki, możesz bezproblemowo wyodrębnić informacje o projekcie i manipulować nimi zgodnie ze swoimi wymaganiami. Aspose.Tasks upraszcza obsługę dokumentów Microsoft Project, umożliwiając wydajną ekstrakcję i manipulację danymi.
## Często zadawane pytania
### P: Czy Aspose.Tasks może służyć do odczytywania danych projektu z innych baz danych niż Microsoft Project?
O: Tak, Aspose.Tasks obsługuje odczytywanie danych projektu z różnych źródeł, w tym z plików XML, baz danych Primavera i Microsoft Project.
### P: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami Microsoft Project?
O: Tak, Aspose.Tasks został zaprojektowany do współpracy z różnymi wersjami Microsoft Project, zapewniając kompatybilność i bezproblemową integrację.
### P: Czy mogę manipulować danymi projektu przed ich zapisaniem?
O: Oczywiście, Aspose.Tasks zapewnia szeroką gamę funkcji do manipulowania danymi projektu, takich jak dodawanie zadań, aktualizowanie zasobów i ustawianie właściwości projektu.
### P: Czy Aspose.Tasks obsługuje wiele formatów wyjściowych?
Odp.: Tak, Aspose.Tasks obsługuje różne formaty wyjściowe, w tym XML, PDF, HTML i formaty obrazów, takie jak PNG i JPEG.
### P: Gdzie mogę znaleźć dalsze wsparcie lub pomoc dotyczącą Aspose.Tasks?
 Odp.: Aby uzyskać dodatkowe wsparcie lub pomoc, możesz odwiedzić forum Aspose.Tasks lub zapoznać się z dokumentacją dostępną na stronie internetowej[Tutaj](https://forum.aspose.com/c/tasks/15).