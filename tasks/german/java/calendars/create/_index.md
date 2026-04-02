---
date: 2026-01-31
description: Erfahren Sie, wie Sie einen Projektkalender erstellen, einen Feiertagskalender
  hinzufügen und das Projekt‑XML mit Aspose.Tasks für Java exportieren.
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man einen Projektkalender mit Aspose.Tasks für Java erstellt
url: /de/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So erstellen Sie einen Projektkalender mit Aspose.Tasks für Java

## Einführung
In modernen Projekt‑Management‑Workflows kann die Möglichkeit, **einen Projektkalender** programmgesteuert zu **erstellen**, Stunden manueller Nachbearbeitung einsparen. Aspose.Tasks für Java bietet Entwicklern eine saubere, typensichere API, um Microsoft‑Project‑Dateien zu manipulieren, ohne den Desktop‑Client zu öffnen. In diesem Tutorial lernen Sie **wie man einen Kalender hinzufügt**, **wie man einen MS‑Project‑Kalender erstellt** und **wie man das Projekt als XML exportiert** – alles mit nur wenigen Zeilen Java‑Code.

## Schnellantworten
- ** eine neue Arbeitszeit‑Definition (Kalender) innerhalb einer Microsoft‑Project‑Datei per Code zu erzeugen.  
- **Welche Bibliothek übernimmt das?**  
  Aspose.Tasks für Java stellt die Klasse `Calendar` und den Container `Project` bereit, um Kalender zu verwalten.  
- **Benötige ich eine Lizenz?**  
  Eine temporäre Evaluierungslizenz reicht für Tests; für den Produktionseinsatz ist eine Voll‑Liz ich die Datei als XML exportieren?**  
  Ja – verwenden Sie `SaveFileFormat.Xml`, um das Projekt als XML‑Datei zu exportieren.  
- **Was sind die Voraussetzungen?**  
  Java JDK 8+ und das Aspose.Tasks‑für?
Ein Projektkalender definiert Arbeitstage, Feiertage und tägliche Arbeitsstunden für ein Projekt. Sobald der Kalender Aufgaben, Ressourcen oder dem gesamten Projekt zugeordnet ist, berücksichtigen alle Planungsberechnungen die definierten Arbeitszeiten.

## Warum Aspose.Tasks für Java zum Erstellente Kalendererstellung über viele Projekte hinweg ohne UI.  
- **Kompatibilität über Versionen hinweg** – Funktioniert mit Project‑Dateien aus neueren Versionen.  
- **Keine Installation von Microsoft Project nötig** – Lä als XML, MPP oder andere unterstützte Formate.

## Voraussetzungen
- **Java Development Kit (JDK) 8 oder neuer** installiert und konfiguriert.  
- **Aspose.Tasks für Java**‑Bibliothek – herunterladen von der [offiziellen Website](https://releases.aspose.com/tasks/java/) und das JAR zum Klassenpfad Ihres Projekts hinzufügen.  
- Eine IDE oder ein Build‑Tool (Maven/Gradle) Ihrer Wahl.

## Schritt‑für‑Schritt‑Anleitung

###.Tasks‑Klassen in den Gültigkeitsbereich, damit Sie mit Projekten und Kalendern arbeiten können.

```java
import com.aspose.tasks.*;
```

### Schritt 2: Den Datenverzeichnis‑Pfad festlegen
Definieren Sie, wo die erzeugte Projektdatei geschrieben werden soll. Ersetzen Sie den Platzhalter durch einen absoluten oder relativen Pfad auf Ihrem Rechner.

```java
String dataDir = "Your Data Directory";
```

### Schritt 3: Eine neue Project‑Instanz erstellen
Instanziieren Sie ein `Project`‑Objekt – dies repräsentiert eine leere Microsoft‑Project‑Datei, die Sie befüllen können.

```java
Project prj = new Project();
```

### Schritt 4: Die Kalender)`, um neue Kalendere diesem Beispiel fügen wir drei Kalender hinzu, Sie können jedoch beliebig viele hinzufügen und deren Arbeitszeiten später konfigurieren.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Profi‑Tipp:** Nachdem Sie einen Kalender hinzugefügt haben, können Sie seine Arbeitstage mit `cal1.getWeekDays().add(...)` anpassen und die täglichen Arbeitsstunden über `cal1.getBaseCalendar().setWorkingTime(...)` festlegen.

### Schritt 5: Das Projekt speichern (Projekt‑XML exportieren)
Persistieren Sie das Projekt, inklusive der neu hinzugefügten Kalender, in einer XML‑Datei. Dieses Format lässt sich leicht inspizieren und ist mit vielen Tools kompatibel.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Schritt 6: Eine Abschlussnachricht anzeigen
Informieren Sie den Benutzer, dass der Vorgang erfolgreich abgeschlossen wurde.

```java
System.out.println("Process completed Successfully");
```

Durch das Befolgen dieser sechs knappen Schritte haben Siei hinzugefügt und **das Projekt als XML exportiert**` bei `prj.getCalendars()`** | Projektobjekt nicht korrekt initialisiert. | Sicherstellen, dass `new Project()` vor dem Zugriff auf Kalender aufgerufen wird. |
| **Datei nicht gefunden beim Speichern** | `dataDir` verweist auf einen nicht existierenden Ordner. | Ordner zuerst erstellen oder einen absoluten Pfad verwenden. |
| **Kalendername erscheint als „no info“** | Platzhalter‑Namen wurden im Beispiel verwendet. | Durch sinnvolle Namen ersetzen, die den Zeitplan widerspiegeln (z. B. „US Holiday Calendar“). |
| **Gespeichertes XML lässt sich in MS Project nicht öffnen** | Veraltete Aspose.Tasks‑Version verwendet. | Auf die neueste Aspose.Tasks‑für‑Java‑Version aktualisieren. |

## Häufig gestellte Fragen

**F: Kann Aspose.Tasks komplexe Kalender mit mehreren Ausnahmen verarbeiten?**  
A: Ja – nachdem Sie einen Kalender hinzugefügt haben, können Sie Ausnahmen und `Exception` definieren.

**F: Ist es möglich, den neuen Kalender bestimmten Aufgaben zuzuweisen?**  
A: Absolut. Rufen Sie eine Aufgabe über `prj.getRootTask().getChildren().add("Task Name")` ab und setzen Sie `task.set(Tsk.CALENDAR, cal3);`.

**F: Unterstützt die Bibliothek das Speichern in anderen Formaten wie MPP?**  
A: Ja. Ersetzen Sie `SaveFileFormat.Xml` durch `SaveFileFormat.Mpp` oder `SaveFileFormat.P6`, je nach Bedarf.

**F: Benötige ich eine Lizenz für Entwicklungs‑Builds?**  
A: Eine temporäre Evaluierungslizenz reicht für Tests; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.

**F: Wo bekomme ich Hilfe, wenn ich auf Probleme stoße?**  
A: Das Aspose.Tasks‑Community‑Forum ist eine ausgezeichnete Ressource: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Fazit
Mit Aspose.Tasks für Java können Sie programmgesteuert **Projektkalender erstellen**, Planungsregeln anpassen und **Projekt‑XML exportieren** – alles mit wenigen Codezeilen. Diese Automatisierung reduziert manuellen Aufwand, eliminiert menschliche Fehler und ermöglicht die Stapelverarbeitung großer Projektportfolios.

---

**Zuletzt aktualisiert:** 2026-01-31  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung aktuell)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}