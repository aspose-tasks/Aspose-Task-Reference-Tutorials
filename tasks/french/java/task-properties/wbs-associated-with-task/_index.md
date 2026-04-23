---
date: 2026-03-03
description: Apprenez à renuméroter le WBS dans Aspose.Tasks pour Java, à gérer la
  décomposition du travail et à personnaliser les codes WBS efficacement grâce à des
  exemples étape par étape.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment renuméroter le WBS dans Aspose.Tasks pour Java
url: /fr/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment renuméroter le WBS dans Aspose.Tasks pour Java

## Introduction
Si vous avez besoin de **comment renuméroter le WBS** dans un fichier Microsoft Project à l’aide d’Aspose.Tasks pour Java, vous êtes au bon endroit. Ce tutoriel vous guide à travers la lecture des codes WBS existants, leur personnalisation, puis le renumérotage de la hiérarchie afin que votre projet reste organisé. Que vous nettoyiez un planning hérité ou que vous en construisiez un nouveau à partir de zéro, maîtriser ces étapes vous aidera à **gérer les structures de répartition du travail** en toute confiance.

## Réponses rapides
- **Que fait le renumérotage du WBS ?** Il recalcule la numérotation hiérarchique des tâches pour refléter tout changement de structure.  
- **Quelle classe effectue le renumérotage ?** `Project.renumberWBSCode`.  
- **Ai‑je besoin d’une licence pour exécuter le code ?** Une licence valide Aspose.Tasks est requise pour une utilisation en production.  
- **Puis‑je personnaliser le format du WBS ?** Oui — utilisez `Task.set(Tsk.WBS, "...")` pour attribuer n’importe quelle chaîne.  
- **Quels sont les prérequis principaux ?** Java JDK, bibliothèque Aspose.Tasks pour Java, et un fichier projet valide (.mpp).

## Qu’est‑ce qu’une Work Breakdown Structure (WBS) ?
Une Work Breakdown Structure (WBS) est une représentation hiérarchique des livrables et des tâches d’un projet. Chaque tâche reçoit un code (par ex. 1.2.3) qui reflète sa position dans la hiérarchie. Le renumérotage devient essentiel lorsque des tâches sont ajoutées, supprimées ou réordonnées, afin que les codes restent logiques et faciles à lire.

## Pourquoi gérer la répartition du travail et personnaliser les codes WBS ?
- **Clarté :** Des codes WBS clairs facilitent la localisation des tâches par les parties prenantes.  
- **Reporting :** De nombreux outils de reporting s’appuient sur une numérotation cohérente.  
- **Flexibilité :** Les codes personnalisés vous permettent d’aligner la structure du projet avec les normes internes.  

## Prérequis
Avant de plonger dans le code, assurez‑vous d’avoir les éléments suivants :

- Java Development Kit (JDK) installé sur votre machine.  
- Bibliothèque Aspose.Tasks pour Java ajoutée à votre projet. Vous pouvez l’obtenir [ici](https://releases.aspose.com/tasks/java/).  

## Importer les packages
Assurez‑vous d’importer les packages nécessaires pour démarrer votre projet :

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Lire les codes WBS
Tout d’abord, nous lirons les codes WBS existants afin que vous puissiez voir avec quoi vous travaillez.

### Étape 1 : Charger le projet
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Étape 2 : Collecter les tâches
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Étape 3 : Analyser et personnaliser
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

L’extrait ci‑dessus affiche le WBS actuel et le niveau de chaque tâche, puis montre comment **personnaliser les codes WBS** en assignant une nouvelle chaîne.

## Renuméroter les codes WBS des tâches
Passons maintenant au renumérotage effectif de la hiérarchie WBS.

### Étape 1 : Charger le projet (exemple de renumérotage)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Étape 2 : Sélectionner toutes les tâches
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Étape 3 : Afficher les codes WBS initiaux
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Étape 4 : Renuméroter les codes WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Étape 5 : Afficher les codes WBS mis à jour
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

En suivant ces étapes, vous pourrez **renuméroter le WBS** pour n’importe quel ensemble de tâches dans votre fichier projet.

## Problèmes courants et solutions
- **WBS not changing after `set` call :** Assurez‑vous de travailler avec la bonne instance de tâche et que le projet soit enregistré après les modifications.  
- **`renumberWBSCode` throws an exception :** Vérifiez que la liste d’ID correspond au nombre de tâches de niveau supérieur ; sinon la méthode ne peut pas mapper correctement les nouveaux numéros.  
- **Missing WBS values :** Certaines tâches peuvent avoir un WBS `null` si elles ont été importées depuis un fichier qui n’en définissait pas. Utilisez une valeur de secours avant l’affichage.  

## Questions fréquentes

**Q : Où puis‑je trouver la documentation d’Aspose.Tasks pour Java ?**  
A : La documentation est disponible [ici](https://reference.aspose.com/tasks/java/).

**Q : Comment puis‑je télécharger Aspose.Tasks pour Java ?**  
A : Vous pouvez le télécharger [ici](https://releases.aspose.com/tasks/java/).

**Q : Existe‑t‑il un essai gratuit d’Aspose.Tasks pour Java ?**  
A : Oui, vous pouvez obtenir un essai gratuit [ici](https://releases.aspose.com/).

**Q : Où puis‑je obtenir du support pour Aspose.Tasks pour Java ?**  
A : Visitez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le support.

**Q : Puis‑je obtenir une licence temporaire pour Aspose.Tasks pour Java ?**  
A : Oui, obtenez une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Puis‑je renommer le format du WBS après le renumérotage ?**  
A : Absolument. Après avoir appelé `renumberWBSCode`, vous pouvez parcourir les tâches et appliquer `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` pour respecter vos conventions de nommage.

**Q : Le renumérotage affecte‑t‑il les dépendances des tâches ?**  
A : Non. La méthode ne met à jour que la chaîne WBS ; les liaisons et contraintes de tâches restent inchangées.

---

**Dernière mise à jour :** 2026-03-03  
**Testé avec :** Aspose.Tasks for Java 24.12 (latest)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}