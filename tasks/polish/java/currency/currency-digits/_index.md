---
date: 2025-12-05
description: Dowiedz się, jak efektywnie obsługiwać cyfry walut w MS Project przy
  użyciu Aspose.Tasks for Java. Przewodnik krok po kroku obejmujący obsługę plików
  projektu w Javie oraz sposób ładowania plików MPP.
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Obsłuż cyfry waluty w MS Project przy użyciu Aspose.Tasks
url: /pl/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obsługa cyfr waluty w MS Project przy użyciu Aspose.Tasks

## Wprowadzenie
W tym obszernym samouczku odkryjesz **jak pracować z wartościami waluty w MS Project** przy użyciu biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy tworzysz narzędzie raportujące, aplikację migracyjną, czy po prostu potrzebujesz odczytać ustawienia waluty z **pliku projektu Java**, ten przewodnik poprowadzi Cię przez każdy krok — od załadowania pliku *.mpp* po wyodrębnienie cyfr waluty. Po zakończeniu będziesz pewnie obsługiwać dane walutowe MS Project w własnych aplikacjach.

## Szybkie odpowiedzi
- **Jaka biblioteka odczytuje pliki MS Project?** Aspose.Tasks for Java.  
- **Ile linii kodu potrzeba, aby uzyskać cyfry waluty?** Tylko trzy zwięzłe linie po załadowaniu projektu.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Jaką wersję Javy obsługuje?** Java 8 lub wyższą (dowolny JDK, który uruchamia Aspose.Tasks).  
- **Czy mogę pobrać inne właściwości projektu?** Tak – Aspose.Tasks udostępnia pełny zestaw pól projektu (np. datę rozpoczęcia, stawki kosztów itp.).

## Czym jest waluta w MS Project?
`ms project currency` odnosi się do precyzji liczbowej (liczby miejsc po przecinku), jaką Microsoft Project używa przy wyświetlaniu wartości pieniężnych. Jest przechowywana w pliku projektu jako właściwość **CURRENCY_DIGITS** i określa, czy kwoty wyświetlane są jako liczby całkowite, z jednym, dwoma itp. miejscami po przecinku.

## Dlaczego używać Aspose.Tasks do obsługi waluty w MS Project?
- **Brak wymogu instalacji Microsoft Project** – pracuj bezpośrednio z plikami *.mpp* na dowolnej platformie obsługującej Javę.  
- **Silne typowanie** – API zwraca silnie typowane wartości, zmniejszając błędy parsowania.  
- **Optymalizacja wydajności** – szybko wczytuj duże projekty i wyodrębniaj tylko potrzebne pola.  
- **Wieloplatformowość** – uruchamiaj na Windows, Linux lub macOS bez modyfikacji.

## Prerequisites
Zanim rozpoczniesz, upewnij się, że masz następujące elementy:

1. **Środowisko programistyczne Java** – zainstalowany i skonfigurowany JDK 8 lub nowszy.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR z oficjalnej strony: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Podstawowa znajomość Javy** – powinieneś swobodnie tworzyć projekt Java, dodawać zewnętrzne biblioteki i uruchamiać metodę `main`.  

## Importowanie pakietów
Najpierw zaimportuj klasy, które będą potrzebne.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Krok 1: Definiowanie katalogu danych
Określ folder, który zawiera Twój **plik projektu Java** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Zastąp `"Your Data Directory"` absolutną lub względną ścieżką, w której znajduje się `project.mpp`.

## Krok 2: Ładowanie pliku MPP  
Teraz zobaczymy **jak ładować pliki mpp** przy użyciu Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Upewnij się, że nazwa pliku jest dokładnie taka; w przeciwnym razie zostanie zgłoszone `IOException`.

## Krok 3: Pobieranie cyfr waluty  
Po załadowaniu projektu wyodrębnienie **cyfr waluty w MS Project** to jednowierszowy kod:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Wywołanie zwraca `Integer` reprezentujący liczbę miejsc po przecinku (np. `2` dla centów). Wartość jest wypisywana w konsoli, ale możesz ją także zapisać w zmiennej do dalszego przetwarzania.

## Typowe problemy i wskazówki
- **Plik nie znaleziony** – sprawdź dwukrotnie ścieżkę `dataDir` i upewnij się, że nazwa pliku jest poprawna, łącznie z rozszerzeniem `.mpp`.  
- **Nieobsługiwana wersja pliku** – Aspose.Tasks obsługuje formaty Project 2000‑2024; starsze lub uszkodzone pliki mogą wymagać konwersji.  
- **Licencja nie ustawiona** – podczas rozwoju wersja próbna działa, ale w produkcji musisz zastosować ważną licencję, aby uniknąć znaków wodnych wersji ewaluacyjnej.

## Frequently Asked Questions

**Q: Czy Aspose.Tasks może obsługiwać inne atrybuty projektu oprócz cyfr waluty?**  
A: Tak, Aspose.Tasks oferuje szeroki zakres funkcjonalności umożliwiających manipulację różnymi aspektami plików Project, takimi jak zadania, zasoby i pola niestandardowe.

**Q: Czy Aspose.Tasks jest odpowiedni dla aplikacji klasy enterprise?**  
A: Absolutnie, Aspose.Tasks jest zaprojektowany tak, aby sprostać wymaganiom projektów klasy enterprise, oferując wysoką wydajność i skalowalność.

**Q: Czy Aspose.Tasks wspiera rozwój wieloplatformowy?**  
A: Tak, możesz używać Aspose.Tasks for Java na dowolnej platformie obsługującej środowisko Java Runtime (Windows, Linux, macOS).

**Q: Czy mogę wypróbować Aspose.Tasks przed zakupem?**  
A: Tak, możesz pobrać darmową wersję próbną z [tutaj](https://releases.aspose.com/).

**Q: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks?**  
A: Wsparcie znajdziesz na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}