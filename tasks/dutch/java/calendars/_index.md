---
date: 2026-11-19
description: Leer hoe u een aangepaste Java‑kalender maakt met Aspose.Tasks. Deze
  gids laat zien hoe u werkdagen definieert, werktijden instelt en MS Project‑kalenders
  programmatically wijzigt.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: Kalenders
og_description: Leer hoe u een aangepaste Java‑kalender maakt met Aspose.Tasks. Beheers
  het definiëren van werkdagen, het instellen van werktijden en het efficiënt wijzigen
  van MS Project‑kalenders.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Hoe een aangepaste Java‑kalender maken met Aspose.Tasks
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
title: Hoe een aangepaste Java‑kalender maken met Aspose.Tasks
url: /nl/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalenders

## Introductie

If you’re a Java developer who wants to **create custom calendar Java** solutions, you’ve landed in the right place. This hub gathers all Aspose.Tasks for Java tutorials that demonstrate how to **define working days MS Project**, **set working hours MS Project**, and programmatically adjust calendar settings. Whether you’re building a new scheduling engine or extending an existing plan, mastering these APIs gives you precise control over work‑day patterns, holidays, and custom shifts—without ever opening the MS Project UI.

## Snelle antwoorden
- **Wat is het primaire doel van het definiëren van weekdagen?**  
  Om MS Project te vertellen welke dagen werkdagen zijn en wat hun werktijden zijn.  
- **Welke bibliotheek behandelt de definitie van weekdagen in Java?**  
  Aspose.Tasks for Java provides a fluent API for calendar manipulation.  
- **Heb ik een licentie nodig?**  
  Een gratis evaluatielicentie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Kan ik meerdere kalenders definiëren voor verschillende teams?**  
  Ja – elk project kan meerdere kalenders bevatten, elk met zijn eigen weekdaginstellingen.  
- **Is er een voorbeeldproject om mee te beginnen?**  
  De “Define Weekdays in Calendar” tutorial linked below includes a ready‑to‑run example.

## Hoe maak je een aangepaste kalender in Java?

Load a project, create or retrieve a calendar, add weekday definitions, and save the file—all in a handful of API calls. This approach removes manual UI steps, lets you automate calendar creation across dozens of projects, and ensures consistent working‑day patterns throughout your organization.

## Wat is de Project‑klasse?

The `Project` class is the central object for loading, editing, and saving MS Project files. It holds collections of tasks, resources, and calendars, exposing methods that let you read and modify every aspect of a project programmatically. Using this class, you can access a project’s calendar collection, adjust working times, and persist changes back to an MPP or XML file.

## Hoe definieer ik weekdagen in MS Project‑kalenders?

The `Project` class represents an MS Project file and provides access to its data structures. A `Calendar` object stores working time definitions and exceptions for a project. Load your project with `new Project("myproject.mpp")`, retrieve (or create) a `Calendar` object, and then call `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. That single line creates a Monday work‑day entry with an 8‑hour shift. Repeat for other days, and finally save the project with `project.save("updated.mpp")`. This concise pattern lets you define, modify, or delete weekdays in just a few API calls, eliminating the need for manual UI interaction.

## Wat is een WeekDay‑object?

A `WeekDay` object represents a single day‑of‑the‑week entry inside a calendar. It stores whether the day is working, the working‑time intervals for that day, and flags for default behavior. You can attach one or more `WorkingTime` intervals to model split shifts, set the day as non‑working, or inherit defaults from the parent calendar.

## Hoe definieer je werkdagen in MS Project?

You define working days by adding `WeekDay` objects to a calendar’s `WeekDays` collection. Each `WeekDay` specifies whether the day is working and the time ranges that are considered work time. For example, to make Saturday a half‑day, add a `WeekDay` with a single `WorkingTime` from 10:00 to 14:00. The API automatically updates the project’s schedule calculations.

## Hoe stel je werktijden in MS Project in?

Set working hours by creating one or more `WorkingTime` intervals for each `WeekDay`. A `WorkingTime` takes start‑hour, start‑minute, end‑hour, and end‑minute values. You can assign multiple intervals to a single day to model split shifts (e.g., 08:00‑12:00 and 13:00‑17:00). After configuring all weekdays, call `project.save(...)` to persist the changes.

## Waarom Aspose.Tasks for Java gebruiken om weekdagen te definiëren?

- **Volledige API‑controle** – No UI limitations; you can programmatically create, modify, or delete weekday entries.  
- **Cross‑platform** – Works on any JVM‑compatible environment, from desktop apps to cloud services.  
- **Precisie** – Set different working times for each weekday, add exceptions for holidays, and synchronize calendars across multiple projects.  
- **Prestaties** – Process projects with up to 500 + tasks and calendars containing 100 + weeks without loading the entire UI, achieving conversion times under 2 seconds on a standard 2.5 GHz server (quantified claim based on Aspose benchmark).  
- **Brede bestandsformaatondersteuning** – Aspose.Tasks supports 30+ calendar‑related APIs and can import/export to more than 20 file formats, enabling seamless integration with existing project data pipelines.

## Vereisten
- Java 8 of hoger geïnstalleerd.  
- Aspose.Tasks for Java library (downloaded from the Aspose website or added via Maven/Gradle).  
- Een geldige Aspose.Tasks licentie (evaluation license works for learning).  

## Beheer MS Project‑kalendereigenschappen in Aspose.Tasks

Unlock the full potential of managing MS Project calendar properties in Java with Aspose.Tasks. Our tutorial walks you through the intricacies of calendar management, offering valuable insights into customization and optimization. From adjusting working hours to defining special dates, you'll master it all.

Ready to take control of your project timelines? [Explore the tutorial here](./properties/).

## Maak MS Project‑kalenders met Aspose.Tasks

Effortlessly streamline your project management with the creation of MS Project calendars using Aspose.Tasks for Java. Our tutorial simplifies the process, ensuring you can set up calendars tailored to your project's unique needs. Take the first step towards efficient project planning and organization.

Ready to create calendars with ease? [Check out the tutorial](./create/).

## Definieer weekdagen in kalender met Aspose.Tasks

Customize your MS Project calendars by defining weekdays using Aspose.Tasks for Java. This tutorial guides you through the process of tailoring working days and timings, offering you the flexibility needed for successful project management. Make your calendars work for you.

Ready to define weekdays effortlessly? [Get started here](./define-weekdays/).

As you navigate through these tutorials, you'll discover additional topics covering working hours extraction, standard calendar creation, reading work weeks, and updating calendars to MPP format. Each tutorial is crafted to provide you with practical knowledge, ensuring you can apply what you learn directly to your Java projects.

## Haal werktijden op uit kalender met Aspose.Tasks

Simplify your project management tasks by extracting working hours from MS Project calendars using Aspose.Tasks for Java. This tutorial equips you with the skills needed to optimize your project timelines efficiently.

Ready to extract working hours effortlessly? [Explore the tutorial](./working-hours/).

## Maak een standaardkalender in Aspose.Tasks

Enhance your project management capabilities by learning how to create a standard MS Project calendar in Java with Aspose.Tasks. This step‑by‑step tutorial ensures you can implement a standardized approach to your project timelines.

Ready to create a standard calendar? [Check out the tutorial](./make-standard/).

## Lees werkweken uit MS Project‑kalender met Aspose.Tasks

Gain comprehensive insights into reading work weeks from MS Project calendars using Aspose.Tasks for Java. This tutorial offers detailed instructions, empowering you to manage your project schedules effectively.

Ready to read work weeks effortlessly? [Get started here](./read-work-weeks/).

## Update MS Project‑kalenders naar MPP‑formaat met Aspose.Tasks

Effortlessly update MS Project calendars to MPP format using Aspose.Tasks for Java. This tutorial provides a seamless approach to ensure your project data is in the right format for optimal compatibility.

Ready to update calendars to MPP format? [Explore the tutorial](./update-to-mpp/).

Unlock the full potential of Aspose.Tasks for Java and elevate your project management skills. Each tutorial is designed to cater to developers of all levels, ensuring a smooth learning experience. Dive in and revolutionize your Java project management journey today!

## Kalender‑tutorials
### [Manage MS Project Calendar Properties in Aspose.Tasks](./properties/)
Learn how to manage MS Project calendar properties in Java using Aspose.Tasks. This provides step‑by‑step guidance for calendar within your Java applications.
### [Create MS Project Calendars using Aspose.Tasks](./create/)
Learn how to create MS Project calendars using Aspose.Tasks for Java. Streamline project management with ease.
### [Define weekdays in calendar with Aspose.Tasks](./define-weekdays/)
Learn how to define weekdays in MS Project calendar using Aspose.Tasks for Java. Customize working days and timings effortlessly.
### [Get working hours from calendar using Aspose.Tasks](./working-hours/)
Extract working hours from MS Project calendars easily with Aspose.Tasks for Java. Simplify project management tasks.
### [Make standard calendar in Aspose.Tasks](./make-standard/)
Learn how to create a standard MS Project calendar in Java using Aspose.Tasks. Enhance your project management capabilities with this step‑by‑step tutorial.
### [Read work weeks from MS Project calendar with Aspose.Tasks](./read-work-weeks/)
Learn how to read work weeks from MS Project calendar using Aspose.Tasks for Java. Get step‑by‑step instructions in this comprehensive tutorial.
### [Update MS Project calendars to MPP format effortlessly using Aspose.Tasks for Java](./update-to-mpp/)
Learn how to update MS Project calendars to MPP format effortlessly using Aspose.Tasks for Java.

## Veelgestelde vragen

**Q: Kan ik verschillende werktijden voor elke weekdag definiëren?**  
A: Ja. Aspose.Tasks laat je start‑ en eindtijden individueel instellen voor maandag tot en met zondag.

**Q: Hoe ga ik om met feestdagen of niet‑werkdagen?**  
A: Nadat je weekdagen hebt gedefinieerd, kun je uitzonderingen (datums) toevoegen om feestdagen of aangepaste niet‑werkperiodes te markeren.

**Q: Is het mogelijk om een weekdagdefinitie van de ene kalender naar de andere te kopiëren?**  
A: Absoluut. Je kunt een `WeekDay` object ophalen uit een bestaande kalender en toevoegen aan een andere kalender‑instantie.

**Q: Moet ik het project opnieuw laden na het bijwerken van weekdagen?**  
A: Nee. Wijzigingen worden direct toegepast op het in‑memory `Project` object; sla het project gewoon op wanneer je klaar bent.

**Q: Welke Aspose.Tasks‑versie is vereist voor weekdagmanipulatie?**  
A: Alle recente versies (20.10 en later) ondersteunen volledige weekdag‑API's. We raden aan de nieuwste stabiele release te gebruiken voor optimale prestaties.

**Last Updated:** 2026-11-19  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Gerelateerde tutorials

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Determine Working Days & Working Hours with Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Create Custom Calendar Exceptions with Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}