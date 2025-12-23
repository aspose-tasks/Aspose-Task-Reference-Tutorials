---
date: 2025-12-23
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java eine MPP‑Zusammenfassung
  erstellen und den Projektautor aktualisieren. Projektinformationen mühelos festlegen
  und abrufen.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man eine MPP‑Zusammenfassung erstellt und den Projektautor mit Aspose.Tasks
  aktualisiert
url: /de/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP-Projektsummary in Aspose.Tasks schreiben

## Einführung
In diesem Tutorial **erstellen Sie MPP‑Summary‑Informationen** für eine Microsoft‑Project‑Datei und lernen, wie Sie **Projekt‑Autor**‑Details mit der Aspose.Tasks‑Bibliothek für Java **aktualisieren**. Egal, ob Sie ein Projekt‑Management‑Tool bauen oder Berichte automatisieren – das programmgesteuerte Steuern von Summary‑Eigenschaften spart Zeit und sorgt für Konsistenz über Ihre Projekte hinweg.

## Schnelle Antworten
- **Was bedeutet „create MPP summary“?** Es bedeutet, die hochrangigen Projekteigenschaften (author, revision, keywords usw.) zu setzen, die im Dialog „Project Summary Information“ von Microsoft Project angezeigt werden.  
- **Welche Bibliothek übernimmt das?** Aspose.Tasks für Java bietet eine fluente API zum Lesen und Schreiben dieser Eigenschaften.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar, aber für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich den Autor nach dem Speichern der Datei ändern?** Ja – Sie können **project author** aktualisieren, indem Sie `project.set(Prj.AUTHOR, "New Author")` aufrufen und die Datei anschließend erneut speichern.  
- **Welche Dateiformate werden unterstützt?** Sowohl MPP als auch XML (SaveFileFormat.Xml) werden vollständig unterstützt.

## Was ist „create MPP summary“?
Das Erstellen eines MPP‑Summary bedeutet, die Metadaten des Projekts zu befüllen – Autor, Revisionsnummer, Schlüsselwörter, Kommentare, Erstellungs‑ und Druckdatum. Diese Metadaten werden im Record **Project Summary Information** gespeichert und im **File → Info**‑Bereich von Microsoft Project angezeigt.

## Warum den Projekt‑Autor aktualisieren?
Die korrekte Angabe des **project author** ist wichtig für Audit‑Trails, Zusammenarbeit und Reporting. Wenn mehrere Teammitglieder beitragen, müssen Sie möglicherweise **project author** aktualisieren, um die neuesten Änderungen widerzuspiegeln oder die Arbeit korrekt zuzuordnen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK) auf Ihrem Rechner installiert.  
2. Aspose.Tasks für Java – laden Sie es von [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. Eine IDE wie IntelliJ IDEA, Eclipse oder NetBeans.

## Pakete importieren
Zunächst importieren Sie die notwendigen Pakete in Ihre Java‑Klasse:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Schritt 1: Projekt einrichten und Summary‑Informationen definieren
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
Im obigen Code **erstellen Sie MPP‑summary‑Felder** wie author, revision und keywords. Sie können später **project author** aktualisieren, indem Sie `project.set(Prj.AUTHOR, "New Name")` aufrufen.

## Schritt 2: Projekt‑Summary‑Informationen speichern
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Durch das Speichern des Projekts werden alle definierten Summary‑Daten persistent geschrieben.

## Schritt 3: Projekt‑Summary‑Informationen lesen
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Dieses Snippet zeigt, wie Sie die Summary‑Informationen **wieder auslesen** und damit bestätigen, dass die **create MPP summary**‑Operation erfolgreich war.

## Häufige Probleme und Lösungen
- **Null‑Werte beim Lesen:** Stellen Sie sicher, dass das Projekt erfolgreich gespeichert wurde, bevor Sie es erneut laden. Prüfen Sie Dateipfade und Berechtigungen.  
- **Unterschiede bei der Datumsformatierung:** `project.get(Prj.CREATION_DATE)` liefert ein `java.util.Date`. Verwenden Sie `SimpleDateFormat`, wenn Sie ein benutzerdefiniertes Anzeigeformat benötigen.  
- **Lizenz nicht gesetzt:** Ohne gültige Lizenz läuft Aspose.Tasks im Evaluationsmodus und kann ein Wasserzeichen einbetten. Registrieren Sie Ihre Lizenz früh im Code.

## Häufig gestellte Fragen
**F: Kann ich Aspose.Tasks für Java mit anderen Java‑Bibliotheken verwenden?**  
A: Ja, Aspose.Tasks für Java lässt sich nahtlos in andere Java‑Bibliotheken integrieren, um Ihre Projekt‑Management‑Funktionen zu erweitern.

**F: Gibt es eine Testversion von Aspose.Tasks für Java?**  
A: Ja, Sie können eine kostenlose Testversion von [hier](https://releases.aspose.com/) herunterladen.

**F: Wie häufig wird Aspose.Tasks für Java aktualisiert?**  
A: Aspose.Tasks für Java wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten Versionen von Java und Microsoft‑Project‑Dateien sicherzustellen.

**F: Kann ich die Projekt‑Summary‑Informationen weiter anpassen?**  
A: Absolut, Aspose.Tasks für Java bietet umfangreiche Optionen zur Anpassung der Projekt‑Summary‑Informationen nach Ihren spezifischen Anforderungen.

**F: Wo bekomme ich Support für Aspose.Tasks für Java?**  
A: Sie erhalten Support im Aspose.Tasks‑Community‑Forum [hier](https://forum.aspose.com/c/tasks/15).

## Fazit
In diesem Tutorial haben wir gezeigt, wie Sie **MPP‑summary‑Daten** erstellen, **project author** aktualisieren und diese Änderungen mit Aspose.Tasks für Java verifizieren. Durch die Automatisierung dieser Schritte erhalten Sie volle Kontrolle über Projektdaten, machen Ihre Anwendungen robuster und Ihre Projektberichte genauer.

---

**Zuletzt aktualisiert:** 2025-12-23  
**Getestet mit:** Aspose.Tasks für Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}