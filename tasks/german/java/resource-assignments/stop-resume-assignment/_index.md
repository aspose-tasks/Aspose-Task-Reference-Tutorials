---
date: 2026-01-10
description: Erfahren Sie, wie Sie Zuweisungen stoppen, Ressourcen‑Zuweisungen verwalten
  und ein Beispiel für eine Ressourcen‑Zuweisung in Aspose.Tasks für Java mit diesem
  Schritt‑für‑Schritt‑Tutorial anzeigen.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man Zuweisungen stoppt und Ressourcenzuweisungen in Aspose.Tasks fortsetzt
url: /de/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Zuweisungen stoppt und Ressourcen‑Zuweisungen in Aspose.Tasks wieder aufnimmt

## Einführung
In diesem Tutorial **erfahren Sie, wie Sie eine Zuweisung stoppen** und später mit Aspose.Tasks für Java wieder aufnehmen können. Aspose.Tasks ist eine leistungsstarke Java‑API, mit der Sie Projektdateien im Java‑Format lesen, Microsoft‑Project‑Daten manipulieren und Ressourcen‑Zuweisungen verwalten können, ohne dass Microsoft Project installiert sein muss. Wir gehen Schritt für Schritt durch, erklären, warum jede Zeile wichtig ist, und geben Ihnen praktische Tipps, die Sie in realen Projekten anwenden können.

## Schnelle Antworten
- **Was bedeutet „Zuweisung stoppen“?** Sie markiert eine Ressourcen‑Zuweisung ab einem bestimmten Stopp‑Datum als vorübergehend inaktiv.  
- **Kann ich dieselbe Zuweisung später wieder aufnehmen?** Ja, indem Sie ein Wiederaufnahme‑Datum für dieselbe Zuweisung festlegen.  
- **Benötige ich Microsoft Project, um diese API zu nutzen?** Nein, Aspose.Tasks funktioniert unabhängig von Microsoft Project.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher wird empfohlen.  
- **Wo kann ich die Bibliothek herunterladen?** Auf der offiziellen Aspose.Tasks‑Java‑Download‑Seite.

## Was bedeutet „wie man Zuweisungen stoppt“ im Kontext von Aspose.Tasks?
Das Stoppen einer Zuweisung weist den Scheduler an, die nach dem **Stopp‑Datum** (und ggf. bis zum **Wiederaufnahme‑Datum**) zugewiesene Arbeit zu ignorieren. Das ist nützlich für Urlaube, Geräteausfälle oder jede Zeitspanne, in der eine Ressource nicht aktiv sein soll.

## Warum Aspose.Tasks zur Verwaltung von Ressourcen‑Zuweisungen verwenden?
- **Kein Microsoft Project nötig** – arbeiten Sie direkt mit .mpp‑Dateien.  
- **Volle Kontrolle über Daten** – Sie können Stopp‑Datum, Wiederaufnahme‑Datum programmgesteuert prüfen und anpassen.  
- **Plattformübergreifend** – läuft auf jedem OS, das Java unterstützt.  
- **Umfangreiche API** – bietet ein *resource assignment example*, das Sie für benutzerdefinierte Berichte erweitern können.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) auf Ihrem System installiert.  
- Aspose.Tasks für Java‑Bibliothek heruntergeladen. Sie können sie von [hier](https://releases.aspose.com/tasks/java/) herunterladen.  
- Grundlegende Kenntnisse in der Java‑Programmierung.  

## Pakete importieren
Zuerst importieren wir die notwendigen Pakete in unser Java‑Projekt:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Schritt 1: Projektdatei laden
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Hier **lesen wir das Projektdatei‑Java‑Format** (`.mpp`) und erstellen ein `Project`‑Objekt, das uns Zugriff auf alle Projektdaten, einschließlich der Ressourcen‑Zuweisungen, gibt.

## Schritt 2: Durch Ressourcen‑Zuweisungen iterieren
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Wir setzen ein **Mindestdatum**, um Platzhalter‑Daten herauszufiltern, und durchlaufen dann jede Zuweisung. Das ist das typische *resource assignment example*-Muster, das verwendet wird, wenn Sie Zuweisungen prüfen oder ändern müssen.

## Schritt 3: Stopp‑ und Wiederaufnahme‑Daten prüfen
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

In diesem Block **prüfen wir das Stopp‑Datum** und **das Wiederaufnahme‑Datum** jeder Zuweisung. Ist das Datum vor unserem `minDate`, behandeln wir es als nicht gesetzt (`"NA"`); andernfalls geben wir das tatsächliche Datum aus. Diese Logik ist entscheidend, um **Ressourcen‑Zuweisungen** korrekt zu verwalten.

## Häufige Probleme und Lösungen
- **Null‑Daten** – `ra.get(Asn.STOP)` kann `null` zurückgeben. Schützen Sie sich mit einer Null‑Prüfung, bevor Sie `.before(minDate)` aufrufen.  
- **Falscher Dateipfad** – Stellen Sie sicher, dass `dataDir` mit einem Pfad‑Trennzeichen (`/` oder `\\`) endet, das zu Ihrem OS passt.  
- **Versionskonflikt** – Verwenden Sie die neueste Aspose.Tasks‑Java‑Version, um fehlende Enum‑Werte zu vermeiden.

## FAQ's
### Kann ich Aspose.Tasks ohne Microsoft Project verwenden?
Ja, Aspose.Tasks ermöglicht die Arbeit mit Microsoft‑Project‑Dateien, ohne dass Microsoft Project auf Ihrem System installiert sein muss.

### Wo finde ich weitere Dokumentation?
Detaillierte Dokumentation finden Sie [hier](https://reference.aspose.com/tasks/java/).

### Gibt es eine kostenlose Testversion?
Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

### Wie erhalte ich Support, wenn ich auf Probleme stoße?
Support erhalten Sie von der Community [hier](https://forum.aspose.com/c/tasks/15).

### Kann ich eine temporäre Lizenz erwerben?
Ja, eine temporäre Lizenz können Sie [hier](https://purchase.aspose.com/temporary-license/) erwerben.

## Häufig gestellte Fragen

**F: Wie setze ich programmgesteuert ein Stopp‑Datum für eine Zuweisung?**  
A: Verwenden Sie `ra.set(Asn.STOP, yourDateObject);`, wobei `yourDateObject` ein `java.util.Date` ist.

**F: Was passiert, wenn das Wiederaufnahme‑Datum vor dem Stopp‑Datum liegt?**  
A: Die API erzwingt keine chronologische Reihenfolge; der Scheduler behandelt die Zuweisung jedoch nur nach dem späteren der beiden Daten als aktiv. Sie sollten die Daten selbst validieren.

**F: Kann ich Zuweisungen filtern, die ein Stopp‑Datum besitzen?**  
A: Ja, iterieren Sie über `prj.getResourceAssignments()` und prüfen Sie `ra.get(Asn.STOP) != null`.

**F: Ist es möglich, ein gesetztes Stopp‑Datum zu entfernen?**  
A: Setzen Sie das Stopp‑Datum mit `ra.set(Asn.STOP, null);` auf `null` und speichern Sie das Projekt anschließend.

**F: Unterstützt Aspose.Tasks weitere datumsbezogene Felder wie Start, Ende oder tatsächlichen Start?**  
A: Absolut. Das `Asn`‑Enum stellt Konstanten für alle Zuweisungsfelder bereit, z. B. `Asn.START`, `Asn.FINISH` usw.

## Fazit
Durch Befolgen dieser Schritte wissen Sie jetzt **wie man Zuweisungen stoppt**, die Stopp‑/Wiederaufnahme‑Daten prüft und die Zuweisung bei Bedarf wieder aufnimmt. Diese Fähigkeit ermöglicht Ihnen, **Ressourcen‑Zuweisungen** präziser zu verwalten, insbesondere in Szenarien wie Urlaubszeiten oder Geräteausfällen. Passen Sie das Beispiel gerne an, um Daten zu aktualisieren, Berichte zu erzeugen oder es in Ihre eigene Terminlogik zu integrieren.

---

**Zuletzt aktualisiert:** 2026-01-10  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}