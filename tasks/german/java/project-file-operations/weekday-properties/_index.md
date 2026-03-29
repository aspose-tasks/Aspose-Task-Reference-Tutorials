---
date: 2026-03-29
description: Erfahren Sie, wie Sie die Tage pro Monat ändern und andere Wochentagseigenschaften
  in Aspose.Tasks für Java verwalten. Passen Sie den Wochenstart an, ändern Sie den
  Projektkalender und speichern Sie das Projekt als XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tage pro Monat ändern mit den Aspose.Tasks‑Wochentagseigenschaften
url: /de/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ändern der Tage pro Monat mit den Wochentagseigenschaften von Aspose.Tasks

## Einleitung
Aspose.Tasks für Java ermöglicht es Ihnen, **Tage pro Monat zu ändern** und andere Wochentagseinstellungen fein abzustimmen, ohne dass Microsoft Project installiert sein muss. Egal, ob Sie einen Projektkalender an einen nicht‑standardmäßigen Geschäftsjahr‑Monat anpassen oder einfach den Wochenstarttag ändern müssen, führt Sie dieses Tutorial durch die gängigsten Szenarien – Abrufen des aktuellen Wochenstarttags, Anpassen des Wochenstartdatums, Ändern des Projektkalenders und Speichern des Projekts als XML.

## Schnelle Antworten
- **Kann ich die Anzahl der Tage pro Monat ändern?** Ja, verwenden Sie `Prj.DAYS_PER_MONTH` im `Project`‑Objekt.  
- **Wie passe ich das Startdatum der Woche an?** Setzen Sie `Prj.WEEK_START_DAY` auf einen `DayType`‑Wert (z. B. `DayType.Monday`).  
- **Welches Format kann ich zum Exportieren des Projekts verwenden?** Das Beispiel speichert die Datei als XML mit `SaveFileFormat.Xml`.  
- **Ist für den Produktionseinsatz eine Lizenz erforderlich?** Eine gültige Aspose.Tasks‑Lizenz ist für den Einsatz außerhalb der Evaluation erforderlich.  
- **Welche IDEs werden unterstützt?** Jede Java‑IDE wie IntelliJ IDEA, Eclipse oder NetBeans funktioniert.

## Was bedeutet „Tage pro Monat ändern“ in Aspose.Tasks?
Das Ändern der Tage pro Monat bedeutet, die Eigenschaft `Prj.DAYS_PER_MONTH` einer `Project`‑Instanz zu aktualisieren. Diese Eigenschaft gibt der Engine an, wie viele Arbeitstage pro Monat berücksichtigt werden sollen, was sich direkt auf die Aufgabenplanung und Kostenberechnungen auswirkt.

## Warum Projektekalendereigenschaften ändern?
Die Anpassung des Projektkalenders – z. B. das Festlegen eines anderen Wochenstarttags oder das Ändern der Minuten pro Tag – hilft Ihnen:

- Zeitpläne an regionale Arbeitswochen anzupassen.  
- Nicht‑standardmäßige Arbeitsmuster zu modellieren (z. B. 4‑Tage‑Wochen).  
- Eine genaue Berichterstattung für Verträge sicherzustellen, die benutzerdefinierte Kalender verwenden.

## Voraussetzungen
- **Java Development Kit (JDK)** – Installieren Sie das neueste JDK von Oracle.  
- **Aspose.Tasks for Java Bibliothek** – Laden Sie sie von der offiziellen Seite [hier](https://releases.aspose.com/tasks/java/) herunter.  
- **IDE Ihrer Wahl** – IntelliJ IDEA, Eclipse oder NetBeans.

## Pakete importieren
Zuerst importieren Sie die wesentlichen Aspose.Tasks‑Klassen:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Schritt 1: Projektdatei laden
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Dies lädt eine vorhandene Microsoft‑Project‑Datei (`project.mpp`) aus dem von Ihnen angegebenen Ordner.

## Schritt 2: Wochentagseigenschaften anzeigen
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Hier rufen wir die aktuellen Wochentagseinstellungen ab und geben sie aus, einschließlich des **Wochenstarttags** und der **Tage pro Monat**.

## Schritt 3: Wochentagseigenschaften festlegen
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
In diesem Schritt **ändern wir die Tage pro Monat** auf 24, setzen den Wochenstart auf Montag und passen die Minuten pro Tag/Woche an. Dies zeigt, wie man programmgesteuert **Projektkalender**‑Werte **ändert**.

## Schritt 4: Projekt speichern
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Das geänderte Projekt wird im **Projekt als XML speichern**‑Format gespeichert, was für die Integration mit anderen Tools oder für versionierte Speicherung praktisch ist.

## Schritt 5: Ergebnis anzeigen
```java
System.out.println("Process completed Successfully");
```
Eine einfache Bestätigung, dass die Vorgänge ohne Fehler abgeschlossen wurden.

## Wie man das Startdatum der Woche anpasst
Wenn Ihre Organisation einen Sonntag‑zuerst‑Kalender verwendet, ersetzen Sie `DayType.Monday` durch `DayType.Sunday`. Die gleiche Eigenschaft (`Prj.WEEK_START_DAY`) wird verwendet, wodurch die Änderung unkompliziert ist.

## Wie man den Wochenstarttag abruft
Sie können jederzeit `project.get(Prj.WEEK_START_DAY)` aufrufen, um **Informationen zum Wochenstarttag** abzurufen, wie in Schritt 2 gezeigt.

## Wie man den Projektkalender ändert
Neben dem Wochenstarttag können Sie auch `Prj.MINUTES_PER_DAY` und `Prj.MINUTES_PER_WEEK` anpassen, um benutzerdefinierte Arbeitszeiten oder Schichtmuster abzubilden.

## Häufige Probleme und Lösungen
- **Falscher DayType‑Wert** – Stellen Sie sicher, dass Sie das `DayType`‑Enum verwenden (z. B. `DayType.Monday`).  
- **Dateipfad‑Fehler** – Prüfen Sie, dass `dataDir` mit dem passenden Dateiseparator endet (`/` oder `\`).  
- **Lizenz nicht gesetzt** – Wenn Sie Lizenzwarnungen sehen, registrieren Sie Ihre Aspose.Tasks‑Lizenz, bevor Sie das `Project`‑Objekt erstellen.

## Häufig gestellte Fragen

**Q: Kann Aspose.Tasks für Java komplexe Projektstrukturen verarbeiten?**  
A: Ja, Aspose.Tasks für Java bietet umfassende Unterstützung zur einfachen Handhabung komplexer Projektstrukturen.

**Q: Ist Aspose.Tasks für Java mit verschiedenen Versionen von Microsoft Project‑Dateien kompatibel?**  
A: Absolut, Aspose.Tasks für Java unterstützt verschiedene Versionen von Microsoft Project‑Dateien und gewährleistet Kompatibilität über Plattformen hinweg.

**Q: Kann ich Aspose.Tasks für Java in meine bestehenden Java‑Anwendungen integrieren?**  
A: Ja, Aspose.Tasks für Java bietet nahtlose Integrationsmöglichkeiten, sodass Sie Ihre Java‑Anwendungen mit leistungsstarken Projektmanagement‑Funktionen erweitern können.

**Q: Bietet Aspose.Tasks für Java Dokumentation und Support?**  
A: Ja, Sie können umfangreiche Dokumentation und Community‑Support für Aspose.Tasks für Java auf ihrer [Website](https://releases.aspose.com/) abrufen.

**Q: Gibt es eine kostenlose Testversion von Aspose.Tasks für Java?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java von ihrer [Website](https://reference.aspose.com/tasks/java/) herunterladen, um die Funktionen vor dem Kauf zu testen.

---

**Zuletzt aktualisiert:** 2026-03-29  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}