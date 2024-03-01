---
title: Verwalten Sie die Eigenschaften des MS Project-Kalenders in Aspose.Tasks
linktitle: Kalendereigenschaften in Aspose.Tasks verwalten
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks MS Project-Kalendereigenschaften in Java verwalten. Dies bietet eine Schritt-für-Schritt-Anleitung für den Kalender in Ihren Java-Anwendungen.
type: docs
weight: 10
url: /de/java/calendars/properties/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie die Kalendereigenschaften von MS Project mit Aspose.Tasks für Java verwalten. Wenn Sie wissen, wie Sie Kalendereigenschaften bearbeiten, können Sie Projektzeitpläne effizient an spezifische Anforderungen anpassen.
## Voraussetzungen
Bevor Sie fortfahren, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### Installation des Java Development Kit (JDK).
Stellen Sie sicher, dass das Java Development Kit (JDK) auf Ihrem System installiert ist.
### Aspose.Tasks für Java-Bibliothek
 Laden Sie die Aspose.Tasks für Java-Bibliothek herunter und richten Sie sie ein[Download-Seite](https://releases.aspose.com/tasks/java/).

## Pakete importieren
Beginnen Sie mit dem Importieren der erforderlichen Pakete:
```java
import com.aspose.tasks.*;
```

## Schritt 1: Richten Sie das Datenverzeichnis ein
```java
String dataDir = "Your Data Directory";
```
 Ersetzen`"Your Data Directory"` mit dem Pfad zu Ihrem Datenverzeichnis.
## Schritt 2: Zeiteinheiten definieren
```java
long OneSec = 1000; // 1000 Millisekunden
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Hier definieren wir der Einfachheit halber Zeiteinheiten.
## Schritt 3: Projektdaten laden
```java
Project project = new Project(dataDir + "project.xml");
```
Laden Sie die MS Project-Daten aus der angegebenen XML-Datei.
## Schritt 4: Kalender durchlaufen
```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Zeigt an, ob es einen Basiskalender hat
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterieren Sie die Wochentage
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```
Diese Schleife durchläuft jeden Kalender im Projekt und zeigt seine Eigenschaften wie UID, Name, Basiskalender und Arbeitszeiten für jeden Tagestyp an.

## Abschluss
Durch Befolgen dieses Tutorials haben Sie gelernt, wie Sie MS Project-Kalendereigenschaften mit Aspose.Tasks für Java verwalten. Dieses Wissen versetzt Sie in die Lage, Projektpläne effektiv anzupassen und so die Übereinstimmung mit den Projektanforderungen sicherzustellen.
## FAQs
### F: Kann ich Kalendereigenschaften programmgesteuert mit Aspose.Tasks ändern?
A: Ja, Aspose.Tasks bietet umfassende APIs zur dynamischen Bearbeitung von Kalendereigenschaften in Java-Anwendungen.
### F: Gibt es Einschränkungen bei der Kalenderanpassung mit Aspose.Tasks?
A: Aspose.Tasks bietet umfassende Flexibilität bei der Kalenderverwaltung mit minimalen Einschränkungen bei den Anpassungsoptionen.
### F: Kann ich Kalenderverwaltungsfunktionen in bestehende Java-Projekte integrieren?
A: Auf jeden Fall! Sie können die Kalenderverwaltungsfunktionen von Aspose.Tasks nahtlos in Ihre Java-Projekte integrieren und so die Projektplanungsmöglichkeiten verbessern.
### F: Unterstützt Aspose.Tasks neben der Kalenderverwaltung auch andere Projektmanagementfunktionen?
A: Ja, Aspose.Tasks bietet umfangreiche Funktionalitäten zur Verwaltung von Aufgaben, Ressourcen und Projektstrukturen und ist damit eine umfassende Lösung für das Projektmanagement in Java.
### F: Ist technischer Support für Entwickler verfügbar, die Aspose.Tasks verwenden?
A: Ja, Entwickler können über das Aspose.Tasks-Forum auf technischen Support zugreifen und so Unterstützung bei Fragen oder Problemen während der Implementierung gewährleisten.