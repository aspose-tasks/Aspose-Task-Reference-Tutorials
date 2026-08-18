---
date: 2026-02-20
description: Explorez comment ajouter une tâche à un projet et gérer les durées avec
  Aspose.Tasks pour Java. Apprenez à définir la durée et à convertir facilement la
  durée.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ajouter une tâche au projet et gérer les durées avec Aspose.Tasks
url: /fr/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une tâche au projet et gérer les durées avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez **comment ajouter une tâche à un projet** et contrôler sa durée à l'aide d'Aspose.Tasks pour Java. Que vous construisiez un nouvel outil de planification de projet ou que vous étendiez une solution existante, maîtriser la gestion des durées des tâches est essentiel pour une planification et un reporting précis.

## Réponses rapides
- **Que signifie « ajouter une tâche à un projet » ?** Cela crée un nouvel objet Task sous la racine du projet ou sous une tâche de synthèse spécifique.  
- **Quelle classe représente une durée ?** `com.aspose.tasks.Duration`.  
- **Comment définir une durée ?** Utilisez `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Puis-je convertir une durée en une autre unité ?** Oui, appelez `duration.convert(TimeUnitType.Hour)` ou tout autre `TimeUnitType`.  
- **Ai-je besoin d’une licence pour la production ?** Une licence valide d'Aspose.Tasks est requise pour une utilisation commerciale.

## Qu’est‑ce que « ajouter une tâche à un projet » ?
Ajouter une tâche à un projet signifie créer un objet `Task` et l’attacher à la hiérarchie des tâches du projet. Cette opération est la première étape avant de pouvoir définir le travail, les ressources ou la durée de cette tâche.

## Pourquoi gérer les durées des tâches ?
Des durées précises permettent d’obtenir des échéanciers réalistes, une allocation des ressources efficace et une analyse du chemin critique. Avec Aspose.Tasks, vous pouvez définir, lire, convertir et ajuster les durées de façon programmatique, vous offrant un contrôle complet sur les plannings de projet.

## Prérequis
- Java Development Kit (JDK) : Assurez‑vous d’avoir Java installé sur votre machine. Vous pouvez le télécharger [ici](https://www.oracle.com/java/technologies/javase-downloads.html).
- Bibliothèque Aspose.Tasks : Téléchargez et incluez la bibliothèque Aspose.Tasks dans votre projet. Vous pouvez la trouver [ici](https://releases.aspose.com/tasks/java/).

## Importer les packages
Dans votre projet Java, importez les packages nécessaires pour travailler avec Aspose.Tasks :
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Étape 1 : Configurer votre projet
```java
// Create a new project
Project project = new Project();
```

## Étape 2 : Ajouter une nouvelle tâche (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Comment définir la durée
Maintenant que la tâche existe, vous pouvez définir sa longueur. Par défaut, les durées sont exprimées en jours.

## Étape 3 : Obtenir et convertir la durée de la tâche
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Comment convertir une durée
La méthode `convert` vous permet de traduire un `Duration` d’un `TimeUnitType` à un autre (par ex., jours → heures, semaines → jours).

## Étape 4 : Mettre à jour la durée de la tâche à 1 semaine
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Étape 5 : Réduire la durée de la tâche
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

En suivant ces étapes, vous avez réussi à **ajouter une tâche à un projet** et à gérer sa durée à l’aide d’Aspose.Tasks pour Java.

## Pièges courants et conseils
- **Piège :** Oublier de convertir la durée avant d’effectuer des opérations arithmétiques peut entraîner des résultats incorrects. Vérifiez toujours l’unité avec `duration.getTimeUnit()`.
- **Conseil :** Utilisez `project.getDuration(value, TimeUnitType)` pour créer des durées dans l’unité souhaitée plutôt que de les convertir ultérieurement.
- **Piège :** Définir une durée négative déclenchera une exception. Assurez‑vous de valider les valeurs d’entrée.

## Conclusion
Dans ce guide, nous avons vu comment **ajouter une tâche à un projet**, lire sa durée par défaut, **définir la durée** et **convertir la durée** vers différentes unités de temps. Vous pouvez désormais intégrer ces techniques dans des applications de planification plus vastes pour une planification de projet précise.

## FAQ
### Aspose.Tasks est‑il compatible avec toutes les versions de Java ?
Aspose.Tasks est compatible avec Java 6 et les versions ultérieures.

### Puis‑je utiliser Aspose.Tasks pour des projets commerciaux ?
Oui, vous pouvez utiliser Aspose.Tasks pour des projets personnels et commerciaux. Consultez [ici](https://purchase.aspose.com/buy) les détails de la licence.

### Où puis‑je trouver un support et des ressources supplémentaires ?
Visitez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le support communautaire et les discussions.

### Comment obtenir une licence temporaire à des fins de test ?
Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/) pour les tests et l’évaluation.

### Existe‑t‑il un essai gratuit pour Aspose.Tasks ?
Oui, vous pouvez accéder à l’essai gratuit [ici](https://releases.aspose.com/) pour explorer Aspose.Tasks avant d’effectuer un achat.

## Questions fréquemment posées

**Q : Comment modifier la durée d’une tâche après l’avoir définie ?**  
R : Récupérez la durée actuelle avec `task.get(Tsk.DURATION)`, modifiez‑la (par ex., `add`, `subtract` ou `convert`), puis réaffectez‑la avec `task.set(Tsk.DURATION, newDuration)`.

**Q : Puis‑je définir une durée en minutes ?**  
R : Oui, utilisez `TimeUnitType.Minute` lors de l’appel à `project.getDuration(value, TimeUnitType.Minute)`.

**Q : La modification de la durée met‑elle automatiquement à jour les dates de début et de fin de la tâche ?**  
R : Seulement si le mode de planification du projet est réglé sur automatique. Sinon, il peut être nécessaire de recalculer le planning avec `project.calculateCriticalPath()`.

**Q : Est‑il possible de récupérer la durée sous forme de nombre brut ?**  
R : Appelez `duration.getTimeSpan()` pour obtenir la valeur numérique dans l’unité de temps actuelle.

**Q : Que se passe‑t‑il si je soustrais plus que la durée actuelle ?**  
R : L’API lèvera une `ArgumentOutOfRangeException`. Validez toujours que la durée résultante reste positive.

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}