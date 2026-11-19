---
date: 2026-11-19
description: Apprenez à créer un calendrier personnalisé Java en utilisant Aspose.Tasks.
  Ce guide vous montre comment définir les jours ouvrables, définir les heures de
  travail et modifier les calendriers MS Project de manière programmatique.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: Calendriers
og_description: Apprenez à créer un calendrier personnalisé Java avec Aspose.Tasks.
  Maîtrisez la définition des jours ouvrables, la définition des heures de travail
  et la modification efficace des calendriers MS Project.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Comment créer un calendrier personnalisé Java avec Aspose.Tasks
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
title: Comment créer un calendrier personnalisé Java avec Aspose.Tasks
url: /fr/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calendriers

## Introduction

If you’re a Java developer who wants to **créer des calendriers Java personnalisés** solutions, you’ve landed in the right place. This hub gathers all Aspose.Tasks for Java tutorials that demonstrate how to **définir les jours ouvrés MS Project**, **définir les heures de travail MS Project**, and programmatically adjust calendar settings. Whether you’re building a new scheduling engine or extending an existing plan, mastering these APIs gives you precise control over work‑day patterns, holidays, and custom shifts—without ever opening the MS Project UI.

## Réponses rapides
- **What is the primary purpose of defining weekdays?**  
  To tell MS Project which days are working days and what their working hours are.  
- **Which library handles weekday definition in Java?**  
  Aspose.Tasks for Java provides a fluent API for calendar manipulation.  
- **Do I need a license?**  
  A free evaluation license works for testing; a commercial license is required for production.  
- **Can I define multiple calendars for different teams?**  
  Yes – each project can contain several calendars, each with its own weekday settings.  
- **Is there a sample project to start from?**  
  The “Define Weekdays in Calendar” tutorial linked below includes a ready‑to‑run example.

## Comment créer un calendrier Java personnalisé ?

Load a project, create or retrieve a calendar, add weekday definitions, and save the file—all in a handful of API calls. This approach removes manual UI steps, lets you automate calendar creation across dozens of projects, and ensures consistent working‑day patterns throughout your organization.

## Qu'est‑ce que la classe Project ?

The `Project` class is the central object for loading, editing, and saving MS Project files. It holds collections of tasks, resources, and calendars, exposing methods that let you read and modify every aspect of a project programmatically. Using this class, you can access a project’s calendar collection, adjust working times, and persist changes back to an MPP or XML file.

## Comment définir les jours de semaine dans les calendriers MS Project ?

The `Project` class represents an MS Project file and provides access to its data structures. A `Calendar` object stores working time definitions and exceptions for a project. Load your project with `new Project("myproject.mpp")`, retrieve (or create) a `Calendar` object, and then call `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. That single line creates a Monday work‑day entry with an 8‑hour shift. Repeat for other days, and finally save the project with `project.save("updated.mpp")`. This concise pattern lets you define, modify, or delete weekdays in just a few API calls, eliminating the need for manual UI interaction.

## Qu'est‑ce qu'un objet WeekDay ?

A `WeekDay` object represents a single day‑of‑the‑week entry inside a calendar. It stores whether the day is working, the working‑time intervals for that day, and flags for default behavior. You can attach one or more `WorkingTime` intervals to model split shifts, set the day as non‑working, or inherit defaults from the parent calendar.

## Comment définir les jours ouvrés dans MS Project ?

You define working days by adding `WeekDay` objects to a calendar’s `WeekDays` collection. Each `WeekDay` specifies whether the day is working and the time ranges that are considered work time. For example, to make Saturday a half‑day, add a `WeekDay` with a single `WorkingTime` from 10:00 to 14:00. The API automatically updates the project’s schedule calculations.

## Comment définir les heures de travail dans MS Project ?

Set working hours by creating one or more `WorkingTime` intervals for each `WeekDay`. A `WorkingTime` takes start‑hour, start‑minute, end‑hour, and end‑minute values. You can assign multiple intervals to a single day to model split shifts (e.g., 08:00‑12:00 and 13:00‑17:00). After configuring all weekdays, call `project.save(...)` to persist the changes.

## Pourquoi utiliser Aspose.Tasks for Java pour définir les jours de semaine ?

- **Full API control** – Pas de limitations d'interface utilisateur ; vous pouvez créer, modifier ou supprimer des entrées de jours de semaine de façon programmatique.  
- **Cross‑platform** – Fonctionne sur tout environnement compatible JVM, des applications de bureau aux services cloud.  
- **Precision** – Définissez des heures de travail différentes pour chaque jour de semaine, ajoutez des exceptions pour les vacances et synchronisez les calendriers entre plusieurs projets.  
- **Performance** – Traitez des projets contenant plus de 500 tâches et des calendriers de plus de 100 semaines sans charger l'interface complète, atteignant des temps de conversion inférieurs à 2 secondes sur un serveur standard de 2,5 GHz (affirmation quantifiée basée sur le benchmark Aspose).  
- **Broad format support** – Aspose.Tasks prend en charge plus de 30 API liées aux calendriers et peut importer/exporter vers plus de 20 formats de fichiers, permettant une intégration fluide avec les pipelines de données de projet existants.

## Prérequis
- Java 8 ou supérieur installé.  
- Bibliothèque Aspose.Tasks for Java (téléchargée depuis le site Aspose ou ajoutée via Maven/Gradle).  
- Une licence Aspose.Tasks valide (une licence d'évaluation suffit pour l'apprentissage).  

## Gérer les propriétés du calendrier MS Project avec Aspose.Tasks

Débloquez tout le potentiel de la gestion des propriétés du calendrier MS Project en Java avec Aspose.Tasks. Notre tutoriel vous guide à travers les subtilités de la gestion des calendriers, offrant des informations précieuses sur la personnalisation et l'optimisation. De l'ajustement des heures de travail à la définition de dates spéciales, vous maîtriserez tout.

Prêt à prendre le contrôle de vos échéanciers de projet ? [Explorez le tutoriel ici](./properties/).

## Créer des calendriers MS Project avec Aspose.Tasks

Simplifiez la gestion de vos projets en créant des calendriers MS Project avec Aspose.Tasks for Java. Notre tutoriel simplifie le processus, vous assurant de pouvoir configurer des calendriers adaptés aux besoins uniques de votre projet. Faites le premier pas vers une planification et une organisation de projet efficaces.

Prêt à créer des calendriers avec aisance ? [Consultez le tutoriel](./create/).

## Définir les jours de semaine dans le calendrier avec Aspose.Tasks

Personnalisez vos calendriers MS Project en définissant les jours de semaine avec Aspose.Tasks for Java. Ce tutoriel vous guide à travers le processus d'adaptation des jours ouvrés et des horaires, vous offrant la flexibilité nécessaire à une gestion de projet réussie. Faites en sorte que vos calendriers travaillent pour vous.

Commencez ici [Commencez ici](./define-weekdays/).

En parcourant ces tutoriels, vous découvrirez des sujets supplémentaires couvrant l'extraction des heures de travail, la création de calendriers standard, la lecture des semaines de travail et la mise à jour des calendriers au format MPP. Chaque tutoriel est conçu pour vous fournir des connaissances pratiques, vous assurant de pouvoir appliquer directement ce que vous apprenez à vos projets Java.

## Obtenir les heures de travail à partir du calendrier avec Aspose.Tasks

Simplifiez vos tâches de gestion de projet en extrayant les heures de travail des calendriers MS Project avec Aspose.Tasks for Java. Ce tutoriel vous dote des compétences nécessaires pour optimiser efficacement vos échéanciers de projet.

Explorez le tutoriel [Explorez le tutoriel](./working-hours/).

## Créer un calendrier standard avec Aspose.Tasks

Améliorez vos capacités de gestion de projet en apprenant à créer un calendrier MS Project standard en Java avec Aspose.Tasks. Ce tutoriel pas à pas vous assure de pouvoir mettre en œuvre une approche standardisée de vos échéanciers de projet.

Consultez le tutoriel [Consultez le tutoriel](./make-standard/).

## Lire les semaines de travail à partir du calendrier MS Project avec Aspose.Tasks

Obtenez des informations complètes sur la lecture des semaines de travail à partir des calendriers MS Project avec Aspose.Tasks for Java. Ce tutoriel offre des instructions détaillées, vous permettant de gérer efficacement les échéanciers de votre projet.

Commencez ici [Commencez ici](./read-work-weeks/).

## Mettre à jour les calendriers MS Project au format MPP avec Aspose.Tasks

Mettez à jour facilement les calendriers MS Project au format MPP avec Aspose.Tasks for Java. Ce tutoriel fournit une approche fluide pour garantir que vos données de projet sont dans le bon format pour une compatibilité optimale.

Explorez le tutoriel [Explorez le tutoriel](./update-to-mpp/).

Débloquez tout le potentiel d'Aspose.Tasks for Java et améliorez vos compétences en gestion de projet. Chaque tutoriel est conçu pour répondre aux développeurs de tous niveaux, assurant une expérience d'apprentissage fluide. Plongez-y et révolutionnez dès aujourd'hui votre parcours de gestion de projet Java !

## Tutoriels sur les calendriers
### [Gérer les propriétés du calendrier MS Project avec Aspose.Tasks](./properties/)
Apprenez à gérer les propriétés du calendrier MS Project en Java avec Aspose.Tasks. Cela fournit un guide pas à pas pour le calendrier au sein de vos applications Java.
### [Créer des calendriers MS Project avec Aspose.Tasks](./create/)
Apprenez à créer des calendriers MS Project avec Aspose.Tasks for Java. Simplifiez la gestion de projet avec aisance.
### [Définir les jours de semaine dans le calendrier avec Aspose.Tasks](./define-weekdays/)
Apprenez à définir les jours de semaine dans le calendrier MS Project avec Aspose.Tasks for Java. Personnalisez les jours ouvrés et les horaires sans effort.
### [Obtenir les heures de travail à partir du calendrier avec Aspose.Tasks](./working-hours/)
Extrayez facilement les heures de travail des calendriers MS Project avec Aspose.Tasks for Java. Simplifiez les tâches de gestion de projet.
### [Créer un calendrier standard avec Aspose.Tasks](./make-standard/)
Apprenez à créer un calendrier MS Project standard en Java avec Aspose.Tasks. Améliorez vos capacités de gestion de projet grâce à ce tutoriel pas à pas.
### [Lire les semaines de travail à partir du calendrier MS Project avec Aspose.Tasks](./read-work-weeks/)
Apprenez à lire les semaines de travail à partir du calendrier MS Project avec Aspose.Tasks for Java. Obtenez des instructions pas à pas dans ce tutoriel complet.
### [Mettre à jour les calendriers MS Project au format MPP facilement avec Aspose.Tasks for Java](./update-to-mpp/)
Apprenez à mettre à jour les calendriers MS Project au format MPP facilement avec Aspose.Tasks for Java.

## Questions fréquemment posées

**Q: Can I define different working hours for each weekday?**  
A: Yes. Aspose.Tasks lets you set start and finish times individually for Monday through Sunday.

**Q: How do I handle holidays or non‑working days?**  
A: After defining weekdays, you can add exceptions (dates) to mark holidays or custom non‑working periods.

**Q: Is it possible to copy a weekday definition from one calendar to another?**  
A: Absolutely. You can retrieve a `WeekDay` object from an existing calendar and add it to another calendar instance.

**Q: Do I need to reload the project after updating weekdays?**  
A: No. Changes are applied directly to the in‑memory `Project` object; just save the project when you’re done.

**Q: Which Aspose.Tasks version is required for weekday manipulation?**  
A: All recent versions (20.10 and later) support full weekday APIs. We recommend using the latest stable release for best performance.

---

**Dernière mise à jour :** 2026-11-19  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Ajouter un calendrier au projet avec Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Déterminer les jours ouvrés et les heures de travail avec Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Créer des exceptions de calendrier personnalisées avec Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}