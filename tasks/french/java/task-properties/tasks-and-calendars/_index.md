---
date: 2026-02-28
description: Apprenez comment ajouter une tâche à un projet et créer un calendrier
  de tâches Java en utilisant Aspose.Tasks for Java – une bibliothèque puissante pour
  la gestion de projets.
linktitle: Tasks and Calendars in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ajouter une tâche au projet et gérer les calendriers avec Aspose.Tasks pour
  Java
url: /fr/java/task-properties/tasks-and-calendars/
weight: 33
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une tâche à un projet et gérer les calendriers avec Aspose.Tasks pour Java

## Introduction
Prêt à **add task to project** et à garder votre planning parfaitement aligné ? Dans ce guide, nous passerons en revue les étapes essentielles pour créer des tâches, les associer à des calendriers personnalisés et exploiter Aspose.Tasks — une **java project management library** leader de l'industrie. À la fin, vous saurez exactement comment **create task calendar java**‑style, vous offrant un contrôle granulaire sur les échéanciers du projet.

## Quick Answers
- **Quel est le but principal ?** Add task to project et l’associer à un calendrier personnalisé.  
- **Quelle bibliothèque dois-je utiliser ?** Aspose.Tasks for Java – a full‑featured project‑management API.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit est disponible ; une licence commerciale est requise pour la production.  
- **Quelle version du JDK est requise ?** Java 8 or higher.  
- **Combien de temps prend l’implémentation ?** Typiquement moins de 15 minutes pour les scénarios de base.

## Qu’est‑ce que “add task to project” ?
Ajouter une tâche à un projet signifie créer un élément de travail à l’intérieur d’un objet Project et définir ses propriétés (durée, date de début, calendrier, etc.). Cette opération est le bloc de construction de toute application centrée sur la planification.

## Pourquoi utiliser une bibliothèque de gestion de projet Java ?
Une bibliothèque dédiée comme Aspose.Tasks gère le format de fichier MS‑Project complexe, le nivellement des ressources et les calculs de calendrier pour vous. Elle vous évite de réinventer la roue et assure la compatibilité avec les outils standards de l’industrie.

## Prérequis
Avant de plonger dans le tutoriel, assurez‑vous d’avoir les prérequis suivants en place :

- Java Development Kit (JDK) : assurez‑vous que Java est installé sur votre système.
- Bibliothèque Aspose.Tasks : téléchargez et incluez la bibliothèque Aspose.Tasks dans votre projet. Vous pouvez trouver la bibliothèque [ici](https://releases.aspose.com/tasks/java/).

## Importer les packages
Dans votre projet Java, importez les packages nécessaires pour Aspose.Tasks :

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

## Étape 1 : Configurer votre projet
Commencez par créer un nouveau projet Java et ajouter le JAR Aspose.Tasks à votre chemin de construction. Cela vous donne accès à l’API complète.

## Étape 2 : Comment add task to project
Créez une nouvelle instance `Project` et ajoutez une tâche de niveau racine nommée **Task1**. Cela illustre l’opération principale “add task to project”.

```java
Project project = new Project();
Task tsk = project.getRootTask().getChildren().add("Task1");
```

## Étape 3 : Comment create task calendar java
Ajoutez un calendrier standard à votre projet. Les calendriers définissent les jours ouvrés, les jours fériés et d’autres règles de planification.

```java
Calendar cal = project.getCalendars().add("TaskCal1");
```

## Étape 4 : Associer la tâche au calendrier
Liez la tâche créée précédemment au nouveau calendrier afin que son planning respecte les heures de travail du calendrier.

```java
tsk.set(Tsk.CALENDAR, cal);
```

*Astuce :* Répétez ces étapes pour chaque tâche et calendrier supplémentaires dont vous avez besoin. Vous pouvez également personnaliser les exceptions de calendrier (p. ex., les jours non ouvrés) en utilisant l’API `Calendar`.

## Problèmes courants et solutions
- **Tâche ne reflète pas les changements du calendrier :** Assurez‑vous d’appeler `project.updateStructure()` après avoir modifié les calendriers.  
- **NullPointerException lors de l’appel `set` :** Vérifiez que le calendrier a bien été ajouté au projet avant de l’assigner.  
- **Dates incorrectes après import/export :** Utilisez `project.save("output.mpp")` et rouvrez le fichier pour confirmer que les données sont conservées.

## Questions fréquemment posées
### Comment télécharger Aspose.Tasks pour Java ?
Visitez [ce lien](https://releases.aspose.com/tasks/java/) pour télécharger la bibliothèque.

### Où puis‑je trouver la documentation d’Aspose.Tasks ?
Explorez la documentation [ici](https://reference.aspose.com/tasks/java/).

### Une version d’essai gratuite est‑elle disponible ?
Oui, vous pouvez accéder à une version d’essai gratuite [ici](https://releases.aspose.com/).

### Comment obtenir du support pour Aspose.Tasks ?
Rejoignez la communauté sur le [Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir de l’aide.

### Puis‑je acheter une licence pour Aspose.Tasks ?
Oui, vous pouvez acheter une licence [ici](https://purchase.aspose.com/buy).

**Questions / Réponses supplémentaires**

**Q : Puis‑je utiliser Aspose.Tasks pour lire des fichiers Microsoft Project existants ?**  
A : Absolument. La classe `Project` peut charger directement les fichiers `.mpp` et `.xml`.

**Q : La bibliothèque prend‑elle en charge plusieurs calendriers par projet ?**  
A : Oui. Vous pouvez créer autant d’objets `Calendar` que nécessaire et les assigner à différentes tâches.

## Conclusion
Félicitations ! Vous avez appris avec succès comment **add task to project**, créer un calendrier personnalisé et les lier ensemble en utilisant Aspose.Tasks pour Java. Cette combinaison puissante vous permet de créer rapidement des applications robustes et conscientes de la planification.

---

**Dernière mise à jour :** 2026-02-28  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}