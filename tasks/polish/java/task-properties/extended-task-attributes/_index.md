---
date: 2026-01-28
description: Dowiedz się, jak odczytywać rozszerzone atrybuty zadań przy użyciu Aspose.Tasks
  dla Javy i efektywnie zmieniać typ pola niestandardowego.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Odczyt rozszerzonych atrybutów zadania przy użyciu Aspose.Tasks dla Javy
url: /pl/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczyt rozszerzonych atrybutów zadań przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
W tym obszernej tutorialu odkryjesz, jak **odczytywać rozszerzone atrybuty zadań** z plików Microsoft Project przy użyciu biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy tworzysz narzędzie raportujące, synchronizujesz dane, czy po prostu potrzebujesz głębszego wglądu w pola niestandardowe, opanowanie tej funkcji umożliwi Ci wyodrębnienie każdej informacji zapisanej w projekcie. Przeprowadzimy Cię przez niezbędną konfigurację, pokażemy, jak przełączać typ pola niestandardowego podczas przetwarzania atrybutów, oraz damy praktyczne wskazówki, jak unikać typowych pułapek.

## Szybkie odpowiedzi
- **Co oznacza „odczyt rozszerzonych atrybutów zadań”?** Odnosi się do wyodrębniania wartości pól niestandardowych, które wykraczają poza domyślne właściwości zadania w pliku Project.  
- **Która klasa zapewnia dostęp do tych atrybutów?** Klasa `ExtendedAttribute` w Aspose.Tasks.  
- **Czy potrzebna jest licencja do uruchomienia kodu?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę zmienić typ atrybutu w czasie działania?** Tak – użyj instrukcji `switch`, aby **przełączać typ pola niestandardowego** na podstawie `CustomFieldType`.  
- **Czy jest to kompatybilne z Java 8 i nowszymi?** Absolutnie, API obsługuje JDK 8+.

## Czym jest odczyt rozszerzonych atrybutów zadań?
Rozszerzone atrybuty zadań to pola definiowane przez użytkownika (tekst, data, liczba, znacznik itp.), które uzupełniają standardowe właściwości zadań w Microsoft Project. Aspose.Tasks udostępnia je poprzez kolekcję `ExtendedAttribute` dołączoną do każdego obiektu `Task`, umożliwiając programowe odczytywanie lub modyfikowanie ich wartości.

## Dlaczego odczytywać rozszerzone atrybuty zadań?
- **Pełna widoczność:** Uzyskaj wgląd w dane niestandardowe, które interesariusze dodali do harmonogramu.  
- **Automatyzacja:** Wypełniaj pulpity nawigacyjne, generuj niestandardowe raporty lub migruj dane do innych systemów bez ręcznego eksportu.  
- **Elastyczność:** Pracuj z dowolnym typem pola niestandardowego — tekst, data, czas trwania, koszt, znacznik — obsługując każdy przypadek odpowiednio.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz:
- Podstawową znajomość programowania w Javie.  
- Zainstalowany Java Development Kit (JDK) na swoim komputerze.  
- Środowisko IDE, takie jak IntelliJ IDEA lub Eclipse.  

## Importowanie pakietów
Zacznij od zaimportowania niezbędnych klas dla projektu Aspose.Tasks:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Krok 1: Dostęp do zadania i rozszerzonych atrybutów
Wczytaj plik Project i iteruj po każdym zadaniu, aby uzyskać dostęp do jego rozszerzonych atrybutów:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## Krok 2: Pobieranie identyfikatora pola i GUID wartości
Wypisz wewnętrzne identyfikatory, które pomogą Ci zrozumieć, z którym polem niestandardowym masz do czynienia:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## Krok 3: Jak przełączać typ pola niestandardowego przy odczycie rozszerzonych atrybutów zadań
Użyj instrukcji `switch` na `CustomFieldType`, aby poprawnie obsłużyć każdy możliwy typ danych:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

Powtórz te kroki dla każdego zadania w swoim projekcie, aby odkrywać i manipulować każdym rozszerzonym atrybutem zadania.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Zwrócone wartości null** | Sprawdź, czy pole niestandardowe jest rzeczywiście wypełnione w źródłowym pliku .mpp. |
| **Wyświetlany nieprawidłowy typ** | Upewnij się, że używasz prawidłowego `CustomFieldType` w instrukcji `switch`; niezgodne typy spowodują wartości domyślne. |
| **Spowolnienie wydajności przy dużych projektach** | Przetwarzaj zadania w partiach lub filtruj tylko potrzebne zadania, używając `project.getRootTask().getChildren().stream()` z odpowiednimi predykatami. |

## Najczęściej zadawane pytania
### Czy mogę modyfikować rozszerzone atrybuty zadań programowo?
Tak, możesz modyfikować rozszerzone atrybuty zadań przy użyciu Aspose.Tasks dla Javy. Zapoznaj się z dokumentacją, aby uzyskać szczegółowe instrukcje.

### Czy dostępna jest wersja próbna?
Tak, możesz uzyskać dostęp do darmowej wersji próbnej [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć wsparcie dla Aspose.Tasks dla Javy?
W celu uzyskania wsparcia odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Jak mogę uzyskać tymczasową licencję?
Możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę kupić pełną wersję Aspose.Tasks dla Javy?
Możesz zakupić pełną wersję [tutaj](https://purchase.aspose.com/buy).

---

**Ostatnia aktualizacja:** 2026-01-28  
**Testowano z:** Aspose.Tasks Java API (latest stable release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}