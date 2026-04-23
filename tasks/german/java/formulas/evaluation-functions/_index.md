---
date: 2026-02-13
description: Erfahren Sie, wie Sie einen Projektbericht erstellen, indem Sie ein Projektobjekt
  in Java erzeugen, erweiterte Attribute hinzufügen und Bewertungsfunktionen mit Aspose.Tasks
  verwenden.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Projektbericht generieren – Projektobjekt in Java erstellen
url: /de/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Unterstützen von Evaluierungsfunktionen in Aspose.Tasks-Formeln

## Einführung
Aspose.Tasks für Java ermöglicht es Ihnen, **Projektberichte zu erstellen**, indem Sie ein **Projektobjekt** in Java erzeugen und Microsoft‑Project‑Funktionen direkt in Ihrem Code auswerten. Durch das Einbetten dieser Formeln können Sie komplexe Berechnungen durchführen, benutzerdefinierte Berichte generieren und die Projektanalyse automatisieren, ohne Ihre Entwicklungsumgebung zu verlassen. In diesem Tutorial führen wir Sie durch das Erstellen eines Projektobjekts, das Hinzufügen eines erweiterten Attributs und die Verwendung von Evaluierungsfunktionen, um **benutzerdefinierte Feld‑Aufgabendaten** hinzuzufügen.

## Schnellantworten
- **Was bedeutet „create project object java“?** Es erzeugt eine im Speicher befindliche `Project`‑Instanz, die Sie programmgesteuert manipulieren können.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (Download von der offiziellen Seite).  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Aspose.Tasks‑Lizenz erforderlich; eine kostenlose Testversion ist verfügbar.  
- **Kann ich benutzerdefinierte Felder verwenden?** Ja – Sie können **erweitertes Attribut** zu Aufgaben hinzufügen und diese als benutzerdefinierte Felder behandeln.  
- **Ist das mit allen Project‑Dateiformaten kompatibel?** Aspose.Tasks unterstützt die Formate MPP, MPT und XML.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java‑Entwicklungsumgebung** – JDK 8+ und eine IDE wie IntelliJ IDEA oder Eclipse.  
2. **Aspose.Tasks für Java Bibliothek** – Downloaden und einbinden der Bibliothek von der [Aspose.Tasks für Java Download‑Seite](https://releases.aspose.com/tasks/java/).

## Pakete importieren
Fügen Sie den Aspose.Tasks‑Namespace zu Ihrer Java‑Klasse hinzu, damit Sie mit Projekten, Aufgaben und erweiterten Attributen arbeiten können:

```java
import com.aspose.tasks.*;
```

## Projektbericht erzeugen – Projektobjekt in Java erstellen
Instanziieren Sie ein neues `Project`‑Objekt. Dieses dient als Container für alle Aufgaben, Ressourcen und benutzerdefinierten Daten, die Sie definieren werden.

```java
Project project = new Project();
```

Die obige Zeile **creates project object java**, das zunächst leer ist und bereit für Anpassungen.

## So fügen Sie ein erweitertes Attribut hinzu
Definieren Sie ein erweitertes Attribut, das für jede Aufgabe benutzerdefinierte numerische Daten (z. B. einen Sinuswert) speichert.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Hier **add extended attribute** vom Typ `Number` mit dem Namen „Sine“ und verknüpfen es mit Aufgaben.

## Das erweiterte Attribut dem Projekt hinzufügen
Registrieren Sie die Attributdefinition im Projekt, sodass jede Aufgabe darauf zugreifen kann.

```java
project.getExtendedAttributes().add(attr);
```

## Eine neue Aufgabe erstellen
Fügen Sie eine einfache Aufgabe mit dem Namen „Task“ unter der Stammaufgabe des Projekts hinzu.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Das erweiterte Attribut mit der Aufgabe verknüpfen
Verknüpfen Sie das zuvor definierte erweiterte Attribut mit der neu erstellten Aufgabe.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Jetzt enthält die Aufgabe ein benutzerdefiniertes Feld „Sine“, das Sie in Formeln oder Berechnungen verwenden können. So **add custom field task** Daten programmgesteuert.

## Warum Evaluierungsfunktionen verwenden?
Das Einbetten von MS‑Project‑Funktionen in Aspose.Tasks‑Formeln ermöglicht Ihnen:

- Sofortige Berechnungen (z. B. `Sin([Start])`) ohne externe Werkzeuge.  
- Alle Projektlogiken in einem einzigen, wartbaren Code‑Base zu behalten.  
- Dynamische Berichte zu erzeugen, die Echtzeit‑Datenänderungen widerspiegeln und Ihnen helfen, **Projektberichte automatisch zu generieren**.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Formel liefert `NaN`** | Prüfen Sie, ob der Typ des benutzerdefinierten Feldes mit dem erwarteten numerischen Typ übereinstimmt. |
| **Erweitertes Attribut nicht sichtbar** | Stellen Sie sicher, dass die Attributdefinition dem Projekt **vor** dem Erstellen von Aufgaben hinzugefügt wird. |
| **Lizenzausnahme** | Installieren Sie eine temporäre oder vollständige **Aspose.Tasks‑Lizenz**; im Testmodus können bestimmte Funktionen eingeschränkt sein. |
| **Temporäre Lizenz fehlt** | Beschaffen Sie eine **temporäre Aspose‑Lizenz** von der Aspose‑Website. |

## Häufig gestellte Fragen

**F: Kann Aspose.Tasks für Java komplexe MS‑Project‑Formeln verarbeiten?**  
A: Ja, Aspose.Tasks für Java unterstützt die Auswertung einer breiten Palette von MS‑Project‑Funktionen, sodass komplexe Berechnungen innerhalb von Java‑Anwendungen möglich sind.

**F: Ist Aspose.Tasks für Java mit verschiedenen Versionen von Microsoft‑Project‑Dateien kompatibel?**  
A: Ja, Aspose.Tasks für Java unterstützt verschiedene Versionen von Microsoft‑Project‑Dateien, einschließlich der Formate MPP, MPT und XML.

**F: Kann ich Aspose.Tasks für Java vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java von der Website [hier](https://purchase.aspose.com/buy) herunterladen.

**F: Wie erhalte ich Support für Aspose.Tasks für Java?**  
A: Sie erhalten Support im Aspose.Tasks‑Community‑Forum [hier](https://forum.aspose.com/c/tasks/15).

**F: Gibt es eine temporäre Lizenz für Aspose.Tasks für Java?**  
A: Ja, Sie können eine temporäre Lizenz für Testzwecke von der Aspose‑Website [hier](https://purchase.aspose.com/temporary-license/) erhalten.

## Fazit
Durch Befolgen dieser Schritte haben Sie gelernt, wie man **Projektobjekt erstellt**, **erweitertes Attribut hinzufügt** und Evaluierungsfunktionen nutzt, um **Projektberichte automatisch zu generieren**. Sie können nun auf dieser Grundlage aufbauen, um umfangreichere Projektanalysen, benutzerdefinierte Dashboards oder automatisierte Planungswerkzeuge zu erstellen – alles angetrieben von Aspose.Tasks für Java.

---

**Zuletzt aktualisiert:** 2026-02-13  
**Getestet mit:** Aspose.Tasks für Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}