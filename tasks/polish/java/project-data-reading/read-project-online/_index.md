---
date: 2025-12-15
description: Dowiedz się, jak odczytywać dane MS Project Online przy użyciu Aspose.Tasks
  w Javie. Ten przewodnik pokazuje, jak pobrać listę projektów, wyświetlić projekty
  SharePoint oraz uzyskać liczbę zasobów.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Aspose.Tasks Java - Bezproblemowe odczytywanie danych z MS Project Online'
url: /pl/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: Bezproblemowe odczytywanie danych z MS Project Online

## Wprowadzenie
W dziedzinie zarządzania projektami efektywne obsługiwanie danych Microsoft Project Online jest kluczowe dla usprawnienia operacji. **aspose tasks java** udostępnia solidne, łatwe w użyciu API, które pozwala odczytywać dane Project Online bez konieczności ręcznego wykonywania niskopoziomowych wywołań HTTP. W tym samouczku pokażemy, jak pobrać listę projektów, wyświetlić projekty SharePoint oraz uzyskać liczbę zasobów w każdym projekcie — wszystko przy użyciu kilku linii kodu Java.

## Szybkie odpowiedzi
- **Co robi aspose tasks java?** Odczytuje i manipuluje plikami Microsoft Project oraz danymi Project Online programistycznie.  
- **Czy potrzebna jest licencja, aby go wypróbować?** Dostępna jest bezpłatna wersja próbna; licencja jest wymagana w środowisku produkcyjnym.  
- **Jakie poświadczenia są wymagane?** Domenę SharePoint, nazwę użytkownika i hasło (lub token Azure AD).  
- **Czy mogę wyświetlić listę projektów SharePoint?** Tak – użyj `ProjectServerManager.getProjectList()`, aby je pobrać.  
- **Jak uzyskać liczbę zasobów?** Załaduj każdy obiekt `Project` i wywołaj `project.getResources().size()`.

## Co to jest aspose tasks java?
**aspose tasks java** to biblioteka skierowana do deweloperów, która abstrahuje złożoność formatów plików Microsoft Project oraz REST API Project Server. Umożliwia odczyt, tworzenie i modyfikację danych projektowych bezpośrednio z aplikacji Java, co upraszcza integrację z istniejącymi systemami korporacyjnymi.

## Dlaczego warto używać aspose tasks java do odczytu MS Project Online?
- **Brak ręcznej obsługi HTTP** – biblioteka zajmuje się uwierzytelnianiem i wywołaniami REST.  
- **Silna typizacja** – pracuj z `Project`, `ProjectInfo` i innymi POJO zamiast surowego JSON.  
- **Wieloplatformowość** – działa w każdym środowisku zgodnym z JVM.  
- **Bogaty zestaw funkcji** – oprócz odczytu możesz także aktualizować zadania, zasoby i harmonogramy.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

1. **Java Development Kit (JDK)** – zainstalowany JDK 8 lub nowszy.  
2. **Aspose.Tasks for Java library** – pobierz ją z [here](https://releases.aspose.com/tasks/java/).  
3. **Konto Microsoft Project Online** – z uprawnieniami do odczytu projektów.  
4. **Adres domeny SharePoint** – gdzie znajduje się Twoja instancja Project Online.  
5. **Nazwę użytkownika i hasło** – lub odpowiednie poświadczenia Azure AD do uwierzytelniania.

## Importowanie pakietów
Najpierw zaimportuj niezbędne klasy Aspose.Tasks, które będą używane w całym samouczku:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Krok 1: Ustaw domenę SharePoint, nazwę użytkownika i hasło
Zdefiniuj szczegóły połączenia dla swojego środowiska Project Online. Zastąp wartości zastępcze własnymi poświadczeniami.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## Krok 2: Uwierzytelnij się przy użyciu poświadczeń serwera projektów
Utwórz obiekt `ProjectServerCredentials` i zainicjalizuj `ProjectServerManager`. Ten menedżer będzie obsługiwał wszystkie kolejne wywołania do Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Krok 3: Pobierz listę projektów i wyświetl informacje
Użyj menedżera, aby **pobrać listę projektów** (lista projektów SharePoint) i wydrukować podstawowe szczegóły, takie jak nazwa, data utworzenia i data ostatniego zapisu.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Krok 4: Załaduj poszczególne projekty i wyświetl liczbę zasobów
Dla każdego projektu zwróconego w poprzednim kroku, załaduj pełny obiekt `Project` i wyświetl **liczbę zasobów**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| **Authentication failed** | Nieprawidłowa domena, nazwa użytkownika lub hasło. | Zweryfikuj poświadczenia i upewnij się, że konto ma uprawnienia do odczytu w Project Online. |
| **SSLHandshakeException** | Środowisko Java nie obsługuje wymaganego wersji TLS. | Zaktualizuj JDK do najnowszej wersji lub włącz TLS 1.2+. |
| **`reader.getProjectList()` returns empty** | Konto nie ma dostępu do żadnych projektów. | Sprawdź uprawnienia w Project Online lub użyj konta administratora. |
| **Large projects cause OutOfMemoryError** | Ładowanie wielu projektów jednocześnie zużywa pamięć. | Ładuj projekty pojedynczo i zwalniaj referencje po użyciu. |

## Najczęściej zadawane pytania
### Q: Czy mogę używać aspose tasks java do modyfikacji danych MS Project Online?
A: Tak, Aspose.Tasks zapewnia rozbudowane możliwości zarówno odczytu **jak i** modyfikacji danych Project Online programistycznie.

### Q: Czy Aspose.Tasks obsługuje inne formaty plików zarządzania projektami?
A: Oczywiście. Obsługuje MPP, XML, Primavera i wiele innych, zapewniając kompatybilność w różnych ekosystemach projektowych.

### Q: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks for Java?
A: Tak, możesz skorzystać z darmowej wersji próbnej dostępnej [here](https://releases.aspose.com/), aby przetestować funkcje i możliwości Aspose.Tasks.

### Q: Gdzie znajdę pełną dokumentację Aspose.Tasks for Java?
A: Szczegółową dokumentację znajdziesz [here](https://reference.aspose.com/tasks/java/), zawierającą kompleksowe wskazówki dotyczące wykorzystania Aspose.Tasks w projektach Java.

### Q: Jakie opcje wsparcia są dostępne dla Aspose.Tasks for Java?
A: Jeśli napotkasz problemy lub masz pytania, możesz uzyskać pomoc na forum społeczności Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Ostatnia aktualizacja:** 2025-12-15  
**Testowano z:** Aspose.Tasks for Java 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}