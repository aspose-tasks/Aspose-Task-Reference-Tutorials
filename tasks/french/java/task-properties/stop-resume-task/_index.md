---
date: 2026-02-26
description: Apprenez à reprendre une tâche et à arrêter une tâche dans Aspose.Tasks
  pour Java, y compris le filtrage des tâches par date pour un contrôle précis du
  projet.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment reprendre une tâche et arrêter une tâche dans Aspose.Tasks
url: /fr/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment reprendre une tâche et arrêter une tâche dans Aspose.Tasks

## Introduction
Si vous développez une solution de gestion de projet basée sur Java, vous aurez souvent besoin de **mettre en pause** une tâche temporairement, puis de **la reprendre** plus tard. Aspose.Tasks for Java facilite cela grâce à des propriétés intégrées pour arrêter et reprendre les tâches. Dans ce tutoriel, vous découvrirez **comment reprendre une tâche** et **comment arrêter une tâche** de manière programmatique, et vous verrez également comment **filtrer les tâches par date** afin de ne travailler qu'avec les éléments pertinents de votre planning.

## Quick Answers
- **Que signifie « stop » pour une tâche ?** Cela définit une date d'arrêt, mettant le travail en pause après ce point.  
- **Comment puis‑je reprendre une tâche arrêtée ?** En attribuant une date de reprise postérieure à la date d'arrêt.  
- **Puis‑je limiter l'opération à une plage de dates ?** Oui – utilisez une date minimale pour filtrer les tâches.  
- **Quelle version de la bibliothèque est requise ?** Toute version récente d'Aspose.Tasks for Java (l'API reste stable).  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise pour la production.

## What is “how to resume task” in Aspose.Tasks?
Reprendre une tâche signifie simplement fournir une date **RESUME** sur un objet `Task`. Lorsque le moteur du projet traite le planning, le travail continuera à partir de cette date. Ceci est particulièrement utile pour gérer les interruptions telles que l'indisponibilité de ressources ou des dépendances externes.

## Why use the stop/resume feature?
- **Contrôle des échéances :** Mettre en pause le travail sans supprimer la tâche.  
- **Rapports précis :** Afficher des dates de début/fin réalistes dans les diagrammes de Gantt.  
- **Automatisation facile :** Combiner avec des filtres de dates pour mettre à jour de nombreuses tâches en une fois.

## Prérequis
Avant de commencer, assurez‑vous d'avoir :

- Une bonne maîtrise des fondamentaux Java.  
- Le JDK installé sur votre machine.  
- La bibliothèque Aspose.Tasks for Java ajoutée à votre projet (téléchargez‑la depuis [here](https://releases.aspose.com/tasks/java/)).  

## Import Packages
Tout d'abord, importez les classes requises afin de pouvoir travailler avec les projets et les tâches.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## Étape 1 : Initialiser le projet et le collecteur
Créez une instance `Project` pointant vers votre fichier MPP et configurez un `ChildTasksCollector` pour rassembler chaque tâche de la hiérarchie.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## Étape 2 : Définir une date minimale pour le filtrage
Si vous ne souhaitez travailler qu'avec les tâches possédant des dates d'arrêt ou de reprise significatives, définissez une **date minimale**. C’est le cœur de la technique de *filtrer les tâches par date*.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## Étape 3 : Parcourir, vérifier et afficher les valeurs d'arrêt/reprise
Parcourez maintenant les tâches collectées, appliquez la logique **how to stop task**, et affichez les dates. Le code montre également **how to resume task** en lisant la propriété `RESUME`.

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **Astuce :** Remplacez les appels `System.out.println` par votre propre logique (par ex., mise à jour des dates, journalisation dans un fichier, ou modification des objets de tâche) pour réellement *arrêter* ou *reprendre* les tâches selon les besoins.

## Problèmes courants et solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| `NullPointerException` sur `tsk.get(Tsk.STOP)` | La tâche n’a aucune date d’arrêt définie. | Vérifiez `null` avant d’appeler `.before(minDate)`. |
| Les dates apparaissent comme `NA` même après définition | La date minimale est trop récente. | Utilisez une `minDate` plus ancienne ou supprimez le filtre. |
| Les modifications ne sont pas reflétées dans le MPP enregistré | Le projet n’est pas enregistré après les modifications. | Appelez `project.save("output.mpp");` après la mise à jour des tâches. |

## Frequently Asked Questions

### Aspose.Tasks for Java convient‑il aux projets à grande échelle ?
Absolument ! Aspose.Tasks for Java est conçu pour gérer des projets de tailles variées, garantissant efficacité et fiabilité.

### Puis‑je personnaliser la date d'arrêt et de reprise des tâches ?
Oui, l’exemple fourni permet de définir la date minimale avec la flexibilité requise selon les besoins de votre projet.

### Où puis‑je trouver un support supplémentaire pour Aspose.Tasks for Java ?
Visitez le [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) pour le support communautaire et les discussions.

### Existe‑t‑il un essai gratuit pour Aspose.Tasks for Java ?
Oui, vous pouvez accéder à l’[essai gratuit](https://releases.aspose.com/) pour explorer les fonctionnalités avant d’acheter.

### Comment obtenir une licence temporaire pour Aspose.Tasks for Java ?
Vous pouvez acquérir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/) à des fins de test.

**Questions / Réponses supplémentaires**

**Q : Comment définir réellement une nouvelle date d’arrêt pour une tâche ?**  
A : Utilisez `tsk.set(Tsk.STOP, new Date(...));` puis enregistrez le projet.

**Q : Puis‑je filtrer les tâches par une plage spécifique au lieu d’une simple date minimale ?**  
A : Oui—comparez à la fois `before` et `after` avec vos dates de début et de fin.

**Q : L’API recalcule‑t‑elle automatiquement le planning après modification des dates d’arrêt/reprise ?**  
A : Après modification des dates, appelez `project.calculateCriticalPath();` pour rafraîchir le planning.

## Conclusion
Dans ce guide, nous avons couvert **how to resume task** et **how to stop task** en utilisant Aspose.Tasks for Java, ainsi qu’une méthode pratique pour **filter tasks by date**. En intégrant ces extraits dans votre application, vous obtenez un contrôle granulaire sur les échéances du projet et pouvez automatiser les ajustements du planning en toute confiance.

---

**Dernière mise à jour :** 2026-02-26  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}