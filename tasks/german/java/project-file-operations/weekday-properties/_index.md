---
date: 2025-12-23
description: Erfahren Sie, wie Sie Aspose.Tasks Java verwenden, um den Projektzeitplan
  zu aktualisieren, den Wochenstarttag festzulegen, die Tage pro Monat zu ändern und
  den Projektkalender effizient anzupassen.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Verwaltung von Wochentagseigenschaften
url: /de/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Verwaltung von Wochentagseigenschaften

## Einführung
Aspose.Tasks for Java (aspose tasks java) ist eine robuste API, die Java‑Entwicklern ermöglicht, mit Microsoft Project‑Dateien zu arbeiten, ohne dass Microsoft Project installiert sein muss. In diesem Tutorial lernen Sie, wie Sie **eine MPP‑Datei laden**, **den Wochenstarttag festlegen**, **die Tage pro Monat ändern** und anderweitig **den Projektkalender anpassen** – alles wesentliche Schritte, um einen Projektzeitplan zu aktualisieren. Am Ende können Sie Wochentagseigenschaften programmgesteuert anpassen und die Änderungen im gewünschten Format speichern.

## Schnelle Antworten
- **Was ist die primäre Klasse zur Projektverwaltung?** `Project` aus der Aspose.Tasks‑Bibliothek.  
- **Wie ändere ich den Wochenstarttag?** Verwenden Sie `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **Kann ich eine vorhandene .mpp‑Datei laden?** Ja – instanziieren Sie `Project` mit dem Dateipfad.  
- **Welche Methode speichert das Projekt als XML?** `project.save(path, SaveFileFormat.Xml)`.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht für die Evaluierung; für die Produktion ist eine Lizenz erforderlich.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java Development Kit (JDK)** – die neueste Version installiert.  
- **Aspose.Tasks for Java library** – laden Sie sie [hier](https://releases.aspose.com/tasks/java/) herunter.  
- **Eine IDE** wie IntelliJ IDEA, Eclipse oder NetBeans.  

## Pakete importieren
Um zu beginnen, importieren Sie die wesentlichen Aspose.Tasks‑Klassen:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Now let’s walk through each step of managing weekday properties.

## Schritt 1: MPP‑Datei laden
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Hier **laden wir eine vorhandene .mpp‑Datei** (`load mpp file`), um ihre Kalendereinstellungen zu prüfen und zu ändern.*

## Schritt 2: Aktuelle Wochentagseigenschaften anzeigen
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Dieser Code gibt den aktuellen **Wochenstarttag**, **Tage pro Monat**, **Minuten pro Tag** und **Minuten pro Woche** aus – die Kernelemente, die Sie häufig benötigen, um den **Projektkalender anzupassen**.

## Schritt 3: Neue Wochentagseigenschaften festlegen
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
In diesem Schritt **setzen wir den Wochenstarttag** auf Montag, **ändern die Tage pro Monat** auf 24 und passen die täglichen sowie wöchentlichen Minutenzahlen an. Diese Einstellungen sind typisch, wenn Sie den **Projektzeitplan** an einen nicht‑standardmäßigen Arbeitskalender anpassen müssen.

## Schritt 4: Aktualisiertes Projekt speichern
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Das modifizierte Projekt wird als XML‑Datei gespeichert, was das Teilen oder den Import in andere Werkzeuge erleichtert.

## Schritt 5: Vorgang bestätigen
```java
System.out.println("Process completed Successfully");
```
Eine einfache Konsolennachricht informiert Sie darüber, dass der Workflow ohne Fehler abgeschlossen wurde.

## Häufige Probleme & Tipps
- **Falscher Dateipfad** – Stellen Sie sicher, dass `dataDir` mit einem Schrägstrich endet oder verwenden Sie `Paths.get(...)` für plattformunabhängige Pfade.  
- **Lizenz nicht gesetzt** – Rufen Sie in einer Produktionsumgebung `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` auf, bevor Sie `Project` erstellen.  
- **Unerwarteter Wochenstarttag** – Stellen Sie sicher, dass Sie den korrekten `DayType`‑Enum‑Wert verwenden (z. B. `DayType.Sunday`).  

## Häufig gestellte Fragen

**F: Kann Aspose.Tasks for Java komplexe Projektstrukturen verarbeiten?**  
A: Ja, Aspose.Tasks for Java bietet umfassende Unterstützung zur einfachen Handhabung komplexer Projektstrukturen.

**F: Ist Aspose.Tasks for Java mit verschiedenen Versionen von Microsoft Project‑Dateien kompatibel?**  
A: Absolut, Aspose.Tasks for Java unterstützt verschiedene Versionen von Microsoft Project‑Dateien und gewährleistet damit Kompatibilität über Plattformen hinweg.

**F: Kann ich Aspose.Tasks for Java in meine bestehenden Java‑Anwendungen integrieren?**  
A: Ja, Aspose.Tasks for Java bietet nahtlose Integrationsmöglichkeiten, sodass Sie Ihre Java‑Anwendungen mit leistungsstarken Projektmanagement‑Funktionen erweitern können.

**F: Stellt Aspose.Tasks for Java Dokumentation und Support bereit?**  
A: Ja, Sie können umfangreiche Dokumentation und Community‑Support für Aspose.Tasks for Java auf ihrer [Website](https://releases.aspose.com/) abrufen.

**F: Gibt es eine kostenlose Testversion von Aspose.Tasks for Java?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks for Java von ihrer [Website](https://reference.aspose.com/tasks/java/) herunterladen, um die Funktionen vor einem Kauf zu erkunden.

---

**Zuletzt aktualisiert:** 2025-12-23  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}