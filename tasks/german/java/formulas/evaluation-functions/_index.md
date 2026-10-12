---
date: 2026-10-10
description: Erfahren Sie, wie Sie erweiterte Attribute in Aspose.Tasks hinzufügen,
  Auswertungsfunktionen verwenden und Projektberichte mit dieser Java-Projektmanagementbibliothek
  erstellen.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Unterstützung von Auswertungsfunktionen in Aspose.Tasks-Formeln
og_description: Erfahren Sie, wie Sie erweiterte Attribute in Aspose.Tasks hinzufügen,
  Auswertungsfunktionen verwenden und Projektberichte mit dieser Java-Projektmanagementbibliothek
  erstellen.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Wie man erweiterte Attribute in Aspose.Tasks-Formeln hinzufügt
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Wie man erweiterte Attribute in Aspose.Tasks-Formeln hinzufügt
url: /de/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man erweiterte Attribute in Aspose.Tasks-Formeln hinzufügt

## Einleitung
Aspose.Tasks for Java ist eine **Java-Projektmanagement-Bibliothek**, die es Ihnen ermöglicht, Projektberichte zu erstellen, indem Sie ein `Project`‑Objekt in Java erzeugen und Microsoft‑Project‑Funktionen direkt in Ihrem Code auswerten. Durch das Einbetten dieser Formeln können Sie komplexe Berechnungen durchführen, benutzerdefinierte Berichte generieren und die Projektanalyse automatisieren, ohne Ihre Entwicklungsumgebung zu verlassen. In diesem Tutorial führen wir Sie durch das Erstellen eines Projektobjekts, das Hinzufügen eines erweiterten Attributs und die Verwendung von Auswertungsfunktionen, um **add custom field task**‑Daten hinzuzufügen.

## Schnelle Antworten
- **Was bedeutet „create project object java“?** Es erstellt eine im Speicher befindliche `Project`‑Instanz, die Sie programmgesteuert manipulieren können.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks for Java (Download von der offiziellen Seite).  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Aspose.Tasks‑Lizenz erforderlich; ein kostenloser Testzeitraum ist verfügbar.  
- **Kann ich benutzerdefinierte Felder verwenden?** Ja – Sie können **add extended attribute** zu Aufgaben hinzufügen und sie als benutzerdefinierte Felder behandeln.  
- **Ist dies mit allen Project-Dateiformaten kompatibel?** Aspose.Tasks unterstützt 3 Hauptformate (MPP, MPT, XML) und über 50 weitere Eingabe-/Ausgabeformate.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java-Entwicklungsumgebung** – JDK 8+ und eine IDE wie IntelliJ IDEA oder Eclipse.  
2. **Aspose.Tasks for Java Bibliothek** – Laden Sie die Bibliothek herunter und binden Sie sie von der [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) ein.

## Pakete importieren
Fügen Sie den Aspose.Tasks‑Namespace zu Ihrer Java‑Klasse hinzu, damit Sie mit Projekten, Aufgaben und erweiterten Attributen arbeiten können:

```java
import com.aspose.tasks.*;
```

## Projektbericht erzeugen – create project object java
Die Klasse `Project` repräsentiert eine Microsoft‑Project‑Datei im Speicher und stellt Aufgaben, Ressourcen und benutzerdefinierte Daten bereit. Durch die Instanziierung dieser Klasse erhalten Sie einen Container für alle Projektelemente, die Sie definieren werden.

```java
Project project = new Project();
```

Die obige Zeile **creates project object java** erzeugt ein leeres Projektobjekt, das bereit für Anpassungen ist.

## So fügen Sie ein erweitertes Attribut hinzu
Die Klasse `ExtendedAttributeDefinition` definiert ein benutzerdefiniertes Feld, das Aufgaben zugeordnet werden kann. Um ein erweitertes Attribut hinzuzufügen, erstellen Sie eine Instanz dieser Klasse mit dem Typ `Number`, geben ihr einen Alias wie „Sine“, fügen sie der `ExtendedAttributes`‑Sammlung des Projekts hinzu und verknüpfen sie anschließend mit jeder Aufgabe, die das benutzerdefinierte Feld benötigt.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Hier **add extended attribute** vom Typ `Number` mit dem Namen „Sine“ und verknüpfen es mit Aufgaben.

## Das erweiterte Attribut zum Projekt hinzufügen
Registrieren Sie die Attributdefinition beim Projekt, damit jede Aufgabe darauf verweisen kann.

```java
project.getExtendedAttributes().add(attr);
```

## Eine neue Aufgabe erstellen
`Task` stellt ein Arbeitselement im Projekt dar und kann benutzerdefinierte Felder enthalten.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Benutzerdefiniertes Feld Aufgabe zum Projekt hinzufügen
Verknüpfen Sie das zuvor definierte erweiterte Attribut mit der neu erstellten Aufgabe, wodurch die Aufgabe ein benutzerdefiniertes Feld „Sine“ erhält, das Sie in Formeln oder Berechnungen verwenden können.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Jetzt enthält die Aufgabe ein benutzerdefiniertes Feld „Sine“, das Sie in Formeln oder Berechnungen verwenden können. So fügen Sie programmgesteuert **add custom field task**‑Daten hinzu.

## Warum Auswertungsfunktionen verwenden?
Auswertungsfunktionen ermöglichen es Ihnen, native Microsoft‑Project‑Formeln (z. B. `Sin([Start])`) direkt in Aspose.Tasks einzubetten, wodurch Berechnungen on‑the‑fly ohne externe Verarbeitung möglich werden. Dadurch bleibt die gesamte Projektlogik an einem Ort, Daten‑Synchronisationsfehler werden reduziert und die Berichtserstellung beschleunigt. Aspose.Tasks unterstützt die Auswertung von über 100 MS‑Project‑Funktionen und bietet eine umfassende Berechnungs‑Engine in Java.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Formel gibt `NaN` zurück** | Stellen Sie sicher, dass der Typ des benutzerdefinierten Feldes dem erwarteten numerischen Typ entspricht. |
| **Erweitertes Attribut nicht sichtbar** | Stellen Sie sicher, dass die Attributdefinition dem Projekt **vor** dem Erstellen von Aufgaben hinzugefügt wird. |
| **Lizenzausnahme** | Installieren Sie eine temporäre oder vollständige **Aspose.Tasks‑Lizenz**; im Testmodus können bestimmte Funktionen eingeschränkt sein. |
| **Temporäre Lizenz fehlt** | Erhalten Sie eine **temporäre Aspose‑Lizenz** von der Aspose‑Website. |

## Häufig gestellte Fragen

**F: Kann Aspose.Tasks for Java komplexe MS‑Project‑Formeln verarbeiten?**  
A: Ja, Aspose.Tasks for Java unterstützt die Auswertung einer breiten Palette von MS‑Project‑Funktionen, wodurch komplexe Berechnungen innerhalb von Java‑Anwendungen möglich sind.

**F: Ist Aspose.Tasks for Java mit verschiedenen Versionen von Microsoft‑Project‑Dateien kompatibel?**  
A: Ja, Aspose.Tasks for Java unterstützt verschiedene Versionen von Microsoft‑Project‑Dateien, einschließlich MPP-, MPT- und XML‑Formaten.

**F: Kann ich Aspose.Tasks for Java vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks for Java von der Website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy) herunterladen.

**F: Wie kann ich Support für Aspose.Tasks for Java erhalten?**  
A: Sie können Unterstützung im Aspose.Tasks‑Community‑Forum erhalten [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**F: Gibt es eine temporäre Lizenz für Aspose.Tasks for Java?**  
A: Ja, Sie können eine temporäre Lizenz für Testzwecke von der Aspose‑Website erhalten [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

## Fazit
Durch das Befolgen dieser Schritte haben Sie gelernt, wie man **create project object**, **add extended attribute** und Auswertungsfunktionen nutzt, um **generate project report** automatisch zu erstellen. Sie können nun diese Grundlage erweitern, um umfangreichere Projektanalysen, benutzerdefinierte Dashboards oder automatisierte Planungswerkzeuge zu bauen – alles angetrieben von Aspose.Tasks for Java.

---

**Last Updated:** 2026-10-10  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose

## Verwandte Tutorials

- [Benutzerdefinierte Spalten und erweiterte Attribute im Java-Projektmanagement](/tasks/java/project-management/extended-attributes/)
- [Erweiterte Aufgabenattribute mit Aspose.Tasks for Java lesen](/tasks/java/task-properties/extended-task-attributes/)
- [Wie man Aspose.Tasks for Java verwendet – Erweiterte Attribute zu Ressourcen‑Zuweisungen hinzufügen](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}