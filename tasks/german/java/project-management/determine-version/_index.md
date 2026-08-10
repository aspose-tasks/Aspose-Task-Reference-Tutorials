---
date: 2026-05-31
description: Erfahren Sie, wie Sie die Projektversion abrufen und das zuletzt gespeicherte
  Datum aus MS Project‑Dateien mit Aspose.Tasks für Java ermitteln. Schritt‑für‑Schritt‑Anleitung
  mit Codebeispielen.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Projektversion bestimmen mit Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Wie man die Projektversion abruft – Aspose Tasks Java‑Tutorial
url: /de/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Projektversion ermittelt – Aspose Tasks Java Tutorial

In diesem **Aspose Tasks Java Tutorial** lernen Sie **wie man die Projektversion** einer Microsoft Project‑Datei ermittelt und außerdem, **wie man das Datum der letzten Speicherung** mit der Aspose.Tasks‑Bibliothek für Java abruft. Das Wissen um die Dateiversion und den Zeitstempel der Speicherung hilft, Kompatibilitätsprobleme zu vermeiden, Migrationsrichtlinien durchzusetzen und genaue Audit‑Logs zu führen. Wir gehen Schritt für Schritt vor – von der Umgebungseinrichtung bis zum Ausgeben von Version und Datum – sodass Sie diese Prüfung mit Vertrauen in jede Java‑Anwendung einbetten können.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Bestimmung der MS Project‑Dateiversion und des letzten Speicherdatums mit Aspose.Tasks für Java.  
- **Benötige ich Microsoft Project installiert?** Nein, Aspose.Tasks arbeitet unabhängig von Microsoft Project.  
- **Welche Dateiformate werden unterstützt?** XML‑basierte Project‑Dateien wie MPP und XML werden vollständig unterstützt.  
- **Wie lange dauert die Implementierung?** Ungefähr 5‑10 Minuten für einen einfachen Versions‑Check.  
- **Ist eine Lizenz erforderlich?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine kommerzielle Lizenz nötig.

## Was ist das Aspose Tasks Java Tutorial?
Das `Aspose.Tasks` Java‑Tutorial ist ein kompakter, praxisorientierter Leitfaden, der zeigt, wie man programmgesteuert mit Microsoft‑Project‑Daten interagiert. Es demonstriert das Lesen, Ändern und Analysieren von Projektinformationen, ohne dass Microsoft Project auf dem Server installiert sein muss. Zusätzlich werden das Laden von Dateien, der Zugriff auf Eigenschaften und das Speichern von Änderungen behandelt, sodass Entwickler Projekt‑Management‑Aufgaben effizient automatisieren können.

## Warum Aspose.Tasks zur Bestimmung der Projektversion verwenden?
Aspose.Tasks liefert **exakte Versions‑Metadaten** und **Zeitstempel der letzten Speicherung**, läuft auf jedem OS, das Java unterstützt, und verarbeitet Dateien mit bis zu **500 Seiten in unter 2 Sekunden** auf einer Standard‑2,5 GHz‑CPU. Damit ist es ideal für Batch‑Automatisierung und groß angelegte Migrationsszenarien.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – Version 8 oder neuer.  
2. **Aspose.Tasks for Java JAR** – herunterladen von der [Website](https://releases.aspose.com/tasks/java/) und dem Projekt‑Classpath hinzufügen.  
3. **MS Project‑Datei** – eine XML‑basierte Project‑Datei (z. B. `input.xml`), die Sie untersuchen möchten.  

> **Pro‑Tipp:** Legen Sie die Project‑Datei in einen eigenen `data`‑Ordner, um Pfade übersichtlich zu halten und versehentliche Überschreibungen zu vermeiden.

## Pakete importieren
Zuerst importieren Sie die wesentlichen Aspose.Tasks‑Klassen:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## So richten Sie das Projektverzeichnis ein
Um Ihre Projektdateien korrekt zu finden, erstellen Sie ein dediziertes Verzeichnis innerhalb Ihrer Anwendungsstruktur und speichern dort alle Eingabedateien. Das hält den Code sauber und verhindert pfadbezogene Fehler beim Laden von Dateien. Verwenden Sie einen klaren Variablennamen für den Verzeichnispfad, der absolut oder relativ zum Projekt‑Root sein kann.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Ersetzen Sie `"Your Data Directory"` durch den absoluten oder relativen Pfad, in dem `input.xml` liegt.

## So laden Sie das Projekt
`Project` ist das primäre Aspose.Tasks‑Objekt, das eine Microsoft Project‑Datei im Speicher repräsentiert und Ihnen Zugriff auf alle Projekteigenschaften und Sammlungen gibt. Nach dem Erzeugen der `Project`‑Instanz können Sie deren Felder abfragen, über Aufgaben iterieren oder Daten ändern, bevor Sie die Datei wieder auf die Festplatte schreiben.

```java
Project project = new Project(dataDir + "input.xml");
```

Falls Ihre Datei einen anderen Namen hat, passen Sie `"input.xml"` entsprechend an.

## So bestimmen Sie die Projektversion
`Prj.SAVE_VERSION` ist eine Eigenschaft, die die Versionsnummer von Microsoft Project angibt, das die Datei gespeichert hat. `Prj.LAST_SAVED` speichert Datum und Uhrzeit der letzten Speicherung. `Prj.SAVE_VERSION` liefert die numerische Version der Microsoft‑Project‑Anwendung (z. B. 12 für Project 2010). `Prj.LAST_SAVED` gibt das genaue Datum und die Uhrzeit des letzten Speichervorgangs zurück.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

Diese Werte ermöglichen es Ihnen, versionsspezifische Geschäftsregeln programmgesteuert durchzusetzen oder Audit‑Berichte zu erstellen.

## So zeigen Sie das Ergebnis an
Nachdem Sie Version und letztes Speicherdatum abgerufen haben, geben Sie sie typischerweise auf der Konsole oder in einer Log‑Datei aus. Verwenden Sie `System.out.println`, um die Werte anzuzeigen und das Datum bei Bedarf zu formatieren. Das bestätigt, dass die Extraktion erfolgreich war, und liefert sofortiges Feedback während der Entwicklung oder in automatisierten Skripten.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|---------|-------|--------|
| `NullPointerException` bei `project.get(...)` | Datei nicht gefunden oder falscher Pfad | `dataDir` und Dateinamen prüfen; für Tests einen absoluten Pfad verwenden. |
| Unerwartete Versionsnummer (z. B. 0) | Laden einer Nicht‑Project‑XML‑Datei | Sicherstellen, dass die Datei eine gültige Microsoft‑Project‑Datei (MPP/XML) ist. |
| Lizenz‑Ausnahme | Nutzung der Testversion ohne gültige Lizenz in der Produktion | Ihre Aspose.Tasks‑Lizenz anwenden (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Häufig gestellte Fragen

**Q:** Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?  
**A:** Ja, Aspose.Tasks unterstützt .NET, Java und C++ unter anderem.

**Q:** Eignet sich Aspose.Tasks für groß angelegte Projekte?  
**A:** Absolut; es kann Projekte mit mehreren hundert Seiten in Sekunden verarbeiten, ohne die gesamte Datei in den Speicher zu laden.

**Q:** Kann ich Projektdaten mit Aspose.Tasks anpassen?  
**A:** Ja, Sie können Aufgaben, Ressourcen, Kalender und jedes andere Projektelement über die API ändern.

**Q:** Benötigt Aspose.Tasks eine Installation von Microsoft Project?  
**A:** Nein, die Bibliothek arbeitet eigenständig und erfordert kein Microsoft Project auf dem Host‑System.

**Q:** Gibt es technischen Support für Aspose.Tasks?  
**A:** Ja, Sie erhalten Hilfe im Aspose.Tasks‑Forum [hier](https://forum.aspose.com/c/tasks/15).

**Zusätzliche Fragen & Antworten**

**Q:** Wie rufe ich andere Projekteigenschaften ab (z. B. Autor, Unternehmen)?  
**A:** Verwenden Sie `project.get(Prj.AUTHOR)` oder `project.get(Prj.COMPANY)` auf dieselbe Weise wie bei der Versionsabfrage.

**Q:** Kann ich die Version einer MPP‑(binären) Datei prüfen?  
**A:** Ja, Aspose.Tasks lädt `.mpp`‑Dateien direkt; die Eigenschaft `Prj.SAVE_VERSION` funktioniert auch für binäre Formate.

**Q:** Gibt es eine Möglichkeit, eine ältere Projektdatei programmgesteuert auf eine neuere Version zu aktualisieren?  
**A:** Laden Sie die ältere Datei und speichern Sie sie mit `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks schreibt die Datei standardmäßig im neuesten Format.

## Fazit
Sie haben nun **gelernt, wie man die Projektversion** und **das Datum der letzten Speicherung** aus MS‑Project‑Dateien mit Aspose.Tasks für Java ermittelt. Integrieren Sie diese Code‑Snippets in Automatisierungspipelines, Reporting‑Tools oder Migrations‑Utilities, um stets die genaue Project‑Version zu kennen, mit der Sie arbeiten.

---

**Zuletzt aktualisiert:** 2026-05-31  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
- [Read microsoft project database with Aspose.Tasks for Java](/tasks/java/project-data-reading/read-project-database/)
- [Save Project as Template, CSV, and Text with Aspose.Tasks for Java](/tasks/java/project-file-operations/save-csv-text-template/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}