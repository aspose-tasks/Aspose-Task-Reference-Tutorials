---
date: 2025-12-04
description: Erfahren Sie, wie Sie Währungseigenschaften in Java aus MS Project‑Dateien
  mit Aspose.Tasks für Java auslesen. Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung,
  um Währungscode, Symbol, Dezimalstellen und Position programmgesteuert zu extrahieren.
language: de
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Währungs‑Eigenschaften in Java mit Aspose.Tasks‑Projekten lesen
url: /java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Währungseigenschaften in Java mit Aspose.Tasks-Projekten lesen

## Einleitung
In diesem Tutorial **lesen Sie Währungseigenschaften in Java** aus Microsoft‑Project‑Dateien mithilfe der Aspose.Tasks für Java API. Aspose.Tasks ermöglicht die Arbeit mit .mpp‑Dateien, ohne dass Microsoft Project installiert sein muss, und ist damit ideal für automatisierte Berichte, Datenmigration oder die Integration in Java‑basierte Unternehmensanwendungen. Am Ende dieses Leitfadens können Sie den Währungscode, das Symbol, die Anzahl der Dezimalstellen und die Symbolposition direkt aus einer Projektdatei extrahieren.

## Schnelle Antworten
- **Was bedeutet “read currency properties java”?** Es bezieht sich auf das Abrufen von währungsbezogenen Metadaten (Code, Symbol, Stellen, Position) aus einer MS Project‑Datei mittels Java‑Code.  
- **Benötige ich eine Lizenz, um dies auszuprobieren?** Eine kostenlose Testversion von Aspose.Tasks ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche JDK‑Version wird benötigt?** Java 8 oder höher.  
- **Kann ich die Währungseinstellungen nach dem Auslesen ändern?** Ja, Aspose.Tasks erlaubt sowohl Lese‑ als auch Schreiboperationen an den Währungseigenschaften.  
- **Ist dies mit allen .mpp‑Versionen kompatibel?** Die API unterstützt Dateien, die mit Microsoft Project 2003‑2021 erstellt wurden.

## Was ist read currency properties java?
Das Lesen von Währungseigenschaften in Java bedeutet, auf die Projekteinstellungen zuzugreifen, die festlegen, wie Geldbeträge in einer Microsoft‑Project‑Datei angezeigt werden. Diese Einstellungen umfassen den ISO‑Währungscode (z. B. **USD**), das Symbol (**$**), die Anzahl der Dezimalstellen und ob das Symbol vor oder nach dem Betrag erscheint.

## Warum read currency properties java mit Aspose.Tasks?
- **Keine Installation von Microsoft Project erforderlich** – die API funktioniert auf jeder Plattform, die Java unterstützt.  
- **Schnelle In‑Prozess‑Extraktion** – ideal für die Stapelverarbeitung großer Mengen von Projektdateien.  
- **Vollständige Kontrolle** – Sie können die abgerufenen Werte mit benutzerdefinierten Berichten kombinieren oder in ERP‑Systeme integrieren.  
- **Versionsübergreifende Unterstützung** – funktioniert mit .mpp‑Dateien von Project 2003 bis zur neuesten 2021‑Version.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – Java 8 oder neuer installiert und in Ihrem `PATH` konfiguriert.  
2. **Aspose.Tasks for Java JAR** – laden Sie die neueste Bibliothek von [hier](https://releases.aspose.com/tasks/java/) herunter und fügen Sie sie dem Klassenpfad Ihres Projekts hinzu.  

## Pakete importieren
Beginnen Sie damit, den für die Projektmanipulation erforderlichen Aspose.Tasks‑Namespace zu importieren:

```java
import com.aspose.tasks.*;
```

## Schritt 1: Projektverzeichnis einrichten
Definieren Sie den Ordner, der die zu analysierende `.mpp`‑Datei enthält. Das Speichern des Pfads in einer Variablen macht den Code wiederverwendbar:

```java
String dataDir = "Your Data Directory";
```

*Ersetzen Sie `"Your Data Directory"` durch den absoluten oder relativen Pfad zu dem Ordner, in dem `project.mpp` liegt.*

## Schritt 2: Projektleser-Instanz erstellen
Laden Sie die Microsoft Project‑Datei in ein `Project`‑Objekt. Dieses Objekt gibt Ihnen Zugriff auf alle Projekteigenschaften, einschließlich der Währungseinstellungen:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Falls Ihre Datei einen anderen Namen hat, ändern Sie `"project.mpp"` entsprechend.*

## Schritt 3: Währungseigenschaften anzeigen
Rufen Sie nun jedes Währungsattribut mit der `Prj`‑Aufzählung ab und geben Sie die Ergebnisse in der Konsole aus. Die API liefert Objekte, die Sie zur Anzeige in Zeichenketten umwandeln können:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Was Sie sehen werden:**  
- **Currency Code** – ISO‑4217‑Code wie `USD`, `EUR`, `JPY`.  
- **Currency Digits** – in der Regel `2` für die meisten Währungen, `0` für den japanischen Yen.  
- **Currency Symbol** – das in Berichten angezeigte Zeichen (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` für **vor** dem Betrag, `1` für **nach** dem Betrag.

## Schritt 4: Prozessabschluss
Signalisieren Sie, dass die Extraktion erfolgreich abgeschlossen wurde. Diese einfache Meldung ist hilfreich, wenn der Code als Teil eines größeren Batch‑Jobs ausgeführt wird:

```java
System.out.println("Process completed Successfully");
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| **FileNotFoundException** | Der Pfad `dataDir` ist falsch oder der Dateiname ist falsch geschrieben. | Überprüfen Sie den Verzeichnis‑String und stellen Sie sicher, dass die `.mpp`‑Datei am angegebenen Ort existiert. |
| **NullPointerException on `project.get(...)`** | Die Projektdatei enthält keine Währungsinformationen (unwahrscheinlich) oder der Eigenschaftsschlüssel ist falsch. | Verwenden Sie `project.contains(Prj.CURRENCY_CODE)`, um die Existenz vor dem Lesen zu prüfen. |
| **LicenseException** | Ausführung ohne gültige Aspose.Tasks‑Lizenz in einer Produktionsumgebung. | Laden Sie eine Lizenzdatei mit `License license = new License(); license.setLicense("Aspose.Tasks.lic");` bevor Sie das `Project`‑Objekt erstellen. |

## Häufig gestellte Fragen

**Q: Ist Aspose.Tasks mit allen Versionen von Microsoft Project kompatibel?**  
A: Aspose.Tasks unterstützt .mpp‑Dateien, die von Microsoft Project 2003‑2021 erzeugt wurden, und deckt sowohl ältere als auch die neuesten Formate ab.

**Q: Kann ich Währungseigenschaften mit Aspose.Tasks ändern?**  
A: Ja, Sie können sowohl lesen als auch schreiben. Verwenden Sie `project.set(Prj.CURRENCY_CODE, "EUR");` und speichern Sie anschließend das Projekt.

**Q: Eignet sich Aspose.Tasks für den kommerziellen Einsatz?**  
A: Absolut. Es handelt sich um eine kommerzielle Bibliothek; Sie können eine Lizenz [hier](https://purchase.aspose.com/buy) erwerben.

**Q: Bietet Aspose.Tasks eine kostenlose Testversion an?**  
A: Ja, eine voll funktionsfähige Testversion ist von [hier](https://releases.aspose.com/) verfügbar.

**Q: Wo kann ich Hilfe oder Support für Aspose.Tasks erhalten?**  
A: Das offizielle Aspose.Tasks‑Forum ist die beste Anlaufstelle – besuchen Sie es [hier](https://forum.aspose.com/c/tasks/15).

## Fazit
Sie haben nun gelernt, wie Sie **Währungseigenschaften in Java lesen** aus einer MS Project‑Datei mithilfe von Aspose.Tasks für Java extrahieren. Diese Fähigkeit ermöglicht es Ihnen, Währungs‑Metadaten in benutzerdefinierte Berichte, Finanzanalysen oder Integrationspipelines einzubinden, ohne Microsoft Project selbst zu benötigen. Experimentieren Sie gern mit dem Ändern der Eigenschaften oder kombinieren Sie diese Daten mit anderen Projekteigenschaften, um umfassendere Lösungen zu erstellen.

---

**Zuletzt aktualisiert:** 2025-12-04  
**Getestet mit:** Aspose.Tasks for Java 24.12 (zum Zeitpunkt der Erstellung aktuell)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}