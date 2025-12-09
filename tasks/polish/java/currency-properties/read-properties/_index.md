---
date: 2025-12-04
description: Dowiedz się, jak odczytywać właściwości waluty w Javie z plików MS Project
  przy użyciu Aspose.Tasks for Java. Postępuj zgodnie z tym przewodnikiem krok po
  kroku, aby programowo wyodrębnić kod waluty, symbol, liczbę cyfr i położenie.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Odczyt właściwości waluty w Javie przy użyciu projektów Aspose.Tasks
url: /pl/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczyt właściwości waluty w Javie z projektami Aspose.Tasks

## Wprowadzenie
W tym samouczku **odczytasz właściwości waluty w Javie** z plików Microsoft Project przy użyciu API Aspose.Tasks for Java. Aspose.Tasks pozwala pracować z plikami .mpp bez konieczności instalacji Microsoft Project, co czyni go idealnym rozwiązaniem do automatycznego raportowania, migracji danych lub integracji z aplikacjami korporacyjnymi opartymi na Javie. Po zakończeniu tego przewodnika będziesz w stanie wyodrębnić kod waluty, symbol, liczbę cyfr po przecinku oraz pozycję symbolu bezpośrednio z pliku projektu.

## Szybkie odpowiedzi
- **Co oznacza „read currency properties java”?** Odnosi się do pobierania metadanych związanych z walutą (kod, symbol, liczba cyfr, pozycja) z pliku MS Project przy użyciu kodu Java.  
- **Czy potrzebna jest licencja, aby to wypróbować?** Dostępna jest darmowa wersja próbna Aspose.Tasks; licencja komercyjna jest wymagana do użytku produkcyjnego.  
- **Jaka wersja JDK jest wymagana?** Java 8 lub nowsza.  
- **Czy mogę zmodyfikować ustawienia waluty po ich odczytaniu?** Tak, Aspose.Tasks umożliwia zarówno odczyt, jak i zapis właściwości waluty.  
- **Czy jest to kompatybilne ze wszystkimi wersjami .mpp?** API obsługuje pliki utworzone w Microsoft Project 2003‑2021.

## Czym jest odczyt właściwości waluty w Javie?
Odczyt właściwości waluty w Javie oznacza dostęp do ustawień na poziomie projektu, które definiują sposób wyświetlania wartości pieniężnych w pliku Microsoft Project. Ustawienia te obejmują kod waluty ISO (np. **USD**), symbol (**$**), liczbę cyfr po przecinku oraz to, czy symbol pojawia się przed czy po kwocie.

## Dlaczego odczytywać właściwości waluty w Javie przy użyciu Aspose.Tasks?
- **Brak potrzeby instalacji Microsoft Project** – API działa na każdej platformie obsługującej Javę.  
- **Szybkie, w‑procesie wyodrębnianie** – idealne do przetwarzania wsadowego dużej liczby plików projektów.  
- **Pełna kontrola** – możesz łączyć pobrane wartości z własnymi raportami lub integrować je z systemami ERP.  
- **Wsparcie wielowersyjne** – działa z plikami .mpp od Project 2003 do najnowszej wersji 2021.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Java Development Kit (JDK)** – Java 8 lub nowszą zainstalowaną i skonfigurowaną w `PATH`.  
2. **Aspose.Tasks for Java JAR** – pobierz najnowszą bibliotekę z [tutaj](https://releases.aspose.com/tasks/java/) i dodaj ją do classpath projektu.

## Importowanie pakietów
Rozpocznij od zaimportowania przestrzeni nazwose.Tasks potrzebnej do manipulacji projektem:

```java
import com.aspose.tasks.*;
```

## Krok 1: Skonfiguruj katalog projektu
Zdefiniuj folder zawierający plik `.mpp`, który chcesz przeanalizować. Przechowywanie ścieżki w zmiennej ułatwia ponowne użycie kodu:

```java
String dataDir = "Your Data Directory";
```

*Zastąp `"Your Data Directory"` absolutną lub względną ścieżką do folderu, w którym znajduje się `project.mpp`.*

## Krok 2: Utwórz instancję czytnika projektu
Załaduj plik Microsoft Project do obiektu `Project`. Obiekt ten zapewnia dostęp do wszystkich właściwości projektu, w tym ustawień waluty:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Jeśli Twój plik ma inną nazwę, zmień `"project.mpp"` odpowiednio.*

## Krok 3: Wyświetl właściwości waluty
Teraz pobierz każdy atrybut waluty przy użyciu wyliczenia `Prj` i wypisz wyniki w konsoli. API zwraca obiekty, które możesz przekształcić w ciągi znaków do wyświetlenia:

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

## Krok 4: Zakończenie procesu
Zasygnalizuj, że wyodrębnianie zakończyło się pomyślnie. Ta prosta wiadomość jest przydatna, gdy kod działa jako część większego zadania wsadowego:

```java
System.out.println("Process completed Successfully");
```

## Typowe problemy i rozwiązania
| Problem | Dlaczego występuje | Rozwiązanie |
|---------|--------------------|-------------|
| **FileNotFoundException** | Ścieżka `dataDir` jest niepoprawna lub nazwa pliku jest błędnie napisana. | Zweryfikuj ciąg katalogu i upewnij się, że plik `.mpp` istnieje w podanej lokalizacji. |
| **NullPointerException przy `project.get(...)`** | Plik projektu nie zawiera informacji o walucie (mało prawdopodobne) lub klucz właściwości jest nieprawidłowy. | Użyj `project.contains(Prj.CURRENCY_CODE)`, aby sprawdzić istnienie przed odczytem. |
| **LicenseException** | Uruchamianie bez ważnej licencji Aspose.Tasks w środowisku produkcyjnym. | Zastosuj plik licencji używając `License license = new License(); license.setLicense("Aspose.Tasks.lic");` przed utworzeniem obiektu `Project`. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project?**  
A: Aspose.Tasks obsługuje pliki .mpp generowane przez Microsoft Project 2003‑2021, obejmując zarówno starsze, jak i najnowsze formaty.

**Q: Czy mogę modyfikować właściwości waluty przy użyciu Aspose.Tasks?**  
A: Tak, możesz zarówno odczytywać, jak i zapisywać ustawienia waluty. Użyj `project.set(Prj.CURRENCY_CODE, "EUR");`, a następnie zapisz projekt.

**Q: Czy Aspose.Tasks nadaje się do użytku komercyjnego?**  
A: Zdecydowanie tak. To komercyjna biblioteka; możesz zakupić licencję [tutaj](https://purchase.aspose.com/buy).

**Q: Czy Aspose.Tasks oferuje darmową wersję próbną?**  
A: Tak, w pełni funkcjonalna wersja próbna jest dostępna [tutaj](https://releases.aspose.com/).

**Q: Gdzie mogę uzyskać pomoc lub wsparcie dla Aspose.Tasks?**  
A: Oficjalne forum Aspose.Tasks jest najlepszym miejscem do uzyskania pomocy – odwiedź je [tutaj](https://forum.aspose.com/c/tasks/15).

## Podsumowanie
Teraz wiesz, jak **odczytać właściwości waluty w Javie** z pliku MS Project przy użyciu Aspose.Tasks for Java. Ta funkcjonalność umożliwia włączenie metadanych waluty do własnych raportów, analiz finansowych lub potoków integracyjnych bez konieczności korzystania z samego Microsoft Project. Śmiało eksperymentuj z modyfikacją właściwości lub łączeniem tych danych z innymi atrybutami projektu, aby tworzyć bardziej rozbudowane rozwiązania.

---

**Ostatnia aktualizacja:** 2025-12-04  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}