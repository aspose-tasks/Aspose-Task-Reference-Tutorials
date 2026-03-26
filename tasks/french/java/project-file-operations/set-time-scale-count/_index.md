---
date: 2025-12-21
description: Apprenez à personnaliser les vues du diagramme de Gantt, à gérer la visualisation
  du projet et à enregistrer le projet au format PDF à l'aide d'Aspose.Tasks pour
  Java. Ajustez le nombre d'échelles de temps sans effort.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Personnaliser le diagramme de Gantt – Maîtriser le comptage de l’échelle de
  temps MS Project dans Aspose.Tasks
url: /fr/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Personnaliser le diagramme de Gantt – Maîtriser le nombre d’échelles de temps MS Project dans Aspose.Tasks

## Introduction
Si vous devez **personnaliser le diagramme de Gantt** dans Microsoft Project, contrôler le nombre d’échelles de temps est une technique clé. Avec Aspose.Tasks for Java, vous pouvez définir programmétiquement les niveaux inférieur et intermédiaire de l’échelle de temps, ajuster la visibilité des repères, puis **enregistrer le projet au format PDF** pour le partager avec les parties prenantes. Ce tutoriel vous guide à travers l’ensemble du processus — de la configuration de l’environnement à la génération d’un PDF soigné reflétant votre vue Gantt personnalisée.

## Réponses rapides
- **Que signifie « personnaliser le diagramme de Gantt » ?** Ajuster les niveaux de l’échelle de temps, les couleurs et la mise en page pour répondre à vos besoins de reporting.  
- **Quelle méthode API définit le nombre du niveau inférieur ?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Puis‑je générer un PDF directement à partir du projet ?** Oui — utilisez `project.save(..., SaveFileFormat.Pdf)`.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence commerciale est requise ; une version d’essai gratuite est disponible.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieur fonctionne avec la dernière bibliothèque Aspose.Tasks.

## Qu’est‑ce que « personnaliser le diagramme de Gantt » dans Aspose.Tasks ?
Personnaliser un diagramme de Gantt signifie modifier programmétiquement ses composants visuels — tels que les intervalles de l’échelle de temps, les repères et les barres de tâches—afin que le diagramme corresponde à la façon dont vous souhaitez **gérer la visualisation du projet**. En changeant le nombre d’échelles de temps, vous contrôlez combien de jours, semaines ou mois chaque segment représente, rendant le diagramme plus clair pour différents publics.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Environnement de développement Java** – JDK 8 ou plus récent installé.  
2. **Bibliothèque Aspose.Tasks for Java** – Téléchargez‑la depuis [ici](https://releases.aspose.com/tasks/java/).  
3. **Connaissances de base en Java** – Familiarité avec la syntaxe Java et les concepts orientés objet.

## Importer les packages
Importez les classes nécessaires dans votre projet Java :

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Guide étape par étape

### Étape 1 : Définir le répertoire de données
Définissez l’endroit où vos fichiers de projet seront lus et écrits :

```java
String dataDir = "Your Data Directory";
```

Remplacez `"Your Data Directory"` par le chemin absolu sur votre machine.

### Étape 2 : Créer une nouvelle instance de projet
Instanciez un objet `Project` vierge qui contiendra toutes les tâches et les paramètres de vue :

```java
Project project = new Project();
```

### Étape 3 : Configurer la vue du diagramme de Gantt
Créez un objet `GanttChartView` — c’est ici que vous **générerez le code Java de la vue Gantt** pour contrôler l’apparence du diagramme :

```java
GanttChartView view = new GanttChartView();
```

### Étape 4 : Définir le nombre d’échelles de temps pour le niveau inférieur
Ajustez le niveau inférieur pour afficher deux intervalles et masquer les repères :

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Étape 5 : Définir le nombre d’échelles de temps pour le niveau intermédiaire
Appliquez la même configuration au niveau intermédiaire :

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Étape 6 : Ajouter la vue personnalisée au projet
Attachez la vue que vous venez de configurer à l’instance `Project` :

```java
project.getViews().add(view);
```

### Étape 7 : Ajouter des tâches d’exemple (données de test)
Créez quelques tâches avec des durées spécifiques pour illustrer le diagramme de Gantt personnalisé :

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Étape 8 : Enregistrer le projet au format PDF
Enfin, exportez le projet—y compris votre **diagramme de Gantt personnalisé**—vers un fichier PDF :

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Le PDF résultant montre comment les niveaux inférieur et intermédiaire de l’échelle de temps ont été **personnalisés**, offrant aux parties prenantes une vue claire et imprimable du planning.

## Problèmes courants et dépannage
- **Le PDF est vide** – Vérifiez que le chemin `dataDir` se termine par un séparateur de fichiers (`/` ou `\`) et que le répertoire existe.  
- **Les repères apparaissent toujours** – Assurez‑vous que `setShowTicks(false)` est appelé sur les deux niveaux.  
- **La durée n’est pas appliquée** – Confirmez que vous utilisez `TimeUnitType.Hour` (ou l’unité appropriée) lors de la création des durées.

## Foire aux questions

**Q : Aspose.Tasks for Java peut‑il gérer des fichiers de projet à grande échelle ?**  
R : Oui, la bibliothèque est optimisée pour le traitement haute performance de données de projet volumineuses.

**Q : Aspose.Tasks for Java est‑il compatible avec différents IDE Java ?**  
R : Absolument — il fonctionne parfaitement avec Eclipse, IntelliJ IDEA, NetBeans et d’autres IDE populaires.

**Q : Puis‑je personnaliser l’apparence des diagrammes de Gantt au‑delà des paramètres d’échelle de temps ?**  
R : Oui, Aspose.Tasks offre de nombreuses options de style telles que les couleurs des barres, les polices et les lignes de grille.

**Q : Existe‑t‑il une version d’essai d’Aspose.Tasks for Java ?**  
R : Oui, vous pouvez obtenir une version d’essai gratuite depuis [ici](https://releases.aspose.com/).

**Q : Où puis‑je obtenir du support pour Aspose.Tasks for Java ?**  
R : Vous trouverez de l’aide sur le forum Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

**Q : Comment changer programmétiquement la couleur de fond du diagramme de Gantt ?**  
R : Utilisez la méthode `view.getGanttChartProperties().setBackgroundColor(Color)` après avoir importé `java.awt.Color`.

## Conclusion
En suivant ces étapes, vous avez appris à **personnaliser les niveaux d’échelle de temps du diagramme de Gantt**, à améliorer la **visualisation du projet**, et à **enregistrer le projet au format PDF** avec Aspose.Tasks for Java. Cette approche vous donne un contrôle total sur la sortie visuelle, facilitant le partage d’horaires clairs et professionnels avec votre équipe ou vos clients.

---

**Dernière mise à jour :** 2025-12-21  
**Testé avec :** Aspose.Tasks for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}