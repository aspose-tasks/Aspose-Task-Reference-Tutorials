---
date: 2026-07-19
description: Erfahren Sie, wie Sie benutzerdefinierte Feldtypen in Aspose.Tasks für
  .NET mit Schritt‑für‑Schritt‑Code, Voraussetzungen und FAQs hinzufügen.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Benutzerdefinierte Feldtypen in Aspose.Tasks
og_description: Erfahren Sie, wie Sie benutzerdefinierte Feldtypen in Aspose.Tasks
  für .NET hinzufügen. Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung, um erweiterte
  Attribute effizient zu erstellen, zu definieren und zu verwenden.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: So fügen Sie benutzerdefinierte Feldtypen in Aspose.Tasks für .NET hinzu
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: So fügen Sie benutzerdefinierte Feldtypen in Aspose.Tasks für .NET hinzu
url: /de/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man benutzerdefinierte Feldtypen in Aspose.Tasks hinzufügt

## Einführung

In diesem Tutorial erfahren Sie **wie man benutzerdefinierte Felder** zu einer Microsoft‑Project‑Datei mit Aspose.Tasks für .NET hinzufügt. Benutzerdefinierte Felder ermöglichen das Speichern zusätzlicher Informationen — wie Risikobewertungen, Abteilungscodes oder benutzerdefinierte Notizen — direkt an Aufgaben, Ressourcen oder dem Projekt selbst. Wir führen Sie durch den gesamten Prozess, von der Einrichtung der Umgebung bis hin zur Definition, dem Hinzufügen und der Überprüfung eines benutzerdefinierten Textfeldes.

## Schnelle Antworten
- **Was ist ein benutzerdefiniertes Feld?** Eine vom Benutzer definierte Spalte, die Text, Zahlen, Daten oder Kennzeichen bei Aufgaben/Ressourcen enthalten kann.  
- **Welche Klasse definiert ein benutzerdefiniertes Feld?** `ExtendedAttributeDefinition`.  
- **Kann ich ein benutzerdefiniertes Feld zu einem bestehenden Projekt hinzufügen?** Ja — Projekt laden, Definition erstellen und dann zur Sammlung hinzufügen.  
- **Benötige ich eine Lizenz für Aspose.Tasks?** Eine Lizenz ist für den Produktionseinsatz erforderlich; eine kostenlose Testversion funktioniert für Evaluierungen.  
- **Unterstützte .NET‑Versionen?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was bedeutet „how to add custom field“ in Aspose.Tasks?
**How to add custom field** bezieht sich auf den Vorgang, eine `ExtendedAttributeDefinition` zu erstellen und sie an die `ExtendedAttributes`‑Sammlung eines Projekts anzuhängen. Dadurch können Sie zusätzliche Metadaten speichern, die nicht Teil des Standard‑Project‑Schemas sind. Das kann für Aufgaben, Ressourcen oder das Projekt selbst verwendet werden, um Informationen wie Risikostufen, Abteilungscodes oder benutzerdefinierte Notizen zu erfassen, die in den Standardfeldern nicht verfügbar sind.

## Warum benutzerdefinierte Felder im Projektmanagement verwenden?
Aspose.Tasks unterstützt **mehr als 50 integrierte erweiterte Attributtypen** und ermöglicht Ihnen die Definition **beliebig vieler benutzerdefinierter Felder**, ohne die Dateigröße wesentlich zu erhöhen. Mit benutzerdefinierten Feldern können Sie:
Diese Felder erscheinen als zusätzliche Spalten in Microsoft Project und können in Formeln, Berichten und Filtern referenziert werden. Sie werden im Projektfile gespeichert und reisen mit diesem mit, sodass nachgelagerte Werkzeuge die benutzerdefinierten Daten beibehalten.

## Voraussetzungen

### 1. Visual Studio installiert
Stellen Sie sicher, dass Visual Studio (2019 oder neuer) auf Ihrem Rechner installiert ist. Sie können es von der Microsoft‑Website herunterladen.

### 2. Aspose.Tasks für .NET
Fügen Sie das Aspose.Tasks‑NuGet‑Paket zu Ihrem Projekt hinzu. Laden Sie die neueste Version von [hier](https://releases.aspose.com/tasks/net/) herunter.

### 3. Grundkenntnisse in C#
Sie sollten mit der C#‑Syntax, Klassen und der .NET‑Projektstruktur vertraut sein.

## Namespaces importieren

Der `Project`, `ExtendedAttributeDefinition` und zugehörige Aufzählungen befinden sich im `Aspose.Tasks`‑Namespace. Importieren Sie ihn am Anfang Ihrer Datei:

Der `Aspose.Tasks`‑Namespace stellt alle Kern‑Typen für die Verarbeitung von Microsoft‑Project‑Dateien bereit.

```csharp

```

## Wie man ein benutzerdefiniertes Feld zu einem Projekt hinzufügt?

Laden Sie das vorhandene Projekt, erstellen Sie eine benutzerdefinierte Felddefinition und fügen Sie sie der Sammlung erweiterter Attribute des Projekts hinzu — alles in drei kompakten Schritten. Dieses Muster funktioniert für Aufgaben, Ressourcen und das Projekt selbst und stellt sicher, dass das benutzerdefinierte Feld beim Speichern der Datei erhalten bleibt.

### Schritt 1: Projektobjekt erstellen
`Project` ist das Top‑Level‑Objekt von Aspose.Tasks, das eine einzelne Projektdatei im Speicher repräsentiert. Durch die Instanziierung wird die Datei geladen und Sie erhalten Zugriff auf Aufgaben, Ressourcen und erweiterte Attribute.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Schritt 2: Benutzerdefiniertes Feld definieren
`ExtendedAttributeDefinition` beschreibt eine neue Spalte. In diesem Beispiel erstellen wir ein **Text**‑Typ‑benutzerdefiniertes Feld für Aufgaben und geben ihm den Alias „MyText“. Der Enum‑Wert `ExtendedAttributeTask.Text1` gibt Aspose.Tasks an, wo der Wert gespeichert werden soll.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Schritt 3: Benutzerdefinierte Felddefinition zum Projekt hinzufügen
Die `ExtendedAttributes`‑Sammlung des Projekts enthält alle Definitionen benutzerdefinierter Felder. Durch das Hinzufügen der Definition wird sie für jede Aufgabe im Projekt verfügbar.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Häufige Probleme und Lösungen
- **Feld erscheint nicht in der MS‑Project‑Benutzeroberfläche** – Stellen Sie sicher, dass Sie die Eigenschaft `Alias` setzen; MS Project zeigt den Alias als Spaltenüberschrift an.  
- **Speichern wirft eine Ausnahme** – Prüfen Sie, ob die Projektdatei schreibgeschützt ist und ob Sie eine gültige Lizenz besitzen.  
- **Benutzerdefinierte Feldwerte gehen nach dem Neuladen verloren** – Stellen Sie sicher, dass Sie `project.Save("output.mpp")` aufrufen, nachdem Sie den Aufgaben Werte zugewiesen haben.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Tasks mit anderen .NET‑Frameworks verwenden?**  
A: Ja, Aspose.Tasks funktioniert mit .NET Framework, .NET Core und .NET 5/6/7.

**Q: Ist Aspose.Tasks für Unternehmens‑Anwendungen geeignet?**  
A: Absolut. Es unterstützt die Verarbeitung von Projekten mit **bis zu 10.000 Aufgaben** und kann in mehr‑threadigen Serverumgebungen laufen.

**Q: Unterstützt Aspose.Tasks mehrere Projektdateiformate?**  
A: Ja — Aspose.Tasks liest und schreibt MPP, XML, HTML und CSV und deckt **alle wichtigen Microsoft‑Project‑Versionen** ab.

**Q: Kann ich Ressourcendaten mit Aspose.Tasks manipulieren?**  
A: Ja, Sie können Ressourcen hinzufügen, aktualisieren und löschen sowie ihnen benutzerdefinierte Felder zuweisen.

**Q: Gibt es ein Community‑Forum für Aspose.Tasks‑Benutzer?**  
A: Ja, Sie können das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) besuchen, um mit anderen Benutzern zu interagieren und Unterstützung vom Aspose‑Team zu erhalten.

---

**Letzte Aktualisierung:** 2026-07-19  
**Getestet mit:** Aspose.Tasks 24.12 für .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Erweiterte Attributdefinitionen in MS Project mit Aspose.Tasks meistern](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Erweiterte Attribute in MS Project mit Aspose.Tasks manipulieren](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Field Helper MS Project Integration in Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}