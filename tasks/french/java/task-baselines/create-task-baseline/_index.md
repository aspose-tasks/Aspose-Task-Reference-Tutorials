---
date: 2026-01-18
description: Apprenez à créer une liste de tâches en Java et à ajouter une tâche à
  Microsoft Project, en définissant une ligne de base sans MS Project à l'aide d'Aspose.Tasks.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Créer une liste de tâches Java – Ligne de base MS Project avec Aspose.Tasks
url: /fr/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une liste de tâches Java – Baseline MS Project avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous **créerez une liste de tâches Java** en générant une baseline de tâche Microsoft Project à l'aide d'Aspose.Tasks pour Java. Aspose.Tasks vous permet de travailler avec des fichiers Project sans avoir Microsoft Project installé, ainsi vous pouvez **ajouter une tâche à Microsoft Project**, manipuler les ressources, et même **définir une baseline sans MS Project** — le tout depuis du code Java pur.

## Réponses rapides
- **Que fait Aspose.Tasks ?** Il fournit une API Java pour créer, lire et modifier des fichiers Microsoft Project sans MS Project.  
- **Dois-je installer Microsoft Project ?** Non, Aspose.Tasks fonctionne de manière indépendante.  
- **Quelle version de Java est requise ?** JDK 8 ou supérieur.  
- **Puis-je définir une baseline pour une tâche unique ?** Oui, utilisez `setBaseline` avec une liste de tâches.  
- **Une licence est‑elle nécessaire en production ?** Oui, une licence commerciale supprime les limites d'évaluation.

## Qu'est‑ce qu'une baseline de tâche ?
Une baseline de tâche enregistre les valeurs originales prévues de début, de fin et de travail pour une tâche. Elle sert de point de référence pour comparer l'avancement réel au plan initial.

## Pourquoi utiliser Aspose.Tasks pour créer une liste de tâches Java ?
- **Pas de dépendance à MS Project** – idéal pour l'automatisation côté serveur.  
- **Contrôle total** sur les tâches, les ressources et les calendriers via le code Java.  
- **Compatibilité multi‑versions** avec les fichiers Project 2007‑2024.

## Prérequis
1. **Java Development Kit (JDK)** – installez JDK 8 ou plus récent.  
2. **Aspose.Tasks for Java** – téléchargez la bibliothèque depuis le [lien de téléchargement](https://releases.aspose.com/tasks/java/).  

## Importer les packages
Pour commencer à travailler avec Aspose.Tasks dans votre projet Java, importez les packages nécessaires :
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Étape 1 : créer un objet Project
```java
Project project = new Project();
```
Ici nous instancions un nouvel objet `Project` – il représente le fichier MS Project qui contiendra notre liste de tâches.

## Étape 2 : ajouter une tâche au projet
```java
Task task = project.getRootTask().getChildren().add("Task");
```
En utilisant `getRootTask()`, nous accédons à la racine de la hiérarchie du projet et **ajoutons une tâche à Microsoft Project**. La chaîne `"Task"` est le nom de la tâche ; vous pouvez la remplacer par n'importe quelle description dont vous avez besoin.

## Étape 3 : définir une baseline pour les tâches spécifiées
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Pour **définir une baseline sans MS Project**, créez une liste des tâches que vous souhaitez inclure dans la baseline (ici `myList`) et transmettez‑la à `setBaseline`. Remplissez `myList` avec les tâches que vous avez ajoutées si vous ne avez besoin que d’une baseline sélective.

## Étape 4 : définir une baseline pour l'ensemble du projet
```java
project.setBaseline(BaselineType.Baseline);
```
Si vous préférez appliquer une baseline à l’ensemble du projet en un seul appel, invoquez simplement `setBaseline` avec le `BaselineType` souhaité.

## Comment ajouter une tâche à Microsoft Project avec Aspose.Tasks
Au-delà de la tâche unique présentée ci‑dessus, vous pouvez ajouter plusieurs tâches, sous‑tâches et affecter des ressources. Chaque appel à `add()` renvoie un objet `Task` que vous pouvez configurer davantage (durée, date de début, etc.).

## Comment définir une baseline sans MS Project
Aspose.Tasks permet la création de baselines entièrement via le code. Vous pouvez définir différents types de baseline (Baseline, Baseline1‑Baseline10) en modifiant l'énumération `BaselineType`, ce qui vous permet de suivre plusieurs baselines de révision sans jamais ouvrir MS Project.

## Problèmes courants et solutions
- **Baseline non affichée :** Assurez‑vous d’appeler `project.save("output.mpp")` après avoir défini la baseline (l’étape de sauvegarde est omise ici pour plus de concision).  
- **La liste des tâches apparaît vide :** Vérifiez que vous ajoutez les tâches au parent correct (`getRootTask()` ou une sous‑tâche).  
- **Erreurs de incompatibilité de version :** Utilisez le dernier JAR Aspose.Tasks pour garantir la compatibilité avec les formats .mpp plus récents.

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Tasks pour Java sans Microsoft Project installé ?**  
R : Oui, Aspose.Tasks fonctionne de manière indépendante et ne nécessite pas Microsoft Project sur la machine hôte.

**Q : Aspose.Tasks pour Java est‑il compatible avec différentes versions de Microsoft Project ?**  
R : Absolument. La bibliothèque prend en charge les fichiers Project de 2007 jusqu’aux dernières versions 2024.

**Q : Puis‑je manipuler les ressources du projet avec Aspose.Tasks pour Java ?**  
R : Oui, vous pouvez ajouter, mettre à jour et supprimer des ressources par programme, tout comme les tâches.

**Q : Aspose.Tasks pour Java prend‑il en charge la définition des dépendances de tâches ?**  
R : Oui, vous pouvez définir des relations prédécesseur‑successeur à l’aide de la classe `TaskLink`.

**Q : Un support technique est‑il disponible pour Aspose.Tasks pour Java ?**  
R : Oui, vous pouvez obtenir de l’aide via le [forum de support](https://forum.aspose.com/c/tasks/15), où le personnel d’Aspose et la communauté répondent aux questions.

## Conclusion
En suivant ces étapes, vous avez appris comment **créer une liste de tâches Java**, **ajouter une tâche à Microsoft Project**, et **définir une baseline sans MS Project** à l’aide d’Aspose.Tasks. Cette approche simplifie l’automatisation des projets, élimine le besoin d’installations de Project sur le bureau, et vous offre un contrôle programmatique complet sur les données de votre projet.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose