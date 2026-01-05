---
date: 2026-01-05
description: Dowiedz się, jak ustawić datę rozpoczęcia projektu i zapisać plik XML
  MS Project przy użyciu Aspose.Tasks for Java. Przewodnik krok po kroku dla programistów
  Java.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ustaw datę rozpoczęcia projektu przy użyciu Aspose.Tasks dla Javy
url: /pl/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw datę rozpoczęcia projektu przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
W tym samouczku nauczysz się **jak ustawić datę rozpoczęcia projektu** w pliku Microsoft Project, a następnie **zapisz plik MS Project XML** przy użyciu biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy automatyzujesz potok raportowania, czy tworzysz własne narzędzie do zarządzania projektami, opanowanie tej czynności zaoszczędzi Twój czas i wyeliminuje błędy ręczne.

## Szybkie odpowiedzi
- **Jaka jest podstawowa metoda ustawiania daty rozpoczęcia?** Użyj `project.set(Prj.START_DATE, …)`.
- **W jakim formacie powinienem wyeksportować plik?** Zapisz go jako XML przy użyciu `SaveFileFormat.Xml`.
- **Czy potrzebna jest licencja do tej operacji?** Wersja próbna działa, ale pełna licencja usuwa znaki wodne.
- **Czy mogę zmienić datę rozpoczęcia po utworzeniu zadań?** Tak, zaktualizuj właściwość projektu przed dodaniem zadań.
- **Czy jest to kompatybilne ze wszystkimi wersjami MS Project?** Aspose.Tasks obsługuje XML, MPP i inne formaty.

## Co to jest „Ustaw datę rozpoczęcia projektu”?
Ustawienie daty rozpoczęcia projektu definiuje bazowy kalendarz, od którego rozpoczynają się wszystkie obliczenia harmonogramu zadań. Jest to pierwszy krok w programistycznym budowaniu wiarygodnego harmonogramu projektu.

## Dlaczego warto używać Aspose.Tasks dla Javy?
Aspose.Tasks dostarcza czyste API w Javie, które działa na każdej platformie bez konieczności instalacji Microsoft Project. Umożliwia szybkie tworzenie, modyfikowanie i eksportowanie danych projektu, co czyni je idealnym rozwiązaniem do automatyzacji po stronie serwera.

## Wymagania wstępne
1. **Java Development Kit (JDK)** – dowolna aktualna wersja JDK.  
2. **Aspose.Tasks for Java** – pobierz z [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse lub ulubione środowisko programistyczne Javy.

## Importowanie pakietów
Najpierw zaimportuj niezbędne klasy:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Krok 1: Ustaw katalog danych
Zdefiniuj, gdzie będą przechowywane wygenerowane pliki.

```java
String dataDir = "Your Data Directory";
```

### Krok 2: Utwórz instancję projektu
Zainicjuj nowy, pusty projekt.

```java
Project project = new Project();
```

### Krok 3: Ustaw właściwości informacji o projekcie
Tutaj **ustawiamy datę rozpoczęcia projektu** oraz powiązane właściwości harmonogramu.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Krok 4: Zapisz MS Project XML
Wyeksportuj skonfigurowany projekt do pliku XML.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Typowe problemy i rozwiązania
- **Nieprawidłowy format daty:** Upewnij się, że używasz `java.util.Calendar` i wywołujesz `getTime()` przed przypisaniem.  
- **Plik nie został zapisany:** Sprawdź, czy `dataDir` wskazuje na istniejący, zapisywalny folder.  
- **Ostrzeżenia licencyjne:** Wersja próbna dodaje znaki wodne; zastosuj ważną licencję, aby je usunąć.

## Najczęściej zadawane pytania

### P: Czy mogę używać Aspose.Tasks dla Javy do odczytu plików MS Project?  
**O:** Tak, Aspose.Tasks dla Javy oferuje rozbudowane funkcje zarówno odczytu, jak i zapisu plików MS Project.

### P: Czy Aspose.Tasks dla Javy jest kompatybilne z różnymi wersjami MS Project?  
**O:** Absolutnie, Aspose.Tasks dla Javy obsługuje różne formaty MS Project, zapewniając szeroką kompatybilność.

### P: Czy istnieją ograniczenia wersji próbnej Aspose.Tasks dla Javy?  
**O:** Wersja próbna pozwala na eksplorację biblioteki, ale dodaje znaki wodne do plików wyjściowych.

### P: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla Javy?  
**O:** Pomoc można uzyskać na forum społeczności Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

### P: Czy mogę kupić tymczasową licencję na Aspose.Tasks dla Javy?  
**O:** Tak, tymczasowe licencje są dostępne na krótkoterminowe użycie. Uzyskaj ją z [here](https://purchase.aspose.com/temporary-license/).

### P: Czy zapisanie jako XML zachowuje pola niestandardowe?  
**O:** Tak, przy zapisie przy użyciu `SaveFileFormat.Xml` wszystkie niestandardowe atrybuty i pola rozszerzone są zachowywane.

### P: Czy mogę zmienić datę rozpoczęcia po dodaniu zadań?  
**O:** Możesz zaktualizować datę rozpoczęcia w dowolnym momencie przed zapisem; wystarczy ponownie wywołać `project.set(Prj.START_DATE, …)`.

---

**Ostatnia aktualizacja:** 2026-01-05  
**Testowane z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}