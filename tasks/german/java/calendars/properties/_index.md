---
date: 2026-02-07
description: Erfahren Sie, wie Sie den Projektkalender in Java festlegen und die Kalender‑Eigenschaften
  von MS Project mit Aspose.Tasks verwalten. Schritt‑für‑Schritt‑Anleitung zur Anzeige
  der Arbeitszeiten des Kalenders und zur Anpassung von Zeitplänen.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man den Projektkalender in Java mit Aspose.Tasks festlegt
url: /de/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man den Projektkalender in Java mit Aspose.Tasks festlegt

## Einleitung
In diesem Tutorial entdecken Sie **how to set project calendar java** programmgesteuert mithilfe der Aspose.Tasks‑Bibliothek für Java. Das Steuern von Kalendereigenschaften ermöglicht es Ihnen, **calendar working hours** anzuzeigen, benutzerdefinierte Arbeitstage zu definieren und Ihren Projektzeitplan an reale Rahmenbedingungen anzupassen. Wir führen Sie Schritt für Schritt durch – von der Einrichtung der Umgebung über das Durchlaufen von Kalendern bis hin zum Auslesen ihrer Eigenschaften – sodass Sie **ms project calendar**‑Einstellungen in Ihren Anwendungen sicher verwalten können.

## Schnellantworten
- **What does “set project calendar” mean?** Was bedeutet „set project calendar“?  
- **Which library is required?** Welche Bibliothek wird benötigt? Aspose.Tasks for Java (jede aktuelle Version).  
- **Do I need a license?** Benötige ich eine Lizenz? Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Can I display calendar working hours?** Kann ich **calendar working hours** anzeigen? Ja – indem Sie jedes `WeekDay` auslesen, können Sie die Stunden für jeden Tagtyp ausgeben.  
- **Is this compatible with Maven/Gradle?** Ist das mit Maven/Gradle kompatibel? Absolut – fügen Sie das Aspose.Tasks‑JAR als Abhängigkeit hinzu.

## Wie man den Projektkalender in Java festlegt
Dieser Abschnitt behandelt das Hauptkeyword direkt. Wir zeigen die genauen Schritte, die Sie benötigen, um **set project calendar java**‑Werte zu setzen, Kalenderarbeitstage zu ändern und **working hours java**‑style zu berechnen.

## Was ist ein Projektkalender?
Ein Projektkalender definiert die Arbeitstage und -stunden für Aufgaben, Ressourcen und den gesamten Projektzeitplan. In MS Project können Kalender von einem Basiskalender erben, und jeder Tagtyp (z. B. **Standard**, **Non‑working**) kann eigene Arbeitszeiten besitzen. Das programmgesteuerte Verwalten dieser Einstellungen ermöglicht dynamische Planungsanpassungen ohne manuelle Bearbeitung.

## Warum MS Project Kalender programmgesteuert verwalten?
- **Automation:** Kalender über viele Projekte hinweg mit einem einzigen Skript anpassen.  
- **Consistency:** Unternehmensweite Arbeitszeit‑Richtlinien durchsetzen.  
- **Integration:** Kalender mit externen Systemen (HR, ERP) synchronisieren.  
- **Visibility:** Schnell **calendar working hours** für Berichte oder Debugging anzeigen.  
- **Flexibility:** **modify calendar working days** oder Ausnahmen on the fly hinzufügen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java Development Kit (JDK) 8+** installiert und `JAVA_HOME` konfiguriert.  
- **Aspose.Tasks for Java** Bibliothek von der [download page](https://releases.aspose.com/tasks/java/) heruntergeladen. Fügen Sie das JAR Ihrem Klassenpfad oder den Maven/Gradle‑Abhängigkeiten hinzu.  

## Pakete importieren
Zuerst importieren wir die Kernklassen von Aspose.Tasks, die wir im gesamten Tutorial verwenden werden:

```java
import com.aspose.tasks.*;
```

## Schritt 1: Datenverzeichnis einrichten
Definieren Sie den Ordner, der Ihre Projektdateien enthält. Ersetzen Sie den Platzhalter durch den tatsächlichen Pfad auf Ihrem Rechner.

```java
String dataDir = "Your Data Directory";
```

## Schritt 2: Zeiteinheiten definieren
Arbeitszeiten werden in Millisekunden angegeben. Wiederverwendbare Konstanten zu definieren macht den Code lesbarer und hilft Ihnen, **calculate working hours java** exakt zu berechnen.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Schritt 3: Projektdaten laden
Erzeugen Sie eine `Project`‑Instanz, indem Sie eine vorhandene MS Project‑XML‑Datei (`.xml` oder `.mpp`) laden. Dadurch erhalten Sie Zugriff auf alle im Dateiformat gespeicherten Kalender.

```java
Project project = new Project(dataDir + "project.xml");
```

## Durchlaufen von Kalendern in Java
Jetzt iterieren wir über jeden Kalender, geben dessen eindeutige Kennung, Namen, Basiskalender und die Arbeitsstunden für jeden Tagtyp aus. Das demonstriert, wie man **set project calendar java**‑Werte setzt und gleichzeitig **calendar working hours** anzeigt.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### Was dieser Code macht
- **Filters unnamed calendars** (some internal calendars may have a `null` name). → Filtert nicht benannte Kalender (einige interne Kalender können einen `null`‑Namen haben).  
- **Prints UID and name** – useful for identifying the calendar later. → Gibt UID und Namen aus – nützlich, um den Kalender später zu identifizieren.  
- **Shows the base calendar** – either “Self” (the calendar is its own base) or the name of the inherited calendar. → Zeigt den Basiskalender an – entweder „Self“ (der Kalender ist sein eigener Basis‑Kalender) oder den Namen des vererbten Kalenders.  
- **Loops through each `WeekDay`** to calculate and output the total working hours (`workingTime` is in milliseconds, so we divide by `OneHour`). → Durchläuft jedes `WeekDay`, um die gesamten Arbeitsstunden zu berechnen und auszugeben (`workingTime` ist in Millisekunden, daher teilen wir durch `OneHour`).  

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | Calendar is a base calendar itself (`isBaseCalendar()` returns `true`). | Use the ternary check as shown (`cal.isBaseCalendar() ? "Self" : ...`). |
| No output for working hours | The project file uses a different time unit (ticks). | Verify the file format; Aspose.Tasks normalizes to milliseconds, but ensure you’re loading the correct file type. |
| Unable to locate `project.xml` | Incorrect `dataDir` path. | Use an absolute path or `Paths.get(dataDir, "project.xml").toString()`. |

## Häufig gestellte Fragen

**Q: Can I modify calendar properties programmatically using Aspose.Tasks?**  
A: Ja, die API bietet vollen Lese‑/Schreibzugriff auf Kalender, sodass Sie Arbeitszeiten, Ausnahmen und Basiskalender‑Beziehungen hinzufügen, bearbeiten oder löschen können.

**Q: Are there any limitations to calendar customization with Aspose.Tasks?**  
A: Die Bibliothek spiegelt die Möglichkeiten von Microsoft Project wider, sodass Sie praktisch alle Kalendereigenschaften anpassen können. Nur sehr alte Project‑Dateiversionen können kleinere Kompatibilitätsprobleme aufweisen.

**Q: Can I integrate calendar management into existing Java projects?**  
A: Absolut. Fügen Sie einfach das Aspose.Tasks‑JAR zu Ihrem Build‑Pfad hinzu und verwenden Sie die hier gezeigten Code‑Muster.

**Q: Does Aspose.Tasks support other project management functionalities besides calendar management?**  
A: Ja, es deckt Aufgaben, Ressourcen, Zuordnungen, Gliederungen, Basispläne und mehr ab – eine umfassende Lösung für Java‑basierte Projekt‑Automatisierung.

**Q: Is technical support available for developers using Aspose.Tasks?**  
A: Ja, Aspose bietet dedizierte Foren, E‑Mail‑Support und umfangreiche Dokumentation für alle lizenzierten Nutzer.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}