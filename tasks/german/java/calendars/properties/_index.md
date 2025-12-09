---
date: 2025-12-04
description: Erfahren Sie, wie Sie den Projektkalender festlegen und die Kalender‑Eigenschaften
  von MS Project in Java mit Aspose.Tasks verwalten. Schritt‑für‑Schritt‑Anleitung
  zur Anzeige der Arbeitszeiten des Kalenders und zur Anpassung von Zeitplänen.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man den Projektkalender mit Aspose.Tasks für Java festlegt
url: /de/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man den Projektkalender mit Aspose.Tasks für Java festlegt

## Einführung
In diesem Tutorial erfahren Sie **wie man den Projektkalender** programmgesteuert mit der Aspose.Tasks‑Bibliothek für Java festlegt. Das Steuern von Kalendereigenschaften ermöglicht es Ihnen, **Kalenderarbeitszeiten anzuzeigen**, benutzerdefinierte Arbeitstage zu definieren und Ihren Projektplan an reale Rahmenbedingungen anzupassen. Wir führen Sie Schritt für Schritt durch – von der Einrichtung der Umgebung über das Durchlaufen der Kalender bis hin zum Auslesen ihrer Eigenschaften – sodass Sie MS‑Project‑Kalender sicher in Ihren Anwendungen verwalten können.

## Schnelle Antworten
- **Was bedeutet „Projektkalender festlegen“?** Es bedeutet, die Arbeitszeiten, das Basiskalender und die Tagstypen eines Kalenders in einer MS‑Project‑Datei zu erstellen oder zu aktualisieren.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (jede aktuelle Version).  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich Kalenderarbeitszeiten anzeigen?** Ja – indem Sie jedes `WeekDay` auslesen, können Sie die Stunden für jeden Tagstyp ausgeben.  
- **Ist das mit Maven/Gradle kompatibel?** Absolut – fügen Sie das Aspose.Tasks‑JAR als Abhängigkeit hinzu.

## Was ist ein Projektkalender?
Ein Projektkalender definiert die Arbeitstage und -stunden für Aufgaben, Ressourcen und den gesamten Projektzeitplan. In MS Project können Kalender von einem Basiskalender erben, und jeder Tagstyp (z. B. **Standard**, **Nicht‑arbeitend**) kann eigene Arbeitszeiten besitzen. Das programmgesteuerte Verwalten dieser Einstellungen ermöglicht dynamische Plananpassungen ohne manuelle Bearbeitung.

## Warum Projektkalender programmgesteuert verwalten?
- **Automatisierung:** Kalender über viele Projekte hinweg mit einem einzigen Skript anpassen.  
- **Konsistenz:** Unternehmensweite Arbeitszeit‑Richtlinien durchsetzen.  
- **Integration:** Kalender mit externen Systemen (HR, ERP) synchronisieren.  
- **Transparenz:** Schnell **Kalenderarbeitszeiten anzeigen** für Berichte oder Fehlersuche.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java Development Kit (JDK) 8+** installiert und `JAVA_HOME` konfiguriert.  
- **Aspose.Tasks für Java**‑Bibliothek von der [Download‑Seite](https://releases.aspose.com/tasks/java/) heruntergeladen. Fügen Sie das JAR Ihrem Klassenpfad oder Ihren Maven/Gradle‑Abhängigkeiten hinzu.  

## Pakete importieren
Importieren Sie zunächst die Kernklassen von Aspose.Tasks, die wir im gesamten Tutorial verwenden:

```java
import com.aspose.tasks.*;
```

## Schritt 1: Datenverzeichnis einrichten
Definieren Sie den Ordner, der Ihre Projektdateien enthält. Ersetzen Sie den Platzhalter durch den tatsächlichen Pfad auf Ihrem Rechner.

```java
String dataDir = "Your Data Directory";
```

## Schritt 2: Zeiteinheiten definieren
Arbeitszeiten werden in Millisekunden angegeben. Wiederverwendbare Konstanten machen den Code leichter lesbar.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Schritt 3: Projektdaten laden
Erzeugen Sie eine `Project`‑Instanz, indem Sie eine vorhandene MS‑Project‑XML‑Datei (`.xml` oder `.mpp`) laden. Dadurch erhalten Sie Zugriff auf alle im Dokument gespeicherten Kalender.

```java
Project project = new Project(dataDir + "project.xml");
```

## Schritt 4: Durch Kalender iterieren und Arbeitszeiten anzeigen
Jetzt durchlaufen wir jeden Kalender, geben seine eindeutige Kennung, den Namen, das Basiskalender und die Arbeitszeiten für jeden Tagstyp aus. Das demonstriert **wie man den Projektkalender** festlegt und gleichzeitig **Kalenderarbeitszeiten anzeigt**.

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
- **Filtert unbenannte Kalender** (einige interne Kalender können einen `null`‑Namen haben).  
- **Gibt UID und Namen aus** – nützlich, um den Kalender später zu identifizieren.  
- **Zeigt das Basiskalender** – entweder „Self“ (der Kalender ist sein eigenes Basiskalender) oder den Namen des vererbten Kalenders.  
- **Durchläuft jedes `WeekDay`**, um die gesamten Arbeitsstunden zu berechnen und auszugeben (`workingTime` ist in Millisekunden, daher teilen wir durch `OneHour`).  

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|--------|-----|
| `NullPointerException` bei `cal.getBaseCalendar()` | Der Kalender ist selbst ein Basiskalender (`isBaseCalendar()` liefert `true`). | Verwenden Sie die ternäre Prüfung wie gezeigt (`cal.isBaseCalendar() ? "Self" : ...`). |
| Keine Ausgabe der Arbeitszeiten | Die Projektdatei verwendet eine andere Zeiteinheit (Ticks). | Prüfen Sie das Dateiformat; Aspose.Tasks normalisiert auf Millisekunden, stellen Sie jedoch sicher, dass Sie den richtigen Dateityp laden. |
| `project.xml` nicht gefunden | Falscher `dataDir`‑Pfad. | Verwenden Sie einen absoluten Pfad oder `Paths.get(dataDir, "project.xml").toString()`. |

## Häufig gestellte Fragen

**F: Kann ich Kalender‑Eigenschaften programmgesteuert mit Aspose.Tasks ändern?**  
A: Ja, die API bietet vollen Lese‑/Schreibzugriff auf Kalender, sodass Sie Arbeitszeiten, Ausnahmen und Basiskalender‑Beziehungen hinzufügen, bearbeiten oder löschen können.

**F: Gibt es Einschränkungen bei der Kalender‑Anpassung mit Aspose.Tasks?**  
A: Die Bibliothek spiegelt die Möglichkeiten von Microsoft Project wider, sodass Sie praktisch alle Kalendereinstellungen anpassen können. Nur sehr alte Projektdatei‑Versionen können geringe Kompatibilitätsprobleme aufweisen.

**F: Kann ich das Kalender‑Management in bestehende Java‑Projekte integrieren?**  
A: Absolut. Fügen Sie einfach das Aspose.Tasks‑JAR zu Ihrem Build‑Pfad hinzu und verwenden Sie die hier gezeigten Code‑Muster.

**F: Unterstützt Aspose.Tasks neben dem Kalender‑Management weitere Projekt‑Management‑Funktionen?**  
A: Ja, es deckt Aufgaben, Ressourcen, Zuordnungen, Gliederungen, Basispläne und mehr ab – eine umfassende Lösung für Java‑basierte Projekt‑Automatisierung.

**F: Gibt es technischen Support für Entwickler, die Aspose.Tasks nutzen?**  
A: Ja, Aspose bietet dedizierte Foren, E‑Mail‑Support und umfangreiche Dokumentation für alle lizenzierten Nutzer.

## Fazit
Nachdem Sie diesem Leitfaden gefolgt sind, wissen Sie nun **wie man den Projektkalender** festlegt, **Kalenderarbeitszeiten anzeigt** und diese Funktionen in jede Java‑Anwendung mit Aspose.Tasks integriert. Das ermöglicht Ihnen, Zeitpläne automatisiert anzupassen, einheitliche Arbeitsrichtlinien durchzusetzen und leistungsfähigere Projekt‑Management‑Lösungen zu bauen.

---

**Zuletzt aktualisiert:** 2025-12-04  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung die neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}