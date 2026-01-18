---
date: 2026-01-18
description: Erfahren Sie, wie Sie in MS Project mit Aspose.Tasks für Java den Standardtarif
  und weitere Ressourceneigenschaften festlegen, einschließlich des Hinzufügens von
  Ressourcen in MS Project und der effizienten Verwaltung von Ressourcen.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man den Standardtarif für Ressourcen in Aspose.Tasks festlegt
url: /de/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Standardtarif für Ressourcen in Aspose.Tasks festlegen

## Einführung
Wenn Sie Java‑Anwendungen entwickeln, die mit Microsoft‑Project‑Dateien interagieren müssen, ist **das Festlegen des Standardtarifs** für eine Ressource eine der häufigsten Aufgaben. In diesem Tutorial lernen Sie, wie Sie **den Standardtarif** und weitere Ressourceneigenschaften mit Aspose.Tasks für Java setzen. Am Ende der Anleitung können Sie ein Projektobjekt erstellen, eine Ressource zu einer MS‑Project‑Datei hinzufügen und MS‑Project‑Ressourcen sicher verwalten.

## Schnellantworten
- **Welche Hauptklasse wird für die Arbeit mit einer Projektdatei verwendet?** `Project`
- **Welche Methode fügt eine neue Ressource hinzu?** `project.getResources().add()`
- **Wie wird der Standardtarif gesetzt?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Benötige ich eine Lizenz für die Produktion?** Ja, eine gültige Aspose.Tasks‑Lizenz ist erforderlich.
- **Welche Java‑Version wird unterstützt?** Java 8+ (die neueste JDK wird empfohlen).

## Was bedeutet „Standardtarif festlegen“?
Der *Standardtarif festlegen*-Vorgang weist einer Ressource einen standardmäßigen Stundensatz zu. Projektmanager verwenden diesen Wert, um Arbeitskosten zu berechnen, Kostenberichte zu erstellen und Budgets zu prognostizieren.

## Warum Tarife mit Aspose.Tasks festlegen?
- **Keine Microsoft‑Project‑Installation nötig** – Dateien direkt aus Java heraus manipulieren.
- **Vollständige Treue** – alle Ressourcenkategorien, einschließlich Überstunden‑ und Kostensätze, bleiben erhalten.
- **Plattformübergreifend** – funktioniert unter Windows, Linux und macOS.
- **Automatisierungsfreundlich** – ideal für Batch‑Verarbeitung oder die Integration in CI‑Pipelines.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### Einrichtung der Java‑Entwicklungsumgebung
1. JDK installieren: Stellen Sie sicher, dass das Java Development Kit (JDK) auf Ihrem System installiert ist. Sie können es von der [Oracle‑Website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) herunterladen.
2. IDE einrichten: Wählen Sie eine integrierte Entwicklungsumgebung (IDE) wie IntelliJ IDEA, Eclipse oder NetBeans und richten Sie sie auf Ihrem Rechner ein.

### Aspose.Tasks für Java installieren
1. Aspose.Tasks für Java herunterladen: Besuchen Sie die [Download‑Seite](https://releases.aspose.com/tasks/java/) und holen Sie sich die neueste Version von Aspose.Tasks für Java.
2. In das Projekt integrieren: Binden Sie die Aspose.Tasks‑Bibliothek in Ihr Java‑Projekt ein, indem Sie sie als Abhängigkeit hinzufügen.

## Pakete importieren
Um zu beginnen, müssen Sie die erforderlichen Pakete von Aspose.Tasks für Java in Ihr Projekt importieren. Dieser Schritt stellt sicher, dass Sie Zugriff auf die benötigten Funktionalitäten haben.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Schritt 1: Ein Projektobjekt erstellen
Das Erstellen eines **Projektobjekts** ist der erste Schritt für jede MS‑Project‑Manipulation. Es repräsentiert die gesamte Projektdatei im Speicher.

```java
Project project = new Project();
```

## Schritt 2: Eine Ressource hinzufügen (add resource ms project)
Jetzt **fügen wir eine Ressource zu MS Project** über die Resources‑Sammlung hinzu. Der Ressourcenname kann beliebig sein, solange er für Ihren Zeitplan sinnvoll ist.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Schritt 3: Ressourceneigenschaften festlegen (how to set rates)
Hier **setzen wir den Standardtarif** und zeigen zudem, wie ein Überstundentarif festgelegt wird. Diese Tarife werden als `BigDecimal`‑Werte gespeichert, um die Genauigkeit zu bewahren.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Häufige Probleme und Lösungen
| Problem | Warum es auftritt | Lösung |
|-------|----------------|-----|
| `NullPointerException` beim Aufruf von `set` | Die Ressource wurde nicht korrekt hinzugefügt. | Sicherstellen, dass `project.getResources().add()` ein nicht‑null `Resource` zurückgibt. |
| Tarife erscheinen als 0 in der gespeicherten Datei | Verwendung von `int` anstelle von `BigDecimal`. | Immer `BigDecimal.valueOf()` für Geldwerte verwenden. |
| Lizenz nicht gefunden | Lizenzdatei wurde nicht geladen, bevor das `Project`‑Objekt erstellt wurde. | Lizenz laden (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) zu Beginn des Programms. |

## Fazit
Durch Befolgen dieser Schritte haben Sie gelernt, wie man **ein Projektobjekt erstellt**, **eine Ressource zu MS Project hinzufügt** und **den Standardtarif** sowie weitere Ressourceneigenschaften festlegt. Damit können Sie Kostenberechnungen automatisieren, benutzerdefinierte Berichte erzeugen und MS‑Project‑Ressourcen vollständig aus Java heraus verwalten.

## FAQ
### Kann Aspose.Tasks für Java komplexe MS‑Project‑Dateien verarbeiten?
Ja, Aspose.Tasks für Java kann eine breite Palette von MS‑Project‑Dateiformaten verarbeiten, einschließlich komplexer Dateien mit umfangreichen Aufgabenhierarchien.

### Gibt es eine kostenlose Testversion von Aspose.Tasks für Java?
Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java [hier](https://releases.aspose.com/) erhalten.

### Wo finde ich Support für Aspose.Tasks für Java?
Unterstützung und Diskussionen zu Aspose.Tasks für Java finden Sie im [Support‑Forum](https://forum.aspose.com/c/tasks/15).

### Wie kann ich eine temporäre Lizenz für Aspose.Tasks für Java erhalten?
Eine temporäre Lizenz erhalten Sie auf der [Seite für temporäre Lizenzen](https://purchase.aspose.com/temporary-license/) für Evaluierungszwecke.

### Wo kann ich eine lizenzierte Version von Aspose.Tasks für Java kaufen?
Eine lizenzierte Version von Aspose.Tasks für Java können Sie über die [Kauf‑Seite](https://purchase.aspose.com/buy) erwerben.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-01-18  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung)  
**Autor:** Aspose