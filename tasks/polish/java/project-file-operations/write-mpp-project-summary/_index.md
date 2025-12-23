---
date: 2025-12-23
description: Dowiedz się, jak tworzyć podsumowanie MPP i aktualizować autora projektu
  przy użyciu Aspose.Tasks for Java. Ustawiaj i pobieraj informacje o projekcie bez
  wysiłku.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak utworzyć podsumowanie MPP i zaktualizować autora projektu przy użyciu Aspose.Tasks
url: /pl/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz podsumowanie projektu MPP w Aspose.Tasks

## Wprowadzenie
W tym samouczku **utworzysz podsumowanie MPP** dla pliku Microsoft Project i dowiesz się, jak **zaktualizować informacje o autorze projektu** przy użyciu biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy tworzysz narzędzie do zarządzania projektami, czy automatyzujesz raportowanie, programowe kontrolowanie właściwości podsumowania oszczędza czas i zapewnia spójność w całych projektach.

## Szybkie odpowiedzi
- **Co oznacza „create MPP summary”?** Oznacza to ustawienie wysokopoziomowych właściwości projektu (autor, wersja, słowa kluczowe itp.), które pojawiają się w oknie dialogowym Informacje o podsumowaniu projektu w Microsoft Project.  
- **Która biblioteka obsługuje to?** Aspose.Tasks for Java udostępnia płynne API do odczytu i zapisu tych właściwości.  
- **Czy potrzebna jest licencja?** Dostępna jest darmowa wersja próbna, ale do użytku produkcyjnego wymagana jest licencja komercyjna.  
- **Czy mogę również zmienić autora po zapisaniu pliku?** Tak – możesz **zaktualizować autora projektu** wywołując `project.set(Prj.AUTHOR, "New Author")` i ponownie zapisując plik.  
- **Jakie formaty plików są obsługiwane?** Pełne wsparcie mają zarówno MPP, jak i XML (SaveFileFormat.Xml).

## Co to jest create MPP summary?
Tworzenie podsumowania MPP polega na wypełnieniu metadanych projektu — autor, numer wersji, słowa kluczowe, komentarze, data utworzenia i data wydruku. Metadane te są przechowywane w rekordzie Project Summary Information i wyświetlane w sekcji **Plik → Informacje** programu Microsoft Project.

## Dlaczego aktualizować autora projektu?
Utrzymanie dokładnych informacji o **autorze projektu** jest niezbędne dla ścieżek audytu, współpracy i raportowania. Gdy wielu członków zespołu przyczynia się do projektu, może być konieczne **zaktualizowanie autora projektu**, aby odzwierciedlić najnowsze zmiany lub prawidłowo przypisać wykonane prace.

## Wymagania wstępne
1. Zainstalowany Java Development Kit (JDK) na komputerze.  
2. Aspose.Tasks for Java – pobierz go z [tutaj](https://releases.aspose.com/tasks/java/).  
3. IDE, takie jak IntelliJ IDEA, Eclipse lub NetBeans.

## Importowanie pakietów
Najpierw zaimportuj niezbędne pakiety do swojej klasy Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Krok 1: Konfiguracja projektu i definiowanie informacji podsumowujących
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
W powyższym kodzie **tworzymy pola podsumowania MPP**, takie jak autor, wersja i słowa kluczowe. Możesz także później **zaktualizować autora projektu**, wywołując `project.set(Prj.AUTHOR, "New Name")`.

## Krok 2: Zapis informacji podsumowujących projektu
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Zapisanie projektu utrwala wszystkie dane podsumowujące, które właśnie zdefiniowano.

## Krok 3: Odczyt informacji podsumowujących projektu
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Ten fragment kodu pokazuje, jak **odczytać** informacje podsumowujące, potwierdzając, że operacja **create MPP summary** zakończyła się sukcesem.

## Typowe problemy i rozwiązania
- **Wartości null po odczycie:** Upewnij się, że projekt został pomyślnie zapisany przed ponownym wczytaniem. Sprawdź ścieżki plików i uprawnienia.  
- **Różnice w formacie daty:** `project.get(Prj.CREATION_DATE)` zwraca `java.util.Date`. Użyj `SimpleDateFormat`, jeśli potrzebny jest niestandardowy format wyświetlania.  
- **Licencja nie ustawiona:** Bez ważnej licencji Aspose.Tasks działa w trybie ewaluacyjnym i może dodawać znak wodny. Zarejestruj licencję wcześnie w kodzie.

## Najczęściej zadawane pytania
**Q: Czy mogę używać Aspose.Tasks for Java z innymi bibliotekami Java?**  
A: Tak, Aspose.Tasks for Java może być płynnie integrowany z innymi bibliotekami Java, aby zwiększyć możliwości zarządzania projektami.

**Q: Czy dostępna jest wersja próbna Aspose.Tasks for Java?**  
A: Tak, możesz pobrać darmową wersję próbną z [tutaj](https://releases.aspose.com/).

**Q: Jak często aktualizowany jest Aspose.Tasks for Java?**  
A: Aspose.Tasks for Java jest regularnie aktualizowany, aby zapewnić kompatybilność z najnowszymi wersjami Javy i plików Microsoft Project.

**Q: Czy mogę dalej dostosować informacje podsumowujące projekt?**  
A: Oczywiście, Aspose.Tasks for Java oferuje rozbudowane opcje dostosowywania informacji podsumowujących projekt do Twoich konkretnych wymagań.

**Q: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks for Java?**  
A: Wsparcie można uzyskać na forum społeczności Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

## Podsumowanie
W tym samouczku pokazaliśmy, jak **utworzyć podsumowanie MPP**, **zaktualizować autora projektu** i zweryfikować te zmiany przy użyciu Aspose.Tasks for Java. Automatyzując te kroki, zyskujesz pełną kontrolę nad metadanymi projektu, co sprawia, że Twoje aplikacje są bardziej solidne, a raporty projektowe bardziej dokładne.

---

**Ostatnia aktualizacja:** 2025-12-23  
**Testowano z:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}