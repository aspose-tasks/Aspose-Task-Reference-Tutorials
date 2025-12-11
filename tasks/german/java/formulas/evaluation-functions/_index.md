---
date: 2025-12-09
description: Erfahren Sie, wie Sie ein Projektobjekt in Java erstellen und Evaluierungsfunktionen
  in Aspose.Tasks‑Formeln mit Java unterstützen. Entdecken Sie, wie Sie ein erweitertes
  Attribut für Aufgaben erstellen.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Projektobjekt in Java erstellen – Evaluierungsfunktionen in Aspose.Tasks unterstützen
url: /de/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Unterstützungs‑Evaluierungsfunktionen in Aspose.Tasks‑Formeln

## Einführung
Aspose.Tasks für Java ermöglicht es Ihnen, **create project object java** Instanzen zu **erstellen** und Microsoft Project‑Funktionen direkt in Ihrem Java‑Code zu evaluieren. Durch das Einbetten dieser Formeln können Sie komplexe Berechnungen durchführen, benutzerdefinierte Berichte erzeugen und die Projektanalyse automatisieren, ohne Ihre Entwicklungsumgebung zu verlassen. Dieses Tutorial führt Sie durch den gesamten Prozess – vom Einrichten des Projektobjekts bis zum Hinzufügen eines erweiterten Attributs, das benutzerdefinierte Daten aufnehmen kann.

## Schnelle Antworten
- **Was bedeutet “create project object java”?** Es erstellt eine im Speicher befindliche `Project`‑Instanz, die Sie programmgesteuert manipulieren können.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (Download von der offiziellen Seite).  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich; eine kostenlose Testversion ist verfügbar.  
- **Kann ich benutzerdefinierte Felder verwenden?** Ja – Sie können erweiterte Attribute zu Aufgaben definieren und anhängen.  
- **Ist das mit allen Project‑Dateiformaten kompatibel?** Aspose.Tasks unterstützt die Formate MPP, MPT und XML.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java‑Entwicklungsumgebung** – JDK 8+ und eine IDE wie IntelliJ IDEA oder Eclipse.  
2. **Aspose.Tasks für Java Bibliothek** – Downloaden und in Ihr Projekt einbinden von der [Aspose.Tasks für Java Download‑Seite](https://releases.aspose.com/tasks/java/).

## Import‑Pakete
Fügen Sie den Aspose.Tasks‑Namespace zu Ihrer Java‑Klasse hinzu, damit Sie mit Projekten, Aufgaben und erweiterten Attributen arbeiten können:

```java
import com.aspose.tasks.*;
```

## Schritt 1: Create Project Object Java
Instanziieren Sie ein neues `Project`‑Objekt. Dieses dient als Container für alle Aufgaben, Ressourcen und benutzerdefinierten Daten, die Sie definieren werden.

```java
Project project = new Project();
```

Die obige Zeile **creates project object java**, das zunächst leer ist und bereit für Anpassungen.

## Schritt 2: Wie man ein erweitertes Attribut erstellt
Definieren Sie ein erweitertes Attribut, das benutzerdefinierte numerische Daten (z. B. einen Sinuswert) für jede Aufgabe speichert.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Hier **create extended attribute** vom Typ `Number` mit dem Namen „Sine“ und verknüpfen es mit Aufgaben.

## Schritt 3: Das erweiterte Attribut zum Projekt hinzufügen
Registrieren Sie die Attributdefinition im Projekt, sodass jede Aufgabe darauf zugreifen kann.

```java
project.getExtendedAttributes().add(attr);
```

## Schritt 4: Eine neue Aufgabe erstellen
Fügen Sie eine einfache Aufgabe mit dem Namen „Task“ unter der Stammaufgabe des Projekts hinzu.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Schritt 5: Das erweiterte Attribut mit der Aufgabe verknüpfen
Verknüpfen Sie das zuvor definierte erweiterte Attribut mit der neu erstellten Aufgabe.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Jetzt enthält die Aufgabe ein benutzerdefiniertes Feld „Sine“, das Sie in Formeln oder Berechnungen verwenden können.

## Warum Evaluierungsfunktionen verwenden?
Das Einbetten von MS‑Project‑Funktionen in Aspose.Tasks‑Formeln ermöglicht Ihnen:

- On‑the‑fly‑Berechnungen (z. B. `Sin([Start])`) ohne externe Werkzeuge durchzuführen.  
- Alle Projektlogik in einem einzigen, wartbaren Code‑Base zu behalten.  
- Dynamische Berichte zu erzeugen, die Echtzeit‑Datenänderungen widerspiegeln.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Formel liefert `NaN`** | Stellen Sie sicher, dass der Typ des benutzerdefinierten Feldes dem erwarteten numerischen Typ entspricht. |
| **Erweitertes Attribut nicht sichtbar** | Vergewissern Sie sich, dass die Attributdefinition dem Projekt **vor** dem Erstellen von Aufgaben hinzugefügt wurde. |
| **Lizenz‑Ausnahme** | Installieren Sie eine temporäre oder vollständige Lizenz; der Testmodus kann bestimmte Funktionen einschränken. |

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

---

**Zuletzt aktualisiert:** 2025-12-09  
**Getestet mit:** Aspose.Tasks für Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}