---
date: 2026-02-07
description: Dowiedz się, jak odczytywać właściwości waluty w Javie i wyodrębniać
  symbol waluty w Javie z plików MS Project przy użyciu Aspose.Tasks for Java. Postępuj
  zgodnie z tym przewodnikiem krok po kroku, aby programowo wyodrębnić kod waluty,
  symbol, liczbę cyfr i pozycję.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Odczyt właściwości waluty w Javie przy użyciu projektów Aspose.Tasks
url: /pl/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczyt właściwości waluty Java z projektami Aspose.Tasks

## Wstęp
W tym samouczku **odczytasz właściwości waluty java** z plików Microsoft Project przy użyciu API Aspose.Tasks dla Javy. Aspose.Tasks pozwala pracować z plikami .mpp bez konieczności instalacji Microsoft Project, co czyni go idealnym do automatycznego raportowania, migracji danych lub integracji z aplikacjami korporacyjnymi opartymi na Javie. Po zakończeniu tego przewodnika będziesz w stanie wyodrębnić kod waluty, symbol, liczbę cyfr po przecinku oraz pozycję symbolu bezpośrednio z pliku projektu.

## Szybkie odpowiedzi
- **Co oznacza „read currency properties java”?** Odnosi się do pobierania metadanych związanych z walutą (kod, symbol, cyfry, pozycja) z pliku MS Project przy użyciu kodu Java.  
- **Czy potrzebuję licencji, aby to wypróbować?** Dostępna jest bezpłatna wersja próbna Aspose.Tasks; licencja komercyjna jest wymagana do użytku produkcyjnego.  
- **Jakiej wersji JDK wymaga?** Java 8 lub nowsza.  
- **Czy mogę zmodyfikować ustawienia waluty po ich odczytaniu?** Tak, Aspose.Tasks umożliwia zarówno odczyt, jak i zapis właściwości waluty.  
- **Czy jest to kompatybilne ze wszystkimi wersjami .mpp?** API obsługuje pliki utworzone w Microsoft Project 2003‑2021.

## Czym jest read currency properties java?
Odczyt właściwości waluty w Javie oznacza dostęp do ustawień na poziomie projektu, które definiują sposób wyświetlania wartości pieniężnych w pliku Microsoft Project. Ustawienia te obejmują kod waluty ISO (np. **USD**), symbol (**$**), liczbę cyfr po przecinku oraz to, czy symbol pojawia się przed czy po kwocie.

## Dlaczego odczytywać właściwości waluty java przy użyciu Aspose.Tasks?
- **Brak konieczności instalacji Microsoft Project** – API działa na każdej platformie obsługującej Javę.  
- **Szybkie, w‑procesie wyodrębnianie** – idealne do przetwarzania wsadowego dużej liczby plików projektów.  
- **Pełna kontrola** – możesz łączyć pobrane wartości z własnymi raportami lub integrować je z systemami ERP.  
- **Wsparcie wielowersyjne** – działa z plikami .mpp od Project 2003 do najnowszej wersji 2021.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

1. **Java Development Kit (JDK)** – Java 8 lub nowsza zainstalowana i skonfigurowana w `PATH`.  
2. **Aspose.Tasks for Java JAR** – pobierz najnowszą bibliotekę z [here](https://releases.aspose.com/tasks/java/) i dodaj ją do classpath projektu.  

## Importowanie pakietów
Begin by importing the Aspose.Tasks namespace required for project manipulation:

```java
import com.aspose.tasks.*;
```

## Krok 1: Skonfiguruj katalog projektu
Define the folder that contains the `.mpp` file you want to analyze. Keeping the path in a variable makes the code reusable:

```java
String dataDir = "Your Data Directory";
```

*Zastąp `"Your Data Directory"` absolutną lub względną ścieżką do folderu, w którym znajduje się `project.mpp`.*

## Krok 2: Utwórz instancję czytnika projektu
Load the Microsoft Project file into a `Project` object. This object gives you access to all project properties, including currency settings:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Jeśli Twój plik ma inną nazwę, zmień `"project.mpp"` odpowiednio.*

## Krok 3: Wyświetl właściwości waluty
Now retrieve each currency attribute using the `Prj` enumeration and print the results to the console. The API returns objects that you can convert to strings for display:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Co zobaczysz:**  
- **Currency Code** – kod ISO‑4217, np. `USD`, `EUR`, `JPY`.  
- **Currency Digits** – zazwyczaj `2` dla większości walut, `0` dla japońskiego jena.  
- **Currency Symbol** – znak wyświetlany w raportach (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` dla **przed** kwotą, `1` dla **po**.

## Jak wyodrębnić symbol waluty java?
Jeśli interesuje Cię tylko sam symbol, możesz skupić się na właściwości `Prj.CURRENCY_SYMBOL`. To samo wywołanie `project.get(...)` zwraca symbol, który możesz przechowywać, logować lub przekazać do innej usługi w celu dalszego przetwarzania. Jest to szczególnie przydatne, gdy musisz **extract currency symbol java** dla pulpitów finansowych lub lokalizowanych komponentów UI.

## Krok 4: Zakończenie procesu
Signal that the extraction finished successfully. This simple message is helpful when the code runs as part of a larger batch job:

```java
System.out.println("Process completed Successfully");
```

## Typowe problemy i rozwiązania
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir` ścieżka jest nieprawidłowa lub nazwa pliku jest błędna. | Sprawdź ciąg katalogu i upewnij się, że plik `.mpp` istnieje w podanej lokalizacji. |
| **NullPointerException on `project.get(...)`** | Plik projektu nie zawiera informacji o walucie (mało prawdopodobne) lub klucz właściwości jest nieprawidłowy. | Użyj `project.contains(Prj.CURRENCY_CODE)`, aby sprawdzić istnienie przed odczytem. |
| **LicenseException** | Uruchamianie bez ważnej licencji Aspose.Tasks w środowisku produkcyjnym. | Zastosuj plik licencji używając `License license = new License(); license.setLicense("Aspose.Tasks.lic");` przed utworzeniem obiektu `Project`. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project?**  
A: Aspose.Tasks obsługuje pliki .mpp generowane przez Microsoft Project 2003‑2021, obejmując zarówno starsze, jak i najnowsze formaty.

**Q: Czy mogę modyfikować właściwości waluty przy użyciu Aspose.Tasks?**  
A: Tak, możesz zarówno odczytywać, jak i zapisywać ustawienia waluty. Użyj `project.set(Prj.CURRENCY_CODE, "EUR");`, a następnie zapisz projekt.

**Q: Czy Aspose.Tasks nadaje się do użytku komercyjnego?**  
A: Zdecydowanie tak. To komercyjna biblioteka; możesz zakupić licencję [here](https://purchase.aspose.com/buy).

**Q: Czy Aspose.Tasks oferuje bezpłatną wersję próbną?**  
A: Tak, w pełni funkcjonalna wersja próbna jest dostępna pod [here](https://releases.aspose.com/).

**Q: Gdzie mogę uzyskać pomoc lub wsparcie dla Aspose.Tasks?**  
A: Oficjalne forum Aspose.Tasks jest najlepszym miejscem do uzyskania pomocy – odwiedź je [here](https://forum.aspose.com/c/tasks/15).

## Dodatkowe FAQ (optymalizowane AI)

**Q: Jak programowo wyodrębnić tylko symbol waluty w Javie?**  
A: Wywołaj `project.get(Prj.CURRENCY_SYMBOL)` i rzutuj wynik na `String`. Zwróci to dokładny symbol używany w pliku projektu.

**Q: Czy mogę odczytać właściwości waluty z chronionego hasłem pliku .mpp?**  
A: Tak. Załaduj plik przy użyciu odpowiedniego przeciążenia konstruktora `Project`, które akceptuje hasło, a następnie odczytaj właściwości jak pokazano.

**Q: Jaką wydajność mogę oczekiwać przy przetwarzaniu wielu plików projektów?**  
A: Aspose.Tasks działa w‑procesie i zazwyczaj odczytuje standardowy plik .mpp w kilku milisekundach. Przy operacjach masowych rozważ ponowne użycie tej samej instancji `Project`, gdy to możliwe.

## Podsumowanie
Nauczyłeś się teraz, jak **read currency properties java** i **extract currency symbol java** z pliku MS Project przy użyciu Aspose.Tasks dla Javy. Ta możliwość pozwala włączać metadane waluty do własnych raportów, analiz finansowych lub potoków integracji bez konieczności korzystania z samego Microsoft Project. Śmiało eksperymentuj z modyfikacją właściwości lub łączeniem tych danych z innymi atrybutami projektu, aby tworzyć bardziej rozbudowane rozwiązania.

---

**Ostatnia aktualizacja:** 2026-02-07  
**Testowano z:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}