---
title: Zarządzaj wartościami konspektu projektu MS za pomocą Aspose.Tasks
linktitle: Zbiór wartości konspektu w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zarządzać wartościami konspektu w plikach Microsoft Project przy użyciu Aspose.Tasks dla .NET. Samouczek krok po kroku z przykładami kodu.
weight: 17
url: /pl/net/outline-code-page-settings/outline-value-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zarządzaj wartościami konspektu projektu MS za pomocą Aspose.Tasks

## Wstęp
Aspose.Tasks dla .NET zapewnia kompleksowy zestaw funkcji do interakcji z plikami Microsoft Project. Jedną z takich funkcji jest możliwość zarządzania wartościami konspektu w projekcie. W tym samouczku odkryjemy, jak zbierać i manipulować wartościami konspektu za pomocą Aspose.Tasks dla .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1.  Aspose.Tasks dla .NET: Możesz pobrać bibliotekę z[Tutaj](https://releases.aspose.com/tasks/net/).
2. Środowisko programistyczne: Upewnij się, że masz zainstalowane odpowiednie środowisko IDE, takie jak Visual Studio.
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie korzystna.
## Importuj przestrzenie nazw
W pliku kodu C# zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do klas i metod Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

```
Podzielmy podany przykład na kilka kroków:
## Krok 1: Załaduj plik projektu
 Po pierwsze, zainicjuj a`Project` obiekt, ładując istniejący plik Microsoft Project:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Krok 2: Wyczyść istniejące wartości konspektu
Następnie usuń z projektu wszelkie istniejące wartości konspektu:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Krok 3: Zdefiniuj nowy kod konspektu
Teraz zdefiniuj nowy kod konspektu z opisem i wartością:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Krok 4: Zaktualizuj wartość konspektu
Zaktualizuj wartość kodu konspektu:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Krok 5: Iteruj po wartościach zarysu
Iteruj wartości konspektu i wydrukuj ich szczegóły:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Krok 6: Manipuluj wartościami konspektu
W razie potrzeby wykonaj operacje, takie jak usuwanie, wstawianie i kopiowanie wartości konspektu:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Wniosek
tym samouczku nauczyliśmy się pracować z wartościami konspektu w plikach Microsoft Project przy użyciu Aspose.Tasks dla .NET. Postępując zgodnie z podanymi krokami, możesz efektywnie zarządzać wartościami konspektu w swoich projektach, zapewniając większą kontrolę i elastyczność.
## Często zadawane pytania
### P: Czy mogę jednocześnie manipulować wieloma kodami konspektu?
Odp.: Tak, możesz definiować i manipulować wieloma kodami konspektu w projekcie za pomocą Aspose.Tasks.
### P: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?
O: Tak, Aspose.Tasks obsługuje różne wersje plików Microsoft Project, w tym formaty MPP i XML.
### P: Jak mogę poradzić sobie z błędami podczas pracy z wartościami konspektu?
O: Możesz zaimplementować mechanizmy obsługi błędów, takie jak bloki try-catch, aby sprawnie zarządzać wyjątkami.
### P: Czy mogę dostosować wygląd wartości konspektu w moim projekcie?
O: Tak, Aspose.Tasks zapewnia rozbudowane interfejsy API umożliwiające dostosowanie wyglądu i zachowania wartości konspektu zgodnie z Twoimi wymaganiami.
### P: Gdzie mogę znaleźć dodatkowe zasoby i wsparcie dla Aspose.Tasks?
 O: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) o wsparcie społeczności i poznaj[dokumentacja](https://reference.aspose.com/tasks/net/) aby uzyskać szczegółowe informacje na temat interfejsów API i funkcji.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
