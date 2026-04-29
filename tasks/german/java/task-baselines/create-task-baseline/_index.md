---
date: 2026-01-18
description: Erfahren Sie, wie Sie in Java eine Aufgabenliste erstellen und Aufgaben
  zu Microsoft Project hinzufügen, wobei Sie eine Basislinie ohne MS Project mit Aspose.Tasks
  festlegen.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aufgabenliste in Java erstellen – MS‑Project‑Baseline mit Aspose.Tasks
url: /de/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aufgabenliste in Java erstellen – MS Project Basislinie mit Aspose.Tasks

## Einführung
In diesem Tutorial **erstellen Sie eine Aufgabenliste in Java**, indem Sie eine Microsoft Project Aufgaben‑Basislinie mit Aspose.Tasks für Java generieren. Aspose.Tasks ermöglicht die Arbeit mit Projektdateien, ohne dass Microsoft Project installiert sein muss, sodass Sie **Aufgaben zu Microsoft Project hinzufügen**, Ressourcen manipulieren und sogar **eine Basislinie ohne MS Project festlegen** können – alles aus reinem Java‑Code.

## Schnelle Antworten
- **Was macht Aspose.Tasks?** Es stellt eine Java‑API zum Erstellen, Lesen und Bearbeiten von Microsoft‑Project‑Dateien ohne MS Project bereit.  
- **Benötige ich Microsoft Project installiert?** Nein, Aspose.Tasks funktioniert eigenständig.  
- **Welche Java‑Version wird benötigt?** JDK 8 oder höher.  
- **Kann ich eine Basislinie für eine einzelne Aufgabe festlegen?** Ja, verwenden Sie `setBaseline` mit einer Aufgabenliste.  
- **Wird für die Produktion eine Lizenz benötigt?** Ja, eine kommerzielle Lizenz entfernt die Evaluationsbeschränkungen.

## Was ist eine Aufgaben‑Basislinie?
Eine Aufgaben‑Basislinie zeichnet die ursprünglich geplanten Start‑, End‑ und Arbeitswerte einer Aufgabe auf. Sie dient als Referenzpunkt, um den tatsächlichen Fortschritt mit dem ursprünglichen Plan zu vergleichen.

## Warum Aspose.Tasks zum Erstellen einer Aufgabenliste in Java verwenden?
- **Keine MS‑Project‑Abhängigkeit** – ideal für serverseitige Automatisierung.  
- **Vollständige Kontrolle** über Aufgaben, Ressourcen und Kalender mittels Java‑Code.  
- **Kompatibilität über Versionen hinweg** mit Project‑Dateien von 2007 bis 2024.

## Voraussetzungen
1. **Java Development Kit (JDK)** – installieren Sie JDK 8 oder neuer.  
2. **Aspose.Tasks for Java** – laden Sie die Bibliothek über den [download link](https://releases.aspose.com/tasks/java/) herunter.

## Pakete importieren
Um mit Aspose.Tasks in Ihrem Java‑Projekt zu arbeiten, importieren Sie die erforderlichen Pakete:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Schritt 1: Projekt‑Objekt erstellen
```java
Project project = new Project();
```
Hier instanziieren wir ein neues `Project`‑Objekt – es repräsentiert die MS‑Project‑Datei, die unsere Aufgabenliste enthält.

## Schritt 2: Aufgabe zum Projekt hinzufügen
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Mit `getRootTask()` greifen wir auf die Wurzel der Projekt‑Hierarchie zu und **fügen eine Aufgabe zu Microsoft Project hinzu**. Der String `"Task"` ist der Aufgabenname; Sie können ihn durch jede gewünschte Beschreibung ersetzen.

## Schritt 3: Basislinie für bestimmte Aufgaben festlegen
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Um **eine Basislinie ohne MS Project festzulegen**, erstellen Sie eine Liste der Aufgaben, die Sie baseline möchten (hier `myList`) und übergeben Sie sie an `setBaseline`. Befüllen Sie `myList` mit den hinzugefügten Aufgaben, falls Sie nur eine selektive Basislinie benötigen.

## Schritt 4: Basislinie für das gesamte Projekt festlegen
```java
project.setBaseline(BaselineType.Baseline);
```
Wenn Sie das gesamte Projekt in einem Aufruf baseline möchten, rufen Sie einfach `setBaseline` mit dem gewünschten `BaselineType` auf.

## Wie man Aufgaben zu Microsoft Project mit Aspose.Tasks hinzufügt
Über die oben gezeigte einzelne Aufgabe hinaus können Sie mehrere Aufgaben, Unteraufgaben hinzufügen und Ressourcen zuweisen. Jeder Aufruf von `add()` gibt ein `Task`‑Objekt zurück, das Sie weiter konfigurieren können (Dauer, Startdatum usw.).

## Wie man eine Basislinie ohne MS Project festlegt
Aspose.Tasks ermöglicht die Erstellung von Basislinien vollständig über Code. Sie können verschiedene Basislinientypen (Baseline, Baseline1‑Baseline10) durch Ändern des `BaselineType`‑Enums festlegen, sodass Sie mehrere Revisions‑Basislinien nachverfolgen können, ohne MS Project zu öffnen.

## Häufige Probleme und Lösungen
- **Basislinie wird nicht angezeigt:** Stellen Sie sicher, dass Sie `project.save("output.mpp")` nach dem Festlegen der Basislinie aufrufen (Speicherschritt hier aus Gründen der Kürze weggelassen).  
- **Aufgabenliste erscheint leer:** Vergewissern Sie sich, dass Sie Aufgaben dem richtigen übergeordneten Element hinzufügen (`getRootTask()` oder einer Unteraufgabe).  
- **Versionskonflikt‑Fehler:** Verwenden Sie die neueste Aspose.Tasks‑JAR, um die Kompatibilität mit neueren .mpp‑Formaten sicherzustellen.

## Häufig gestellte Fragen

**F: Kann ich Aspose.Tasks für Java ohne Microsoft Project installiert verwenden?**  
A: Ja, Aspose.Tasks funktioniert unabhängig und erfordert kein Microsoft Project auf dem Host‑Rechner.

**F: Ist Aspose.Tasks für Java mit verschiedenen Versionen von Microsoft Project kompatibel?**  
A: Absolut. Die Bibliothek unterstützt Projektdateien von 2007 bis zu den neuesten 2024‑Versionen.

**F: Kann ich Projektressourcen mit Aspose.Tasks für Java manipulieren?**  
A: Ja, Sie können Ressourcen programmgesteuert hinzufügen, aktualisieren und löschen, genau wie Aufgaben.

**F: Unterstützt Aspose.Tasks für Java das Festlegen von Aufgabenabhängigkeiten?**  
A: Ja, Sie können Vorgänger‑Nachfolger‑Beziehungen mit der Klasse `TaskLink` definieren.

**F: Ist technischer Support für Aspose.Tasks für Java verfügbar?**  
A: Ja, Sie können Hilfe über das [support forum](https://forum.aspose.com/c/tasks/15) erhalten, wo Aspose‑Mitarbeiter und die Community auf Anfragen reagieren.

## Fazit
Durch das Befolgen dieser Schritte haben Sie gelernt, wie man **Aufgabenliste in Java erstellt**, **Aufgaben zu Microsoft Project hinzufügt** und **eine Basislinie ohne MS Project festlegt** mit Aspose.Tasks. Dieser Ansatz optimiert die Projekt‑Automatisierung, eliminiert die Notwendigkeit von Desktop‑Project‑Installationen und gibt Ihnen volle programmgesteuerte Kontrolle über Ihre Projektdaten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose