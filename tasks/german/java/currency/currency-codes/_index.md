---
date: 2026-02-10
description: Erfahren Sie, wie Sie Währungscodes aus MS Project‑Dateien mit Aspose.Tasks
  für Java abrufen – der schnelle Weg, den Java‑Entwicklern benötigten Währungscode
  zu erhalten.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man die Währung aus MS Project mit Aspose.Tasks abruft
url: /de/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Währung aus MS Project mit Aspise.Tasks abruft

## Einführung
Willkommen! In diesem Tutorial entdecken Sie **wie man die Währung abruft** Codes aus einer MS Project‑Datei mithilfe der Aspose.Tasks Java API. Egal, ob Sie mehrwährungsige Finanzberichte erstellen, Projekte aus verschiedenen Regionen konsolidieren oder einfach die korrekten Währungssymbole für die Weiterverarbeitung benötigen – dieser Leitfaden führt Sie Schritt für Schritt von der Einrichtung Ihrer Umgebung bis zum programmgesteuerten Extrahieren des Währungscodes. Am Ende können Sie MS Project‑Dateien lesen und den **get currency code java** Aufruf verwenden, um den ISO‑Währungsidentifikator zu erhalten.

## Schnelle Antworten
- **Was macht die API?** Sie liest MS Project‑Dateien und stellt Eigenschaften wie den Währungscode bereit.  
- **Welche Sprache wird verwendet?** Java, über die Aspose.Tasks‑Bibliothek für Java.  
- **Brauche ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich den Code in einer Zeile abrufen?** Ja—`prj.get(Prj.CURRENCY_CODE)` gibt den Währungscode‑String zurück.  
- **Ist es mit allen Project‑Versionen kompatibel?** Aspose.Tasks unterstützt sowohl ältere (MPP) als auch neuere (XML, XER) Formate.

## Was ist **read ms project file**?
Das Lesen einer MS‑Project‑Datei bedeutet, programmgesteuert ein *.mpp* (oder ein anderes unterstütztes) Projektdokument zu öffnen und auf seine Datenstrukturen – Aufgaben, Ressourcen, Kalender und finanzielle Einstellungen – zuzugreifen, ohne manuell mit Microsoft Project zu interagieren.

## Warum Aspose.Tasks zum **read msproject**‑Dateien verwenden?
- **Vollständige Formatunterstützung** – funktioniert mit Dateien von Project 98 bis zu den neuesten Office‑Versionen.  
- **Keine COM‑ oder Office‑Installation erforderlich** – reines Java, ideal für serverseitige Automatisierung.  
- **Umfangreiche API** – bietet direkten Zugriff auf Eigenschaften wie `Prj.CURRENCY_CODE` und ermöglicht es Ihnen, **wie man die Währung abruft** Informationen sofort zu erhalten.  
- **Performance** – leichtgewichtiges Parsen, ideal für die Stapelverarbeitung vieler Projekte.

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

### Java Development Kit (JDK) installiert
Stellen Sie sicher, dass ein aktuelles JDK auf Ihrem Rechner verfügbar ist. Sie können die neueste JDK‑Version von [hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) herunterladen und installieren.

### Aspose.Tasks für Java‑Bibliothek
Laden Sie die Aspose.Tasks für Java‑Bibliothek herunter und richten Sie sie ein. Detaillierte Dokumentation und die neuesten Binärdateien sind [hier](https://reference.aspose.com/tasks/java/) verfügbar.

## Pakete importieren
Um loszulegen, importieren wir die notwendigen Pakete in Ihrem Java‑Projekt:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis einrichten
Definieren Sie den Ordner, der Ihre *.mpp*-Datei enthält. Passen Sie den Pfad an Ihre Umgebung an.
```java
String dataDir = "Your Data Directory";
```

### Schritt 2: Projektdatei laden
Erstellen Sie eine `Project`‑Instanz, indem Sie die MS‑Project‑Datei laden. Dies ist der Punkt, an dem Sie **read msproject**‑Daten in den Speicher laden.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Schritt 3: Währungscode abrufen
Jetzt, wo das Projekt geladen ist, können Sie **wie man die Währung abruft** Informationen mit einem einzigen Aufruf erhalten. Dies demonstriert die Verwendung von **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Die Ausgabe ist der dreibuchstabige ISO‑Währungscode (z. B. `USD`, `EUR`, `GBP`), den das Projekt verwendet.

### Schritt 4: Wie man den Währungscode in Java abruft (Zusätzlicher Kontext)
Wenn Sie den Wert für die spätere Verwendung speichern müssen, weisen Sie ihn einfach einer Variablen zu:

*Kein zusätzlicher Code‑Block erforderlich* – behalten Sie einfach den von `prj.get(Prj.CURRENCY_CODE)` zurückgegebenen String und übergeben Sie ihn an einen beliebigen Finanzdienst, Reporting‑Engine oder UI‑Komponente.

### Schritt 5: (Optional) Den Währungscode verwenden
Möglicherweise möchten Sie den abgerufenen Code an anderer Stelle einsetzen – z. B. Kostenwerte in einem benutzerdefinierten Bericht formatieren oder ihn an eine Finanz‑API übergeben. Typische Szenarien umfassen:

- **Berichtserstellung** – den Code vor die Kostenspalten setzen (`USD 1.200`).  
- **API‑Integration** – den ISO‑Code an Zahlungs‑Gateways senden, die einen Währungsbezeichner benötigen.  
- **Datenkonsolidierung** – mehrere Projekte nach Währung gruppieren für Portfolio‑Analysen.

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|-------|--------|-----|
| **Null‑Ausgabe** | Die Projektdatei definiert keine Währung (Standard ist leer). | Setzen Sie die Währung in Microsoft Project oder weisen Sie sie vor dem Lesen über `prj.set(Prj.CURRENCY_CODE, "USD");` zu. |
| **Datei nicht gefunden** | Falscher `dataDir`‑Pfad. | Überprüfen Sie den Pfad und stellen Sie sicher, dass der Dateiname exakt übereinstimmt, einschließlich Groß‑/Kleinschreibung. |
| **Nicht unterstützte Dateiversion** | Sehr alte oder beschädigte *.mpp*-Datei. | Verwenden Sie die neueste Aspose.Tasks‑Version oder konvertieren Sie die Datei zuerst in ein neueres Format in Microsoft Project. |

## Häufig gestellte Fragen

**Q: Kann Aspose.Tasks komplexe Projektstrukturen verarbeiten?**  
A: Ja, die API kann mehrstufige Aufgabenhierarchien, Ressourcengruppen und benutzerdefinierte Felder problemlos lesen und manipulieren.

**Q: Ist Aspose.Tasks mit verschiedenen Versionen von MS‑Project‑Dateien kompatibel?**  
A: Absolut. Es unterstützt MPP, XML, XER und andere Formate über viele Microsoft‑Project‑Versionen hinweg.

**Q: Bietet Aspose.Tasks Dokumentation und Support?**  
A: Umfassende Dokumentation, Code‑Beispiele und dedizierter Support sind auf der Aspose‑Website verfügbar.

**Q: Kann ich Aspose.Tasks vor dem Kauf testen?**  
A: Eine kostenlose Testversion wird angeboten, damit Sie alle Funktionen, einschließlich des Lesens von Währungscodes, evaluieren können.

**Q: Wo kann ich temporäre Lizenzen für Aspose.Tasks erhalten?**  
A: Temporäre Lizenzen können von der [Website](https://purchase.aspose.com/temporary-license/) für kurzfristige Evaluierung bezogen werden.

---

**Zuletzt aktualisiert:** 2026-02-10  
**Getestet mit:** Aspose.Tasks for Java (neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}