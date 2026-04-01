---
date: 2026-04-01
description: Erfahren Sie, wie Sie XML speichern, das Geschäftsjahr festlegen und
  MPP mit Aspose.Tasks für Java in XML konvertieren. Schritt‑für‑Schritt‑Anleitung
  mit Codebeispielen.
keywords:
- how to save xml
- how to set fiscal
- convert mpp to xml
linktitle: Wie man XML speichert und das Geschäftsjahr in Aspose.Tasks verwaltet
second_title: Aspose.Tasks Java API
title: Wie man XML speichert und das Fiskaljahr in Aspose.Tasks verwaltet
url: /de/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man XML speichert & das Geschäftsjahr in Aspose.Tasks

## Einführung
Wenn Sie **how to save xml** Dateien benötigen, die aus Microsoft Project‑Daten generiert wurden, bietet Aspose.Tasks für Java eine saubere, lizenz‑freie Möglichkeit, dies zu tun. In diesem Tutorial führen wir Sie durch das Laden einer MPP‑Datei, das Anzeigen von Geschäftsjahrsinformationen, das Festlegen von Geschäftsjahreseigenschaften und schließlich das **how to save xml** Ergebnis. Sie sehen außerdem, wie man **how to set fiscal** Details und **how to convert mpp** Dateien verarbeitet, ohne Microsoft Project zu öffnen.

## Schnelle Antworten
- **Was bedeutet „manage fiscal year“ in Aspose.Tasks?** Es ermöglicht Ihnen, den Startmonat des Geschäftsjahres festzulegen und die Geschäftsjahresnummerierung für ein Projekt zu aktivieren.  
- **Wie legt man den Startmonat des Geschäftsjahres fest?** Verwenden Sie die Eigenschaft `Prj.FY_START_DATE` mit einem `Month`‑Enum‑Wert (z. B. `Month.JULY`).  
- **Kann ich eine MPP‑Datei laden?** Ja, erstellen Sie einfach eine `Project`‑Instanz mit dem Pfad zur *.mpp*‑Datei.  
- **Wie konvertiert man MPP zu XML?** Rufen Sie `project.save(..., SaveFileFormat.Xml)` auf, nachdem Sie die gewünschten Eigenschaften gesetzt haben.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  

## Was bedeutet „manage fiscal year“ in Projektdateien?
Die Verwaltung des Geschäftsjahres bedeutet, den Kalender zu konfigurieren, dem Ihr Projekt für die Finanzberichterstattung folgt. Dies beinhaltet das Festlegen des Startmonats des Geschäftsjahres und optional das Aktivieren der Geschäftsjahresnummerierung, die beeinflusst, wie Daten in Berichten berechnet und angezeigt werden.

## Warum Aspose.Tasks für die Handhabung des Geschäftsjahres verwenden?
- **Kein Microsoft Project erforderlich** – Arbeiten Sie direkt in Java mit Projektdateien.  
- **Vollständige Kontrolle** – Legen Sie den Start des Geschäftsjahres fest, aktivieren Sie die Nummerierung und konvertieren Sie Formate programmgesteuert.  
- **Robuste API** – Zuverlässige Verarbeitung großer MPP‑Dateien und nahtloser XML‑Export.  

## Voraussetzungen
1. Java Development Kit (JDK) auf Ihrem System installiert.  
2. Aspose.Tasks für Java JAR – laden Sie es von [hier](https://releases.aspose.com/tasks/java/) herunter und fügen Sie es dem Klassenpfad Ihres Projekts hinzu.

## Pakete importieren
Um zu beginnen, importieren Sie die erforderlichen Klassen in Ihrer Java‑Quelldatei:
```java
import com.aspose.tasks.*;
```

## Wie man eine MPP‑Datei lädt und Geschäftsjahrsinformationen anzeigt
Im Folgenden zerlegen wir den Prozess in klare, nummerierte Schritte.

### Schritt 1: Projektdatei laden
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Hier **laden wir eine MPP‑Datei** (`project.mpp`) aus dem angegebenen Verzeichnis. Dies ist der erste Schritt bei jeder geschäftsjahresbezogenen Manipulation.

### Schritt 2: Geschäftsjahreseigenschaften anzeigen
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
Die Eigenschaften `Prj.FY_START_DATE` und `Prj.FISCAL_YEAR_START` ermöglichen es Ihnen, **display fiscal year** Details anzuzeigen und die Frage „Wie ist die aktuelle Geschäftsjahreskonfiguration?“ zu beantworten.

### Schritt 3: Start des Geschäftsjahres festlegen und Nummerierung aktivieren
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
In diesem Schritt konfigurieren wir **how to set fiscal** Einstellungen:
- `Month.JULY` definiert den Startmonat des Geschäftsjahres.  
- `NullableBool(true)` aktiviert die Geschäftsjahresnummerierung.  
- Schließlich wird das Projekt **converted MPP to XML** mittels `SaveFileFormat.Xml`.

### Schritt 4: Vorgang bestätigen
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
Eine einfache Konsolennachricht bestätigt, dass das Geschäftsjahr konfiguriert und die Datei gespeichert wurde.

## Warum das wichtig ist
Das Speichern des Projekts als XML liefert Ihnen eine portable, textbasierte Darstellung, die leicht geparst, versioniert oder in andere Systeme integriert werden kann. Wenn die Geschäftsjahreseinstellungen korrekt sind, stimmen nachgelagerte Finanzberichte und Dashboards mit den Buchungsperioden Ihrer Organisation überein.

## Häufige Anwendungsfälle
- **Finanzberichterstattung** – Projektpläne mit einem Geschäftskalender abgleichen, bevor sie in BI‑Tools exportiert werden.  
- **Datenmigration** – Legacy‑*.mpp*-Dateien in XML konvertieren, um sie in cloudbasierte Projektmanagement‑Plattformen zu importieren.  
- **Automatisierte Audits** – Programmgesteuert prüfen, dass jedes Projekt den korrekten Startmonat des Geschäftsjahres verwendet.

## Tipps zur Fehlerbehebung & häufige Fallstricke
| Problem | Lösung |
|---------|--------|
| **Falscher Monatswert** | Stellen Sie sicher, dass Sie das `Month`‑Enum verwenden (z. B. `Month.JANUARY`). |
| **Datei nicht gefunden** | Überprüfen Sie, dass `dataDir` auf den richtigen Ordner zeigt und der Dateiname übereinstimmt. |
| **Speichern fehlgeschlagen** | Prüfen Sie die Schreibberechtigungen im Zielverzeichnis und ob das `SaveFileFormat` unterstützt wird. |
| **Geschäftsjahr nicht im XML wiedergegeben** | Öffnen Sie nach dem Speichern das XML und prüfen Sie, dass die Knoten `<FiscalYearStart>` und `<FiscalYearNumbering>` die erwarteten Werte enthalten. |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Tasks für Java verwenden, um andere Projekteigenschaften zu manipulieren?**  
A: Ja, Aspose.Tasks bietet umfassende Funktionen, um verschiedene Projekteigenschaften über die Geschäftsjahreseinstellungen hinaus zu verwalten.

**Q: Ist Aspose.Tasks für Java mit verschiedenen Projektdateiformaten kompatibel?**  
A: Ja, es unterstützt eine Vielzahl von Formaten, darunter MPP, XML und andere.

**Q: Wie kann ich Unterstützung erhalten, wenn ich beim Einsatz von Aspose.Tasks für Java auf Probleme stoße?**  
A: Sie können Hilfe von der Aspose.Tasks‑Community im [Forum](https://forum.aspose.com/c/tasks/15) erhalten oder sich direkt an deren Support‑Team wenden.

**Q: Bietet Aspose.Tasks eine kostenlose Testversion an?**  
A: Ja, Sie können die kostenlose Testversion von Aspose.Tasks über [hier](https://releases.aspose.com/) erhalten.

**Q: Wo kann ich eine Lizenz für Aspose.Tasks für Java erwerben?**  
A: Sie können eine Lizenz für Aspose.Tasks für Java über [hier](https://purchase.aspose.com/buy) erwerben.

## Fazit
Die Verwaltung von Geschäftsjahreseigenschaften in Aspose.Tasks für Java ist unkompliziert. Wenn Sie die obigen Schritte befolgen, können Sie **how to save xml**, **load mpp file**, **display fiscal year**, **set fiscal year** und **convert mpp to xml** mit Zuversicht durchführen. Nutzen Sie diese Techniken, um Ihre Projektpläne mit dem Finanzkalender Ihrer Organisation abzustimmen und portable XML‑Darstellungen für nachgelagerte Verarbeitungen zu erstellen.

---

**Zuletzt aktualisiert:** 2026-04-01  
**Getestet mit:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}