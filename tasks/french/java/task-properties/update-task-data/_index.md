---
date: 2026-03-03
description: Apprenez comment mettre à jour les données de tâches au format MPP en
  utilisant Aspose.Tasks Java. Suivez notre guide étape par étape pour une gestion
  de projet efficace.
linktitle: Update Task Data to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Mettre à jour les données de tâche au format MPP
url: /fr/java/task-properties/update-task-data/
weight: 35
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mettre à jour les données de tâche au format MPP dans Aspose.Tasks

## Introduction
Bienvenue dans notre guide étape par étape sur **la mise à jour des données de tâche au format MPP à l'aide d'Aspose.Tasks pour Java**. Dans ce tutoriel, vous apprendrez à manipuler les fichiers de projet de manière programmatique avec *aspose tasks java*, depuis la création d'une tâche récapitulative jusqu'à la conversion d'un projet XML en fichier MPP. À la fin, vous serez capable de gérer les tâches de projet efficacement et d'intégrer la solution dans vos applications Java.

## Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Mise à jour des données de tâche et sauvegarde d'un projet au format MPP avec Aspose.Tasks pour Java.  
- **Ai-je besoin d'une licence ?** Une licence temporaire ou complète est requise pour une utilisation en production ; un essai gratuit est disponible.  
- **Quel IDE est le plus adapté ?** Tout IDE Java (IntelliJ IDEA, Eclipse, VS Code) fonctionnera.  
- **Puis-je convertir XML en MPP ?** Oui – l'exemple charge un projet XML et le sauvegarde en MPP.  
- **Combien de tâches sont créées ?** L'exemple crée une tâche principale, une tâche récapitulative et dix tâches supplémentaires.

## Qu'est-ce qu'Aspose.Tasks pour Java ?
Aspose.Tasks pour Java est une API puissante qui permet aux développeurs de lire, écrire et modifier les fichiers Microsoft Project (MPP, XML, et plus) sans nécessiter l'installation de Microsoft Project. Elle prend en charge la manipulation complète au niveau du projet, y compris la création de tâches, la gestion des contraintes et la conversion de formats de fichiers.

## Pourquoi utiliser Aspose.Tasks Java pour la gestion de projet ?
- **Contrôle complet** sur les propriétés des tâches telles que la date de début, la durée et les contraintes.  
- **Conversion transparente** entre XML et MPP, permettant l'intégration avec les pipelines de données de projet existants.  
- **Pas d'interop COM** – Java pur, idéal pour les environnements multiplateformes.  
- **Haute performance** pour les gros fichiers de projet, le rendant adapté aux solutions à l'échelle de l'entreprise.

## Prérequis
Avant de plonger dans le tutoriel, assurez-vous d'avoir les prérequis suivants en place :

- Aspose.Tasks pour Java : Assurez-vous d'avoir la bibliothèque Aspose.Tasks installée. Vous pouvez la télécharger depuis la [page de diffusion](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK) : Assurez-vous d'avoir Java installé sur votre système.
- Environnement de développement intégré (IDE) : Utilisez l'IDE de votre choix pour le développement Java.

## Importer les packages
Commencez par importer les packages nécessaires dans votre projet Java. Le fragment suivant montre comment importer les packages :

```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```

## Comment créer une tâche récapitulative
Une tâche récapitulative regroupe les sous‑tâches liées, vous offrant une vue d'ensemble des lots de travail. Dans le code ci‑dessous, nous créons une tâche récapitulative et attachons la première tâche comme son enfant.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Continue with the rest of the code)
```

## Comment définir la date de début d'une tâche
Définir la date de début est essentiel pour une planification précise. L'exemple utilise une instance `Calendar` pour définir le début du projet et l'attribue à la tâche.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Continue with the rest of the code)
```

## Comment convertir XML en MPP
L'API peut lire un fichier de projet XML et le sauvegarder directement en fichier MPP, facilitant la migration depuis les formats hérités.

```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Continue with the rest of the code)
```

## Comment définir une date limite et ajouter des notes de tâche
Les dates limites aident à maintenir les tâches sur la bonne voie, tandis que les notes offrent du contexte aux membres de l'équipe.

```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Continue with the rest of the code)
```

## Comment configurer les contraintes de tâche et mettre à jour la durée de la tâche
Des contraintes telles que *Finish No Later Than* guident le planificateur. Vous pouvez également changer le format de durée pour refléter les jours estimés.

```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Continue with the rest of the code)
```

## Comment créer des tâches supplémentaires (Gestion des tâches de projet)
La boucle ci‑dessous montre comment générer plusieurs tâches de manière programmatique, une exigence courante lors de l'importation de données en masse.

```java
// Create 10 new tasks
for (int i = 0; i < 10; i++) {
    //... (Continue with the rest of the code)
}
//... (Continue with the rest of the code)
```

## Comment sauvegarder le projet (Exportation en MPP)
Enfin, persistez les modifications en sauvegardant le projet sous forme de fichier MPP.

```java
// Save the Project
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```

En suivant ces étapes, vous avez réussi à **mettre à jour les données de tâche au format MPP à l'aide d'aspose tasks java**. Vous disposez maintenant d'une base solide pour gérer les tâches de projet, créer des tâches récapitulatives, définir des dates de début et convertir des projets XML en MPP.

## Conclusion
Félicitations ! Vous avez terminé un guide complet sur la mise à jour des données de tâche au format MPP à l'aide d'Aspose.Tasks pour Java. Cette bibliothèque puissante simplifie les tâches de gestion de projet, en faisant un outil précieux pour les développeurs Java qui doivent **gérer les tâches de projet** de manière programmatique.

## Frequently Asked Questions

### Q : Où puis‑je trouver la documentation d'Aspose.Tasks pour Java ?
R : La documentation est disponible [ici](https://reference.aspose.com/tasks/java/).

### Q : Comment puis‑je télécharger Aspose.Tasks pour Java ?
R : Vous pouvez le télécharger depuis la [page de diffusion](https://releases.aspose.com/tasks/java/).

### Q : Un essai gratuit est‑il disponible ?
R : Oui, vous pouvez accéder à l'essai gratuit [ici](https://releases.aspose.com/).

### Q : Où puis‑je obtenir du support pour Aspose.Tasks pour Java ?
R : Visitez le forum de support [ici](https://forum.aspose.com/c/tasks/15).

### Q : Proposez‑vous des licences temporaires à des fins de test ?
R : Oui, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Tasks for Java 24.11 (latest)  
**Author:** Aspose