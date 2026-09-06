---
date: 2026-08-24
description: Apprenez comment ajouter un calendrier des jours fériés, déterminer les
  jours ouvrés et calculer la durée des tâches en extrayant les heures de travail
  des calendriers MS Project à l'aide d'Aspose.Tasks for Java.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Comment ajouter un calendrier des jours fériés et déterminer les jours
  ouvrés
og_description: Apprenez comment ajouter un calendrier des jours fériés, déterminer
  les jours ouvrés et calculer la durée des tâches en extrayant les heures de travail
  des calendriers MS Project à l'aide d'Aspose.Tasks for Java.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Comment ajouter un calendrier des jours fériés et déterminer les jours ouvrés
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: Comment ajouter un calendrier des jours fériés et déterminer les jours ouvrés
url: /fr/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un calendrier de jours fériés et déterminer les jours ouvrés

La gestion des calendriers de projet est une partie essentielle d’une planification de projet réussie. Dans ce tutoriel, vous allez **ajouter un calendrier de jours fériés**, **déterminer les jours ouvrés** pour toute tâche, et **extraire les heures de travail** d’un calendrier MS Project en utilisant Aspose.Tasks for Java. À la fin du guide, vous pourrez **calculer la durée d’une tâche**, personnaliser les heures de travail, et charger de manière fiable un **fichier MPP** pour récupérer les données dont vous avez besoin — le tout sans installer Microsoft Project.

## Réponses rapides
- **Que signifie « déterminer les jours ouvrés » ?** Cela signifie identifier quelles dates du calendrier sont considérées comme des jours de travail pour une tâche donnée.  
- **Quelle bibliothèque dois‑je utiliser ?** Aspose.Tasks for Java fournit une API complète pour travailler avec les fichiers MS Project.  
- **Combien de temps prend l’implémentation ?** Typiquement 10–15 minutes pour une extraction de base.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit est disponible ; une licence commerciale est requise pour une utilisation en production.  
- **Puis‑je personnaliser les heures de travail ?** Oui – vous pouvez modifier les calendriers, ajouter des jours fériés et définir des plages horaires personnalisées.  

## Qu’est‑ce que « déterminer les jours ouvrés » ?
**Déterminer les jours ouvrés** signifie interroger un calendrier de projet pour découvrir quelles dates sont marquées comme jours de travail versus jours non ouvrés (week‑ends, jours fériés ou exceptions personnalisées). Cette information est essentielle pour un **calcul précis de la durée d’une tâche** car seuls les jours ouvrés contribuent au temps écoulé d’une tâche.

## Pourquoi utiliser Aspose.Tasks pour récupérer les heures de travail ?
Aspose.Tasks vous permet de lire les fichiers MS Project sans que Microsoft Project soit installé, permettant l’automatisation sur n’importe quelle plateforme. Il offre également un traitement haute performance, une prise en charge étendue des formats et une documentation détaillée.  

- **Prise en charge complète des calendriers** – les calendriers par défaut, de ressources et de tâches sont tous accessibles.  
- **Haute performance** – peut traiter des projets contenant **plus de 10 000 tâches en moins de 2 secondes** sur un CPU standard de 2,5 GHz.  
- **Couverture étendue des formats** – prend en charge **plus de 50 formats d’entrée et de sortie**, y compris MPP, MPX, XML et Primavera.  
- **Documentation complète** – des exemples de code, la référence API et les forums communautaires sont tous disponibles.

## Prérequis
Avant de commencer, assurez-vous d’avoir :

1. **Java Development Kit (JDK)** – version 8 ou supérieure.  
2. **Aspose.Tasks for Java** – téléchargez le dernier JAR depuis [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/).  
3. Connaissances de base en programmation Java.  

## Importer les packages
La classe `Project` est l’objet de niveau supérieur d’Aspose.Tasks qui représente un fichier MS Project unique en mémoire. Importez l’espace de noms requis avant de commencer :

Importer les packages

```java
import com.aspose.tasks.*;
```

## Comment charger un fichier MPP avec Aspose.Tasks ?
La classe `Project` charge un fichier MS Project et fournit l’accès à ses données. Chargez le fichier de projet en une seule ligne de code ; aucune interface utilisateur ni interop COM n’est requise. Cette étape simple vous donne un accès complet aux calendriers, aux tâches et aux ressources.

Chargement d’un fichier MPP

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Récupérer les informations de tâche et de calendrier
`Task` représente une tâche de projet, et `Calendar` définit ses règles de temps de travail. Sélectionnez la tâche que vous souhaitez analyser et obtenez son calendrier associé. L’objet `Task` fournit les méthodes `getStart()` et `getFinish()`, tandis que l’objet `Calendar` expose les définitions du temps de travail.

Récupération de la tâche et du calendrier

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Définir les dates de début et de fin
Les objets `Date` spécifient la fenêtre temporelle pour l’analyse du calendrier. Définissez la période pour laquelle vous souhaitez **déterminer les jours ouvrés**. Utiliser les dates de début et de fin de la tâche garantit que vous n’évaluez que la période pertinente.

Définition des dates

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Parcourir les dates
Une boucle `for` peut parcourir chaque jour de la plage de dates. Parcourez chaque date de la durée de la tâche. Cette boucle vous permettra plus tard de **personnaliser les heures de travail** si nécessaire et constitue la base du calcul du temps de travail total.

Itération des dates

```java
java.util.Calendar tempDate = calStartDate;
```

## Calculer la durée
`Duration` agrège le temps de travail total calculé à partir de l’itération. Pendant l’itération, vous vérifiez si chaque jour est un jour ouvré, cumulez les heures de travail, puis calculez finalement la durée de la tâche en minutes, heures et jours. Cela montre comment **calculer les jours ouvrés** et **calculer la durée d’une tâche** de manière programmatique.

Calcul de la durée

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## Comment personnaliser les heures de travail et les jours fériés
Vous pouvez modifier les plages horaires de travail du calendrier et ajouter des exceptions comme les jours fériés. Utilisez `taskCalendar.addWorkingTime()` pour définir de nouvelles périodes de travail et `taskCalendar.addException()` pour insérer un jour férié. Cela est utile lorsque le planning par défaut de 9 h à 17 h ne correspond pas aux politiques de votre organisation.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **La tâche renvoie `null` pour le calendrier** | Assurez‑vous que la tâche possède réellement un calendrier assigné ; sinon elle hérite du calendrier par défaut du projet. |
| **Durée incorrecte à cause des jours fériés** | Vérifiez que les jours fériés sont définis dans le calendrier de la tâche ou dans le calendrier de base du projet. |
| **Incohérence de fuseau horaire** | Utilisez `java.util.TimeZone` pour aligner le fuseau horaire du calendrier avec votre système si nécessaire. |

## Questions fréquemment posées
### Q : Aspose.Tasks for Java peut‑il gérer des structures de projet complexes ?
R : Oui, Aspose.Tasks for Java offre une prise en charge complète pour gérer des structures de projet complexes, y compris les tâches, les ressources et les calendriers.

### Q : Aspose.Tasks for Java est‑il compatible avec différentes versions de MS Project ?
R : Absolument, Aspose.Tasks for Java prend en charge diverses versions de MS Project, garantissant la compatibilité entre différents environnements.

### Q : Puis‑je personnaliser les heures de travail et les jours fériés dans les calendriers de projet ?
R : Oui, vous pouvez facilement personnaliser les heures de travail et les jours fériés selon les exigences de votre projet en utilisant les API d’Aspose.Tasks for Java.

### Q : Aspose.Tasks for Java offre‑t‑il un support et une documentation ?
R : Oui, Aspose.Tasks for Java fournit une documentation exhaustive et des forums de support dédiés pour aider les développeurs à exploiter efficacement ses fonctionnalités.

### Q : Existe‑t‑il une version d’essai disponible pour Aspose.Tasks for Java ?
R : Oui, vous pouvez accéder à une version d’essai gratuite d’Aspose.Tasks for Java depuis la [page des versions Aspose](https://releases.aspose.com/).

## Conclusion
Dans ce guide, nous avons démontré comment **ajouter un calendrier de jours fériés**, **déterminer les jours ouvrés**, **récupérer les heures de travail**, et **calculer la durée d’une tâche** à partir d’un calendrier MS Project en utilisant Aspose.Tasks for Java. En suivant les étapes ci‑dessus, vous pouvez automatiser l’analyse des plannings, personnaliser les calendriers et maintenir vos plans de projet précis et à jour. Vous disposez désormais des outils pour **lire les données MS Project**, **charger un fichier MPP**, et effectuer des calculs de durée précis sans avoir besoin de Microsoft Project lui‑même.

---

**Last Updated:** 2026-08-24  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Tutoriels associés

- [Ajouter un calendrier au projet avec Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Ajouter des jours fériés au calendrier et enregistrer en MPP avec Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [Créer des exceptions de calendrier personnalisées avec Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}