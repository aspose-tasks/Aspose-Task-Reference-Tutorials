---
date: 2026-02-20
description: Erfahren Sie, wie Sie das Projektstartdatum festlegen und Projektabweichungen
  mit Aspose.Tasks für Java verwalten. Dieser Leitfaden zeigt außerdem, wie Sie die
  Aufgabendauer effizient festlegen.
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projektstartdatum festlegen & Aufgabenabweichungen verarbeiten Aspose.Tasks
url: /de/java/task-properties/handle-variances/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektstartdatum festlegen & Aufgabenabweichungen verwalten Aspose.Tasks

## Einführung
In der Welt des Projektmanagements ist **set project start date** einer der ersten Schritte, um Ihrem Zeitplan eine solide Grundlage zu geben. Aspose.Tasks für Java macht diesen Schritt – und die anschließende Handhabung von Aufgabenabweichungen – einfach und zuverlässig. In diesem Tutorial lernen Sie, wie man das Projektstartdatum festlegt, die Aufgabendauer setzt und Projektabweichungen effizient verwaltet.

## Schnelle Antworten
- **Was ist die primäre Methode, um das Projektstartdatum festzulegen?** Verwenden Sie `project.set(Prj.START_DATE, …)` mit einer `java.util.Calendar`-Instanz.  
- **Welche Klasse repräsentiert eine Basislinie für die Abweichungsverfolgung?** `BaselineType.Baseline`.  
- **Kann ich Start- und Enddaten von Aufgaben anpassen, nachdem die Basislinie gesetzt wurde?** Ja, einfach `Tsk.START` und `Tsk.STOP` aktualisieren.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine temporäre Lizenz ist für die Evaluierung verfügbar.  
- **Welche Version von Aspose.Tasks funktioniert mit diesem Code?** Die neueste Aspose.Tasks für Java-Version.

## Was ist **set project start date**?
Das Festlegen des Projektstartdatums definiert den Kalendertag, von dem aus alle Aufgabendaten berechnet werden. Es beeinflusst die Zeitplanberechnungen, die Analyse des kritischen Pfads und die Erstellung von Basislinien und ist damit entscheidend für eine genaue Abweichungsverwaltung.

## Warum das Projektstartdatum festlegen und Abweichungen verwalten?
- **Vorhersagbarkeit:** Stellt eine bekannte Basislinie bereit, um den tatsächlichen Fortschritt zu vergleichen.  
- **Flexibilität:** Ermöglicht das Anpassen einzelner Aufgabendaten, ohne den ursprünglichen Plan zu verlieren.  
- **Berichterstattung:** Ermöglicht klare Abweichungsberichte, die Terminverschiebungen oder vorzeitige Abschlüsse hervorheben.  

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Java-Entwicklungsumgebung – ein installiertes JDK und eine IDE oder ein Build‑Tool bereit.  
- Aspose.Tasks‑Bibliothek – laden Sie die Bibliothek **[hier](https://releases.aspose.com/tasks/java/)** herunter.  

## Pakete importieren
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Schritt 1: Projekt einrichten
Erstellen Sie eine neue `Project`‑Instanz, die alle Aufgaben und Planungsinformationen enthält.

```java
Project project = new Project();
```

## Schritt 2: Aufgabe hinzufügen
Fügen Sie eine Aufgabe unter der Stammaufgabe hinzu. Dies wird das Arbeitselement sein, das wir später anpassen.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Schritt 3: Startdatum und Dauer festlegen
Definieren Sie das Startdatum des Projekts und geben Sie der Aufgabe eine Dauer. Dies demonstriert **set task duration** in der Praxis.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## Schritt 4: Basislinie festlegen
Erstellen Sie eine Basislinie, damit Sie später geplante mit tatsächlichen Daten vergleichen können – entscheidend für **manage project variances**.

```java
project.setBaseline(BaselineType.Baseline);
```

## Schritt 5: Start- und Enddaten der Aufgabe anpassen
Ändern Sie die Start- und Enddaten der Aufgabe, um ein Abweichungsszenario zu simulieren.

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*Passen Sie die Daten und Dauern gerne an die spezifischen Anforderungen Ihres Projekts an.*

## Häufige Probleme & Tipps
- **Die Basislinie muss vor dem Anpassen der Daten gesetzt werden.** Wenn Sie zuerst die Daten ändern, erfasst die Basislinie den geänderten Zeitplan anstelle des ursprünglichen Plans.  
- **Kalendermonate sind nullbasiert.** Denken Sie daran, dass `Calendar.FEBRUARY` dem Monat 1 entspricht, nicht 2.  
- **Dauereinheiten:** `project.getDuration(2)` erzeugt standardmäßig eine Dauer von zwei Tagen; passen Sie die Einheit an, wenn Sie Stunden oder Wochen benötigen.

## Fazit
Durch das Beherrschen von **set project start date**, **set task duration** und **manage project variances** erhalten Sie die volle Kontrolle über Ihren Projektzeitplan mit Aspose.Tasks für Java. Die obigen Schritte bieten eine solide Grundlage, die Sie auf komplexere Szenarien wie mehrphasige Projekte, Ressourcenallokation und automatisierte Berichterstattung erweitern können.

## Häufig gestellte Fragen
### Ist Aspose.Tasks für alle Projektmanagement‑Bedürfnisse geeignet?
Aspose.Tasks ist ein vielseitiges Werkzeug, das für ein breites Spektrum an Projektmanagement‑Anforderungen geeignet ist und Flexibilität sowie robuste Funktionen bietet.

### Kann ich Aspose.Tasks in mein bestehendes Java‑Projekt integrieren?
Ja, Sie können Aspose.Tasks problemlos in Ihr Java‑Projekt integrieren, indem Sie der bereitgestellten Dokumentation **[hier](https://reference.aspose.com/tasks/java/)** folgen.

### Ist eine temporäre Lizenz für Aspose.Tasks verfügbar?
Ja, Sie können eine temporäre Lizenz für Aspose.Tasks **[hier](https://purchase.aspose.com/temporary-license/)** erhalten.

### Wo kann ich Unterstützung für Aspose.Tasks erhalten?
Für Support und Diskussionen besuchen Sie das Aspose.Tasks‑Forum **[hier](https://forum.aspose.com/c/tasks/15)**.

### Kann ich Aspose.Tasks für Java herunterladen?
Ja, laden Sie die neueste Version von Aspose.Tasks für Java **[hier](https://releases.aspose.com/tasks/java/)** herunter.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-02-20  
**Getestet mit:** Aspose.Tasks latest Java release  
**Autor:** Aspose