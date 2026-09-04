---
date: 2026-06-25
description: Apprenez comment ajouter une tâche et mettre à jour des fichiers MPP
  en utilisant Aspose.Tasks for Java, une bibliothèque de gestion de projet java qui
  vous permet de créer des fichiers de tâches Microsoft Project et d’enregistrer le
  projet au format MPP.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Comment ajouter une tâche et mettre à jour un fichier MPP dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Comment ajouter une tâche et mettre à jour un fichier MPP dans Aspose.Tasks
url: /fr/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter une tâche et mettre à jour le fichier MPP dans Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez **comment ajouter une tâche** à un fichier Microsoft Project (MPP) existant, puis enregistrerez le planning mis à jour à l'aide d'Aspose.Tasks for Java, une **bibliothèque de gestion de projet Java** de premier plan. Que vous construisiez un planificateur personnalisé, automatisiez des mises à jour en masse ou intégriez des données de projet dans un système plus large, le guide étape par étape ci‑dessous montre exactement comment charger un projet, insérer une nouvelle tâche, définir ses dates et persister le résultat sous forme d'un nouveau document MPP.

## Réponses rapides
- **Que signifie “how to add task” dans ce contexte ?** Cela signifie créer programmaticalement un nouvel élément de travail dans un fichier MPP existant.  
- **Quelle bibliothèque gère l'opération ?** Aspose.Tasks for Java, une bibliothèque robuste de gestion de projet java.  
- **Ai-je besoin d'une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis-je enregistrer le résultat au format MPP ?** Oui—utilisez `project.save(..., SaveFileFormat.Mpp)` pour **save project as mpp**.  
- **Quelle version de Java est requise ?** Java 8 ou supérieure.

## Qu’est-ce que “how to add task” dans un fichier MPP ?
Ajouter une tâche signifie insérer un nouvel élément de travail dans la hiérarchie du projet, définir ses dates de début/fin, et persister la modification dans le fichier MPP. Aspose.Tasks abstrait les détails du format de fichier bas‑niveau, vous permettant de vous concentrer sur la logique métier tout en gérant automatiquement les affectations de ressources, les calendriers et les calculs de dépendances. Il met également à jour toutes les affectations liées et recalcul le planning du projet pour maintenir la cohérence entre les tâches dépendantes.

## Pourquoi utiliser Aspose.Tasks pour Java ?
- **Full compatibility** : Prend en charge 100 % des fonctionnalités de Microsoft Project 2007‑2021 (plus de 150 types de tâches et 200 champs de ressources).  
- **Zero‑dependency** : Aucun COM, Office ou bibliothèque native requis—API Java pure qui fonctionne partout où la JRE est disponible.  
- **Rich feature set** : Inclut le chaînage des tâches, l’allocation des ressources, les champs personnalisés et les rapports intégrés.  
- **High performance** : Traite des projets contenant jusqu’à 10 000 tâches avec moins de 200 Mo de RAM, ce qui le rend idéal pour l’automatisation côté serveur.

## Prérequis
1. **Environnement de développement Java** – JDK 8+ installé et configuré.  
2. **Aspose.Tasks for Java** – Téléchargez depuis la [download page](https://releases.aspose.com/tasks/java/).  
3. **Connaissances de base en Java** – Familiarité avec les classes, les objets et la gestion des dates.  

## Importer les packages
Tout d'abord, importez les classes dont vous avez besoin. Cela vous donne accès à la manipulation de projet, aux propriétés des tâches et à la gestion des dates.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` représente un fichier Microsoft Project chargé en mémoire. `SaveFileFormat` énumère les formats dans lesquels vous pouvez enregistrer, tels que MPP ou PDF. `Task` modélise un élément de travail individuel dans la hiérarchie du projet. `Tsk` fournit des constantes pour les champs de tâche utilisés lors de la définition ou de la récupération de valeurs. `Calendar` offre des utilitaires de date‑heure pour définir les plannings.

## Étape 1 : définir le répertoire de données
```java
String dataDir = "Your Data Directory";
```  
Remplacez "Your Data Directory" par le chemin absolu où se trouve votre fichier MPP source.

## Étape 2 : lire le projet existant
La classe `Project` est l'objet principal d'Aspose.Tasks qui représente un fichier Microsoft Project en mémoire.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
Le constructeur charge **SampleMSP2010.mpp**, vous offrant un modèle d'objet entièrement manipulable.

## Étape 3 : créer une nouvelle tâche (how to add task)
La classe `Task` représente un élément de travail individuel dans la hiérarchie du projet.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Cette ligne **creates task in mpp** ajoute un enfant nommé *Task1* à la tâche racine.

## Étape 4 : définir les dates de début et de fin
La classe `Calendar` fournit des utilitaires de date‑heure ; les mois sont indexés à partir de zéro (par ex., `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Ici nous définissons le planning pour la tâche nouvellement ajoutée. Ajustez les dates pour correspondre à la chronologie de votre projet.

## Étape 5 : enregistrer le projet (save project as mpp)
`SaveFileFormat.Mpp` indique à Aspose.Tasks d'écrire le fichier au format natif Microsoft Project.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
Le projet mis à jour, contenant maintenant la nouvelle tâche, est enregistré sous **AfterLinking.mpp**.

## Problèmes courants et solutions
| Issue | Solution |
|-------|----------|
| **Fichier non trouvé** | Vérifiez que `dataDir` se termine par un séparateur de chemin (`/` ou `\\`) et que le nom du fichier est correct. |
| **Dates incorrectes** | Rappelez‑vous que les mois de `Calendar` sont indexés à zéro ; `Calendar.JULY` correspond à juillet. |
| **Exception de licence** | Installez une licence Aspose.Tasks valide avant d'appeler toute API afin d'éviter les filigranes d'évaluation. |

## Questions fréquentes
**Q : Comment ajouter plusieurs tâches à la fois ?**  
R : Parcourez une collection de noms de tâches et répétez le bloc “create task” à l'intérieur de la boucle.

**Q : Puis‑je définir des champs personnalisés pour la nouvelle tâche ?**  
R : Oui—utilisez `task.set(Tsk.CUSTOM_FIELD_x, value)` où *x* est l'index du champ.

**Q : Est‑il possible de copier une tâche existante comme modèle ?**  
R : Clonez la tâche source (`Task cloned = sourceTask.clone();`) puis ajoutez‑la au parent souhaité.

**Q : Que faire si je dois mettre à jour une tâche existante au lieu d'en ajouter une nouvelle ?**  
R : Récupérez la tâche par ID (`Task existing = project.getRootTask().getChildren().getById(id);`) et modifiez ses propriétés.

**Q : Aspose.Tasks prend‑il en charge l'enregistrement dans d'autres formats comme PDF ou PNG ?**  
R : Oui—utilisez `project.save("output.pdf", SaveFileFormat.Pdf);` ou `SaveFileFormat.Png` pour les représentations visuelles.

---

**Dernière mise à jour :** 2026-06-25  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer un fichier MPP – Créer et enregistrer un projet vide au format MPP avec Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Comment créer un projet – Définir les attributs d'une nouvelle tâche avec Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Créer une liste de tâches Java – Baseline MS Project avec Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}