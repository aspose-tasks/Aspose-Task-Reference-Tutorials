---
date: 2026-01-07
description: Apprenez à ajouter une ressource à un projet et à gérer les propriétés
  de délai de nivellement des affectations de ressources à l’aide d’Aspose.Tasks pour
  Java.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment ajouter une ressource à un projet et gérer les propriétés de délai
  de nivellement dans Aspose.Tasks
url: /fr/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter une ressource à un projet et gérer les propriétés de délai de nivellement dans Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez **comment ajouter une ressource à un projet** tout en gérant les propriétés de délai de nivellement pour les affectations de ressources avec Aspose.Tasks for Java. Que vous construisiez un moteur de planification ou que vous automatisiez des mises à jour de projet, maîtriser ces étapes vous permet de garder vos données de projet précises sans avoir besoin de Microsoft Project installé.

## Réponses rapides
- **Que signifie « ajouter une ressource à un projet » ?** Cela crée une nouvelle entrée de ressource qui peut être affectée aux tâches.  
- **Puis‑je définir un délai de nivellement après l’affectation ?** Oui, en utilisant les champs `Asn.DELAY` ou `Asn.LEVELING_DELAY`.  
- **Ai‑je besoin d’une licence pour exécuter ce code ?** Une version d’essai gratuite suffit pour le développement ; une licence payante est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou ultérieure.  
- **Cette solution est‑elle compatible avec tous les formats de fichiers MS Project ?** Aspose.Tasks prend en charge .MPP, .XML, .XER, et plus encore.

## Qu’est‑ce que « ajouter une ressource à un projet » dans Aspose.Tasks ?
Ajouter une ressource à un projet signifie créer un objet `Resource` à l’intérieur du modèle `Project`. Cet objet pourra ensuite être lié aux tâches via `ResourceAssignment`, vous permettant de suivre le travail, les coûts et les paramètres de nivellement.

## Pourquoi gérer les propriétés de délai de nivellement ?
Le délai de nivellement aide le planificateur à répartir le travail lorsque les ressources sont sur‑allouées. En définissant un délai, vous indiquez au moteur de reporter le début d’une affectation, évitant ainsi les conflits et maintenant le projet réaliste.

## Prérequis
Avant de commencer, assurez‑vous de disposer des prérequis suivants :
1. Java Development Kit (JDK) : assurez‑vous que le JDK Java est installé sur votre système. Vous pouvez le télécharger et l’installer depuis le [site web](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Bibliothèque Aspose.Tasks for Java : téléchargez la bibliothèque Aspose.Tasks for Java depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/).

## Importer les packages
Tout d’abord, importez les packages nécessaires dans votre projet Java pour utiliser les fonctionnalités d’Aspose.Tasks :
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Étape 1 : créer un objet Project
Instanciez un objet `Project`, qui servira de conteneur pour toutes les tâches, ressources et affectations :
```java
Project prj = new Project();
```

## Étape 2 : créer une tâche
Ajoutez une tâche au projet. Cela montre **comment ajouter une tâche** de façon programmatique :
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Étape 3 : définir la date de début et la durée de la tâche
Spécifiez quand la tâche commence et combien de temps elle doit durer :
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Étape 4 : ajouter une ressource
Nous **ajoutons maintenant une ressource au projet** en créant une nouvelle entrée `Resource` :
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Étape 5 : créer une affectation de ressource
Liez la tâche et la ressource nouvellement ajoutée ensemble :
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Étape 6 : définir le délai de nivellement
Configurez le délai de nivellement pour l’affectation. Le définir à zéro signifie aucun délai supplémentaire, mais vous pouvez ajuster la valeur selon vos besoins :
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Étape 7 : afficher les résultats
Imprimez les propriétés importantes pour vérifier que tout a été correctement configuré :
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Pièges courants et astuces
- **Piège :** Oublier de définir la date de début de la tâche peut entraîner le réglage de l’affectation sur la date de début du projet.  
- **Astuce :** Utilisez `prj.getDuration(value, TimeUnitType.Day)` pour contrôler la granularité du délai.  
- **Astuce :** Après avoir ajouté plusieurs ressources, appelez `prj.updateResourceAssignments()` pour que le planificateur recalcule le nivellement.

## Conclusion
En suivant ces étapes, vous savez maintenant **comment ajouter une ressource à un projet**, l’affecter à une tâche et gérer les propriétés de délai de nivellement en utilisant Aspose.Tasks for Java. Cette connaissance vous permet de créer des solutions d’automatisation de projet robustes qui restent en phase avec les contraintes réelles des ressources.

## FAQ
### Q : Puis‑je utiliser Aspose.Tasks avec d’autres bibliothèques Java ?

R : Oui, Aspose.Tasks peut être intégré à d’autres bibliothèques Java pour enrichir les capacités de gestion de projet.

### Q : Aspose.Tasks est‑il compatible avec différentes versions de fichiers Microsoft Project ?

R : Oui, Aspose.Tasks prend en charge diverses versions de fichiers Microsoft Project, assurant la compatibilité entre différents environnements.

### Q : Où puis‑je trouver un support supplémentaire pour Aspose.Tasks ?

R : Vous pouvez obtenir du support et des ressources sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q : Puis‑je essayer Aspose.Tasks avant de l’acheter ?

R : Oui, vous pouvez obtenir une version d’essai gratuite d’Aspose.Tasks depuis la [page des releases](https://releases.aspose.com/).

### Q : Comment obtenir une licence temporaire pour Aspose.Tasks ?

R : Vous pouvez demander une licence temporaire sur la [page de licence temporaire](https://purchase.aspose.com/temporary-license/) à des fins d’évaluation.

## Questions fréquentes supplémentaires

**Q : Que se passe‑t‑il si je définis un délai de nivellement différent de zéro ?**  
R : Le planificateur reportera le début de l’affectation de la durée spécifiée, aidant à résoudre les sur‑allocations.

**Q : Puis‑je récupérer le délai de nivellement après avoir enregistré le projet ?**  
R : Oui, vous pouvez rouvrir le fichier de projet et lire la propriété `Asn.DELAY` de l’affectation.

**Q : Existe‑t‑il un moyen d’appliquer le délai de nivellement à toutes les affectations en même temps ?**  
R : Vous pouvez parcourir `prj.getResourceAssignments()` et définir le délai pour chaque affectation dans une boucle.

---

**Dernière mise à jour :** 2026-01-07  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}