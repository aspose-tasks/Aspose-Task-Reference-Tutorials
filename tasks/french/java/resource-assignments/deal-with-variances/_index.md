---
date: 2026-01-05
description: Apprenez à gérer efficacement le travail prévu vs réel et les autres
  écarts de projet avec Aspose.Tasks pour Java. Gérez sans effort les écarts de travail,
  de coût, de début et de fin.
linktitle: Deal with Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Travail prévu vs réel : Gestion efficace des écarts de projet avec Aspose.Tasks'
url: /fr/java/resource-assignments/deal-with-variances/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Travail prévu vs réel : Gestion efficace des écarts de projet avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous découvrirez **comment récupérer les données d'écart** et comparer le *travail prévu vs réel* à l'aide de l'API Aspose.Tasks pour Java. Les écarts—qu'ils concernent le travail, le coût, les dates de début ou de fin—sont des indicateurs clés de la santé du planning. À la fin de ce guide, vous serez capable de calculer l'écart de coût, d'extraire les valeurs d'écart pour chaque affectation de ressource et de gérer les écarts de projet efficacement afin de garder vos projets sur la bonne voie.

## Réponses rapides
- **Qu’est‑ce que le “travail prévu vs réel” ?** C’est la différence entre le travail initialement planifié et le travail réellement effectué.  
- **Quelle classe API fournit les données d'écart ?** La classe `Asn` (par ex., `Asn.WORK_VARIANCE`, `Asn.COST_VARIANCE`).  
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?** Une version d’essai gratuite suffit pour l’évaluation ; une licence commerciale est requise en production.  
- **Puis‑je récupérer tous les types d’écart en une seule boucle ?** Oui—parcourez les objets `ResourceAssignment` et appelez `ra.get(Asn.*_VARIANCE)`.  
- **Quelle version de Java est requise ?** Java 8 ou supérieur est recommandé.

## Pré‑requis
Avant de continuer, assurez‑vous de disposer des pré‑requis suivants :
1. Kit de développement Java (JDK) installé sur votre système.  
2. Bibliothèque Aspose.Tasks pour Java téléchargée et ajoutée à votre projet. Vous pouvez la télécharger [ici](https://releases.aspose.com/tasks/java/).  
3. Connaissances de base du langage de programmation Java.

## Importer les packages
Tout d’abord, importez les packages nécessaires pour travailler avec Aspose.Tasks :

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Étape 1 : Parcourir les affectations de ressources
Pour **gérer les écarts de projet**, nous devons itérer sur chaque affectation de ressource dans le fichier projet chargé :

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Perform operations on each resource assignment
}
```

## Étape 2 : Récupérer l'écart de travail (Travail prévu vs réel)
L'écart de travail montre l'écart entre **travail prévu et travail réel**. Récupérez‑le avec :

```java
System.out.println(ra.get(Asn.WORK_VARIANCE));
```

## Étape 3 : Récupérer l'écart de coût
Si vous devez **calculer l'écart de coût**, utilisez l’appel suivant :

```java
System.out.println(ra.get(Asn.COST_VARIANCE));
```

## Étape 4 : Récupérer l'écart de début
L'écart de début indique la différence entre la date de début planifiée et la date de début réelle :

```java
System.out.println(ra.get(Asn.START_VARIANCE));
```

## Étape 5 : Récupérer l'écart de fin
L'écart de fin reflète la déviation entre la date de fin prévue et la date de fin réelle :

```java
System.out.println(ra.get(Asn.FINISH_VARIANCE));
```

## Pourquoi récupérer les données d'écart ?
Comprendre les écarts vous permet de :
- Détecter tôt les glissements de planning.  
- Ajuster l’allocation des ressources avant que les coûts n’explosent.  
- Générer des rapports d’état précis pour les parties prenantes.  
- Réaliser une analyse des causes profondes des tâches retardées.

## Écueils courants et conseils
- **Écueil :** Oublier de charger le bon chemin de fichier `.mpp`.  
  **Conseil :** Vérifiez que `dataDir` pointe vers le dossier contenant `ResourceAssignmentVariance.mpp`.  
- **Écueil :** Supposer que les valeurs d'écart sont toujours numériques.  
  **Conseil :** Certaines affectations peuvent renvoyer `null` si les données ne sont pas disponibles ; ajoutez des vérifications de nullité.  
- **Astuce pro :** Utilisez `ra.get(Asn.WORK)` conjointement avec `ra.get(Asn.WORK_VARIANCE)` pour calculer le travail réellement effectué.

## Conclusion
Gérer le **travail prévu vs réel** et les autres écarts est essentiel pour un contrôle de projet efficace. Avec Aspose.Tasks pour Java, vous pouvez récupérer et analyser ces métriques de façon programmatique, permettant des décisions basées sur les données qui maintiennent les projets dans les délais et le budget.

## FAQ
### Q : Puis‑je intégrer Aspose.Tasks avec d’autres bibliothèques Java ?
R : Oui, Aspose.Tasks peut être intégré de manière transparente avec d’autres bibliothèques Java pour enrichir les capacités de gestion de projet.  
### Q : Aspose.Tasks convient‑il aux projets de grande envergure ?
R : Absolument, Aspose.Tasks est conçu pour gérer des projets de toute taille, offrant des performances et une fiabilité robustes.  
### Q : Puis‑je personnaliser les rapports en fonction de l’analyse des écarts ?
R : Bien sûr, Aspose.Tasks propose de nombreuses fonctionnalités pour personnaliser les rapports selon les exigences d’analyse des écarts.  
### Q : Un support technique est‑il disponible pour les utilisateurs d’Aspose.Tasks ?
R : Oui, les utilisateurs peuvent accéder au support technique via le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour toute assistance ou question.  
### Q : Puis‑je essayer Aspose.Tasks avant de l’acheter ?
R : Oui, vous pouvez profiter d’une version d’essai gratuite d’Aspose.Tasks [ici](https://releases.aspose.com/) pour évaluer ses fonctionnalités avant l’achat.

## Questions fréquemment posées

**Q : Comment calculer l'écart de coût pour une tâche spécifique ?**  
R : Utilisez `ra.get(Asn.COST_VARIANCE)` après avoir parcouru l’affectation ; combinez‑le avec `ra.get(Asn.COST)` pour une analyse complète des coûts.

**Q : Que faire si une valeur d'écart renvoie null ?**  
R : Null indique que la donnée n’est pas définie dans le fichier source. Protégez votre code avec une vérification de nullité avant d’afficher ou d’utiliser la valeur.

**Q : Puis‑je exporter les données d'écart vers Excel ?**  
R : Oui—collectez les valeurs dans une collection et utilisez une bibliothèque comme Apache POI pour les écrire dans une feuille Excel.

**Q : Aspose.Tasks prend‑il en charge les métriques d’écart pour les projets Agile ?**  
R : Bien que l’API se concentre sur les données MS‑Project traditionnelles, vous pouvez mapper les informations de sprint Agile aux tâches et récupérer tout de même les valeurs d’écart.

**Q : Existe‑t‑il un moyen de mettre à jour les valeurs d'écart en lot ?**  
R : Vous pouvez modifier les champs sous‑jacents (par ex., `Asn.WORK`) puis enregistrer le projet ; les champs d’écart seront recalculés lors de la prochaine lecture.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-01-05  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose