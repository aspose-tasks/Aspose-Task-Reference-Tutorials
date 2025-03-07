---
title: Zapisz zaktualizowane dane zasobów w Aspose.Tasks
linktitle: Zapisz zaktualizowane dane zasobów w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak bez wysiłku aktualizować dane zasobów w plikach MS Project za pomocą Aspose.Tasks dla Java.
weight: 21
url: /pl/java/resource-management/write-updated-resource-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz zaktualizowane dane zasobów w Aspose.Tasks

## Wstęp
W tym samouczku przeprowadzimy Cię przez proces aktualizowania danych zasobów programu Microsoft Project przy użyciu Aspose.Tasks dla Java. Aspose.Tasks to potężny interfejs API języka Java, który umożliwia manipulowanie plikami programu Microsoft Project bez konieczności instalowania programu Microsoft Project w systemie.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2.  Aspose.Tasks dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/java/).
3. Podstawowa znajomość programowania w języku Java.

## Importuj pakiety

Najpierw musisz zaimportować niezbędne pakiety do pracy z Aspose.Tasks w swoim kodzie Java. Dodaj następujące instrukcje importu do pliku Java:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: Skonfiguruj swój katalog danych

Zdefiniuj katalog, w którym znajdują się pliki danych:

```java
String dataDir = "Your Data Directory";
```

## Krok 2: Określ pliki wejściowe i wyjściowe

Zdefiniuj ścieżki wejściowego pliku MS Project i wynikowego zaktualizowanego pliku:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Plik testowy z jednym rsc do aktualizacji
String resultFile = dataDir + "OutputMPP.mpp"; // Plik do napisania projektu testowego
```

## Krok 3: Załaduj projekt

 Załaduj plik MS Project do pliku`Project` obiekt:

```java
Project project = new Project(file);
```

## Krok 4: Dodaj zasób i ustaw atrybuty

Dodaj nowy zasób do projektu i ustaw jego atrybuty takie jak stawka standardowa, stawka za nadgodziny i grupa:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Krok 5: Zapisz projekt

Zapisz zaktualizowany projekt ze zmodyfikowanymi danymi zasobów:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Wniosek

W tym samouczku pokazaliśmy, jak zaktualizować dane zasobów MS Project za pomocą Aspose.Tasks dla Java. Wykonując poniższe kroki, można efektywnie programowo manipulować informacjami o zasobach w plikach MS Project.

## Często zadawane pytania

### P1: Czy mogę zaktualizować wiele zasobów w tym samym projekcie, używając Aspose.Tasks dla Java?

Odpowiedź 1: Tak, możesz zaktualizować wiele zasobów, przeglądając je i odpowiednio ustawiając ich atrybuty.

### P2: Czy Aspose.Tasks obsługuje inne formaty plików oprócz MS Project?

O2: Tak, Aspose.Tasks obsługuje różne formaty plików, w tym XML, MPP i inne.

### P3: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami Java?

O3: Aspose.Tasks jest kompatybilny z wersją Java 6 i nowszą.

### P4: Czy mogę wykonywać inne operacje na plikach MS Project za pomocą Aspose.Tasks?

Odpowiedź 4: Tak, możesz wykonywać szeroki zakres operacji, takich jak czytanie, pisanie i manipulowanie zadaniami, zasobami i kalendarzami.

### P5: Gdzie mogę znaleźć dodatkową pomoc lub wsparcie dla Aspose.Tasks?

 A5: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy lub pytań.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
