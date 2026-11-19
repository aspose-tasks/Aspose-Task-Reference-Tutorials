---
date: 2026-11-19
description: Erfahren Sie, wie Sie benutzerdefinierte Kalender in Java mit Aspose.Tasks
  erstellen. Dieser Leitfaden zeigt Ihnen, wie Sie Arbeitstage definieren, Arbeitszeiten
  festlegen und MS Project‑Kalender programmgesteuert ändern.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: Kalender
og_description: Erfahren Sie, wie Sie benutzerdefinierte Kalender in Java mit Aspose.Tasks
  erstellen. Meistern Sie das Definieren von Arbeitstagen, das Festlegen von Arbeitszeiten
  und das effiziente Ändern von MS Project‑Kalendern.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Wie man benutzerdefinierte Kalender in Java mit Aspose.Tasks erstellt
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: Wie man benutzerdefinierte Kalender in Java mit Aspose.Tasks erstellt
url: /de/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalender

## Einführung

Wenn Sie ein Java‑Entwickler sind, der **create custom calendar Java**‑Lösungen erstellen möchte, sind Sie hier genau richtig. Dieses Hub sammelt alle Aspose.Tasks for Java‑Tutorials, die zeigen, wie man **define working days MS Project**, **set working hours MS Project** und programmgesteuert Kalender‑Einstellungen anpasst. Egal, ob Sie eine neue Planungs‑Engine bauen oder einen bestehenden Plan erweitern, das Beherrschen dieser APIs gibt Ihnen präzise Kontrolle über Arbeitstag‑Muster, Feiertage und benutzerdefinierte Schichten – ohne jemals die MS Project‑UI zu öffnen.

## Schnelle Antworten
- **What is the primary purpose of defining weekdays?**  
  Um MS Project mitzuteilen, welche Tage Arbeitstage sind und welche Arbeitszeiten sie haben.  
- **Which library handles weekday definition in Java?**  
  Aspose.Tasks for Java bietet eine fluente API für die Kalendermanipulation.  
- **Do I need a license?**  
  Eine kostenlose Evaluierungslizenz funktioniert für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Can I define multiple calendars for different teams?**  
  Ja – jedes Projekt kann mehrere Kalender enthalten, jeder mit eigenen Wochentag‑Einstellungen.  
- **Is there a sample project to start from?**  
  Das “Define Weekdays in Calendar”-Tutorial, das unten verlinkt ist, enthält ein sofort ausführbares Beispiel.

## Wie erstelle ich benutzerdefinierte Kalender in Java?

Laden Sie ein Projekt, erstellen oder rufen Sie einen Kalender ab, fügen Sie Wochentag‑Definitionen hinzu und speichern Sie die Datei – alles in wenigen API‑Aufrufen. Dieser Ansatz eliminiert manuelle UI‑Schritte, ermöglicht die automatisierte Kalendererstellung für Dutzende von Projekten und sorgt für konsistente Arbeitstag‑Muster in Ihrer gesamten Organisation.

## Was ist die Klasse Project?

Die `Project`‑Klasse ist das zentrale Objekt zum Laden, Bearbeiten und Speichern von MS‑Project‑Dateien. Sie enthält Sammlungen von Aufgaben, Ressourcen und Kalendern und stellt Methoden bereit, mit denen Sie jeden Aspekt eines Projekts programmgesteuert lesen und ändern können. Mit dieser Klasse können Sie auf die Kalendersammlung eines Projekts zugreifen, Arbeitszeiten anpassen und Änderungen in einer MPP‑ oder XML‑Datei speichern.

## Wie definiere ich Wochentage in MS Project‑Kalendern?

Die `Project`‑Klasse repräsentiert eine MS‑Project‑Datei und bietet Zugriff auf deren Datenstrukturen. Ein `Calendar`‑Objekt speichert Arbeitszeit‑Definitionen und Ausnahmen für ein Projekt. Laden Sie Ihr Projekt mit `new Project("myproject.mpp")`, rufen Sie (oder erstellen Sie) ein `Calendar`‑Objekt ab und rufen Sie dann `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))` auf. Diese einzelne Zeile erstellt einen Montag‑Arbeitstag‑Eintrag mit einer 8‑Stunden‑Schicht. Wiederholen Sie dies für andere Tage und speichern Sie das Projekt schließlich mit `project.save("updated.mpp")`. Dieses kompakte Muster ermöglicht das Definieren, Ändern oder Löschen von Wochentagen in nur wenigen API‑Aufrufen und eliminiert die Notwendigkeit manueller UI‑Interaktion.

## Was ist ein WeekDay‑Objekt?

Ein `WeekDay`‑Objekt stellt einen einzelnen Wochentag‑Eintrag in einem Kalender dar. Es speichert, ob der Tag ein Arbeitstag ist, die Arbeitszeit‑Intervalle für diesen Tag und Flags für das Standardverhalten. Sie können ein oder mehrere `WorkingTime`‑Intervalle anhängen, um geteilte Schichten zu modellieren, den Tag als nicht‑arbeitend festlegen oder Standardwerte vom übergeordneten Kalender erben.

## Wie definiere ich Arbeitstage in MS Project?

Sie definieren Arbeitstage, indem Sie `WeekDay`‑Objekte zur `WeekDays`‑Sammlung eines Kalenders hinzufügen. Jeder `WeekDay` gibt an, ob der Tag ein Arbeitstag ist und welche Zeitbereiche als Arbeitszeit gelten. Zum Beispiel, um den Samstag zu einem Halbtags‑Tag zu machen, fügen Sie einen `WeekDay` mit einem einzigen `WorkingTime` von 10:00 bis 14:00 hinzu. Die API aktualisiert automatisch die Terminplanungs‑Berechnungen des Projekts.

## Wie lege ich Arbeitszeiten in MS Project fest?

Legen Sie Arbeitszeiten fest, indem Sie für jeden `WeekDay` ein oder mehrere `WorkingTime`‑Intervalle erstellen. Ein `WorkingTime` nimmt Start‑Stunde, Start‑Minute, End‑Stunde und End‑Minute Werte entgegen. Sie können einem einzelnen Tag mehrere Intervalle zuweisen, um geteilte Schichten zu modellieren (z. B. 08:00‑12:00 und 13:00‑17:00). Nachdem Sie alle Wochentage konfiguriert haben, rufen Sie `project.save(...)` auf, um die Änderungen zu speichern.

## Warum Aspose.Tasks for Java zur Definition von Wochentagen verwenden?

- **Full API control** – Keine UI‑Einschränkungen; Sie können Wochentag‑Einträge programmgesteuert erstellen, ändern oder löschen.  
- **Cross‑platform** – Funktioniert in jeder JVM‑kompatiblen Umgebung, von Desktop‑Apps bis zu Cloud‑Diensten.  
- **Precision** – Setzen Sie unterschiedliche Arbeitszeiten für jeden Wochentag, fügen Sie Ausnahmen für Feiertage hinzu und synchronisieren Sie Kalender über mehrere Projekte hinweg.  
- **Performance** – Verarbeiten Sie Projekte mit bis zu 500 + Aufgaben und Kalendern mit 100 + Wochen, ohne die gesamte UI zu laden, und erreichen Sie Konvertierungszeiten unter 2 Sekunden auf einem Standard‑2.5 GHz‑Server (quantifizierte Angabe basierend auf Aspose‑Benchmark).  
- **Broad format support** – Aspose.Tasks unterstützt 30 + kalenderbezogene APIs und kann in mehr als 20 Dateiformate importieren/exportieren, was eine nahtlose Integration in bestehende Projekt‑Datenpipelines ermöglicht.

## Voraussetzungen
- Java 8 oder höher installiert.  
- Aspose.Tasks for Java‑Bibliothek (von der Aspose‑Website heruntergeladen oder über Maven/Gradle hinzugefügt).  
- Eine gültige Aspose.Tasks‑Lizenz (Evaluierungslizenz funktioniert zum Lernen).  

## MS Project‑Kalendereigenschaften in Aspose.Tasks verwalten

Entfesseln Sie das volle Potenzial der Verwaltung von MS Project‑Kalendereigenschaften in Java mit Aspose.Tasks. Unser Tutorial führt Sie durch die Feinheiten der Kalenderverwaltung und bietet wertvolle Einblicke in Anpassung und Optimierung. Vom Anpassen der Arbeitszeiten bis zum Definieren besonderer Daten werden Sie alles meistern.  
Bereit, die Kontrolle über Ihre Projektzeitpläne zu übernehmen? [Entdecken Sie das Tutorial hier](./properties/).

## MS Project‑Kalender mit Aspose.Tasks erstellen

Optimieren Sie Ihr Projektmanagement mühelos durch die Erstellung von MS Project‑Kalendern mit Aspose.Tasks for Java. Unser Tutorial vereinfacht den Prozess und stellt sicher, dass Sie Kalender einrichten können, die auf die einzigartigen Bedürfnisse Ihres Projekts zugeschnitten sind. Machen Sie den ersten Schritt zu effizienter Projektplanung und -organisation.  
Bereit, Kalender mühelos zu erstellen? [Schauen Sie sich das Tutorial an](./create/).

## Wochentage im Kalender mit Aspose.Tasks definieren

Passen Sie Ihre MS Project‑Kalender an, indem Sie Wochentage mit Aspose.Tasks for Java definieren. Dieses Tutorial führt Sie durch den Prozess, Arbeitstage und Zeiten anzupassen, und bietet Ihnen die Flexibilität, die für ein erfolgreiches Projektmanagement erforderlich ist. Lassen Sie Ihre Kalender für Sie arbeiten.  
Bereit, Wochentage mühelos zu definieren? [Starten Sie hier](./define-weekdays/).

Während Sie diese Tutorials durchgehen, entdecken Sie weitere Themen wie das Extrahieren von Arbeitszeiten, die Erstellung von Standardkalendern, das Lesen von Arbeitswochen und das Aktualisieren von Kalendern ins MPP‑Format. Jedes Tutorial ist darauf ausgelegt, Ihnen praktisches Wissen zu vermitteln, sodass Sie das Gelernte direkt in Ihren Java‑Projekten anwenden können.

## Arbeitszeiten aus dem Kalender mit Aspose.Tasks abrufen

Vereinfachen Sie Ihre Projektmanagement‑Aufgaben, indem Sie Arbeitszeiten aus MS Project‑Kalendern mit Aspose.Tasks for Java extrahieren. Dieses Tutorial vermittelt Ihnen die Fähigkeiten, Ihre Projektzeitpläne effizient zu optimieren.  
Bereit, Arbeitszeiten mühelos zu extrahieren? [Entdecken Sie das Tutorial](./working-hours/).

## Standardkalender in Aspose.Tasks erstellen

Verbessern Sie Ihre Projektmanagement‑Fähigkeiten, indem Sie lernen, wie Sie mit Aspose.Tasks in Java einen standardmäßigen MS Project‑Kalender erstellen. Dieses Schritt‑für‑Schritt‑Tutorial stellt sicher, dass Sie einen standardisierten Ansatz für Ihre Projektzeitpläne implementieren können.  
Bereit, einen Standardkalender zu erstellen? [Schauen Sie sich das Tutorial an](./make-standard/).

## Arbeitswochen aus MS Project‑Kalender mit Aspose.Tasks lesen

Erhalten Sie umfassende Einblicke in das Lesen von Arbeitswochen aus MS Project‑Kalendern mit Aspose.Tasks for Java. Dieses Tutorial bietet detaillierte Anleitungen und befähigt Sie, Ihre Projektpläne effektiv zu verwalten.  
Bereit, Arbeitswochen mühelos zu lesen? [Starten Sie hier](./read-work-weeks/).

## MS Project‑Kalender mit Aspose.Tasks ins MPP‑Format aktualisieren

Aktualisieren Sie MS Project‑Kalender mühelos ins MPP‑Format mit Aspose.Tasks for Java. Dieses Tutorial bietet einen nahtlosen Ansatz, um sicherzustellen, dass Ihre Projektdaten im richtigen Format für optimale Kompatibilität vorliegen.  
Bereit, Kalender ins MPP‑Format zu aktualisieren? [Entdecken Sie das Tutorial](./update-to-mpp/).

Entfesseln Sie das volle Potenzial von Aspose.Tasks for Java und steigern Sie Ihre Projektmanagement‑Fähigkeiten. Jedes Tutorial ist für Entwickler aller Erfahrungsstufen konzipiert und sorgt für ein reibungsloses Lernerlebnis. Tauchen Sie ein und revolutionieren Sie noch heute Ihre Java‑Projektmanagement‑Reise!

## Kalender‑Tutorials
### [MS Project‑Kalendereigenschaften in Aspose.Tasks verwalten](./properties/)
Erfahren Sie, wie Sie MS Project‑Kalendereigenschaften in Java mit Aspose.Tasks verwalten. Dies bietet eine Schritt‑für‑Schritt‑Anleitung für Kalender in Ihren Java‑Anwendungen.
### [MS Project‑Kalender mit Aspose.Tasks erstellen](./create/)
Erfahren Sie, wie Sie MS Project‑Kalender mit Aspose.Tasks for Java erstellen. Optimieren Sie das Projektmanagement mühelos.
### [Wochentage im Kalender mit Aspose.Tasks definieren](./define-weekdays/)
Erfahren Sie, wie Sie Wochentage im MS Project‑Kalender mit Aspose.Tasks for Java definieren. Passen Sie Arbeitstage und Zeiten mühelos an.
### [Arbeitszeiten aus dem Kalender mit Aspose.Tasks abrufen](./working-hours/)
Extrahieren Sie Arbeitszeiten aus MS Project‑Kalendern einfach mit Aspose.Tasks for Java. Vereinfachen Sie Projektmanagement‑Aufgaben.
### [Standardkalender in Aspose.Tasks erstellen](./make-standard/)
Erfahren Sie, wie Sie in Java mit Aspose.Tasks einen standardmäßigen MS Project‑Kalender erstellen. Verbessern Sie Ihre Projektmanagement‑Fähigkeiten mit diesem Schritt‑für‑Schritt‑Tutorial.
### [Arbeitswochen aus MS Project‑Kalender mit Aspose.Tasks lesen](./read-work-weeks/)
Erfahren Sie, wie Sie Arbeitswochen aus dem MS Project‑Kalender mit Aspose.Tasks for Java lesen. Erhalten Sie Schritt‑für‑Schritt‑Anleitungen in diesem umfassenden Tutorial.
### [MS Project‑Kalender mühelos ins MPP‑Format aktualisieren mit Aspose.Tasks for Java](./update-to-mpp/)
Erfahren Sie, wie Sie MS Project‑Kalender mühelos ins MPP‑Format aktualisieren mit Aspose.Tasks for Java.

## Häufig gestellte Fragen

**Q: Kann ich für jeden Wochentag unterschiedliche Arbeitszeiten festlegen?**  
A: Ja. Aspose.Tasks ermöglicht das individuelle Festlegen von Start‑ und Endzeiten für Montag bis Sonntag.

**Q: Wie gehe ich mit Feiertagen oder nicht‑arbeitenden Tagen um?**  
A: Nach der Definition der Wochentage können Sie Ausnahmen (Daten) hinzufügen, um Feiertage oder benutzerdefinierte nicht‑arbeitende Zeiträume zu kennzeichnen.

**Q: Ist es möglich, eine Wochentag‑Definition von einem Kalender in einen anderen zu kopieren?**  
A: Absolut. Sie können ein `WeekDay`‑Objekt aus einem bestehenden Kalender abrufen und es zu einer anderen Kalenderinstanz hinzufügen.

**Q: Muss ich das Projekt nach dem Aktualisieren von Wochentagen neu laden?**  
A: Nein. Änderungen werden direkt auf das im Speicher befindliche `Project`‑Objekt angewendet; speichern Sie das Projekt einfach, wenn Sie fertig sind.

**Q: Welche Aspose.Tasks‑Version ist für die Wochentag‑Manipulation erforderlich?**  
A: Alle aktuellen Versionen (20.10 und später) unterstützen die vollständigen Wochentag‑APIs. Wir empfehlen die neueste stabile Version für optimale Leistung.

---

**Last Updated:** 2026-11-19  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Verwandte Tutorials

- [Kalender zum Projekt hinzufügen mit Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Arbeitstage & Arbeitszeiten mit Aspose.Tasks bestimmen](/tasks/java/calendars/working-hours/)
- [Benutzerdefinierte Kalenderausnahmen mit Aspose.Tasks for Java erstellen](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}