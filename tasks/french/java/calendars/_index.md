---
date: 2026-08-08
description: Apprenez à définir les jours de la semaine dans les calendriers MS Project
  en utilisant Aspose.Tasks for Java. Ce guide vous montre comment modifier le calendrier
  MS Project, créer un calendrier personnalisé Java, et planifier les jours ouvrables
  efficacement.
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: Calendriers
og_description: Apprenez à définir les jours de la semaine dans les calendriers MS
  Project en utilisant Aspose.Tasks for Java. Maîtrisez le calendrier personnalisé
  Java, modifiez le calendrier MS Project, et planifiez les jours ouvrables efficacement.
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: Comment définir les jours de la semaine dans les calendriers MS Project
  – Aspose.Tasks Java
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
title: Comment définir les jours de la semaine dans les calendriers MS Project – Aspose.Tasks
  Java
url: /fr/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calendriers

## Introduction

Si vous êtes développeur Java et que vous cherchez à **définir les jours de la semaine** dans le planning de votre projet, vous êtes au bon endroit. Dans ce hub, nous rassemblons tous les tutoriels Aspose.Tasks for Java qui montrent **comment définir les jours de la semaine** dans les calendriers MS Project, ajuster les heures de travail et garder vos échéances parfaitement claires. Que vous construisiez un nouveau moteur de planification ou que vous ajustiez un plan existant, maîtriser la définition des jours de la semaine vous donne un contrôle précis sur les modèles de jours ouvrés, les jours fériés et les équipes personnalisées. Ce guide explique également **comment modifier les paramètres du calendrier MS Project** de façon programmatique, afin que vous puissiez automatiser la création de calendriers pour des dizaines de projets.

## Réponses rapides
- **Quel est le but principal de la définition des jours de la semaine ?**  
  Indiquer à MS Project quels jours sont ouvrés et quelles sont leurs heures de travail.
- **Quelle bibliothèque gère la définition des jours de la semaine en Java ?**  
  Aspose.Tasks for Java fournit une API fluide pour la manipulation des calendriers.
- **Ai-je besoin d’une licence ?**  
  Une licence d’évaluation gratuite suffit pour les tests ; une licence commerciale est requise pour la production.
- **Puis-je définir plusieurs calendriers pour différentes équipes ?**  
  Oui – chaque projet peut contenir plusieurs calendriers, chacun avec ses propres paramètres de jours de la semaine.
- **Existe‑t‑il un projet d’exemple pour démarrer ?**  
  Le tutoriel « Define Weekdays in Calendar » lié ci‑dessous comprend un exemple prêt à l’exécution.

## Comment définir les jours de la semaine dans les calendriers MS Project ?

La classe `Project` représente un fichier MS Project et fournit l’accès à ses structures de données. Un objet `Calendar` stocke les définitions des temps de travail et les exceptions pour un projet. Chargez votre projet avec `new Project("myproject.mpp")`, récupérez (ou créez) un objet `Calendar`, puis appelez `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. Cette ligne unique crée une entrée de jour ouvré pour le lundi avec un quart de travail de 8 heures. Répétez pour les autres jours, puis enregistrez le projet avec `project.save("updated.mpp")`. Ce modèle concis vous permet de définir, modifier ou supprimer des jours de la semaine en quelques appels d’API seulement, éliminant ainsi le besoin d’une interaction manuelle avec l’interface utilisateur.

## Qu’est‑ce qu’un objet WeekDay ?

Un objet `WeekDay` représente une entrée unique de jour de la semaine dans un calendrier Aspose.Tasks, stockant son statut de travail et ses intervalles de temps de travail. Vous pouvez configurer les heures de début/fin, le définir comme non ouvré, ou y ajouter des périodes d’heures supplémentaires. Il peut contenir plusieurs intervalles `WorkingTime` pour modéliser des quarts de travail fractionnés, et il prend en charge des indicateurs pour les jours ouvrés par défaut. Utilisez l’API `WeekDay` pour activer ou désactiver un jour, attribuer des heures régulières ou spécifier des règles d’heures supplémentaires pour des scénarios de planification avancés.

## Pourquoi utiliser Aspose.Tasks for Java pour définir les jours de la semaine ?

- **Contrôle complet de l’API** – Aucun limitation d’interface ; vous pouvez créer, modifier ou supprimer des entrées de jours de la semaine de façon programmatique.  
- **Multiplateforme** – Fonctionne sur tout environnement compatible JVM, des applications de bureau aux services cloud.  
- **Précision** – Définissez des heures de travail différentes pour chaque jour de la semaine, ajoutez des exceptions pour les jours fériés et synchronisez les calendriers entre plusieurs projets.  
- **Performance** – Traitez des projets contenant plus de 500 tâches et des calendriers avec plus de 100 semaines sans charger l’intégralité de l’interface, obtenant des temps de conversion inférieurs à 2 secondes sur un serveur standard de 2,5 GHz (affirmation quantifiée basée sur le benchmark Aspose).  

## Prérequis
- Java 8 ou supérieur installé.  
- Bibliothèque Aspose.Tasks for Java (téléchargée depuis le site Aspose ou ajoutée via Maven/Gradle).  
- Une licence Aspose.Tasks valide (la licence d’évaluation fonctionne pour l’apprentissage).  

## Gérer les propriétés du calendrier MS Project dans Aspose.Tasks

Débloquez tout le potentiel de la gestion des propriétés du calendrier MS Project en Java avec Aspose.Tasks. Notre tutoriel vous guide à travers les subtilités de la gestion des calendriers, offrant des informations précieuses sur la personnalisation et l’optimisation. De l’ajustement des heures de travail à la définition de dates spéciales, vous maîtriserez tout.

Prêt à prendre le contrôle de vos échéances de projet ? [Explorez le tutoriel ici](./properties/).

## Créer des calendriers MS Project avec Aspose.Tasks

Simplifiez la gestion de vos projets en créant des calendriers MS Project avec Aspose.Tasks for Java. Notre tutoriel simplifie le processus, vous assurant de pouvoir configurer des calendriers adaptés aux besoins uniques de votre projet. Faites le premier pas vers une planification et une organisation de projet efficaces.

Prêt à créer des calendriers facilement ? [Découvrez le tutoriel](./create/).

## Définir les jours de la semaine dans le calendrier avec Aspose.Tasks

Personnalisez vos calendriers MS Project en définissant les jours de la semaine avec Aspose.Tasks for Java. Ce tutoriel vous guide à travers le processus d’adaptation des jours ouvrés et des horaires, vous offrant la flexibilité nécessaire à une gestion de projet réussie. Faites en sorte que vos calendriers travaillent pour vous.

Prêt à définir les jours de la semaine sans effort ? [Commencez ici](./define-weekdays/).

En parcourant ces tutoriels, vous découvrirez des sujets supplémentaires couvrant l’extraction des heures de travail, la création de calendriers standard, la lecture des semaines de travail et la mise à jour des calendriers au format MPP. Chaque tutoriel est conçu pour vous fournir des connaissances pratiques, vous assurant de pouvoir appliquer directement ce que vous apprenez à vos projets Java.

## Obtenir les heures de travail du calendrier avec Aspose.Tasks

Simplifiez vos tâches de gestion de projet en extrayant les heures de travail des calendriers MS Project avec Aspose.Tasks for Java. Ce tutoriel vous donne les compétences nécessaires pour optimiser efficacement vos échéances de projet.

Prêt à extraire les heures de travail sans effort ? [Explorez le tutoriel](./working-hours/).

## Créer un calendrier standard avec Aspose.Tasks

Améliorez vos capacités de gestion de projet en apprenant à créer un calendrier MS Project standard en Java avec Aspose.Tasks. Ce tutoriel pas à pas vous assure de pouvoir mettre en œuvre une approche standardisée de vos échéances de projet.

Prêt à créer un calendrier standard ? [Découvrez le tutoriel](./make-standard/).

## Lire les semaines de travail du calendrier MS Project avec Aspose.Tasks

Obtenez des informations complètes sur la lecture des semaines de travail à partir des calendriers MS Project avec Aspose.Tasks for Java. Ce tutoriel propose des instructions détaillées, vous permettant de gérer efficacement vos plannings de projet.

Prêt à lire les semaines de travail sans effort ? [Commencez ici](./read-work-weeks/).

## Mettre à jour les calendriers MS Project au format MPP avec Aspose.Tasks

Mettez à jour facilement les calendriers MS Project au format MPP avec Aspose.Tasks for Java. Ce tutoriel offre une approche fluide pour garantir que vos données de projet sont dans le bon format pour une compatibilité optimale.

Prêt à mettre à jour les calendriers au format MPP ? [Explorez le tutoriel](./update-to-mpp/).

Débloquez tout le potentiel d’Aspose.Tasks for Java et améliorez vos compétences en gestion de projet. Chaque tutoriel est conçu pour répondre aux développeurs de tous niveaux, assurant une expérience d’apprentissage fluide. Plongez‑y et révolutionnez dès aujourd’hui votre parcours de gestion de projet Java !

## Tutoriels de calendriers
### [Gérer les propriétés du calendrier MS Project dans Aspose.Tasks](./properties/)
Apprenez à gérer les propriétés du calendrier MS Project en Java avec Aspose.Tasks. Cela fournit des instructions pas à pas pour les calendriers dans vos applications Java.
### [Créer des calendriers MS Project avec Aspose.Tasks](./create/)
Apprenez à créer des calendriers MS Project avec Aspose.Tasks for Java. Simplifiez la gestion de projet avec facilité.
### [Définir les jours de la semaine dans le calendrier avec Aspose.Tasks](./define-weekdays/)
Apprenez à définir les jours de la semaine dans le calendrier MS Project avec Aspose.Tasks for Java. Personnalisez les jours ouvrés et les horaires sans effort.
### [Obtenir les heures de travail du calendrier avec Aspose.Tasks](./working-hours/)
Extrayez facilement les heures de travail des calendriers MS Project avec Aspose.Tasks for Java. Simplifiez les tâches de gestion de projet.
### [Créer un calendrier standard avec Aspose.Tasks](./make-standard/)
Apprenez à créer un calendrier MS Project standard en Java avec Aspose.Tasks. Améliorez vos capacités de gestion de projet grâce à ce tutoriel pas à pas.
### [Lire les semaines de travail du calendrier MS Project avec Aspose.Tasks](./read-work-weeks/)
Apprenez à lire les semaines de travail à partir du calendrier MS Project avec Aspose.Tasks for Java. Obtenez des instructions pas à pas dans ce tutoriel complet.
### [Mettre à jour les calendriers MS Project au format MPP avec Aspose.Tasks](./update-to-mpp/)
Apprenez à mettre à jour les calendriers MS Project au format MPP sans effort avec Aspose.Tasks for Java.

## Questions fréquemment posées

**Q : Puis‑je définir des heures de travail différentes pour chaque jour de la semaine ?**  
R : Oui. Aspose.Tasks vous permet de définir les heures de début et de fin individuellement pour chaque jour, du lundi au dimanche.

**Q : Comment gérer les jours fériés ou les jours non ouvrés ?**  
R : Après avoir défini les jours de la semaine, vous pouvez ajouter des exceptions (dates) pour marquer les jours fériés ou des périodes non ouvrées personnalisées.

**Q : Est‑il possible de copier une définition de jour de la semaine d’un calendrier à un autre ?**  
R : Absolument. Vous pouvez récupérer un objet `WeekDay` d’un calendrier existant et l’ajouter à une autre instance de calendrier.

**Q : Dois‑je recharger le projet après avoir mis à jour les jours de la semaine ?**  
R : Non. Les modifications sont appliquées directement à l’objet `Project` en mémoire ; il suffit d’enregistrer le projet une fois terminé.

**Q : Quelle version d’Aspose.Tasks est requise pour la manipulation des jours de la semaine ?**  
R : Toutes les versions récentes (20.10 et suivantes) prennent en charge l’ensemble des API de jours de la semaine. Nous recommandons d’utiliser la dernière version stable pour des performances optimales.

**Dernière mise à jour :** 2026-08-08  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Ajouter un calendrier au projet avec Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Déterminer les jours ouvrés et les heures de travail avec Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Créer des exceptions de calendrier personnalisées avec Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}