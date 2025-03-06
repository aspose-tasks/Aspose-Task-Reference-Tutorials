---
title: Calculs de pourcentage terminés pour les tâches dans Aspose.Tasks
linktitle: Calculs de pourcentage terminés pour les tâches dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Explorez Aspose.Tasks pour Java et rationalisez le suivi de l'avancement du projet. Calculez sans effort les pourcentages de tâches pour une gestion de projet efficace.
weight: 25
url: /fr/java/task-properties/percentage-complete-calculations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calculs de pourcentage terminés pour les tâches dans Aspose.Tasks

## Introduction
Bienvenue dans notre guide détaillé sur la maîtrise des calculs de pourcentage de tâches à l'aide d'Aspose.Tasks pour Java. Aspose.Tasks est une puissante bibliothèque Java conçue pour travailler avec des fichiers Microsoft Project, offrant un ensemble robuste de fonctionnalités pour la gestion de projet. Dans ce didacticiel, nous nous concentrerons sur les calculs de pourcentage achevé, vous fournissant les connaissances nécessaires pour surveiller et analyser efficacement l'avancement du projet.
## Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
- Environnement de développement Java : assurez-vous que Java est installé sur votre système.
-  Bibliothèque Aspose.Tasks : téléchargez la bibliothèque Aspose.Tasks pour Java à partir de[ce lien](https://releases.aspose.com/tasks/java/).
## Importer des packages
Commençons par importer les packages nécessaires à votre projet Aspose.Tasks for Java. Incluez l'extrait de code suivant dans votre projet :
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
Maintenant, décomposons chaque étape avec des explications détaillées.
## Étape 1 : Importation de packages
Dans la première étape, nous importons les packages nécessaires pour configurer notre projet Aspose.Tasks.
## Étape 2 : Définition du répertoire de documents
 Définissez le chemin d'accès à votre répertoire de documents à l'aide du`dataDir`variable. Assurez-vous que votre fichier Microsoft Project, tel que « Software Development.mpp », se trouve dans ce répertoire.
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
```
## Étape 3 : Chargement du projet
 Initialiser un nouveau`Project` objet et chargez votre fichier Microsoft Project dans l’instance de projet.
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## Étape 4 : Récupération de la collection de tâches
 Récupérez la tâche racine du projet et récupérez ses enfants sous forme de collection en utilisant`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## Étape 5 : Impression du pourcentage terminé
Parcourez chaque tâche de la collection et imprimez le pourcentage achevé, le pourcentage de travail achevé et le pourcentage physique achevé.
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
Répétez ces étapes pour chaque tâche de votre projet afin d'avoir un aperçu de la progression de chacune.
## Conclusion
Toutes nos félicitations! Vous maîtrisez avec succès les calculs de pourcentage de tâches à l'aide d'Aspose.Tasks pour Java. Cette puissante bibliothèque permet aux développeurs de gérer et d'analyser efficacement l'avancement du projet.
## FAQ
### Q : Où puis-je trouver la documentation Aspose.Tasks ?
 La documentation est disponible[ici](https://reference.aspose.com/tasks/java/).
### Q : Comment puis-je télécharger la bibliothèque Aspose.Tasks pour Java ?
 Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/java/).
### Q : Existe-t-il un essai gratuit ?
Oui, vous pouvez accéder à un essai gratuit[ici](https://releases.aspose.com/).
### Q : Où puis-je obtenir de l'aide pour Aspose.Tasks ?
 Visitez le forum d'assistance[ici](https://forum.aspose.com/c/tasks/15).
### Q : Comment puis-je obtenir une licence temporaire ?
 Vous pouvez acquérir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
