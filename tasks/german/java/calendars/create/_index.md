---
date: 2025-12-02
description: Erfahren Sie, wie Sie dem Projekt einen Kalender hinzufügen, einen MS‑Project‑Kalender
  erstellen und das Projekt mit Aspose.Tasks für Java als XML speichern.
language: de
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Kalender zum Projekt hinzufügen mit Aspose.Tasks für Java
url: /java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalender zu einem Projekt mit Aspose.Tasks für Java hinzufügen

## Einführung
In modernen Projekt‑Management‑Workflows kann die Möglichkeit, **einen Kalender zu einem Projekt** programmgesteuert hinzuzufügen, Stunden manueller Bearbeitung einsparen. Aspose.Tasks für Java bietet Entwicklern eine saubere, typensichere API zum Manipulieren von Microsoft‑Project‑Dateien, ohne den Desktop‑Client zu öffnen. In diesem Tutorial lernen Sie **wie man einen Kalender hinzufügt**, **wie man einen MS‑Project‑Kalender erstellt** und **wie man das Projekt als XML speichert** – alles mit nur wenigen Zeilen Java‑Code.

## Schnellantworten
- **Was bedeutet „Kalender zu einem Projekt hinzufügen“?**  
  Es bedeutet, eine neue Arbeitszeit‑Definition (Kalender) in eine Microsoft‑Project‑Datei per Code einzufügen.  
- **Welche Bibliothek übernimmt das?**  
  Aspose.Tasks für Java stellt die Klasse `Calendar` und den Container `Project` bereit, um Kalender zu verwalten.  
- **Benötige ich eine Lizenz?**  
  Eine temporäre Evaluierungslizenz reicht für Tests; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **Kann ich die Datei als XML speichern?**  
  Ja – verwenden Sie `SaveFileFormat.Xml`, um das Projekt als XML‑Datei zu exportieren.  
- **Was sind die Voraussetzungen?**  
  Java JDK 8+ und das Aspose.Tasks‑für‑Java‑JAR in Ihrem Klassenpfad.

## Was bedeutet „Kalender zu einem Projekt hinzufügen“?
Das Hinzufügen eines Kalenders zu einem Projekt erstellt einen benutzerdefinierten Zeitplan, der Arbeitstage, Feiertage und tägliche Arbeitsstunden definiert. Dieser Kalender kann dann Aufgaben, Ressourcen oder dem gesamten Projekt zugewiesen werden, sodass Berechnungen wie Startdaten und Dauern die definierten Arbeitszeiten berücksichtigen.

## Warum Aspose.Tasks für Java verwenden, um einen Kalender zu einem Projekt hinzuzufügen?
- **Vollständige Kontrolle** – Keine UI nötig; automatisieren Sie die massenhafte Kalendererstellung über viele Projekte hinweg.  
- **Kompatibilität über Versionen hinweg** – Funktioniert mit Project‑Dateien aus 2007, 2010, 2013, 2016 und neueren Versionen.  
- **Keine Installation von Microsoft Project erforderlich** – Ausführen auf jedem Server oder CI‑Pipeline.  
- **Export‑Flexibilität** – Speichern Sie als XML, MPP oder andere unterstützte Formate.

## Voraussetzungen
- **Java Development Kit (JDK) 8 oder neuer** installiert und konfiguriert.  
- **Aspose.Tasks für Java**‑Bibliothek – herunterladen von der [offiziellen Website](https://releases.aspose.com/tasks/java/) und das JAR zum Klassenpfad Ihres Projekts hinzufügen.  
- Eine IDE oder ein Build‑Tool (Maven/Gradle) Ihrer Wahl.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Das erforderliche Aspose.Tasks‑Paket importieren
Zuerst die Aspose.Tasks‑Klassen importieren, damit Sie mit Projekten und Kalendern arbeiten können.

```java
import com.aspose.tasks.*;
```

### Schritt 2: Den Datenverzeichnis‑Pfad festlegen
Definieren Sie, wo die erzeugte Projektdatei geschrieben werden soll. Ersetzen Sie den Platzhalter durch einen absoluten oder relativen Pfad auf Ihrem Rechner.

```java
String dataDir = "Your Data Directory";
```

### Schritt 3: Eine neue Project‑Instanz erstellen
Instanziieren Sie ein `Project`‑Objekt – das stellt eine leere Microsoft‑Project‑Datei dar, die Sie befüllen können.

```java
Project prj = new Project();
```

### Schritt 4: Die Kalender definieren, die Sie hinzufügen möchten
Verwenden Sie die Methode `Calendars.add(String name)`, um neue Kalendereinträge zu erstellen. In diesem Beispiel fügen wir drei Kalender hinzu, Sie können jedoch beliebig viele hinzufügen und deren Arbeitszeiten später konfigurieren.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Pro‑Tipp:** Nach dem Hinzufügen eines Kalenders können Sie seine Arbeitstage mit `cal1.getWeekDays().add(...)` anpassen und tägliche Arbeitsstunden über `cal1.getBaseCalendar().setWorkingTime(...)` festlegen.

### Schritt 5: Das Projekt speichern (Projekt als XML speichern)
Persistieren Sie das Projekt, einschließlich der neu hinzugefügten Kalender, in einer XML‑Datei. Dieses Format lässt sich leicht inspizieren und ist mit vielen Tools kompatibel.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Schritt 6: Eine Abschlussnachricht anzeigen
Informieren Sie den Benutzer, dass der Vorgang erfolgreich abgeschlossen wurde.

```java
System.out.println("Process completed Successfully");
```

Durch das Befolgen dieser sechs knappen Schritte haben Sie **einen Kalender zu einem Projekt hinzugefügt** und das Ergebnis als XML‑Datei gespeichert.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|--------|-----|
| **`NullPointerException` bei `prj.getCalendars()`** | Projektobjekt nicht korrekt initialisiert. | Sicherstellen, dass `new Project()` vor dem Zugriff auf Kalender aufgerufen wird. |
| **Datei nicht gefunden beim Speichern** | `dataDir` verweist auf einen nicht existierenden Ordner. | Den Ordner zuerst erstellen oder einen absoluten Pfad verwenden. |
| **Kalendername erscheint als „no info“** | Platzhalternamen wurden im Beispiel verwendet. | Durch aussagekräftige Namen ersetzen, die den Zeitplan widerspiegeln (z. B. „US Holiday Calendar“). |
| **Gespeichertes XML lässt sich in MS Project nicht öffnen** | Veraltete Aspose.Tasks‑Version verwendet. | Auf die neueste Aspose.Tasks‑für‑Java‑Version aktualisieren. |

## Häufig gestellte Fragen

**F: Kann Aspose.Tasks komplexe Kalender mit mehreren Ausnahmen verarbeiten?**  
A: Ja – nach dem Hinzufügen eines Kalenders können Sie Ausnahmen, Arbeitszeiten und Nicht‑Arbeitstage über die Klassen `WeekDay` und `Exception` definieren.

**F: Ist es möglich, den neuen Kalender bestimmten Aufgaben zuzuweisen?**  
A: Absolut. Rufen Sie eine Aufgabe über `prj.getRootTask().getChildren().add("Task Name")` ab und setzen Sie `task.set(Tsk.CALENDAR, cal3);`.

**F: Unterstützt die Bibliothek das Speichern in anderen Formaten wie MPP?**  
A: Ja. Ersetzen Sie `SaveFileFormat.Xml` durch `SaveFileFormat.Mpp` oder `SaveFileFormat.P6` nach Bedarf.

**F: Benötige ich eine Lizenz für Entwicklungs‑Builds?**  
A: Eine temporäre Evaluierungslizenz reicht für Tests; für Produktions‑Deployments ist eine Voll‑Lizenz erforderlich.

**F: Wo bekomme ich Hilfe, wenn ich auf Probleme stoße?**  
A: Das Aspose.Tasks‑Community‑Forum ist eine ausgezeichnete Ressource: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Fazit
Mit Aspose.Tasks für Java können Sie programmgesteuert **einen Kalender zu einem Projekt hinzufügen**, Planungsregeln anpassen und **das Projekt als XML speichern** – alles mit wenigen Codezeilen. Diese Automatisierung reduziert manuellen Aufwand, eliminiert menschliche Fehler und ermöglicht die Batch‑Verarbeitung großer Projektportfolios.

---

**Zuletzt aktualisiert:** 2025-12-02  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung aktuell)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}