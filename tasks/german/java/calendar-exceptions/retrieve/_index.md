---
title: Kalenderausnahmen mit Aspose.Tasks abrufen
linktitle: Kalenderausnahmen mit Aspose.Tasks abrufen
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java Kalenderausnahmen aus MS Project abrufen. Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
weight: 13
url: /de/java/calendar-exceptions/retrieve/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalenderausnahmen mit Aspose.Tasks abrufen

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.Tasks-Bibliothek für Java Kalenderausnahmen aus MS Project abrufen. Aspose.Tasks ist ein leistungsstarkes Tool, mit dem Entwickler Microsoft Project-Dateien programmgesteuert bearbeiten können. Wir führen Sie Schritt für Schritt durch den Prozess und unterteilen jedes Beispiel zum leichteren Verständnis in mehrere Schritte.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
2.  Aspose.Tasks für Java: Laden Sie Aspose.Tasks für Java herunter und installieren Sie es von[Hier](https://releases.aspose.com/tasks/java/).
3. Integrierte Entwicklungsumgebung (IDE): Sie können jede IDE Ihrer Wahl verwenden, beispielsweise IntelliJ IDEA oder Eclipse.

## Pakete importieren
Zuerst müssen Sie die notwendigen Pakete importieren, um mit Aspose.Tasks arbeiten zu können:
```java
import com.aspose.tasks.*;
```
## Schritt 1: Richten Sie Ihr Datenverzeichnis ein
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Data Directory";
```
 Stellen Sie sicher, dass Sie es ersetzen`"Your Data Directory"` mit dem Pfad zu Ihrem Verzeichnis, das die MS Project-Datei enthält.
## Schritt 2: MS Project-Datei laden
```java
Project project = new Project(dataDir + "project.mpp");
```
 Diese Zeile initialisiert eine neue`Project` Objekt durch Laden der durch den Pfad angegebenen MS Project-Datei.
## Schritt 3: Kalenderausnahmen abrufen
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
Hier durchlaufen wir jeden Kalender im Projekt und dann jede Kalenderausnahme innerhalb dieses Kalenders. Wir drucken das Start- und Enddatum jeder Ausnahme aus.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für Java Kalenderausnahmen aus MS Project abruft. Wenn Sie diese einfachen Schritte befolgen, können Sie diese Funktionalität nahtlos in Ihre Java-Anwendungen integrieren.
## Häufig gestellte Fragen
### Kann Aspose.Tasks verschiedene Versionen von MS Project-Dateien verarbeiten?
Ja, Aspose.Tasks unterstützt verschiedene Versionen von MS Project-Dateien, einschließlich der Formate MPP, MPT und XML.
### Gibt es eine kostenlose Testversion für Aspose.Tasks?
 Ja, Sie können eine kostenlose Testversion von Aspose.Tasks herunterladen unter[Hier](https://releases.aspose.com/).
### Wo finde ich Dokumentation für Aspose.Tasks für Java?
 Sie können sich auf die Dokumentation beziehen[Hier](https://reference.aspose.com/tasks/java/).
### Wie kann ich Unterstützung für Aspose.Tasks erhalten?
 Unterstützung erhalten Sie im Community-Forum[Hier](https://forum.aspose.com/c/tasks/15).
### Gibt es eine Option für temporäre Lizenzen für Aspose.Tasks?
 Ja, Sie können temporäre Lizenzen erhalten von[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
