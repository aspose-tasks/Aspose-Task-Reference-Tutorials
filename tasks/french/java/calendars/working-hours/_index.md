---
date: 2025-12-05
description: Apprenez à déterminer les jours ouvrables et à calculer la durée des
  tâches en extrayant les heures de travail des calendriers MS Project à l'aide d'Aspose.Tasks
  pour Java.
language: fr
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Déterminer les jours ouvrés et les heures de travail avec Aspose.Tasks
url: /java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Déterminer les jours ouvrés et les heures de travail avec Aspose.Tasks

## Introduction
La gestion des calendriers de projet est une composante essentielle d’une planification de projet réussie. Dans ce tutoriel, vous allez **déterminer les jours ouvrés** pour toute tâche et **extraire les heures de travail** d’un calendrier MS Project en utilisant Aspose.Tasks pour Java. À la fin du guide, vous serez capable de **calculer la durée d’une tâche**, de personnaliser les heures de travail et de **charger de façon fiable un fichier MPP** pour récupérer les données dont vous avez besoin.

## Quick Answers
- **Que signifie « déterminer les jours ouvrés » ?** Cela consiste à identifier les dates du calendrier considérées comme jours de travail pour une tâche donnée.  
- **Quelle bibliothèque dois‑je utiliser ?** Aspose.Tasks for Java fournit une API complète pour travailler avec les fichiers MS Project.  
- **Combien de temps prend l’implémentation ?** Environ 10–15 minutes pour une extraction de base.  
- **Ai‑je besoin d’une licence ?** Une version d’essai gratuite est disponible ; une licence commerciale est requise pour une utilisation en production.  
- **Puis‑je personnaliser les heures de travail ?** Oui – vous pouvez modifier les calendriers, ajouter des jours fériés et définir des plages horaires personnalisées.

## Qu’est‑ce que « déterminer les jours ouvrés » ?
Lorsqu’une tâche est planifiée, le calendrier du projet définit quels jours sont des jours de travail et quels jours sont non ouvrés (week‑ends, jours fériés). Déterminer les jours ouvrés signifie interroger ce calendrier pour savoir exactement quand le travail peut avoir lieu, ce qui est essentiel pour des calculs précis de **calculer la durée d’une tâche**.

## Pourquoi utiliser Aspose.Tasks pour récupérer les heures de travail ?
- **Pas besoin de Microsoft Project** – travaillez avec des fichiers .MPP sur n’importe quelle plateforme.  
- **Support complet des calendriers** – comprend les calendriers par défaut, de ressources et de tâches.  
- **Haute performance** – traitez de grands projets rapidement.  
- **Documentation exhaustive** – des exemples et la référence de l’API sont facilement disponibles.

## Prérequis
1. **Java Development Kit (JDK)** – version 8 ou supérieure.  
2. **Aspose.Tasks for Java** – téléchargez le JAR le plus récent depuis [here](https://releases.aspose.com/tasks/java/).  
3. Connaissances de base en programmation Java.

## Import Packages
Tout d'abord, importez l'espace de noms principal d’Aspose.Tasks :

```java
import com.aspose.tasks.*;
```

## Étape 1 : Charger le fichier MPP
Chargez votre fichier de projet (l’étape **load mpp file**) afin de pouvoir travailler avec ses calendriers :

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Étape2 : Récupérer les informations de tâche et de calendrier
Choisissez la tâche que vous souhaitez analyser et obtenez son calendrier associé. C’est ici que nous **récupérons les heures de travail** pour la tâche :

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Étape 3 : Définir les dates de début et de fin
Définissez la fenêtre temporelle pour laquelle vous voulez **déterminer les jours ouvrés** :

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Étape 4 : Parcourir les dates
Parcourez chaque date de la durée de la tâche. Cette boucle nous aidera à **personnaliser les heures de travail** plus tard si nécessaire :

```java
java.util.Calendar tempDate = calStartDate;
```

## Étape 5 : Calculer la durée
Pendant l’itération, nous vérifions si chaque jour est un jour ouvré, additionnons les heures de travail, puis calculons finalement la durée de la tâche en minutes, heures et jours :

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

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Task returns `null` for calendar** | Assurez‑vous que la tâche possède réellement un calendrier attribué ; sinon elle hérite du calendrier par défaut du projet. |
| **Incorrect duration because of holidays** | Vérifiez que les jours fériés sont définis dans le calendrier de la tâche ou dans le calendrier de base du projet. |
| **Time zone mismatch** | Utilisez `java.util.TimeZone` pour aligner le fuseau horaire du calendrier avec celui de votre système si nécessaire. |

## Questions fréquentes
### Q : Aspose.Tasks for Java peut‑il gérer des structures de projet complexes ?
**A :** Oui, Aspose.Tasks for Java offre un support complet pour gérer des structures de projet complexes, y compris les tâches, les ressources et les calendriers.

### Q : Aspose.Tasks for Java est‑il compatible avec différentes versions de MS Project ?
**A :** Absolument, Aspose.Tasks for Java prend en charge diverses versions de MS Project, garantissant la compatibilité sur différents environnements.

### Q : Puis‑je personnaliser les heures de travail et les jours fériés dans les calendriers de projet ?
**A :** Oui, vous pouvez facilement personnaliser les heures de travail et les jours fériés selon les exigences de votre projet en utilisant les API d’Aspose.Tasks for Java.

### Q : Aspose.Tasks for Java propose‑t‑il une assistance et de la documentation ?
**A :** Oui, Aspose.Tasks for Java fournit une documentation exhaustive ainsi que des forums d’assistance dédiés pour aider les développeurs à exploiter efficacement ses fonctionnalités.

### Q : Existe‑t‑il une version d’essai disponible pour Aspose.Tasks for Java ?
**A :** Oui, vous pouvez accéder à une version d’essai gratuite d’Aspose.Tasks for Java depuis [here](https://releases.aspose.com/).

## Conclusion
Dans ce guide, nous avons démontré comment **déterminer les jours ouvrés**, **récupérer les heures de travail** et **calculer la durée d’une tâche** à partir d’un calendrier MS Project en utilisant Aspose.Tasks pour Java. En suivant les étapes ci‑dessus, vous pouvez automatiser l’analyse des plannings, personnaliser les calendriers et maintenir vos plans de projet précis et à jour.

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}