---
date: 2026-03-29
description: Erfahren Sie, wie Sie Schlüsselwörter festlegen und das Erstellungsdatum
  in einem MPP‑Projekt mit Aspose.Tasks für Java setzen. Schritt‑für‑Schritt‑Anleitung
  mit Codebeispielen.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man Schlüsselwörter in der MPP-Projektzusammenfassung mit Aspose.Tasks
  festlegt
url: /de/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Schlüsselwörter in der MPP-Projektzusammenfassung mit Aspose.Tasks festlegt

## Einführung
In diesem Tutorial erfahren Sie **wie man Schlüsselwörter festlegt** und weitere Zusammenfassungsinformationen für eine MPP‑Projektdatei mithilfe von Aspose.Tasks für Java. Egal, ob Sie Autorinformationen, Versionsnummern oder ein benutzerdefiniertes Erstellungsdatum einbetten müssen, führt Sie diese Anleitung Schritt für Schritt durch, inklusive sofort ausführbarem Code. Am Ende können Sie Schlüsselwörter festlegen, das Erstellungsdatum in Java setzen und die Daten aus der Datei wieder auslesen.

## Schnelle Antworten
- **Welche Bibliothek wird verwendet?** Aspose.Tasks für Java  
- **Hauptzweck?** Schlüsselwörter, Autorinformationen und Erstellungsdatum in einer MPP‑Datei festlegen  
- **Wie viele Code‑Schritte?** Drei einfache Codeblöcke (Initialisieren, Speichern, Lesen)  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich  
- **Unterstützte Java‑Version?** Java 8 und höher  

## Was bedeutet „wie man Schlüsselwörter festlegt“ in einer MPP‑Datei?
Schlüsselwörter sind Metadatenfelder, die in einer Microsoft Project (MPP)‑Datei gespeichert werden. Sie helfen, Projekte zu kategorisieren, ermöglichen schnelles Suchen und liefern kontextbezogene Informationen für nachgelagerte Werkzeuge. Aspose.Tasks stellt die Eigenschaft `Prj.KEYWORDS` bereit, wodurch das Schreiben oder Aktualisieren dieses Wertes programmgesteuert einfach wird.

## Warum Aspose.Tasks für Java verwenden, um Schlüsselwörter und Erstellungsdatum festzulegen?
* **Vollständige .MPP‑Kompatibilität** – funktioniert mit allen Project‑Formaten 2007‑2023.  
* **Kein COM‑ oder Office‑Installationsbedarf** – reines Java, ideal für serverseitige Umgebungen.  
* **Umfangreiche API** – neben Schlüsselwörtern können Sie Autor, Revision, Kommentare und Daten in einem Aufruf festlegen.  
* **Performance‑optimiert** – schnelles Lesen/Schreiben selbst bei großen Projektdateien.

## Voraussetzungen
1. **Java Development Kit (JDK)** – JDK 8 oder neuer installiert.  
2. **Aspose.Tasks für Java** – laden Sie das neueste JAR von [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans oder ein beliebiger Editor Ihrer Wahl.

## Pakete importieren
Zuerst importieren Sie die benötigten Klassen. Diese Importe geben Ihnen Zugriff auf das `Project`‑Objekt, die Aufzählung `Prj` für Zusammenfassungsfelder und die Aufzählung `SaveFileFormat` zum Speichern.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Schritt 1: Projekt einrichten und Zusammenfassungsinformationen definieren
Erstellen Sie eine `Project`‑Instanz und verwenden Sie anschließend die `set`‑Methode, um die gewünschten Metadaten zu schreiben. Beachten Sie, wie wir **die Schlüsselwörter festlegen** und **das Erstellungsdatum in Java setzen** mithilfe eines `Calendar`‑Objekts.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Schritt 2: Projektzusammenfassungsinformationen speichern
Nachdem Sie die Felder gefüllt haben, speichern Sie die Änderungen. Hier speichern wir das Projekt als XML zur einfachen Inspektion, Sie können es jedoch auch wieder als MPP speichern.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Schritt 3: Projektzusammenfassungsinformationen lesen
Um zu überprüfen, ob die Metadaten korrekt geschrieben wurden, laden Sie die Datei erneut und lesen jede Eigenschaft aus. Dieser Schritt zeigt, dass **wie man Schlüsselwörter festlegt** tatsächlich end‑to‑end funktioniert.

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
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| **NullPointerException bei `project.get(Prj.CREATION_DATE)`** | Der Kalender wurde vor dem Speichern nie gesetzt. | Stellen Sie sicher, dass Sie `project.set(Prj.CREATION_DATE, cal.getTime())` vor `save()` aufrufen. |
| **Schlüsselwörter werden nicht in der Microsoft Project UI angezeigt** | Die Datei wurde als XML gespeichert und direkt in Project geöffnet. | Speichern Sie zurück als MPP (`SaveFileFormat.MPP`) oder öffnen Sie das XML über *Import* in Project. |
| **Datumswerte durch Zeitzone verschoben** | Java `Date` enthält Zeitzoneninformationen. | Verwenden Sie `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))`, wenn Sie UTC-Daten benötigen. |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Tasks für Java mit anderen Java-Bibliotheken verwenden?**  
A: Ja, Aspose.Tasks für Java kann nahtlos mit anderen Java-Bibliotheken integriert werden, um Ihre Projektmanagement‑Funktionen zu erweitern.

**Q: Gibt es eine Testversion von Aspose.Tasks für Java?**  
A: Ja, Sie können eine kostenlose Testversion von [hier](https://releases.aspose.com/) herunterladen.

**Q: Wie häufig wird Aspose.Tasks für Java aktualisiert?**  
A: Aspose.Tasks für Java wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten Versionen von Java und Microsoft Project‑Dateien sicherzustellen.

**Q: Kann ich die Projektzusammenfassungsinformationen weiter anpassen?**  
A: Absolut, Aspose.Tasks für Java bietet umfangreiche Optionen zur Anpassung der Projektzusammenfassungsinformationen nach Ihren spezifischen Anforderungen.

**Q: Wo kann ich Unterstützung für Aspose.Tasks für Java erhalten?**  
A: Sie können Unterstützung im Aspose.Tasks Community‑Forum [hier](https://forum.aspose.com/c/tasks/15) erhalten.

---

**Letzte Aktualisierung:** 2026-03-29  
**Getestet mit:** Aspose.Tasks für Java 24.11 (zum Zeitpunkt des Schreibens die neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}