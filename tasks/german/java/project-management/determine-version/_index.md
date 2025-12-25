---
date: 2025-12-25
description: Entdecken Sie dieses Aspose Tasks Java‑Tutorial, um zu lernen, wie man
  die Projektversion von MS‑Project‑Dateien ermittelt. Schritt‑für‑Schritt‑Anleitung
  mit Codebeispielen.
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Aspose Tasks Java‑Tutorial: Bestimmen der MS‑Project-Version'
url: /de/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java Tutorial: Bestimmen der MS Project-Version

## Einführung
In diesem **aspose tasks java tutorial** erfahren Sie, wie Sie programmgesteuert die Version einer Microsoft‑Project‑Datei mithilfe der Aspose.Tasks‑Bibliothek für Java ermitteln können. Das Wissen um die Dateiversion hilft Ihnen, Kompatibilitätsprobleme zu bewältigen, Migrationsrichtlinien durchzusetzen oder einfach zu protokollieren, welche Project‑Version die Datei erstellt hat. Wir führen Sie Schritt für Schritt durch den gesamten Prozess – von der Einrichtung der Umgebung bis zum Ausgeben der Versions‑ und zuletzt‑gespeicherten‑Datum‑Informationen – sodass Sie diese Prüfung problemlos in jede Java‑Anwendung integrieren können.

## Schnelle Antworten
- **Was behandelt dieses Tutorial?** Bestimmung der MS‑Project‑Dateiversion mit Aspose.Tasks für Java.  
- **Benötige ich Microsoft Project installiert?** Nein, Aspose.Tasks arbeitet eigenständig.  
- **Welche Dateiformate werden unterstützt?** XML‑basierte Project‑Dateien (MPP, XML usw.).  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten für eine Basis‑Prüfung.  
- **Ist eine Lizenz erforderlich?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine Lizenz nötig.

## Was ist Aspose Tasks Java Tutorial?
Ein **aspose tasks java tutorial** bietet praxisnahe Anleitungen zur Nutzung der Aspose.Tasks‑API in Java‑Projekten. Es zeigt, wie Sie Microsoft‑Project‑Daten lesen, ändern und analysieren können, ohne Microsoft Project selbst zu benötigen.

## Warum Aspose.Tasks zur Bestimmung der Projektversion verwenden?
- **Keine Abhängigkeit von Microsoft Project** – ideal für serverseitige Automatisierung.  
- **Genaues Versions‑Metadaten** – ruft die exakten Felder SAVE_VERSION und LAST_SAVED ab.  
- **Plattformübergreifend** – funktioniert auf jedem Betriebssystem, das Java unterstützt.  
- **Hohe Leistung** – leichtgewichtiges Parsen, geeignet für Batch‑Verarbeitung.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – ein aktuelles JDK (8 oder höher).  
2. **Aspose.Tasks for Java JAR** – laden Sie es von der [Website](https://releases.aspose.com/tasks/java/) herunter und fügen Sie es dem Klassenpfad Ihres Projekts hinzu.  
3. **MS Project‑Datei** – eine XML‑basierte Project‑Datei (z. B. `input.xml`), die Sie untersuchen möchten.  

> **Pro‑Tipp:** Legen Sie die Project‑Datei in einem eigenen `data`‑Ordner ab, um die Pfadangaben zu vereinfachen.

## Pakete importieren
Importieren Sie zunächst die wesentlichen Aspose.Tasks‑Klassen:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Schritt 1: Projektverzeichnis festlegen
Definieren Sie den Ordner, der Ihre Project‑Datei enthält.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Ersetzen Sie `"Your Data Directory"` durch den absoluten oder relativen Pfad, in dem sich `input.xml` befindet.

## Schritt 2: Projekt laden
Erzeugen Sie eine `Project`‑Instanz, indem Sie die XML‑Datei laden.

```java
Project project = new Project(dataDir + "input.xml");
```

Falls Ihre Datei einen anderen Namen hat, passen Sie `"input.xml"` entsprechend an.

## Schritt 3: Projektversion bestimmen
Rufen Sie die Versionsinformationen und den Zeitstempel des letzten Speichervorgangs ab.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

Die Eigenschaft `Prj.SAVE_VERSION` gibt die Microsoft‑Project‑Version an, mit der die Datei gespeichert wurde (z. B. 12 für Project 2010). `Prj.LAST_SAVED` liefert Datum/Uhrzeit des letzten Speicherns.

## Schritt 4: Ergebnis anzeigen
Signalisiert den erfolgreichen Abschluss der Versionsprüfung.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|---------|----------|--------|
| `NullPointerException` bei `project.get(...)` | Datei nicht gefunden oder falscher Pfad | `dataDir` und Dateinamen prüfen; für Tests absoluten Pfad verwenden. |
| Unerwartete Versionsnummer (z. B. 0) | Laden einer nicht‑Project‑XML‑Datei | Sicherstellen, dass die Datei eine gültige Microsoft‑Project‑Datei (MPP/XML) ist. |
| Lizenz‑Ausnahme | Nutzung der Testversion ohne gültige Lizenz in der Produktion | Ihre Aspose.Tasks‑Lizenz anwenden (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Häufig gestellte Fragen

### Q: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?
A: Ja, Aspose.Tasks unterstützt mehrere Sprachen, darunter .NET, Java und C++.

### Q: Ist Aspose.Tasks für groß angelegte Projekte geeignet?
A: Absolut, Aspose.Tasks ist darauf ausgelegt, Projekte jeder Größe problemlos zu verarbeiten.

### Q: Kann ich Projektdaten mit Aspose.Tasks anpassen?
A: Ja, Sie können Projektdaten manipulieren, Aufgaben, Ressourcen und vieles mehr mit Aspose.Tasks ändern.

### Q: Benötigt Aspose.Tasks eine Installation von Microsoft Project?
A: Nein, Aspose.Tasks arbeitet eigenständig und erfordert keine Installation von Microsoft Project.

### Q: Gibt es technischen Support für Aspose.Tasks?
A: Ja, Sie erhalten technischen Support im Aspose.Tasks‑Forum unter [hier](https://forum.aspose.com/c/tasks/15).

### Weitere Fragen & Antworten

**Q: Wie rufe ich andere Projekteigenschaften ab (z. B. Autor, Unternehmen)?**  
A: Verwenden Sie `project.get(Prj.AUTHOR)` bzw. `project.get(Prj.COMPANY)` analog zum Versionsbeispiel.

**Q: Kann ich die Version einer MPP‑Datei (binäres Format) prüfen?**  
A: Ja, Aspose.Tasks kann `.mpp`‑Dateien direkt laden; die gleiche Eigenschaft `Prj.SAVE_VERSION` funktioniert.

**Q: Gibt es eine Möglichkeit, eine ältere Projektdatei programmgesteuert auf eine neuere Version zu aktualisieren?**  
A: Laden Sie die ältere Datei und speichern Sie sie anschließend mit `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks schreibt standardmäßig im neuesten Format.

## Fazit
Sie haben nun ein kompaktes **aspose tasks java tutorial** abgeschlossen, das **zeigt, wie man die Projektversion** von MS‑Project‑Dateien mithilfe von Aspose.Tasks für Java bestimmt. Integrieren Sie dieses Snippet in größere Automatisierungs‑Workflows, Reporting‑Tools oder Migrations‑Utilities, um stets die genaue Project‑Version zu kennen, mit der Sie arbeiten.

---

**Zuletzt aktualisiert:** 2025-12-25  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}