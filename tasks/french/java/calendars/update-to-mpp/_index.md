---
date: 2026-08-13
description: Découvrez comment ajouter des jours fériés à un calendrier, affecter
  le calendrier à un projet et enregistrer le fichier MS Project au format MPP à l'aide
  d'Aspose.Tasks pour Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Mettre à jour le calendrier au format MPP dans Aspose.Tasks
og_description: Ajoutez des jours fériés au calendrier, affectez‑le à un projet et
  convertissez le planning au format MPP à l'aide d'Aspose.Tasks pour Java. Découvrez
  l'automatisation étape par étape.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Ajouter des jours fériés au calendrier et enregistrer au format MPP avec
  Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Ajouter des jours fériés au calendrier et enregistrer au format MPP avec Aspose.Tasks
url: /fr/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des jours fériés au calendrier et enregistrer au format MPP avec Aspose.Tasks

## Introduction

Dans la gestion de projet moderne, vous devez souvent **ajouter des jours fériés au calendrier** des fichiers, créer un **calendrier MS Project** et ensuite partager le planning au format natif MPP. Que vous consolidiez des chronologies provenant de multiples sources ou que vous migriez des données héritées, générer un calendrier de façon programmatique élimine les erreurs manuelles et accélère la livraison. Ce tutoriel vous guide à travers le processus complet de création d'un calendrier dans MS Project, sa personnalisation avec des jours fériés, **attribuer le calendrier au projet**, et enfin **convertir le projet en MPP** en utilisant l'API Java d'Aspose.Tasks.

## Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Ajouter des jours fériés à un calendrier, l'assigner à un projet, et enregistrer le résultat sous forme de fichier MPP avec Aspose.Tasks pour Java.  
- **Ai-je besoin d'une licence ?** Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour la production.  
- **Quelle version de Java est requise ?** Java 8 ou supérieure (JDK 8+).  
- **Puis-je personnaliser le calendrier ?** Oui – vous pouvez ajouter des heures de travail, des exceptions et des jours fériés.  
- **Combien de temps prend l'implémentation ?** Environ 10‑15 minutes pour un calendrier de base.  

## Qu’est-ce que « créer un calendrier MS Project » ?

Créer un calendrier MS Project signifie définir les jours ouvrés, les heures et les exceptions qui régissent la planification des tâches dans un fichier Microsoft Project. Avec Aspose.Tasks, vous pouvez créer ce calendrier de façon programmatique, définir les jours fériés et l'intégrer à un projet sans ouvrir l'interface MS Project.

## Pourquoi utiliser Aspose.Tasks pour cette tâche ?

Vous devez utiliser Aspose.Tasks car il offre une compatibilité Java complète, aucune nécessité d'avoir Microsoft Office, et vous permet de générer et d'enregistrer des fichiers MPP natifs directement depuis le code. La bibliothèque prend en charge toutes les fonctionnalités de calendrier, fonctionne sur n'importe quel environnement serveur, et traite des projets contenant jusqu'à 10 000 tâches en moins d'une seconde.

## Prérequis

1. **Java Development Kit (JDK) 8+** – assurez‑vous que `java -version` renvoie 1.8 ou une version plus récente.  
2. **Aspose.Tasks for Java** – téléchargez le dernier JAR depuis le [site Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, ou tout éditeur de votre choix.  
4. **Connaissances de base en Java** – familiarité avec les classes, les méthodes et les entrées/sorties de fichiers.

## Comment ajouter des jours fériés au calendrier

Pour ajouter des jours fériés, vous créez un nouvel objet `Calendar`, récupérez sa collection `Exceptions` et ajoutez des entrées `DateException` pour chaque date de jour férié. `DateException` représente une date ou une plage de dates non travaillées dans un calendrier. Aspose.Tasks considère alors ces dates comme des jours non ouvrés, garantissant que les tâches sont planifiées autour des jours fériés définis.

### Étape 1 : importer les packages requis

Tout d'abord, importez les classes Aspose.Tasks et les utilitaires Java.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Étape 2 : configurer le répertoire de données

Définissez l'emplacement où vos modèles d'entrée et fichiers de sortie seront stockés. Remplacez le texte de substitution par le chemin réel sur votre machine.

```java
String dataDir = "Your Data Directory";
```

### Étape 3 : définir les noms des fichiers d'entrée et de sortie

Nous chargerons un fichier MPP existant (ou un projet vierge) et écrirons le résultat dans un nouveau fichier.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Étape 4 : charger le projet et ajouter un nouveau calendrier

La classe `Project` représente un fichier MS Project en mémoire et fournit l'accès à ses calendriers, tâches et ressources.

Créez une instance `Project` à partir du fichier source et ajoutez un calendrier nommé **« Calendar 1 »**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Étape 5 : personnaliser le calendrier (facultatif)

L'objet `Calendar` définit les jours ouvrés, les heures et les exceptions pour le planning d'un projet.

Si vous avez besoin d'heures de travail spécifiques, de jours fériés ou d'exceptions, appelez votre propre méthode d'assistance. L'exemple utilise `GetTestCalendar` comme texte de substitution.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Astuce :** Vous pouvez manipuler directement `cal1.getWeekDays()` pour définir les heures de travail de chaque jour de la semaine, ou utiliser `cal1.getExceptions()` pour **ajouter des jours fériés au calendrier**.

### Étape 6 : assigner le calendrier au projet

Indiquez au projet d'utiliser le calendrier nouvellement créé pour tous ses calculs de planification.

```java
project.set(Prj.CALENDAR, cal1);
```

### Étape 7 : enregistrer le projet au format MPP

L'énumération `SaveFileFormat` spécifie le format de sortie, `Mpp` indiquant le format natif Microsoft Project.

Maintenant **convertissez le projet en MPP** en l'enregistrant avec l'option `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Étape 8 : confirmer la réussite

Un simple message console vous indique que le processus s'est terminé sans erreurs.

```java
System.out.println("Process completed Successfully");
```

## Cas d’utilisation courants

- **Génération automatisée d'un planning** pour les projets récurrents (p. ex., sprints hebdomadaires).  
- **Migration de calendriers CSV ou Excel hérités** vers un fichier MS Project complet.  
- **Rapports côté serveur** où un service web renvoie un fichier MPP à la demande.  

## Dépannage et pièges courants

| Problème | Cause | Solution |
|----------|-------|----------|
| `NullPointerException` on `project.save` | `dataDir` points to a non‑existent folder | Assurez‑vous que le répertoire existe ou créez‑le programmatique­ment. |
| Calendar not applied to tasks | Tasks still reference the default calendar | Après avoir défini `Prj.CALENDAR`, mettez également à jour `Task.CALENDAR` de chaque tâche si elles étaient précédemment remplacées. |
| Output file is 0 KB | Missing write permissions | Exécutez la JVM avec les droits d'accès au système de fichiers appropriés ou choisissez un chemin accessible en écriture. |

## Questions fréquemment posées

**Q : Aspose.Tasks pour Java est‑il compatible avec différentes versions de MS Project ?**  
R : Oui, Aspose.Tasks prend en charge tous les formats de fichiers Microsoft Project de Project 2007 à Project 2024, couvrant plus de 10 versions.

**Q : Puis‑je personnaliser les calendriers selon des exigences spécifiques du projet ?**  
R : Absolument. Vous pouvez définir les jours ouvrés, définir des semaines de travail personnalisées, ajouter des jours fériés, et même créer plusieurs calendriers dans un même fichier de projet.

**Q : Aspose.Tasks pour Java offre‑t‑il un support pour le dépannage et l’assistance ?**  
R : Oui, vous pouvez obtenir de l'aide sur le forum communautaire Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Tasks pour Java ?**  
R : Oui, un essai gratuit pleinement fonctionnel est disponible [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Tasks pour Java ?**  
R : Les licences temporaires peuvent être demandées via le site Aspose [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2026-08-13  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Ajouter un calendrier au projet avec Aspose.Tasks pour Java](/tasks/java/calendars/create/)
- [Comment définir les jours de la semaine dans les calendriers MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Créer des exceptions de calendrier personnalisées avec Aspose.Tasks pour Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}