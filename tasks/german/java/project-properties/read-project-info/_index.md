---
date: 2025-12-31
description: Erfahren Sie, wie Sie Projektinformationen, einschließlich des Zeitplans
  von Anfang an, mit Aspose.Tasks für Java lesen können. Entdecken Sie, wie Sie Projekteigenschaften
  in Java schnell extrahieren.
linktitle: Read Project Info with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man Projektinformationen aus Microsoft Project mit Aspose.Tasks für Java
  liest
url: /de/java/project-properties/read-project-info/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So lesen Sie Projektinformationen aus Microsoft Project mit Aspose.Tasks für Java

## Einführung
Wenn Sie **wie man Projekt**‑Details wie Startdaten, Enddaten oder Kalendereinstellungen direkt aus einer Microsoft‑Project‑Datei auslesen müssen, bietet Aspose.Tasks für Java einen sauberen, code‑first Ansatz. In diesem Tutorial sehen Sie genau **wie man Projekt**‑Metadaten liest, verstehen den **Projektzeitplan vom Start** und lernen, weitere wichtige Eigenschaften zu holen – alles in wenigen Zeilen Java‑Code.

## Schnellantworten
- **Was macht Aspose.Tasks für Java?** Es ermöglicht den programmgesteuerten Zugriff auf Microsoft‑Project‑Dateien (MPP, XML usw.) ohne installierten Microsoft Project.  
- **Welche Eigenschaft gibt an, ob der Zeitplan vom Start ausgeht?** `Prj.SCHEDULE_FROM_START` – true bedeutet Zeitplan vom Start, false bedeutet vom Ende.  
- **Kann ich Projekteigenschaften in Java extrahieren?** Ja, Sie können Startdatum, Enddatum, aktuelles Datum, Stichtagsdatum und Kalendernamen auslesen.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose temporäre Lizenz reicht für die Evaluierung; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher mit dem Aspose.Tasks‑JAR im Klassenpfad.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java‑Entwicklungsumgebung** – JDK 8 oder neuer installiert und konfiguriert.  
2. **Aspose.Tasks für Java** – Laden Sie die neueste Bibliothek von der [Website](https://releases.aspose.com/tasks/java/) herunter.  

## Pakete importieren
Um mit Projektdateien zu arbeiten, importieren Sie den Kern‑Namespace von Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis festlegen
Legen Sie den Ordner fest, der Ihre `.mpp`‑Datei enthält. Ersetzen Sie den Platzhalter durch den tatsächlichen Pfad auf Ihrem Rechner.

```java
String dataDir = "Your Data Directory";
```

### Schritt 2: Projektdatei laden
Erzeugen Sie eine `Project`‑Instanz, indem Sie die Microsoft‑Project‑Datei laden, die Sie untersuchen möchten.

```java
Project project = new Project(dataDir + "ReadProjectInfo.mpp");
```

### Schritt 3: Basis des Projektzeitplans bestimmen
Prüfen Sie, ob der Zeitplan vom Projekt‑Startdatum oder vom Enddatum berechnet wird. Dies ist der Kern von **wie man Projekt**‑Planungsinformationen ausliest.

```java
if (project.get(Prj.SCHEDULE_FROM_START).getValue()) {
    System.out.println("Project Start Date: " + project.get(Prj.START_DATE));
} else {
    System.out.println("Project Finish Date: " + project.get(Prj.FINISH_DATE));
}
```

> **Pro Tipp:** `Prj.SCHEDULE_FROM_START` gibt einen Boolean zurück; `true` bedeutet *Projektzeitplan vom Start*.

### Schritt 4: Weitere Projektzeitplan‑Informationen abrufen
Neben den Start‑/Enddaten benötigen Sie häufig das aktuelle Datum, das Stichtagsdatum und den dem Projekt zugeordneten Kalender. Das demonstriert **read project properties java** in Aktion.

```java
String strSchdl = (project.get(Prj.SCHEDULE_FROM_START).getValue()) ? "Project Start Date" : "Project Finish Date";
System.out.println("Project Schedule From: " + strSchdl);
System.out.println("Current Date: " + project.get(Prj.CURRENT_DATE));
System.out.println("Status Date: " + project.get(Prj.STATUS_DATE));
System.out.println("Calendar: " + project.get(Prj.CALENDAR).getName());
```

## Häufige Probleme & Lösungen
| Problem | Ursache | Lösung |
|-------|-------|-----|
| `NullPointerException` bei `project.get(Prj.CALENDAR)` | Projektdatei hat keinen Standardkalender. | Stellen Sie sicher, dass die MPP‑Datei einen Kalender definiert oder führen Sie `null`‑Prüfungen durch. |
| Daten werden als `null` ausgegeben | Projektdatei beschädigt oder fehlende Datumsfelder. | Validieren Sie die Quelldatei in Microsoft Project, bevor Sie sie verarbeiten. |
| Kompilierungsfehler: `cannot find symbol Prj` | Aspose.Tasks‑JAR nicht im Klassenpfad. | Fügen Sie `aspose-tasks-xx.jar` dem Build‑Pfad Ihres Projekts hinzu. |

## Häufig gestellte Fragen

### F: Kann ich Aspose.Tasks für Java mit jeder Version von Microsoft‑Project‑Dateien verwenden?
A: Ja, Aspose.Tasks für Java unterstützt verschiedene Versionen von Microsoft‑Project‑Dateien, einschließlich MPP‑ und XML‑Formaten.

### F: Ist Aspose.Tasks für Java mit allen Java‑Entwicklungsumgebungen kompatibel?
A: Aspose.Tasks für Java ist mit den meisten Java‑Entwicklungsumgebungen kompatibel und bietet somit Flexibilität bei der Integration.

### F: Bietet Aspose.Tasks für Java Unterstützung für die Manipulation von Projektdaten über das reine Auslesen hinaus?
A: Absolut, Aspose.Tasks für Java bietet umfangreiche Funktionen zur Manipulation von Projektdaten, einschließlich Bearbeiten, Speichern und Exportieren.

### F: Kann ich die Extraktion von Projektinformationen mit Aspose.Tasks für Java automatisieren?
A: Ja, Aspose.Tasks für Java ermöglicht Automatisierung über seine umfassende API, wodurch Prozesse zur Datenextraktion und -analyse optimiert werden.

### F: Gibt es ein Community‑Forum oder einen Support‑Kanal für Aspose.Tasks‑Java‑Nutzer?
A: Ja, Sie finden hilfreiche Ressourcen und können sich mit der Community im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) austauschen.

### F: Wie lese ich Projekteigenschaften in Java, ohne den gesamten Aufgaben‑Baum zu laden?
A: Verwenden Sie die Methode `Project.get` mit den benötigten `Prj`‑Aufzählungswerten; dadurch werden nur die angeforderten Metadaten abgerufen, was den Speicherverbrauch gering hält.

### F: Was ist der beste Weg, große MPP‑Dateien beim Extrahieren von Eigenschaften zu handhaben?
A: Laden Sie das Projekt im *Read‑Only*‑Modus (`new Project(filePath, LoadOptions)`) und fragen Sie nur die benötigten Eigenschaften ab, um einen hohen Speicherverbrauch zu vermeiden.

## Fazit
Durch Befolgen dieser Anleitung wissen Sie jetzt **wie man Projekt**‑Informationen wie Zeitplan‑Ursprung, Daten und Kalendereinstellungen mit Aspose.Tasks für Java ausliest. Das Einbinden dieser Code‑Snippets in Ihre Anwendungen ermöglicht automatisierte Berichte, benutzerdefinierte Dashboards und fundiertere Entscheidungen, ohne manuell mit Microsoft Project interagieren zu müssen.

---

**Zuletzt aktualisiert:** 2025-12-31  
**Getestet mit:** Aspose.Tasks für Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}