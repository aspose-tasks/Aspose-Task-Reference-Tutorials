---
date: 2026-01-25
description: Apprenez à utiliser Aspose Tasks Java pour la gestion des tâches, en
  traitant les tâches critiques et à effort dirigé dans vos projets. Améliorez les
  flux de travail de vos projets avec ce guide.
linktitle: Aspose Tasks Java – Manage Critical and Effort‑Driven Tasks
second_title: Aspose.Tasks Java API
title: Aspose Tasks Java – Gérer les tâches critiques et à effort dirigé
url: /fr/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java : gérer les tâches critiques et effort‑driven

Dans la gestion de projet moderne, **aspose tasks java** vous donne le pouvoir d’identifier et de contrôler les tâches critiques et effort‑driven directement depuis votre code Java. Que vous construisiez un planificateur, un outil de reporting ou un tableau de bord personnalisé, gérer correctement ces propriétés de tâche peut faire la différence entre un projet qui reste sur la bonne voie et un projet qui part en vrille. Dans ce tutoriel, nous passerons en revue tout ce que vous devez savoir pour travailler avec les tâches critiques et effort‑driven en utilisant Aspose Tasks Java.

## Réponses rapides
- **Que signifie « critical » ?** Une tâche dont le retard prolongera la date de fin du projet.  
- **Qu’est‑ce que « effort‑driven » ?** Une tâche qui ajuste automatiquement sa durée lorsque vous modifiez l’effort de travail.  
- **Quelle bibliothèque fournit ces fonctionnalités ?** Aspose Tasks Java.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour l’évaluation ; une licence est requise pour la production.  
- **Puis‑je exécuter cela sur n’importe quel OS ?** Oui – la bibliothèque est indépendante de la plateforme (Windows, Linux, macOS).

## Quelles sont les tâches critiques et effort‑driven ?
Les tâches critiques sont celles situées sur le chemin critique du projet ; tout glissement impacte directement le planning global. Les tâches effort‑driven, quant à elles, recalculent leur durée en fonction de la quantité de travail assignée, ce qui les rend idéales pour des ressources pouvant faire des heures supplémentaires ou partager l’effort entre plusieurs affectations.

## Pourquoi utiliser Aspose Tasks Java pour cela ?
- **API complète de style .NET en Java basés sur XML sans- **Ensemble riche sont en place :
- Bibliothèque Aspose.Tasks for Java : téléchargez et installez la bibliothèque depuis la [documentation Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/).
- Java Development Kit (JDK) : assurez‑vous que Java est installé sur votre système.
- Environnement de développement intégré (IDE) : utilisez votre IDE préféré pour le développement Java.
- Fichier de projet : préparez un fichier de projet au format XML que vous utiliserez pour la démonstration.

## Importer les packages
Dans votre projet Java, importez les packages nécessaires pour exploiter les fonctionnalités d’Aspose.Tasks for Java :

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

### Étape 1 : Collecter les tâches avec `ChildTasksCollector`
Créez une instance de `ChildTasksCollector` pour collecter toutes les tâches à partir de la tâche racine en utilisant `TaskUtils.apply`. Cela garantit que vous avez accès à chaque tâche du projet.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Étape 2 : Parcourir les tâches collectées
Parcourez toutes les tâches collectées à l’aide d’une boucle `for`. Pour chaque tâche, déterminez si elle est effort‑driven et critique, puis affichez le statut correspondant.

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

En suivant ces étapes, vous pouvez gérer efficacement les tâches critiques et effort‑driven dans vos projets en utilisant **aspose tasks java**.

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| `NullPointerException` on `tsk.get(Tsk.IS_CRITICAL)` | La tâche n’a pas la propriété définie (par ex., une tâche récapitulative). | Vérifiez `tsk.get(Tsk.TASK_TYPE)` avant d’accéder au drapeau, ou filtrez les tâches récapitulatives. |
| Fichier de projet introuvable | Chemin `dataDir` incorrect ou extension de fichier manquante. | Utilisez `Paths.get(dataDir, \"project.xml\").toString()` et vérifiez que le fichier existe. |
| Licence non appliquée | La bibliothèque fonctionne en mode d’évaluation, limitant les fonctionnalités. | Chargez votre fichier de licence avec `License license = new License(); license.setLicense(\"Aspose.Tasks.Java.lic\");` avant de créer l’objet `Project`. |

## Questions fréquentes
### Q : Puis‑je utiliser Aspose.Tasks for Java à la fois sous Windows et Linux ?
R : Oui, Aspose.Tasks for Java est indépendant de la plateforme et peut être utilisé à la fois sous Windows et Linux.

### Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Tasks for Java ?
R : Oui, vous pouvez accéder à un essai gratuit d’Aspose.Tasks for Java [ici](https://releases.aspose.com/).

### Q : Où puis‑je trouver du support pour Aspose.Tasks for Java ?
R : Visitez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le support communautaire et les discussions.

### Q : Comment puis‑je obtenir une licence temporaire pour Aspose.Tasks for Java ?
R : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Q : Où puis‑je acheter Aspose.Tasks for Java ?
R : Vous pouvez acheter Aspose.Tasks for Java depuis la [page d’achat](https://purchase.aspose.com/buy).

**Dernière mise à jour** : 2026-01-25  
**Testé avec** : Aspose.Tasks Java 24.11 (dernière version au moment de la rédaction)  
**Auteur** : Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}