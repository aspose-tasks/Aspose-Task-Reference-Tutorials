---
date: 2026-03-29
description: Apprenez à replanifier le travail non achevé, mettre à jour le travail
  du projet et enregistrer les fichiers MS Project au format XML en utilisant Aspose.Tasks
  pour Java.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Replanifier le travail non terminé et mettre à jour les fichiers MS Project
  avec Aspose.Tasks
url: /fr/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Replanifier le travail non terminé et mettre à jour les fichiers MS Project avec Aspose.Tasks

## Introduction
Microsoft Project est un outil de gestion de projet largement utilisé qui aide les équipes à planifier les tâches, allouer les ressources et suivre les échéances. Aspose.Tasks for Java offre aux développeurs une API riche pour manipuler les fichiers Microsoft Project de manière programmatique. Dans ce tutoriel, vous apprendrez comment **mettre à jour le travail du projet**, **replanifier le travail non terminé**, et **enregistrer le fichier MS Project** au format XML en utilisant Aspose.Tasks for Java.

## Réponses rapides
- **Que signifie « replanifier le travail non terminé » ?** Il déplace tout travail de tâche restant pour commencer après une date choisie, en laissant les parties terminées intactes.  
- **Quelle méthode marque le travail comme complet ?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Comment persister les modifications ?** Utilisez `project.save(<path>, SaveFileFormat.Xml)`.  
- **Ai-je besoin d’une licence pour la production ?** Oui, une licence valide d’Aspose.Tasks est requise pour une utilisation commerciale.  
- **Quelle version de Java est prise en charge ?** Java 8 et les versions ultérieures sont entièrement prises en charge.

## Qu’est‑ce que « replanifier le travail non terminé » ?
Le replanification du travail non terminé ajuste les dates de début de toutes les tâches qui ne sont pas encore terminées, les repoussant pour commencer après une date de coupure spécifiée. Cela est utile lorsqu’un calendrier de projet est modifié en raison de retards ou de changements de périmètre.

## Pourquoi utiliser Aspose.Tasks pour mettre à jour le travail du projet et replanifier les tâches ?
- **Fine‑grained control:** Définir directement les pourcentages d’achèvement du travail et les dates.  
- **No UI required:** Automatiser les mises à jour en masse sur de nombreux fichiers de projet.  
- **Cross‑platform:** Fonctionne sur tout système exécutant Java.  
- **Preserves data integrity:** Toutes les dépendances, contraintes et ressources restent cohérentes.

## Prérequis
Avant de commencer, assurez-vous de disposer de ce qui suit :
1. Java Development Kit (JDK) installé sur votre système.  
2. Bibliothèque Aspose.Tasks for Java. Vous pouvez la télécharger depuis [ici](https://releases.aspose.com/tasks/java/).  
3. Compréhension de base du langage de programmation Java.

## Importer les packages
Tout d'abord, importez les packages nécessaires dans votre code Java :
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

## Étape 1 : Configurer le projet
Initialisez un nouvel objet `Project`, définissez les tâches, définissez les durées et établissez les dépendances. Cela crée le projet de base que nous mettrons ensuite à jour et replanifierons.
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

## Étape 2 : Mettre à jour le travail du projet
Marquez le travail comme complet jusqu’à une date spécifique. Cette étape montre l’opération **update project work**, qui est souvent la première action avant le replanification.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Étape 3 : Replanifier le travail non terminé
Nous déplaçons maintenant tout travail restant (non terminé) afin qu’il commence après la même date de coupure. C’est la fonctionnalité principale de **reschedule uncompleted work**.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Conclusion
Dans ce tutoriel, nous avons vu comment **update project work**, **reschedule uncompleted work**, et **save the MS Project file** au format XML en utilisant Aspose.Tasks for Java. Ces capacités sont essentielles lorsque les calendriers de projet doivent être ajustés en fonction de l’avancement réel ou des priorités commerciales changeantes.

## FAQ
### Q : Aspose.Tasks for Java peut‑il gérer des structures de projet complexes ?
R : Oui, Aspose.Tasks for Java fournit des API robustes pour gérer efficacement les tâches, les dépendances, les ressources et d’autres éléments du projet.

### Q : Existe‑t‑il une version d’essai disponible pour Aspose.Tasks for Java ?
R : Oui, vous pouvez obtenir un essai gratuit depuis [ici](https://releases.aspose.com/).

### Q : Comment obtenir du support pour Aspose.Tasks for Java ?
R : Vous pouvez visiter le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour toute assistance ou question.

### Q : Puis‑je acheter une licence temporaire pour Aspose.Tasks for Java ?
R : Oui, des licences temporaires sont disponibles à l’achat [ici](https://purchase.aspose.com/temporary-license/).

### Q : Où puis‑je trouver la documentation détaillée pour Aspose.Tasks for Java ?
R : Vous pouvez consulter la documentation [ici](https://reference.aspose.com/tasks/java/) pour des guides complets et des références d’API.

## Questions fréquemment posées supplémentaires

**Q : Comment garantir que le fichier enregistré est compatible avec les versions antérieures de Microsoft Project ?**  
R : Enregistrez le projet avec `SaveFileFormat.Xml` ; le XML est largement pris en charge par les différentes versions de Project.

**Q : Puis‑je replanifier uniquement un sous‑ensemble de tâches au lieu de l’ensemble du projet ?**  
R : Oui, vous pouvez parcourir des tâches spécifiques et appeler `task.setStart(date)` après avoir calculé la nouvelle date de début.

**Q : Que se passe‑t‑il avec les allocations de ressources lors du replanification du travail non terminé ?**  
R : Les affectations de ressources sont automatiquement déplacées pour correspondre aux nouvelles dates de début des tâches, préservant la logique d’allocation.

**Q : Est‑il possible d’annuler une opération de replanification programmatiquement ?**  
R : Vous pouvez recharger le fichier de projet original (ou une sauvegarde) pour annuler les modifications.

**Q : Aspose.Tasks prend‑il en charge l’enregistrement dans d’autres formats comme .mpp ?**  
R : Absolument. Utilisez `SaveFileFormat.MPP` pour enregistrer au format natif Microsoft Project.

---

**Dernière mise à jour :** 2026-03-29  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}