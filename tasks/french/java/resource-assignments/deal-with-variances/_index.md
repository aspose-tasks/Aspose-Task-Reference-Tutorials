---
date: 2026-05-20
description: Apprenez à gérer les écarts de projet avec Aspose.Tasks pour Java, y
  compris comment obtenir les écarts de coût, les écarts de travail et les écarts
  de dates efficacement.
keywords:
- handle project variances
- get cost variance
- Aspose.Tasks Java
linktitle: Gérer les écarts dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to handle project variances with Aspose.Tasks for Java, including
    how to get cost variance, work variance, and date variances efficiently.
  headline: How to Handle Project Variances with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to handle project variances with Aspose.Tasks for Java, including
    how to get cost variance, work variance, and date variances efficiently.
  name: How to Handle Project Variances with Aspose.Tasks for Java
  steps:
  - name: Iterate through Resource Assignments
    text: 'To deal with variances, we need to iterate through resource assignments
      in the project. This is achieved using a simple loop:'
  - name: Retrieve Work Variance
    text: 'Work variance represents the deviation between planned work and actual
      work performed by a resource. To retrieve work variance for each resource assignment,
      use the following code snippet:'
  - name: Retrieve Start Variance
    text: 'Start variance signifies the variance between planned and actual start
      dates for a task. To fetch start variance, utilize the following code:'
  - name: Retrieve Finish Variance
    text: 'Finish variance denotes the difference between planned and actual finish
      dates for a task. To acquire finish variance, employ the following code:'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with libraries such as Jackson
      for JSON, Apache POI for Excel, and JFreeChart for reporting.
    question: Can I integrate Aspose.Tasks with other Java libraries?
  - answer: Absolutely. It efficiently processes projects containing up to 10,000
      tasks and 5,000 resources without loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Certainly. Use the variance values you retrieve to feed custom PDF, Excel,
      or HTML reports via Aspose.Words, Aspose.Cells, or standard Java templating
      engines.
    question: Can I customize reports based on variance analysis?
  - answer: Yes, users can access technical support through the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Is technical support available for Aspose.Tasks users?
  - answer: Yes, you can avail of a free trial of Aspose.Tasks from [here](https://releases.aspose.com/)
      to evaluate its features before making a purchase.
    question: Can I try Aspose.Tasks before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Comment gérer les écarts de projet avec Aspose.Tasks pour Java
url: /fr/java/resource-assignments/deal-with-variances/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment gérer les écarts de projet avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous apprendrez **comment gérer les écarts de projet** à l’aide d’Aspose.Tasks pour Java. Les écarts — différences entre le travail, le coût, les dates de début ou de fin prévus et réels — sont des indicateurs essentiels qui vous indiquent si un projet est sur la bonne voie. Aspose.Tasks vous offre un moyen propre et programmatique de récupérer et d’analyser ces valeurs afin que vous puissiez effectuer rapidement des ajustements basés sur les données.

## Réponses rapides
- **Quelle est la classe principale pour accéder aux écarts ?** `ResourceAssignment` fournit des propriétés telles que `WorkVariance`, `CostVariance`, `StartVariance` et `FinishVariance`.  
- **Quelle méthode renvoie l’écart de coût ?** Utilisez `getCostVariance()` sur une instance de `ResourceAssignment`.  
- **Ai‑je besoin d’une licence pour cette fonctionnalité ?** Oui, une licence valide d’Aspose.Tasks débloque toutes les API d’écarts.  
- **Les grands projets peuvent‑ils être traités ?** Aspose.Tasks gère les projets contenant jusqu’à 10 000 tâches sans charger le fichier complet en mémoire.  
- **Quelle version de Java est requise ?** Java 8 ou supérieure est prise en charge.

## Qu’est‑ce que « gérer les écarts de projet » ?
Gérer les écarts de projet consiste à extraire les différences entre les valeurs de référence (planifiées) et les résultats réels pour le travail, le coût, les dates de début et de fin. En analysant ces écarts, les chefs de projet peuvent évaluer la performance, identifier les dépassements de planning ou de budget, et prendre des décisions éclairées pour re‑planifier ou ajuster les ressources, garantissant ainsi que le projet reste sur la bonne voie.

## Pourquoi utiliser Aspose.Tasks pour l’analyse des écarts ?
Aspose.Tasks prend en charge **plus de 30 formats de fichiers d’entrée/sortie** et peut traiter des plannings de plusieurs centaines de pages en moins d’une seconde sur un matériel serveur standard. Son API renvoie directement les valeurs d’écart, éliminant ainsi le besoin de calculs manuels ou d’extensions tierces.

## Prérequis
Avant de continuer, assurez‑vous de disposer des prérequis suivants :
1. Java Development Kit (JDK) installé sur votre système.  
2. Bibliothèque Aspose.Tasks pour Java téléchargée et ajoutée à votre projet. Vous pouvez la télécharger depuis [ici](https://releases.aspose.com/tasks/java/).  
3. Connaissances de base du langage de programmation Java.

## Importer les packages
La classe `ResourceAssignment` se trouve dans l’espace de noms `com.aspose.tasks`. Importez les packages nécessaires avant de commencer à coder :

La classe `ResourceAssignment` représente le lien entre une ressource et une tâche, exposant les propriétés d’écart que vous pouvez interroger.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;

```

## Comment gérer les écarts de projet dans Aspose.Tasks ?
Chargez votre projet avec `new Project("yourfile.mpp")`, puis parcourez chaque `ResourceAssignment` pour lire ses champs d’écart. Cette passe unique vous fournit les écarts de travail, de coût, de début et de fin pour chaque affectation, permettant des tableaux de bord de performance instantanés.

### Étape 1 : Parcourir les affectations de ressources
Pour gérer les écarts, nous devons parcourir les affectations de ressources dans le projet. Cela se réalise à l’aide d’une boucle simple :

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Perform operations on each resource assignment
}
```

### Étape 2 : Récupérer l’écart de travail
L’écart de travail représente la déviation entre le travail planifié et le travail réellement effectué par une ressource. Pour récupérer l’écart de travail pour chaque affectation de ressource, utilisez l’extrait de code suivant :

```java
System.out.println(ra.get(Asn.WORK_VARIANCE));
```

### Comment obtenir l’écart de coût pour une affectation de ressource ?
Pour obtenir l’écart de coût d’une affectation spécifique, invoquez la méthode `getCostVariance()` sur une instance de `ResourceAssignment`. Cette méthode calcule la différence monétaire entre le coût de référence et le coût réel engagé, renvoyant une valeur `double` qui reflète l’écart dans la devise par défaut du projet. Vous pouvez ensuite utiliser ce chiffre pour l’analyse budgétaire.

```java
System.out.println(ra.get(Asn.COST_VARIANCE));
```

### Étape 4 : Récupérer l’écart de début
L’écart de début indique la différence entre les dates de début planifiées et réelles d’une tâche. Pour récupérer l’écart de début, utilisez le code suivant :

```java
System.out.println(ra.get(Asn.START_VARIANCE));
```

### Étape 5 : Récupérer l’écart de fin
L’écart de fin représente la différence entre les dates de fin planifiées et réelles d’une tâche. Pour obtenir l’écart de fin, utilisez le code suivant :

```java
System.out.println(ra.get(Asn.FINISH_VARIANCE));
```

## Problèmes courants et solutions
- **Valeurs null :** Si une tâche n’a pas de référence, les propriétés d’écart renvoient `null`. Vérifiez toujours la présence de `null` avant d’utiliser la valeur.  
- **Incohérences de fuseau horaire :** Les dates sont stockées en UTC ; convertissez‑les dans votre fuseau local si vous les affichez aux utilisateurs.  
- **Fichiers volumineux :** Pour les projets contenant des milliers d’affectations, envisagez de traiter les affectations par lots afin de limiter l’utilisation de la mémoire.

## Questions fréquemment posées

**Q : Puis‑je intégrer Aspose.Tasks avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.Tasks s’intègre parfaitement avec des bibliothèques telles que Jackson pour JSON, Apache POI pour Excel et JFreeChart pour les rapports.

**Q : Aspose.Tasks convient‑il aux projets à grande échelle ?**  
R : Absolument. Il traite efficacement les projets contenant jusqu’à 10 000 tâches et 5 000 ressources sans charger le fichier complet en mémoire.

**Q : Puis‑je personnaliser les rapports basés sur l’analyse des écarts ?**  
R : Bien sûr. Utilisez les valeurs d’écart récupérées pour alimenter des rapports PDF, Excel ou HTML personnalisés via Aspose.Words, Aspose.Cells ou des moteurs de modèles Java standards.

**Q : Un support technique est‑il disponible pour les utilisateurs d’Aspose.Tasks ?**  
R : Oui, les utilisateurs peuvent accéder au support technique via le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour toute assistance ou question.

**Q : Puis‑je essayer Aspose.Tasks avant d’acheter ?**  
R : Oui, vous pouvez profiter d’un essai gratuit d’Aspose.Tasks depuis [ici](https://releases.aspose.com/) pour évaluer ses fonctionnalités avant d’effectuer un achat.

---

**Dernière mise à jour :** 2026-05-20  
**Testé avec :** Aspose.Tasks 24.12 for Java  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Suivi des coûts du projet avec Aspose.Tasks - Heures supplémentaires et Travail](/tasks/java/resource-assignments/overtime-remaining-costs-work/)
- [Gestion des coûts des ressources MS Project avec Aspose.Tasks pour Java](/tasks/java/resource-management/resource-cost/)
- [Définir la date de début du projet dans MS Project à l’aide d’Aspose.Tasks pour Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}