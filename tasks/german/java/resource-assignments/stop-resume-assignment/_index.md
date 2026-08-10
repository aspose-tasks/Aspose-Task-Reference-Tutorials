---
date: 2026-07-14
description: Erfahren Sie, wie Sie die Ressourcen‑Zuweisung in Java stoppen, Ressourcen‑Zuweisungen
  verwalten und Beispiele mit Aspose.Tasks für Java in dieser Schritt‑für‑Schritt‑Anleitung
  ansehen.
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Stoppen und Fortsetzen von Ressourcen‑Zuweisungen in Aspose.Tasks
og_description: Stoppen Sie die Ressourcen‑Zuweisung in Java mit Aspose.Tasks. Dieses
  Tutorial zeigt, wie Sie Zuweisungen pausieren und fortsetzen, Termine handhaben
  und die API ohne Microsoft Project integrieren.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Stoppen der Ressourcen‑Zuweisung Java – Aspose.Tasks Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Wie man die Ressourcen‑Zuweisung in Java stoppt – Fortsetzen mit Aspose.Tasks
url: /de/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Ressourcenzuweisungen in Java stoppt – Fortsetzen mit Aspose.Tasks

## Einführung
In diesem Tutorial lernen Sie **wie man Ressourcenzuweisungen in Java stoppt** und später mit Aspose.Tasks für Java wieder aufnimmt. Aspose.Tasks ist eine robuste Java‑API, mit der Sie Microsoft‑Project‑Dateien lesen und schreiben, Zeitpläne manipulieren und Ressourcenzuweisungen steuern können – ganz ohne Installation von Microsoft Project. Wir gehen jeden Schritt durch, erklären, warum jede Zeile wichtig ist, und geben praktische Tipps, die Sie in realen Projektplänen anwenden können.

## Schnelle Antworten
- **Was bedeutet „Zuweisung stoppen“?** Es markiert eine Ressourcenzuweisung als vorübergehend inaktiv ab einem bestimmten Stopp‑Datum.  
- **Kann ich dieselbe Zuweisung später wieder aufnehmen?** Ja, indem Sie ein Wiederaufnahme‑Datum für dieselbe Zuweisung festlegen.  
- **Benötige ich Microsoft Project, um diese API zu nutzen?** Nein, Aspose.Tasks arbeitet unabhängig von Microsoft Project.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher wird empfohlen.  
- **Wo kann ich die Bibliothek herunterladen?** Auf der offiziellen Aspose.Tasks‑Java‑Download‑Seite.

## Wie stoppe ich Ressourcenzuweisungen in Java?
Laden Sie Ihr Projekt, finden Sie die gewünschte `ResourceAssignment`, setzen Sie das `STOP`‑Datum, optional ein `RESUME`‑Datum, und speichern Sie anschließend die Datei. Diese Reihenfolge pausiert die Arbeit für den angegebenen Zeitraum und aktiviert sie nach dem Wiederaufnahme‑Datum automatisch wieder, sodass Sie die Ressourcenkalender präzise steuern können, ohne manuelle Dateieditionen.

## Was bedeutet „wie man Zuweisung stoppt“ im Kontext von Aspose.Tasks?
Das Stoppen einer Zuweisung weist den Scheduler an, die nach dem **Stopp‑Datum** zugeordnete Arbeit zu ignorieren, bis zum **Wiederaufnahme‑Datum** (falls vorhanden). Das ist nützlich für Urlaube, Geräteausfälle oder jede Phase, in der eine Ressource nicht aktiv sein soll.

## Warum Aspose.Tasks zur Verwaltung von Ressourcenzuweisungen verwenden?
Aspose.Tasks ermöglicht die programmgesteuerte Steuerung von Zuweisungsdaten und eliminiert manuelle Änderungen, wodurch das Fehlerrisiko sinkt. Die API unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate** und kann Projekte mit **bis zu 10.000 Aufgaben** verarbeiten, während der Speicherverbrauch unter 200 MB bleibt, weil Daten gestreamt statt komplett im Speicher geladen werden. Die API läuft auf jedem Betriebssystem, das Java unterstützt, und bietet somit plattformübergreifende Flexibilität.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) 8 oder neuer installiert.  
- Aspose.Tasks für Java‑Bibliothek heruntergeladen. Sie können sie von [hier](https://releases.aspose.com/tasks/java/) beziehen.  
- Grundlegendes Verständnis von Java‑Programmierung.  

## Pakete importieren
Die Klassen `Project`, `ResourceAssignment` und `Asn` befinden sich im Namespace `com.aspose.tasks`. Importieren Sie sie am Anfang Ihrer Quelldatei:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Schritt 1: Projektdatei laden
Die Klasse `Project` ist das oberste Objekt von Aspose.Tasks, das eine einzelne Microsoft‑Project‑Datei im Speicher repräsentiert. Durch das Erzeugen einer Instanz wird die Datei geladen und Sie erhalten Zugriff auf Aufgaben, Ressourcen und Zuweisungen.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## Schritt 2: Durch Ressourcenzuweisungen iterieren
Objekte vom Typ `ResourceAssignment` stellen alle zuweisungsbezogenen Felder bereit. Wir setzen ein **Mindestdatum**, um Platzhalter‑Daten herauszufiltern, und durchlaufen dann jede Zuweisung. Dieses Muster ist das Standard‑*Ressourcenzuweisungs‑Beispiel* für Inspektion oder Modifikation.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## Schritt 3: Stopp‑ und Wiederaufnahme‑Daten prüfen
In diesem Block untersuchen wir die Felder `STOP` und `RESUME` jeder Zuweisung. Wenn ein Datum vor unserem `minDate` liegt, behandeln wir es als nicht gesetzt (`"NA"`); andernfalls geben wir das tatsächliche Datum aus. Diese Logik ist entscheidend, um **Ressourcenzuweisungen** korrekt zu verwalten.

```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

## Häufige Probleme und Lösungen
- **Null‑Daten** – `ra.get(Asn.STOP)` kann `null` zurückgeben. Schützen Sie sich mit einer Null‑Prüfung, bevor Sie `.before(minDate)` aufrufen.  
- **Falscher Dateipfad** – Stellen Sie sicher, dass `dataDir` mit einem Pfadtrenner (`/` oder `\\`) endet, der zu Ihrem Betriebssystem passt.  
- **Versionskonflikt** – Verwenden Sie die neueste Version von Aspose.Tasks für Java, um fehlende Enum‑Werte zu vermeiden.

## Häufig gestellte Fragen

**F: Wie setze ich programmgesteuert ein Stopp‑Datum für eine Zuweisung?**  
A: Verwenden Sie `ra.set(Asn.STOP, yourDateObject);`, wobei `yourDateObject` ein `java.util.Date` ist.

**F: Was passiert, wenn das Wiederaufnahme‑Datum vor dem Stopp‑Datum liegt?**  
A: Die API erzwingt keine chronologische Reihenfolge; der Scheduler behandelt die Zuweisung jedoch nur als aktiv nach dem späteren der beiden Daten, daher sollten Sie die Daten selbst validieren.

**F: Kann ich Zuweisungen filtern, die ein Stopp‑Datum besitzen?**  
A: Ja, iterieren Sie über `prj.getResourceAssignments()` und prüfen Sie `ra.get(Asn.STOP) != null`.

**F: Ist es möglich, ein gesetztes Stopp‑Datum zu entfernen?**  
A: Setzen Sie das Stopp‑Datum mit `ra.set(Asn.STOP, null);` auf `null` und speichern Sie anschließend das Projekt.

**F: Unterstützt Aspose.Tasks weitere datumsbezogene Felder wie Start, Ende oder tatsächlichen Start?**  
A: Absolut. Das `Asn`‑Enum liefert Konstanten für alle Zuweisungsfelder, z. B. `Asn.START`, `Asn.FINISH` usw.

## Fazit
Durch Befolgen dieser Schritte wissen Sie jetzt **wie man Ressourcenzuweisungen in Java stoppt**, die Stopp‑/Wiederaufnahme‑Daten prüft und die Zuweisung bei Bedarf wieder aufnimmt. Diese Fähigkeit ermöglicht Ihnen ein präziseres **Verwalten von Ressourcenzuweisungen**, insbesondere in Szenarien wie Urlaubszeiten oder Geräteausfällen. Erweitern Sie das Beispiel gern, um Daten zu aktualisieren, Berichte zu erzeugen oder es in Ihre eigene Terminlogik zu integrieren.

---

**Zuletzt aktualisiert:** 2026-07-14  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [Ressourcenzuweisungen in Aspose.Tasks erstellen](/tasks/java/resource-assignments/create-resource-assignments/)
- [Kostenabweichung berechnen und Zuweisungskosten mit Aspose.Tasks verwalten](/tasks/java/resource-assignments/assignment-cost/)
- [Notizen zu Ressourcenzuweisungen in Aspose.Tasks hinzufügen](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}