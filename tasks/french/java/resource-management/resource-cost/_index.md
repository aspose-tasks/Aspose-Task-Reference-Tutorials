---
date: 2026-06-15
description: Apprenez à gérer les coûts dans les fichiers MS Project en utilisant
  Aspose.Tasks for Java, y compris comment charger un fichier MPP et lire le travail
  de coût réel ainsi que le calendrier de coût budgété.
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: Gérer le coût des ressources dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Comment gérer les coûts dans MS Project avec Aspose.Tasks for Java
url: /fr/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment gérer les coûts dans MS Project avec Aspose.Tasks pour Java

## Introduction

La gestion des budgets de projet est une responsabilité fondamentale pour tout chef de projet, et **comment gérer les coûts** efficacement peut faire ou défaire le succès d’un projet. Aspose.Tasks pour Java vous donne un contrôle programmatique sur les fichiers Microsoft Project, vous permettant de lire et de mettre à jour les données de coût des ressources sans jamais ouvrir le fichier .mpp manuellement. Dans ce tutoriel, vous verrez étape par étape comment charger un fichier MPP, inspecter le travail réel de coût, et extraire le calendrier de coût budgété pour chaque ressource.

## Réponses rapides
- **Que fait Aspose.Tasks pour Java ?** Il lit et écrit les fichiers Microsoft Project (.mpp) sans nécessiter l’installation de Microsoft Project.  
- **Comment charger un fichier MPP ?** Utilisez `new Project("path/to/file.mpp")` – l’API analyse le fichier en mémoire.  
- **Quels champs de coût sont disponibles ?** Actual Cost Work (ACWP), Budgeted Cost of Work Scheduled (BCWS) et Budgeted Cost of Work Performed (BCWP).  
- **Ai‑je besoin d’une licence pour le développement ?** Une licence temporaire gratuite fonctionne pour les tests ; une licence complète est requise pour la production.  
- **Quelles versions de Java sont prises en charge ?** Java 8 et ultérieures, y compris Java 17 LTS.

## Comment gérer les coûts dans MS Project ?

Chargez votre projet avec `new Project("yourFile.mpp")`, puis parcourez chaque objet `Resource` pour lire les propriétés liées aux coûts telles que ACWP, BCWS et BCWP. Aspose.Tasks convertit automatiquement les valeurs de coût internes dans la devise du projet, vous permettant de les afficher ou de les stocker directement. Cette approche élimine les calculs manuels sur feuille de calcul et garantit la cohérence des données dans tous les rapports de projet.

## Prérequis

1. Compréhension de base de la programmation Java.  
2. Bibliothèque Aspose.Tasks pour Java ajoutée à votre projet (Maven/Gradle ou JAR manuel).  
3. Accès à un fichier Microsoft Project (`.mpp`) que vous souhaitez analyser.  

## Importer les packages

Les classes `Project` et `Resource` sont les points d’entrée pour travailler avec les données du projet.

La classe `Project` est l’objet de niveau supérieur d’Aspose.Tasks qui représente un fichier Microsoft Project unique en mémoire.  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## Étape 1 : définir le répertoire de données

Tout d’abord, spécifiez le dossier qui contient votre fichier `.mpp`. Ce chemin peut être absolu ou relatif au répertoire de travail de votre application.

```text
```java
String dataDir = "Your Data Directory";
```
```

## Étape 2 : charger le fichier MS Project

`Project` charge le fichier et construit un modèle d’objet que vous pouvez interroger. L’API analyse le fichier sans nécessiter Microsoft Project installé, prenant en charge plus de 30 formats d’entrée.

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## Étape 3 : parcourir les ressources

Les objets `Resource` représentent des personnes, du matériel ou des équipements qui consomment le budget. Vous pouvez parcourir la collection `project.getResources()` pour accéder à chaque ressource.

```text
```java
for (Resource res : prj.getResources()) {
```
```

## Étape 4 : vérifier le nom et les coûts de la ressource

Pour chaque ressource, vérifiez que le nom est défini, puis lisez les champs de coût. La méthode `getActualCost()` renvoie le **travail réel de coût** (ACWP), tandis que `getBudgetedCost()` vous donne le **calendrier de coût budgété** (BCWS/BCWP).

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## Pourquoi utiliser Aspose.Tasks pour Java pour charger un fichier MPP ?

Aspose.Tasks prend en charge **plus de 30 formats de fichiers** (y compris `.mpp`, `.xml` et `.xlsx`) et peut traiter des projets contenant **jusqu’à 10 000 tâches** tout en utilisant moins de 200 Mo de RAM. La bibliothèque effectue tous les calculs côté serveur, éliminant le besoin d’une copie sous licence de Microsoft Project.

## Problèmes courants et solutions

- **Noms de ressources nuls :** Certains fichiers anciens contiennent des ressources factices. Vérifiez toujours `resource.getName() != null` avant d’accéder aux propriétés de coût.  
- **Fichiers volumineux provoquant une pression mémoire :** `LoadOptions` est une classe de configuration qui vous permet de spécifier quelles données du projet charger. Utilisez `project.setLoadOptions(LoadOptions.setLoadResourceData(false))` pour ne charger que les données nécessaires, puis activez‑les plus tard si besoin.  
- **Incohérences de devise :** L’API respecte les paramètres de devise du projet ; vous pouvez les remplacer avec `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` si nécessaire. `CostRateTableType` énumère les différentes tables de taux de coût pouvant être appliquées à une tâche.

## Questions fréquemment posées

**Q : Aspose.Tasks pour Java peut‑il gérer des structures de projet complexes ?**  
R : Oui, il prend en charge les tâches récapitulatives imbriquées, plusieurs calendriers de ressources et des champs personnalisés pour toutes les versions de Project prises en charge.

**Q : La bibliothèque est‑elle compatible avec différentes versions de fichiers Microsoft Project ?**  
R : Absolument. Aspose.Tasks lit et écrit les fichiers de Microsoft Project 2000 jusqu’au format le plus récent de 2023.

**Q : Puis‑je intégrer Aspose.Tasks pour Java avec d’autres bibliothèques Java ?**  
R : Oui, l’API renvoie des objets Java standards, permettant une intégration fluide avec des frameworks de journalisation, des outils ORM ou des bibliothèques de reporting.

**Q : Aspose.Tasks pour Java offre‑t‑il un support client ?**  
R : Aspose propose un support dédié via les forums, une documentation détaillée et une assistance par e‑mail réactive pour les utilisateurs sous licence.

**Q : Existe‑t‑il une version d’essai gratuite d’Aspose.Tasks pour Java ?**  
R : Vous pouvez télécharger une licence d’évaluation de 30 jours depuis le site d’Aspose pour explorer toutes les fonctionnalités sans frais.

---

**Dernière mise à jour :** 2026-06-15  
**Testé avec :** Aspose.Tasks pour Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Comment calculer la variance des coûts et gérer les coûts d’affectation avec Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Gestion du budget, du travail et des coûts pour les tâches dans Aspose.Tasks](/tasks/java/task-properties/task-budget-work-cost/)
- [Ajouter une ressource au projet avec Aspose.Tasks pour Java](/tasks/java/resource-management/create-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}