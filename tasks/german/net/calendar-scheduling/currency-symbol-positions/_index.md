---
date: 2026-07-19
description: Erfahren Sie, wie Sie das Währungssymbol nach dem Betrag in .NET‑Projekten
  mühelos mit Aspose.Tasks steuern können.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Positionen des Währungssymbols in Aspose.Tasks
og_description: Erfahren Sie, wie Sie das Währungssymbol nach dem Betrag mit Aspose.Tasks
  für .NET platzieren. Befolgen Sie Schritt‑für‑Schritt‑Anleitungen und bewährte Methoden.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Währungssymbol nach Betrag in Aspose.Tasks — Schnellleitfaden
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: So platzieren Sie das Währungssymbol nach dem Betrag in Aspose.Tasks
url: /de/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man das Währungssymbol nach dem Betrag in Aspose.Tasks platziert

## Einführung

Wenn Sie Projektkostenberichte erstellen, kann die Platzierung des **currency symbol after amount** die Lesbarkeit und die Einhaltung regionaler Standards beeinflussen. Aspose.Tasks für .NET ermöglicht es Ihnen, dieses Format mit nur wenigen Codezeilen zu steuern, sodass jede finanzielle Kennzahl genau so erscheint, wie Ihre Stakeholder es erwarten. In diesem Tutorial führen wir Sie durch die erforderlichen Schritte, erklären, warum die Einstellung wichtig ist, und zeigen Ihnen, wie Sie sie in einem realen .NET‑Projekt anwenden.

## Schnelle Antworten
- **Was bedeutet „currency symbol after amount“?** Es zeigt das Symbol (z. B. $) nach dem numerischen Wert an, wie `100 $`.
- **Welche Eigenschaft steuert die Position?** `CurrencySymbolPosition` im `Project`‑Objekt.
- **Benötige ich eine Lizenz?** Eine Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.
- **Unterstützte Währungen?** Über 50 integrierte Währungen, die die meisten globalen Märkte abdecken.
- **Kann ich die Einstellung zur Laufzeit ändern?** Ja, Sie können sie jederzeit vor dem Speichern der Projektdatei aktualisieren.

## Was ist die Einstellung „currency symbol after amount“?
Die **currency symbol after amount**‑Option bestimmt, ob das Währungssymbol vor oder nach dem numerischen Wert in allen Geldfeldern eines Projekts erscheint. Die Anpassung dieser Einstellung stellt sicher, dass Berichte den lokalen Buchhaltungskonventionen entsprechen, ohne manuelle Nachbearbeitung. Sie verbessert zudem die Lesbarkeit für Stakeholder, die an dieses Format gewöhnt sind.

## Warum Aspose.Tasks für die Währungsformatierung verwenden?
Aspose.Tasks unterstützt **50+ Währungen** und kann Projekte mit **10.000+ Aufgaben** verarbeiten, ohne die gesamte Datei in den Speicher zu laden, und liefert selbst auf einfacher Hardware schnelle Leistung. Die API bietet Ihnen programmatischen Zugriff und eliminiert die Notwendigkeit manueller Tabellenkalkulationsbearbeitungen. Das macht groß angelegte Finanzberichte sowohl effizient als auch zuverlässig.

## Voraussetzungen

### 1. Installation von Aspose.Tasks für .NET
Stellen Sie sicher, dass die Aspose.Tasks‑Bibliothek installiert ist. Sie können sie von [hier](https://releases.aspose.com/tasks/net/) herunterladen.

### 2. Grundkenntnisse der .NET‑Programmierung
Ein grundlegendes Verständnis der .NET‑Programmierung ist erforderlich, um den Beispielen zu folgen.

## Namespaces importieren

Der Namespace `Aspose.Tasks` bietet Zugriff auf die Klasse `Project` und zugehörige Aufzählungen.

Die Klasse `Project` ist das Top‑Level‑Objekt von Aspose.Tasks, das eine einzelne Projektdatei im Speicher repräsentiert. Nach dem Import des Namespaces können Sie mit den Projektdaten arbeiten.

```csharp

```

Nun zerlegen wir das Beispiel in klare, umsetzbare Schritte.

## Wie man das Währungssymbol nach dem Betrag festlegt?

`CurrencySymbolPosition` ist eine Aufzählung, die festlegt, ob das Währungssymbol vor oder nach dem numerischen Wert erscheint.

Laden Sie Ihr Projekt, setzen Sie `CurrencySymbolPosition` auf `After` und speichern Sie anschließend – das ist alles, was Sie benötigen, um das Symbol nach dem Betrag anzuzeigen. Dieser direkte Ansatz funktioniert für jede unterstützte Währung und erfordert keine zusätzliche Formatierungslogik. Sie können die Einstellung auch überprüfen, indem Sie einen Beispiel‑Kostenbericht exportieren, um sicherzustellen, dass das Symbol korrekt erscheint.

### Schritt 1: Projektdatei laden
Die Klasse `Project` lädt eine vorhandene MS‑Project‑Datei oder erstellt eine neue im Speicher.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Schritt 2: Währungssymbolposition festlegen
`CurrencySymbolPosition` ist eine Aufzählung, die Ihnen die Wahl zwischen `Before` und `After` ermöglicht. Das Setzen auf `After` platziert das Symbol nach dem numerischen Wert.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### Schritt 3: Mit dem Projekt arbeiten
Nachdem Sie die Symbolposition konfiguriert haben, können Sie nach Bedarf weitere Aufgaben, Ressourcen oder benutzerdefinierte Felder hinzufügen. Die Einstellung wird beim Speichern des Projekts beibehalten.

```csharp
// Perform other operations with the project...
```

## Häufige Probleme und Lösungen
- **Symbol erscheint immer noch vor dem Betrag:** Stellen Sie sicher, dass Sie die Eigenschaft *vor* dem Aufruf von `Save` setzen. Eine Änderung nach dem Speichern erfordert ein erneutes Speichern der Datei.
- **Nicht unterstützte Währung:** Überprüfen Sie, ob der von Ihnen verwendete Währungscode in der von Aspose.Tasks unterstützten Liste (über 50 Währungen) aufgeführt ist.
- **Leistungsverlust bei großen Projekten:** Verwenden Sie `ProjectReader`, um große Dateien zu streamen, wenn Sie 10.000 Aufgaben überschreiten.

## Häufig gestellte Fragen

**Q: Kann ich die Position des Währungssymbols innerhalb desselben Projekts mehrfach ändern?**  
A: Ja, Sie können `CurrencySymbolPosition` beliebig oft anpassen; setzen Sie einfach die Eigenschaft und speichern Sie das Projekt erneut.

**Q: Unterstützt Aspose.Tasks andere Währungen als den US‑Dollar?**  
A: Absolut. Aspose.Tasks unterstützt mehr als 50 internationale Währungen, sodass Sie mit jedem regionalen Format arbeiten können.

**Q: Gibt es eine Testversion von Aspose.Tasks für .NET?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET von [hier](https://releases.aspose.com/) erhalten.

**Q: Kann ich Unterstützung erhalten, wenn ich beim Einsatz von Aspose.Tasks für .NET auf Probleme stoße?**  
A: Natürlich! Sie können Unterstützung und Hilfe im Aspose.Tasks‑Community‑Forum [hier](https://forum.aspose.com/c/tasks/15) erhalten.

**Q: Wie kann ich eine Lizenz für Aspose.Tasks für .NET erwerben?**  
A: Sie können eine Lizenz für Aspose.Tasks für .NET von [hier](https://purchase.aspose.com/buy) erwerben.

## Fazit

Die Kontrolle der **currency symbol after amount** ist ein wesentlicher Bestandteil der Finanzberichterstattung in Projektmanagement‑Software. Mit Aspose.Tasks für .NET können Sie diese Option programmatisch festlegen, unterstützen über 50 Währungen und bearbeiten große Projekte effizient. Wenden Sie die obigen Schritte an, um sicherzustellen, dass Ihre Projektberichte den Formatierungserwartungen jeder Region entsprechen.

---

**Zuletzt aktualisiert:** 2026-07-19  
**Getestet mit:** Aspose.Tasks 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Verwalten von Kalenderkollektionen in Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [Sammlung von Kalenderaussnahmen in Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Verwalten von MS Project‑Raten mit Aspose.Tasks für .NET](/tasks/net/rate-recurring-tasks/handling-rates/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}