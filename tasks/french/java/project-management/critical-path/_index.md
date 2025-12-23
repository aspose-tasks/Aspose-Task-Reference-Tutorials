---
date: 2025-12-23
description: Apprenez à créer des dépendances de tâches et à calculer le chemin critique
  dans MS Project en utilisant Aspose.Tasks pour Java. Guide étape par étape pour
  la gestion de projet.
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Créer des dépendances de tâches et calculer le chemin critique dans Aspose.Tasks
url: /fr/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer des dépendances de tâches et calculer le chemin critique dans Aspose.Tasks

## Introduction
Dans ce tutoriel, **vous apprendrez comment créer des dépendances de tâches** et calculer le chemin critique dans un fichier MS Project en utilisant Aspose.Tasks pour Java. Comprendre et visualiser le chemin critique vous aide à maintenir votre projet dans les délais, tandis que le lien correct des tâches garantit que tout retard est immédiatement visible. Parcourons l’ensemble du processus, de la configuration de l’environnement à l’affichage du chemin critique final.

## Quick Answers
- **Quelle est la première étape ?** Configurez votre projet Java et ajoutez la bibliothèque Aspose.Tasks.  
- **Quel mode doit être activé ?** `CalculationMode.Automatic` (activer le calcul automatique).  
- **Comment lier les tâches ?** Utilisez `project.getTaskLinks().add(...)` pour créer des dépendances de tâches.  
- **Comment afficher le chemin critique ?** Parcourez `project.getCriticalPath()` et affichez le nom de chaque tâche.  
- **Ai‑je besoin d’une licence ?** Oui, une licence valide Aspose.Tasks est requise pour une utilisation en production.

## What is “create task dependencies”?
Créer des dépendances de tâches signifie définir des relations (par ex., Fin‑à‑Début) entre les tâches afin que le planning reflète les contraintes du monde réel. Dans Aspose.Tasks, cela se fait via des objets `TaskLink`.

## Why calculate the critical path in MS Project?
Le **chemin critique de MS Project** montre la séquence la plus longue de tâches dépendantes qui détermine la durée minimale du projet. En le calculant, vous pouvez rapidement identifier les tâches qui ne peuvent pas glisser sans affecter le calendrier global—essentiel pour les applications de **gestion de projet Java** efficaces.

## Prerequisites
Avant de commencer, assurez‑vous d’avoir :

1. Le Java Development Kit (JDK) installé sur votre système.  
2. La bibliothèque Aspose.Tasks pour Java téléchargée et ajoutée à votre projet. Vous pouvez la télécharger [ici](https://releases.aspose.com/tasks/java/).  

## Import Packages
Pour commencer, importez les packages nécessaires dans votre classe Java :
```java
import com.aspose.tasks.*;
```

## How to set automatic calculation?
Définir le mode de calcul sur automatique garantit que toute modification des tâches ou des liens met immédiatement à jour le planning, y compris le chemin critique.
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## Step‑by‑Step Guide

### Step 1: Set Up Data Directory
Définissez le chemin du dossier qui contient votre fichier MS Project.
```java
String dataDir = "Your Data Directory";
```

### Step 2: Load MS Project File
Chargez le fichier de projet existant (par ex., *New project 2013.mpp*) à l’aide d’Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### Step 3: Add Tasks
Créez trois sous‑tâches simples que nous lierons plus tard.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### Step 4: Create Task Links (create task dependencies)
Définissez les dépendances entre les tâches. Ici nous utilisons un lien Fin‑à‑Début, qui est le type le plus courant.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### Step 5: Display Critical Path (display critical path)
Récupérez et affichez le chemin critique. La méthode `getCriticalPath()` renvoie la liste des tâches qui forment la chaîne critique.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### Step 6: Confirm Completion
Affichez un message convivial une fois le processus terminé.
```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Problème | Solution |
|----------|----------|
| **Le chemin critique est vide** | Assurez‑vous que `CalculationMode.Automatic` est défini avant d’ajouter les liens. |
| **Les tâches ne sont pas liées** | Vérifiez que vous avez ajouté des objets `TaskLink` pour chaque dépendance. |
| **Exception de licence** | Chargez une licence valide Aspose.Tasks avant de créer l’instance `Project`. |

## FAQ's
### Q : Puis‑je utiliser Aspose.Tasks pour Java avec n’importe quelle version de fichiers MS Project ?
R : Oui, Aspose.Tasks pour Java prend en charge diverses versions de fichiers MS Project, y compris les fichiers .mpp de MS Project 2003 à MS Project 2019.  

### Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Tasks pour Java ?
R : Oui, vous pouvez télécharger un essai gratuit [ici](https://releases.aspose.com/).  

### Q : Où puis‑je trouver du support pour Aspose.Tasks pour Java ?
R : Vous pouvez obtenir du support sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).  

### Q : Puis‑je acheter une licence temporaire pour Aspose.Tasks pour Java ?
R : Oui, vous pouvez acheter une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).  

### Q : Comment acheter Aspose.Tasks pour Java ?
R : Vous pouvez acheter Aspose.Tasks pour Java sur le site web [ici](https://purchase.aspose.com/buy).

## Conclusion
En suivant ces étapes, vous avez **créé des dépendances de tâches**, activé le **calcul automatique**, et affiché avec succès le **chemin critique** de votre fichier MS Project. Ce flux de travail vous donne un contrôle complet sur la logique du planning et vous aide à garder vos projets sur la bonne voie grâce au code de **gestion de projet** basé sur Java.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}