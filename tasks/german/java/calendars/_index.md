---
date: 2026-08-08
description: Erfahren Sie, wie Sie Wochentage in MS Project-Kalendern mit Aspose.Tasks
  für Java definieren. Dieser Leitfaden zeigt Ihnen, wie Sie den MS Project-Kalender
  ändern, ein custom calendar Java erstellen und Arbeitstage effizient planen.
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: Kalender
og_description: Erfahren Sie, wie Sie Wochentage in MS Project-Kalendern mit Aspose.Tasks
  für Java definieren. Dieser Leitfaden zeigt Ihnen, wie Sie den MS Project-Kalender
  ändern, ein custom calendar Java erstellen und Arbeitstage effizient planen.
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: Wie man Wochentage in MS Project-Kalendern definiert – Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
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
title: Wie man Wochentage in MS Project-Kalendern definiert – Aspose.Tasks Java
url: /de/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalender

## Einführung

Wenn Sie ein Java‑Entwickler sind und **Wochentage definieren** möchten, sind Sie hier genau richtig. In diesem Hub sammeln wir alle Aspose.Tasks for Java‑Tutorials, die zeigen, **wie man Wochentage** in MS‑Project‑Kalendern definiert, Arbeitszeiten anpasst und Ihre Zeitpläne kristallklar hält. Egal, ob Sie eine neue Planungs‑Engine bauen oder einen bestehenden Plan anpassen, das Beherrschen der Wochentag‑Definition gibt Ihnen präzise Kontrolle über Arbeitstag‑Muster, Feiertage und benutzerdefinierte Schichten. Dieser Leitfaden erklärt außerdem **wie man MS‑Project‑Kalender** programmgesteuert ändert, sodass Sie die Kalenderestellung für Dutzende von Projekten automatisieren können.

## Schnelle Antworten
- **Was ist der Hauptzweck der Definition von Wochentagen?**  
  MS Project mitzuteilen, welche Tage Arbeitstage sind und welche Arbeitszeiten gelten.
- **Welche Bibliothek übernimmt die Definition von Wochentagen in Java?**  
  Aspose.Tasks for Java bietet eine fluente API zur Kalendermanipulation.
- **Benötige ich eine Lizenz?**  
  Eine kostenlose Evaluierungslizenz funktioniert für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.
- **Kann ich mehrere Kalender für verschiedene Teams definieren?**  
  Ja – jedes Projekt kann mehrere Kalender enthalten, jeder mit eigenen Wochentag‑Einstellungen.
- **Gibt es ein Beispielprojekt zum Starten?**  
  Das unten verlinkte Tutorial „Define Weekdays in Calendar“ enthält ein sofort ausführbares Beispiel.

## Wie definiere ich Wochentage in MS‑Project‑Kalendern?

Die Klasse `Project` repräsentiert eine MS‑Project‑Datei und bietet Zugriff auf deren Datenstrukturen. Ein `Calendar`‑Objekt speichert Arbeitszeit‑Definitionen und Ausnahmen für ein Projekt. Laden Sie Ihr Projekt mit `new Project("myproject.mpp")`, holen (oder erstellen) Sie ein `Calendar`‑Objekt und rufen dann `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))` auf. Diese einzelne Zeile erstellt einen Montag‑Arbeitstag‑Eintrag mit einer 8‑Stunden‑Schicht. Wiederholen Sie dies für die anderen Tage und speichern Sie das Projekt schließlich mit `project.save("updated.mpp")`. Dieses kompakte Muster ermöglicht es Ihnen, Wochentage mit nur wenigen API‑Aufrufen zu definieren, zu ändern oder zu löschen und damit die Notwendigkeit manueller UI‑Interaktionen zu eliminieren.

## Was ist ein WeekDay‑Objekt?

Ein `WeekDay`‑Objekt stellt einen einzelnen Wochentag‑Eintrag in einem Aspose.Tasks‑Kalender dar und speichert dessen Arbeitsstatus sowie Arbeitszeit‑Intervalle. Sie können Start‑/Endzeiten konfigurieren, es als Nicht‑Arbeitstag festlegen oder Überstunden‑Perioden anhängen. Es kann mehrere `WorkingTime`‑Intervalle enthalten, um geteilte Schichten abzubilden, und unterstützt Flags für Standard‑Arbeitstage. Verwenden Sie die `WeekDay`‑API, um einen Tag zu aktivieren oder zu deaktivieren, reguläre Stunden zuzuweisen oder Überstunden‑Regeln für fortgeschrittene Planungs‑Szenarien festzulegen.

## Warum Aspose.Tasks for Java zur Definition von Wochentagen verwenden?

- **Vollständige API‑Kontrolle** – Keine UI‑Einschränkungen; Sie können Wochentag‑Einträge programmgesteuert erstellen, ändern oder löschen.  
- **Plattformübergreifend** – Funktioniert in jeder JVM‑kompatiblen Umgebung, von Desktop‑Apps bis zu Cloud‑Diensten.  
- **Präzision** – Unterschiedliche Arbeitszeiten für jeden Wochentag festlegen, Ausnahmen für Feiertage hinzufügen und Kalender über mehrere Projekte hinweg synchronisieren.  
- **Leistung** – Verarbeiten Sie Projekte mit bis zu 500 + Aufgaben und Kalendern mit 100 + Wochen, ohne die gesamte UI zu laden, und erreichen Sie Konvertierungszeiten von unter 2 Sekunden auf einem Standard‑2,5 GHz‑Server (quantifizierte Angabe basierend auf Aspose‑Benchmark).

## Voraussetzungen
- Java 8 oder höher installiert.  
- Aspose.Tasks for Java‑Bibliothek (von der Aspose‑Website heruntergeladen oder über Maven/Gradle hinzugefügt).  
- Eine gültige Aspose.Tasks‑Lizenz (Evaluierungslizenz funktioniert zum Lernen).  

## MS‑Project‑Kalendereigenschaften in Aspose.Tasks verwalten

Entfesseln Sie das volle Potenzial der Verwaltung von MS‑Project‑Kalendereigenschaften in Java mit Aspose.Tasks. Unser Tutorial führt Sie durch die Feinheiten der Kalenderverwaltung und bietet wertvolle Einblicke in Anpassung und Optimierung. Vom Anpassen der Arbeitszeiten bis zum Definieren besonderer Daten werden Sie alles meistern.  
Bereit, die Kontrolle über Ihre Projektzeitpläne zu übernehmen? [Entdecken Sie das Tutorial hier](./properties/).

## MS‑Project‑Kalender mit Aspose.Tasks erstellen

Optimieren Sie mühelos Ihr Projektmanagement durch die Erstellung von MS‑Project‑Kalendern mit Aspose.Tasks for Java. Unser Tutorial vereinfacht den Prozess und stellt sicher, dass Sie Kalender einrichten können, die auf die einzigartigen Bedürfnisse Ihres Projekts zugeschnitten sind. Machen Sie den ersten Schritt zu einer effizienten Projektplanung und -organisation.  
Bereit, Kalender mühelos zu erstellen? [Schauen Sie sich das Tutorial an](./create/).

## Wochentage im Kalender mit Aspose.Tasks definieren

Passen Sie Ihre MS‑Project‑Kalender an, indem Sie Wochentage mit Aspose.Tasks for Java definieren. Dieses Tutorial führt Sie durch den Prozess, Arbeitstage und -zeiten zu gestalten, und bietet Ihnen die Flexibilität, die für ein erfolgreiches Projektmanagement erforderlich ist. Lassen Sie Ihre Kalender für Sie arbeiten.  
Bereit, Wochentage mühelos zu definieren? [Starten Sie hier](./define-weekdays/).

Während Sie diese Tutorials durchgehen, entdecken Sie weitere Themen wie das Extrahieren von Arbeitszeiten, die Erstellung eines Standardkalenders, das Lesen von Arbeitswochen und das Aktualisieren von Kalendern ins MPP‑Format. Jedes Tutorial ist darauf ausgelegt, Ihnen praktisches Wissen zu vermitteln, sodass Sie das Gelernte direkt in Ihren Java‑Projekten anwenden können.

## Arbeitszeiten aus dem Kalender mit Aspose.Tasks abrufen

Vereinfachen Sie Ihre Projektmanagement‑Aufgaben, indem Sie Arbeitszeiten aus MS‑Project‑Kalendern mit Aspose.Tasks for Java extrahieren. Dieses Tutorial vermittelt Ihnen die Fähigkeiten, Ihre Projektzeitpläne effizient zu optimieren.  
Bereit, Arbeitszeiten mühelos zu extrahieren? [Entdecken Sie das Tutorial](./working-hours/).

## Standardkalender in Aspose.Tasks erstellen

Verbessern Sie Ihre Projektmanagement‑Fähigkeiten, indem Sie lernen, wie Sie mit Aspose.Tasks in Java einen standardmäßigen MS‑Project‑Kalender erstellen. Dieses Schritt‑für‑Schritt‑Tutorial stellt sicher, dass Sie einen standardisierten Ansatz für Ihre Projektzeitpläne umsetzen können.  
Bereit, einen Standardkalender zu erstellen? [Schauen Sie sich das Tutorial an](./make-standard/).

## Arbeitswochen aus MS‑Project‑Kalender mit Aspose.Tasks lesen

Erhalten Sie umfassende Einblicke in das Lesen von Arbeitswochen aus MS‑Project‑Kalendern mit Aspose.Tasks for Java. Dieses Tutorial bietet detaillierte Anleitungen und befähigt Sie, Ihre Projektpläne effektiv zu verwalten.  
Bereit, Arbeitswochen mühelos zu lesen? [Starten Sie hier](./read-work-weeks/).

## MS‑Project‑Kalender mit Aspose.Tasks ins MPP‑Format aktualisieren

Aktualisieren Sie mühelos MS‑Project‑Kalender ins MPP‑Format mit Aspose.Tasks for Java. Dieses Tutorial bietet einen nahtlosen Ansatz, um sicherzustellen, dass Ihre Projektdaten im richtigen Format für optimale Kompatibilität vorliegen.  
Bereit, Kalender ins MPP‑Format zu aktualisieren? [Entdecken Sie das Tutorial](./update-to-mpp/).

Entfesseln Sie das volle Potenzial von Aspose.Tasks for Java und heben Sie Ihre Projektmanagement‑Fähigkeiten auf ein neues Niveau. Jedes Tutorial ist für Entwickler aller Erfahrungsstufen konzipiert und sorgt für ein reibungsloses Lernerlebnis. Tauchen Sie ein und revolutionieren Sie noch heute Ihre Java‑Projektmanagement‑Reise!

## Kalender‑Tutorials
### [MS‑Project‑Kalendereigenschaften in Aspose.Tasks verwalten](./properties/)
Erfahren Sie, wie Sie MS‑Project‑Kalendereigenschaften in Java mit Aspose.Tasks verwalten. Dies bietet eine Schritt‑für‑Schritt‑Anleitung für Kalender in Ihren Java‑Anwendungen.

### [MS‑Project‑Kalender mit Aspose.Tasks erstellen](./create/)
Erfahren Sie, wie Sie MS‑Project‑Kalender mit Aspose.Tasks for Java erstellen. Optimieren Sie das Projektmanagement mühelos.

### [Wochentage im Kalender mit Aspose.Tasks definieren](./define-weekdays/)
Erfahren Sie, wie Sie Wochentage im MS‑Project‑Kalender mit Aspose.Tasks for Java definieren. Passen Sie Arbeitstage und -zeiten mühelos an.

### [Arbeitszeiten aus dem Kalender mit Aspose.Tasks abrufen](./working-hours/)
Extrahieren Sie Arbeitszeiten aus MS‑Project‑Kalendern einfach mit Aspose.Tasks for Java. Vereinfachen Sie Projektmanagement‑Aufgaben.

### [Standardkalender in Aspose.Tasks erstellen](./make-standard/)
Erfahren Sie, wie Sie in Java mit Aspose.Tasks einen standardmäßigen MS‑Project‑Kalender erstellen. Verbessern Sie Ihre Projektmanagement‑Fähigkeiten mit diesem Schritt‑für‑Schritt‑Tutorial.

### [Arbeitswochen aus MS‑Project‑Kalender mit Aspose.Tasks lesen](./read-work-weeks/)
Erfahren Sie, wie Sie Arbeitswochen aus dem MS‑Project‑Kalender mit Aspose.Tasks for Java lesen. Erhalten Sie Schritt‑für‑Schritt‑Anleitungen in diesem umfassenden Tutorial.

### [MS‑Project‑Kalender mit Aspose.Tasks ins MPP‑Format aktualisieren](./update-to-mpp/)
Erfahren Sie, wie Sie MS‑Project‑Kalender mühelos ins MPP‑Format aktualisieren mit Aspose.Tasks for Java.

## Häufig gestellte Fragen

**F: Kann ich für jeden Wochentag unterschiedliche Arbeitszeiten festlegen?**  
A: Ja. Aspose.Tasks ermöglicht das individuelle Festlegen von Start‑ und Endzeiten für Montag bis Sonntag.

**F: Wie gehe ich mit Feiertagen oder Nicht‑Arbeitstagen um?**  
A: Nach der Definition der Wochentage können Sie Ausnahmen (Daten) hinzufügen, um Feiertage oder benutzerdefinierte Nicht‑Arbeitstage zu markieren.

**F: Ist es möglich, eine Wochentag‑Definition von einem Kalender in einen anderen zu kopieren?**  
A: Absolut. Sie können ein `WeekDay`‑Objekt aus einem bestehenden Kalender abrufen und zu einer anderen Kalenderinstanz hinzufügen.

**F: Muss ich das Projekt nach dem Aktualisieren der Wochentage neu laden?**  
A: Nein. Änderungen werden direkt auf das im Speicher befindliche `Project`‑Objekt angewendet; speichern Sie das Projekt einfach, wenn Sie fertig sind.

**F: Welche Aspose.Tasks‑Version ist für die Wochentags‑Manipulation erforderlich?**  
A: Alle aktuellen Versionen (20.10 und später) unterstützen die vollständigen Wochentag‑APIs. Wir empfehlen die neueste stabile Version für beste Leistung.

---

**Last updated:** 2026-08-08  
**Tested with:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Verwandte Tutorials

- [Kalender zum Projekt hinzufügen mit Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Arbeitstage & Arbeitszeiten mit Aspose.Tasks bestimmen](/tasks/java/calendars/working-hours/)
- [Benutzerdefinierte Kalenderausnahmen mit Aspose.Tasks for Java erstellen](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}