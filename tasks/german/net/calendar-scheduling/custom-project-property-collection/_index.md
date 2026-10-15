---
date: 2026-10-15
description: Erfahren Sie, wie Sie ein custom property hinzufügen und custom project
  properties in Aspose.Tasks für .NET verwalten, um die Kontrolle über Ihre project
  metadata zu verbessern.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Verwalten der Custom Project Property Collection in Aspose.Tasks
og_description: Fügen Sie ein custom property zu Ihren Projektdateien mit Aspose.Tasks
  für .NET hinzu. Dieser Leitfaden zeigt Ihnen, wie Sie custom properties verwalten,
  auslesen und boolean- oder string-Werte effizient hinzufügen.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Fügen Sie ein custom property mit der Aspose.Tasks .NET API für Projekte
  hinzu
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Wie man ein custom property in Aspose.Tasks für .NET hinzufügt
url: /de/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein benutzerdefiniertes Property in Aspose.Tasks für .NET hinzufügt

## Einleitung

Die Unterstützung für benutzerdefinierte Eigenschaften ermöglicht es Ihnen, projektspezifische Metadaten zu speichern, die von den integrierten Feldern nicht abgedeckt werden. In diesem Tutorial lernen Sie, wie Sie **eine benutzerdefinierte Eigenschaft hinzufügen**, sie wieder auslesen und die gesamte Sammlung benutzerdefinierter Eigenschaften mit Aspose.Tasks für .NET verwalten. Am Ende können Sie Projektdateien mit Boolean-, DateTime-, Double- und String‑Werten an Ihre Geschäftsregeln anpassen.

## Kurzantworten
- **Kann ich eine Boolean‑benutzerdefinierte Eigenschaft hinzufügen?** Ja – verwenden Sie `CustomPropertyType.Boolean`.
- **Wie viele Typen benutzerdefinierter Eigenschaften werden unterstützt?** Vier: Boolean, DateTime, Double, String.
- **Ist die Sammlung benutzerdefinierter Eigenschaften schreibgeschützt?** Sie kann schreibgeschützt sein, wenn das Projekt aus einer schreibgeschützten Quelle geladen wird.
- **Benötige ich eine Lizenz, um diese Funktion zu nutzen?** Eine temporäre Lizenz funktioniert für die Evaluierung; für die Produktion ist eine Voll‑Lizenz erforderlich.
- **Welche .NET‑Versionen sind kompatibel?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was ist eine benutzerdefinierte Eigenschaft?

Eine benutzerdefinierte Eigenschaft ist ein vom Benutzer definiertes Metadatenfeld, das Sie an ein Project‑Objekt anhängen. Sie ermöglicht das Speichern zusätzlicher Informationen wie „Risikoniveau“, „Kunden‑ID“ oder einer beliebigen Boolean‑Markierung, die von den Standard‑MS‑Project‑Feldern nicht abgedeckt wird.

## Warum benutzerdefinierte Eigenschaften in Aspose.Tasks hinzufügen?

Aspose.Tasks unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate** und kann Projekte mit **bis zu 10.000 Aufgaben** verarbeiten, ohne die gesamte Datei in den Speicher zu laden. Das Hinzufügen benutzerdefinierter Eigenschaften ermöglicht es, geschäftskritische Daten direkt in die Projektdatei einzubetten, wodurch externe Datenbanken überflüssig werden und die Daten mit dem Projekt mitreisen.

## Voraussetzungen

- Visual Studio (beliebige aktuelle Edition) auf Ihrem Arbeitsplatz installiert.  
- Aspose.Tasks für .NET – laden Sie es über den [Download‑Link](https://releases.aspose.com/tasks/net/) herunter.  
- Grundlegende Kenntnisse der C#‑Syntax und der .NET‑Projektstruktur.

## Namespaces importieren

Die folgenden Namespaces geben Ihnen Zugriff auf das Kern‑Projektmodell und die APIs für benutzerdefinierte Eigenschaften.

```csharp
using Aspose.Tasks;
using System;


```

## Wie fügt man eine benutzerdefinierte Eigenschaft in Aspose.Tasks hinzu?

Um eine benutzerdefinierte Eigenschaft hinzuzufügen, laden Sie zunächst das Projekt, erstellen dann ein `CustomProperty`‑Objekt, setzen dessen Namen, Typ und Wert und fügen es schließlich zur `CustomProperties`‑Sammlung des Projekts hinzu. Dieser Vorgang bettet die Metadaten direkt in die Projektdatei ein, und die Änderungen werden gespeichert, wenn Sie `project.Save(...)` aufrufen.  

`CustomProperty` stellt ein einzelnes benutzerdefiniertes Feld dar, das an ein Projekt angehängt ist.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Schritt 1: Projekt initialisieren

`Project` ist die Hauptklasse, die eine Projektdatei in Aspose.Tasks repräsentiert.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Schritt 2: Überprüfen, ob die Sammlung benutzerdefinierter Eigenschaften bereit ist

`CustomProperties` ist die Sammlung, die alle benutzerdefinierten Eigenschaftsobjekte für ein Projekt enthält.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Schritt 3: Benutzerdefinierte Eigenschaften hinzufügen

Die Methode `Add` fügt eine neue benutzerdefinierte Eigenschaft in die Projektsammlung ein.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Schritt 4: Auf benutzerdefinierte Eigenschaften zugreifen

Die Sammlung `CustomProperties` implementiert IEnumerable und ermöglicht die Iteration über jedes `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Schritt 5: Den Wert einer benutzerdefinierten Eigenschaft abrufen

Die Methode `Get` gibt den Wert einer benutzerdefinierten Eigenschaft anhand ihres Namens zurück.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Schritt 6: Über die Namen benutzerdefinierter Eigenschaften iterieren

Die Eigenschaft `Names` liefert eine Liste aller Namen benutzerdefinierter Eigenschaften in der Sammlung.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Schritt 7: Benutzerdefinierte Eigenschaften entfernen oder leeren

Die Methode `Remove` löscht eine bestimmte Eigenschaft, während `Clear` die gesamte Sammlung leert.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Häufige Fallstricke und Fehlersuche

- **Schreibgeschützte Sammlung** – Wenn `project.CustomProperties.IsReadOnly` `true` zurückgibt, stellen Sie sicher, dass die Quelldatei nicht exklusiv im Lese‑Modus geöffnet ist, oder kopieren Sie sie vor dem Bearbeiten an einen beschreibbaren Ort.  
- **Typ‑Mismatch** – Das Zuweisen eines Wertes, der **nicht zum** deklarierten `CustomPropertyType` passt, löst eine `ArgumentException` aus. Setzen Sie immer `Value`, nachdem Sie den korrekten `Type` definiert haben.  
- **Änderungen speichern** – Nach dem Hinzufügen oder Entfernen von Eigenschaften rufen Sie `project.Save("output.mpp")` auf, um die Änderungen zu persistieren; andernfalls verbleiben die Änderungen nur im Speicher.

## Häufig gestellte Fragen

**F: Kann ich benutzerdefinierte Eigenschaften beliebiger Datentypen zu meinem Projekt mit Aspose.Tasks für .NET hinzufügen?**  
A: Ja, Sie können benutzerdefinierte Eigenschaften hinzufügen, die die Typen Boolean, DateTime, Double und String unterstützen.

**F: Ist es möglich, über die Namen benutzerdefinierter Eigenschaften in Aspose.Tasks für .NET zu iterieren?**  
A: Absolut, Sie können über die Namen benutzerdefinierter Eigenschaften mit der Eigenschaft `Names` iterieren.

**F: Wie kann ich eine bestimmte benutzerdefinierte Eigenschaft aus meinem Projekt entfernen?**  
A: Sie können eine benutzerdefinierte Eigenschaft anhand ihres Namens mit der Methode `Remove` entfernen.

**F: Bietet Aspose.Tasks für .NET Unterstützung für temporäre Lizenzen?**  
A: Ja, Sie können eine temporäre Lizenz von der Aspose‑Website für Evaluierungszwecke erhalten.

**F: Wo finde ich Unterstützung oder weitere Hilfe zu Aspose.Tasks für .NET?**  
A: Sie können das Aspose.Tasks‑Forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) für Fragen oder Unterstützung besuchen.

---

**Zuletzt aktualisiert:** 2026-10-15  
**Getestet mit:** Aspose.Tasks 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man integrierte Projekt‑Eigenschaften mit Aspose.Tasks für .NET ausliest](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Verwalten der MS Project‑Attribut‑Sammlung in Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Aspose.Tasks benutzerdefinierte Feldtypen – Kalender und Zeitplanung](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}