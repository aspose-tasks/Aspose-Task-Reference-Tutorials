---
date: 2025-12-28
description: Apprenez à ajouter des tâches et à mettre à jour des fichiers MPP à l'aide
  d'Aspose.Tasks pour Java, une bibliothèque de gestion de projets Java. Suivez notre
  guide étape par étape pour créer une tâche dans un fichier MPP et enregistrer le
  projet au format MPP.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment ajouter une tâche et mettre à jour le fichier MPP dans Aspose.Tasks
url: /fr/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter une tâche et mettre à jour un fichier MPP avec Aspose.Tasks

## Introduction
Dans ce tutoriel, nous vous montrons **comment ajouter une tâche** et mettre à jour un fichier MPP à l’aide d’Aspose.Tasks pour Java, une bibliothèque **java de gestion de projet** de premier plan. Que vous construisiez un planificateur personnalisé ou que vous ayez besoin de modifier des plans de projet existants de façon programmatique, ce guide vous accompagne à chaque étape — du chargement du fichier à l’enregistrement des modifications dans un nouveau document MPP.

## Réponses rapides
- **Que signifie « how to add task » dans ce contexte ?** Il s’agit de créer programmatique une nouvelle tâche dans un fichier Microsoft Project (MPP) existant.  
- **Quelle bibliothèque gère l’opération ?** Aspose.Tasks pour Java, une bibliothèque java de gestion de projet robuste.  
- **Ai‑je besoin d’une licence ?** Une version d’essai gratuite suffit pour le développement ; une licence commerciale est requise en production.  
- **Puis‑je enregistrer le résultat au format MPP ?** Oui — utilisez `project.save(..., SaveFileFormat.Mpp)` pour **save project as mpp**.  
- **Quelle version de Java est requise ?** Java 8 ou supérieure.

## Qu’est‑ce que « how to add task » dans un fichier MPP ?
Ajouter une tâche consiste à insérer un nouvel élément de travail dans la hiérarchie du projet, à définir ses dates de début/fin, puis à persister la modification dans le fichier MPP. Aspose.Tasks masque les détails bas‑niveau du format de fichier, vous permettant de vous concentrer sur la logique métier.

## Pourquoi utiliser Aspose.Tasks pour Java ?
- **Compatibilité totale** avec les fichiers Microsoft Project 2007‑2021.  
- **Pas de COM ni d’installation d’Office** requis — API purement Java.  
- **Ensemble de fonctionnalités riche** : liaison de tâches, affectation de ressources, champs personnalisés, etc.  
- **Performance élevée** pour les gros fichiers de projet, idéal pour l’automatisation côté serveur.

## Prérequis
1. **Environnement de développement Java** – JDK 8+ installé et configuré.  
2. **Aspose.Tasks pour Java** – Téléchargez depuis la [download page](https://releases.aspose.com/tasks/java/).  
3. **Connaissances de base en Java** – Familiarité avec les classes, objets et la gestion des dates.  

## Importer les packages
Tout d’abord, importez les classes dont vous aurez besoin. Cela vous donne accès à la manipulation de projet, aux propriétés des tâches et à la gestion des dates.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Étape 1 : Définir le répertoire de données
```java
String dataDir = "Your Data Directory";
```
Remplacez `"Your Data Directory"` par le chemin absolu où se trouve votre fichier MPP source.

## Étape 2 : Lire le projet existant
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
Le constructeur `Project` charge **SampleMSP2010.mpp**, vous offrant un modèle d’objet manipulable.

## Étape 3 : Créer une nouvelle tâche (how to add task)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Cette ligne **creates task in mpp** en ajoutant un enfant nommé *Task1* à la tâche racine.

## Étape 4 : Définir les dates de début et de fin
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Ici nous définissons le planning de la tâche nouvellement ajoutée. Ajustez les dates selon votre calendrier de projet.

## Étape 5 : Enregistrer le projet (save project as mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
Le projet mis à jour, contenant maintenant la nouvelle tâche, est persistant sous le nom **AfterLinking.mpp**.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Fichier introuvable** | Vérifiez que `dataDir` se termine par un séparateur de chemin (`/` ou `\\`) et que le nom du fichier est correct. |
| **Dates incorrectes** | Souvenez‑vous que les mois du `Calendar` sont indexés à zéro ; `Calendar.JULY` correspond bien à juillet. |
| **Exception de licence** | Installez une licence valide d’Aspose.Tasks avant d’appeler toute API afin d’éviter les filigranes d’évaluation. |

## FAQ
### Q : Aspose.Tasks pour Java peut‑il gérer des structures de projet complexes ?
R : Oui, Aspose.Tasks pour Java offre des fonctionnalités robustes pour gérer efficacement des structures de projet complexes.  
### Q : Existe‑t‑il une version d’essai gratuite d’Aspose.Tasks pour Java ?
R : Oui, vous pouvez télécharger une version d’essai gratuite depuis le [website](https://releases.aspose.com/).  
### Q : Aspose.Tasks pour Java prend‑il en charge différentes versions de fichiers Microsoft Project ?
R : Absolument, Aspose.Tasks pour Java supporte plusieurs versions de fichiers Microsoft Project, y compris les formats MPP, MPT et XML.  
### Q : Puis‑je obtenir des licences temporaires pour Aspose.Tasks pour Java ?
R : Oui, des licences temporaires sont disponibles à des fins de test. Vous pouvez les obtenir sur la [temporary license page](https://purchase.aspose.com/temporary-license/).  
### Q : Où puis‑je obtenir de l’aide ou du support concernant Aspose.Tasks pour Java ?
R : Vous pouvez consulter le [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) pour toute assistance ou question.

## Questions fréquemment posées
**Q : Comment ajouter plusieurs tâches en même temps ?**  
R : Parcourez une collection de noms de tâches et répétez le bloc « create task » à l’intérieur de la boucle.

**Q : Puis‑je définir des champs personnalisés pour la nouvelle tâche ?**  
R : Oui—utilisez `task.set(Tsk.CUSTOM_FIELD_x, value)` où *x* représente l’indice du champ.

**Q : Est‑il possible de copier une tâche existante comme modèle ?**  
R : Clonez la tâche source (`Task cloned = sourceTask.clone();`) puis ajoutez‑la au parent souhaité.

**Q : Que faire si je dois mettre à jour une tâche existante au lieu d’en créer une nouvelle ?**  
R : Récupérez la tâche par son ID (`Task existing = project.getRootTask().getChildren().getById(id);`) et modifiez ses propriétés.

**Q : Aspose.Tasks prend‑il en charge l’enregistrement vers d’autres formats comme PDF ou PNG ?**  
R : Oui—utilisez `project.save("output.pdf", SaveFileFormat.Pdf);` ou `SaveFileFormat.Png` pour des représentations visuelles.

---

**Dernière mise à jour :** 2025-12-28  
**Testé avec :** Aspose.Tasks pour Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}