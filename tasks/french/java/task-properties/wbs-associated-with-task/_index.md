---
title: WBS associé à la tâche dans Aspose.Tasks
linktitle: WBS associé à la tâche dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Maîtrisez WBS avec Aspose.Tasks pour Java - Apprenez à lire et à renuméroter les codes WBS des tâches. Boostez l’efficacité de la gestion de projet !
weight: 36
url: /fr/java/task-properties/wbs-associated-with-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WBS associé à la tâche dans Aspose.Tasks

## Introduction
Bienvenue dans le monde de la gestion de projet avec Aspose.Tasks pour Java ! Dans ce didacticiel, nous aborderons les subtilités de la structure de répartition du travail (WBS) associée aux tâches utilisant Aspose.Tasks pour Java. Que vous soyez un développeur chevronné ou tout juste débutant, ce guide vous aidera à découvrir les éléments essentiels d'une gestion efficace des codes WBS.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Kit de développement Java (JDK) installé sur votre machine.
-  Bibliothèque Aspose.Tasks pour Java téléchargée et ajoutée à votre projet. Vous pouvez l'obtenir de[ici](https://releases.aspose.com/tasks/java/).
## Importer des packages
Assurez-vous d'importer les packages nécessaires pour démarrer votre projet :
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## Lire les codes WBS
Commençons par lire les codes WBS associés aux tâches. Suivez ces étapes:
## Étape 1 : Charger le projet
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Étape 2 : Collecter les tâches
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Étape 3 : analyser et personnaliser
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Cet extrait lit et personnalise les codes WBS associés aux tâches de votre projet.
## Renuméroter les codes WBS de tâches
Explorons maintenant la renumérotation des codes WBS pour les tâches :
## Étape 1 : Charger le projet
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Étape 2 : sélectionner toutes les tâches
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Étape 3 : sortie des codes WBS initiaux
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Étape 4 : Renuméroter les codes WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Étape 5 : Sortie des codes WBS mis à jour
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
En suivant ces étapes, vous renuméroterez efficacement les codes WBS pour les tâches de votre projet.
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès à travailler avec des codes WBS à l'aide d'Aspose.Tasks pour Java. Ces connaissances vous permettront de gérer et de personnaliser efficacement la hiérarchie des tâches de votre projet.
## FAQ
### Q : Où puis-je trouver la documentation d'Aspose.Tasks pour Java ?
 R : La documentation est disponible[ici](https://reference.aspose.com/tasks/java/).
### Q : Comment puis-je télécharger Aspose.Tasks pour Java ?
 R : Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/java/).
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez bénéficier d'un essai gratuit[ici](https://releases.aspose.com/).
### Q : Où puis-je obtenir de l'aide pour Aspose.Tasks pour Java ?
 R : Visitez le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le soutien.
### Q : Puis-je obtenir une licence temporaire pour Aspose.Tasks pour Java ?
 R : Oui, obtenez une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
