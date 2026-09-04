---
date: 2026-07-05
description: Erfahren Sie, wie Sie das Projektbudget verfolgen und Projektkosten mit
  Aspose.Tasks für .NET verwalten. Definieren Sie Cost Accrual Types für eine genaue
  Kostenverfolgung.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Cost Accrual Types in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Projektbudget mit Cost Accrual Types in Aspose.Tasks verfolgen
url: /de/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektbudget mit Kostenabrechnungsarten in Aspose.Tasks verfolgen

## Einführung

Genaues **Verfolgen des Projektbudgets** ist das Rückgrat einer erfolgreichen Projektabwicklung. Wenn Kostendaten zum richtigen Zeitpunkt erfasst werden, können Sie Überschreitungen prognostizieren, Ressourcen anpassen und Stakeholder informieren. Aspose.Tasks für .NET gibt Entwicklern eine feinkörnige Kontrolle über die Kostenabrechnung und lässt Sie entscheiden, *wann* Kosten erfasst werden – ob zu Beginn der Arbeit, kontinuierlich oder erst, wenn die Arbeit abgeschlossen ist. Dieses Tutorial führt Sie durch die Konzepte, zeigt, wie man einen Abrechnungstyp festlegt, und demonstriert bewährte Methoden für eine zuverlässige Budgetverfolgung.

## Schnelle Antworten
- **Was ist der Hauptzweck von Kostenabrechnungsarten?** Sie bestimmen den Zeitpunkt im Lebenszyklus einer Aufgabe, an dem Kosten erkannt werden, und ermöglichen eine präzise Budgetverfolgung.  
- **Welcher Enum-Wert verzögert Kosten bis zum Abschluss der Arbeit?** `CostAccrualType.End`.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Ja, eine gültige Aspose.Tasks‑Lizenz ist für den Produktionseinsatz erforderlich.  
- **Kann ich Abrechnungstypen für viele Ressourcen gleichzeitig ändern?** Ja — iterieren Sie über die `Resources`‑Sammlung und weisen Sie den gewünschten Typ zu.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was ist ein Kostenabrechnungs‑Typ?
Ein **Kostenabrechnungs‑Typ** teilt Aspose.Tasks mit, wann die Kosten einer Ressource auf das Projektbudget angewendet werden sollen. Er wird durch die Aufzählung `CostAccrualType` dargestellt und kann pro‑Ressource oder pro‑Aufgabe festgelegt werden. Die Wahl des richtigen Typs stellt sicher, dass Kostendaten mit den Abrechnungsrichtlinien Ihrer Organisation übereinstimmen, egal ob Sie Kosten zu Beginn der Arbeit, anteilig über die Dauer oder erst nach Abschluss erfassen müssen.

## Warum das Projektbudget mit Kostenabrechnungsarten verfolgen?
Aspose.Tasks unterstützt **vier** Abrechnungsoptionen — `Start`, `Prorated`, `Duration` und `End` — und deckt damit das gesamte Spektrum typischer Projektbuchhaltungsszenarien ab. Die Auswahl der passenden Option ermöglicht es Ihnen, die Kostenerkennung an vertragliche Abrechnungszyklen anzupassen, Schwankungen in Finanzberichten zu reduzieren und Kostenaufstellungen zu erzeugen, die sich nahtlos in ERP‑Systeme integrieren, und das bei geringem Speicherverbrauch für große Projekte.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

### 1. Installieren Sie Aspose.Tasks für .NET
Um zu beginnen, müssen Sie Aspose.Tasks für .NET in Ihrer Entwicklungsumgebung installiert haben. Sie können die Bibliothek von der [download page](https://releases.aspose.com/tasks/net/) herunterladen und den bereitgestellten Installationsanweisungen folgen.

### 2. Vertrautheit mit dem .NET Framework
Grundkenntnisse des .NET‑Frameworks und der Programmiersprache C# sind erforderlich, um den Beispielen in diesem Tutorial folgen zu können.

## Wie setze ich den Kostenabrechnungs‑Typ für eine Ressource?

Laden Sie das Projekt, finden Sie die Zielressource und weisen Sie den gewünschten `CostAccrualType` zu. Das untenstehende Zwei‑Zeilen‑Muster ist der Standardansatz: Erstellen Sie eine `Project`‑Instanz, holen Sie die Ressource per ID und setzen Sie dann `CostAccrualType`. Diese kompakte Sequenz stellt sicher, dass Sie das **Projektbudget** genau ab dem Moment verfolgen, in dem die Ressource hinzugefügt wird.

### Schritt 1: Namespaces importieren
Lassen Sie uns zunächst die erforderlichen Namespaces importieren, um die Aspose.Tasks‑Funktionalität in unserem .NET‑Projekt zu nutzen:

```csharp

```

Jetzt, da die Namespaces bereitstehen, können wir mit dem Laden einer Projektdatei fortfahren.

### Schritt 2: Projektdatei laden
Die Klasse `Project` repräsentiert eine Microsoft Project‑Datei und bietet Zugriff auf deren Aufgaben, Ressourcen und weitere Daten.

```csharp
var project = new Project("Project2.mpp");
```

Zuerst müssen wir die Projektdatei in unsere Anwendung laden. Wir erstellen ein neues `Project`‑Objekt und initialisieren es mit dem Pfad zu unserer Projektdatei.

### Schritt 3: Ressource zugreifen
Die Sammlung `Resources` enthält alle im Projekt definierten Ressourcen. Die Methode `GetById` ruft eine Ressource anhand ihrer eindeutigen Kennung ab.

```csharp
var resource = project.Resources.GetById(1);
```

Als Nächstes greifen wir auf die Ressource zu, der wir den Kostenabrechnungs‑Typ zuweisen wollen. Wir verwenden die `GetById`‑Methode der `Resources`‑Sammlung und übergeben die Ressourcen‑ID als Argument. Dies demonstriert **Zugriff auf Ressource per ID**, ein häufiges Szenario bei der Automatisierung von Kostenupdates.

### Schritt 4: Kostenabrechnungs‑Typ festlegen
Die Methode `Set` weist einem Ressourcenfeld einen Wert zu.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Hier setzen wir den Kostenabrechnungs‑Typ für die Ressource. In diesem Beispiel setzen wir ihn auf `CostAccrualType.End`, was bedeutet, dass Kosten erst dann erfasst werden, wenn die verbleibende Arbeit null ist. Die Wahl von `End` ist ideal, wenn Sie das **Projektbudget** erst nach vollständigem Abschluss einer Aufgabe verfolgen möchten.

### Schritt 5: Weiter mit dem Projekt arbeiten
Nachdem der Kostenabrechnungs‑Typ gesetzt wurde, können Sie weiter mit dem Projekt arbeiten, zusätzliche Vorgänge oder Berechnungen durchführen, wie das Erzeugen von Kostenberichten, das Aktualisieren von Zuordnungen oder das Exportieren der Datei.

## Häufige Fallstricke und Profi‑Tipps
- **Pro‑Tipp:** Rufen Sie immer `project.Save` auf, nachdem Sie Abrechnungstypen geändert haben, um die Änderungen zu speichern.  
- **Fallstrick:** Das Setzen von `CostAccrualType.Start` bei einer Ressource, die nie mit der Arbeit beginnt, führt zu aufgeblähten Budgetberichten – prüfen Sie zuerst die Aufgabenpläne.  
- **Pro‑Tipp:** Verwenden Sie `project.Resources.ToList()`, wenn Sie viele Ressourcen stapelweise aktualisieren müssen; dies vermeidet wiederholte Suchen in der Sammlung und verbessert die Leistung bei großen Projekten.

## Häufig gestellte Fragen

**F: Kann ich den Kostenabrechnungs‑Typ für mehrere Ressourcen gleichzeitig ändern?**  
A: Ja, iterieren Sie über `project.Resources` und weisen Sie jedem Ressourcenobjekt innerhalb einer `foreach`‑Schleife den gewünschten `CostAccrualType` zu.

**F: Welche anderen verfügbaren Kostenabrechnungs‑Typen gibt es neben `End`?**  
A: Aspose.Tasks bietet `Start`, `Prorated` und `Duration` – jeder entspricht einer anderen Abrechnungsstrategie.

**F: Wie kann ich den aktuellen Kostenabrechnungs‑Typ für eine bestimmte Ressource ermitteln?**  
A: Rufen Sie den Wert über `resource.Get(TskResource.CostAccrualType)` ab; er gibt das Enum zurück, das die aktuelle Einstellung darstellt.

**F: Ist es möglich, unterschiedliche Kostenabrechnungs‑Typen auf verschiedene Aufgaben im selben Projekt anzuwenden?**  
A: Absolut. Sowohl Aufgaben als auch Ressourcen stellen eine `CostAccrualType`‑Eigenschaft bereit, die eine unabhängige Konfiguration pro Entität ermöglicht.

**F: Unterstützt Aspose.Tasks benutzerdefinierte Kostenabrechnungs‑Typen?**  
A: Nein, die Bibliothek unterstützt derzeit nur die vier integrierten Typen; benutzerdefinierte Logik muss bei Bedarf extern implementiert werden.

---

**Zuletzt aktualisiert:** 2026-07-05  
**Getestet mit:** Aspose.Tasks 24.8 für .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Aspose.Tasks Kalender und Planung](/tasks/net/calendar-scheduling/)
- [Verwalten von MS Project‑Raten mit Aspose.Tasks für .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [MS Project‑Ressourcen mühelos verwalten mit Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}