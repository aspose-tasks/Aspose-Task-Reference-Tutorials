---
date: 2025-12-23
description: Apprenez comment mettre à jour les fichiers MS Project et replanifier
  le travail non terminé en utilisant Aspose.Tasks pour Java. Découvrez également
  comment enregistrer le XML de MS Project.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Mettre à jour MS Project et replanifier le travail avec Aspose.Tasks
url: /fr/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mettre à jour MS Project et replanifier le travail avec Aspose.Tasks

## Introduction
Microsoft Project est un outil de gestion de projet largement utilisé qui aide les équipes à planifier, suivre et livrer le travail à temps. Lorsque les plannings changent, vous devez souvent **mettre à jour MS Project** de façon programmatique — marquer le travail comme terminé, déplacer les tâches restantes et garder la ligne de base du projet précise. Aspose.Tasks for Java vous offre une API propre et typée pour faire exactement cela sans ouvrir l’interface graphique. Dans ce tutoriel, vous verrez comment mettre à jour un projet, marquer le travail comme fini jusqu’à une date précise, puis **comment replanifier MS Project** pour le travail encore en attente.

## Quick Answers
- **Que signifie « mettre à jour MS Project » ?** Il marque les tâches comme terminées jusqu’à une date donnée et écrit les modifications dans le fichier.  
- **Puis-je replanifier automatiquement le travail restant ?** Oui — utilisez `rescheduleUncompletedWorkToStartAfter` pour repousser les tâches inachevées.  
- **Quel format de fichier est enregistré ?** Les exemples enregistrent le projet au format XML (`SaveFileFormat.Xml`).  
- **Ai‑je besoin d’une licence pour exécuter le code ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise en production.  
- **Quelle version de Java est requise ?** JDK 8 ou supérieur.

## What is “update MS Project” in code?
Mettre à jour un projet signifie modifier programmatique les dates, durées ou pourcentages d’achèvement des tâches et persister ces changements. Aspose.Tasks expose des méthodes comme `updateProjectWorkAsComplete` qui appliquent les modifications en fonction d’une `Date` de référence que vous fournissez.

## Why use Aspose.Tasks for Java to update MS Project?
- **Pas de dépendance UI** – automatiser des modifications en masse sur de nombreux fichiers.  
- **Haute fidélité** – la bibliothèque préserve toutes les données natives de Project (ressources, calendriers, champs personnalisés).  
- **Multi‑plateforme** – exécuter le même code sous Windows, Linux ou macOS.  
- **Enregistrer MS Project XML** – vous pouvez exporter le projet mis à jour au format XML largement supporté pour les outils en aval.

## Prerequisites
1. Kit de développement Java (JDK) installé.  
2. Bibliothèque Aspose.Tasks for Java – téléchargez‑la depuis [here](https://releases.aspose.com/tasks/java/).  
3. Familiarité de base avec la syntaxe Java et les concepts orientés objet.

## Import Packages
First, import the necessary Aspose.Tasks classes and Java utilities:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Set up the Project
Create a new `Project` instance, define a few sample tasks, set their durations, and establish dependencies. Then persist the initial state so you can see the before‑and‑after effect.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Step 2: Update Project Work
Mark work as complete up to a specific cutoff date. This is the core of **update MS Project**—the API will adjust task progress and dates automatically.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Step 3: Reschedule Uncompleted Work
After marking completed work, you often need to push the remaining tasks forward. The following call moves any unfinished work to start after the same cutoff date, effectively **how to reschedule MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| Les tâches n’affichent pas les dates mises à jour | Le projet a été enregistré dans un format différent (par ex., `.mpp`) | Utilisez `SaveFileFormat.Xml` pour conserver la structure XML. |
| `updateProjectWorkAsComplete` semble ne rien faire | La date de référence est antérieure au début du projet | Assurez‑vous que la date du `Calendar` se situe dans la chronologie du projet. |
| Les tâches replanifiées se chevauchent | Aucun calendrier ou nivellement des ressources appliqué | Appliquez un calendrier `Project` ou utilisez `Task.setStart` manuellement après la replanification. |

## Frequently Asked Questions (Extended)

**Q : Aspose.Tasks for Java peut‑il gérer des structures de projet complexes ?**  
R : Oui, Aspose.Tasks for Java fournit des API robustes pour gérer efficacement les tâches, dépendances, ressources et autres éléments du projet.

**Q : Existe‑t‑il une version d’essai disponible pour Aspose.Tasks for Java ?**  
R : Oui, vous pouvez obtenir un essai gratuit depuis [here](https://releases.aspose.com/).

**Q : Comment obtenir du support pour Aspose.Tasks for Java ?**  
R : Vous pouvez consulter le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour toute assistance ou question.

**Q : Puis‑je acheter une licence temporaire pour Aspose.Tasks for Java ?**  
R : Oui, des licences temporaires sont disponibles à l’achat [here](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je trouver la documentation détaillée d’Aspose.Tasks for Java ?**  
R : Vous pouvez consulter la documentation [here](https://reference.aspose.com/tasks/java/) pour des guides complets et des références API.

## Conclusion
Dans ce tutoriel, nous avons parcouru le processus complet de **mise à jour des fichiers MS Project**, de marquage du travail comme terminé, puis de **replanification de MS Project** pour les tâches qui restent inachevées. En enregistrant le projet au format XML, vous conservez la compatibilité avec d’autres outils et maintenez une trace d’audit claire des modifications. Utilisez ces modèles pour automatiser les ajustements de planning dans de grands portefeuilles, intégrer les pipelines CI ou créer des tableaux de bord de reporting personnalisés.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}