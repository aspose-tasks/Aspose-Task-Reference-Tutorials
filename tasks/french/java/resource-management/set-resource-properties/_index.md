---
date: 2026-08-24
description: Apprenez comment ajouter une ressource MS Project, définir le tarif standard
  et d’autres propriétés de ressource dans MS Project en utilisant Aspose.Tasks pour
  Java, et gérer les ressources efficacement.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Définir les propriétés de la ressource dans Aspose.Tasks
og_description: Ajoutez une ressource MS Project et définissez le tarif standard à
  l’aide d’Aspose.Tasks pour Java. Apprenez les prérequis, le code étape par étape
  et le dépannage dans ce guide concis.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Ajouter une ressource MS Project et définir le tarif avec Aspose.Tasks (Java)
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Comment ajouter une ressource MS Project avec Aspose.Tasks
url: /fr/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une ressource ms project et définir le tarif dans Aspose.Tasks

## Introduction
Si vous développez des applications Java qui doivent lire ou écrire des fichiers Microsoft Project, **ajouter une ressource ms project** et configurer son tarif standard est une tâche courante mais essentielle. Dans ce guide, vous verrez comment créer un objet `Project`, ajouter une ressource et définir les tarifs standard et heures supplémentaires à l'aide d'Aspose.Tasks pour Java. À la fin, vous pourrez automatiser les calculs de coûts et maintenir vos calendriers de projet à jour sans nécessiter l'installation de Microsoft Project.

## Réponses rapides
- **Quelle classe représente un fichier Project ?** `Project`
- **Quel appel ajoute une nouvelle ressource ?** `project.getResources().add()`
- **Comment définir le tarif standard ?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Une licence est‑elle requise pour une utilisation en production ?** Oui, vous devez charger une licence Aspose.Tasks valide.
- **Quelles versions de Java sont prises en charge ?** Java 8 et ultérieures (Java 17+ recommandé).

## Qu'est-ce que « définir le tarif standard » ?
L'opération *définir le tarif standard* attribue un coût horaire par défaut à une ressource. Ce tarif est utilisé par les chefs de projet pour calculer les dépenses de main‑d'œuvre, générer des rapports de coûts et prévoir les budgets, garantissant que les calculs de coûts reflètent le prix attendu du travail effectué par chaque ressource tout au long du cycle de vie du projet.

## Pourquoi définir les tarifs avec Aspose.Tasks ?
Aspose.Tasks peut traiter **plus de 50 formats d'entrée et de sortie**, y compris les fichiers MPP, MPX, XML et Primavera, et il gère des projets de plusieurs centaines de pages sans charger le fichier complet en mémoire. Cela permet un traitement par lots à haut débit sur des serveurs Windows, Linux ou macOS, réduisant l'effort manuel jusqu'à 90 % dans les scénarios d'automatisation typiques.

## Prérequis
Avant de commencer, assurez-vous que les éléments suivants sont prêts :

### Configuration de l'environnement de développement Java
1. Installez le JDK 8 ou une version plus récente. Vous pouvez le télécharger depuis le [site Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Choisissez un IDE tel qu'IntelliJ IDEA, Eclipse ou NetBeans et configurez‑le pour le développement Java.

### Installation d'Aspose.Tasks pour Java
1. Téléchargez le dernier package Aspose.Tasks pour Java depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/).  
2. Ajoutez les fichiers JAR à votre classpath de projet ou déclarez la dépendance Maven/Gradle comme indiqué dans la documentation du produit.

## Importer les packages
Importez les classes principales d'Aspose.Tasks dont vous aurez besoin. Cette étape vous donne accès aux types `Project`, `Resource` et `Rsc` utilisés plus tard.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Étape 1 : créer un objet projet
La classe `Project` est l'objet de niveau supérieur qui représente un fichier MS Project complet en mémoire. L'instancier crée un projet vierge que vous pouvez remplir avec des tâches, des ressources et d'autres données.

```java
Project project = new Project();
```

## Étape 2 : ajouter une ressource (add resource ms project)
La classe `Resource` modélise une ressource de projet unique telle qu'une personne, un équipement ou un matériau. L'ajout d'une ressource via `project.getResources().add()` renvoie une instance `Resource` non nulle prête à être configurée.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Étape 3 : définir les propriétés de la ressource (how to set rates)
L'énumération `Rsc` contient des constantes pour les champs de ressource tels que `STANDARD_RATE` et `OVERTIME_RATE`.  
Vous définissez les tarifs standard et heures supplémentaires en appelant `set` sur l'objet `Resource` avec les valeurs d'énumération `Rsc` appropriées. Les tarifs sont stockés en tant que `BigDecimal` afin de préserver la précision monétaire.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|---------------------------|----------|
| `NullPointerException` when calling `set` | La ressource n'a pas été ajoutée correctement. | Assurez‑vous que `project.getResources().add()` renvoie une `Resource` non nulle. |
| Rates appear as 0 in the saved file | Utilisation d'un `int` au lieu de `BigDecimal`. | Utilisez toujours `BigDecimal.valueOf()` pour les valeurs monétaires. |
| License not found | Le fichier de licence n'a pas été chargé avant la création du `Project`. | Chargez la licence (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) au démarrage du programme. |

## Conclusion
Vous savez maintenant comment **ajouter une ressource ms project**, créer un objet `Project` et **définir les tarifs standard et heures supplémentaires** à l'aide d'Aspose.Tasks pour Java. Cette capacité vous permet d'automatiser les calculs de coûts, de générer des rapports personnalisés et de gérer entièrement les ressources MS Project depuis n'importe quelle application Java.

## Questions fréquemment posées
**Q : Aspose.Tasks pour Java peut‑il gérer des fichiers MS Project complexes ?**  
R : Oui, il prend en charge tous les principaux formats Project, y compris les gros fichiers contenant des milliers de tâches et de ressources, en préservant chaque champ sans perte de données.

**Q : Existe‑t‑il un essai gratuit ?**  
R : Oui, vous pouvez accéder à un essai gratuit d'Aspose.Tasks pour Java depuis la [page d'essai gratuit d'Aspose.Tasks](https://releases.aspose.com/).

**Q : Où puis‑je obtenir de l'aide pour Aspose.Tasks pour Java ?**  
R : Vous pouvez demander de l'assistance sur le [forum de support](https://forum.aspose.com/c/tasks/15).

**Q : Comment obtenir une licence temporaire pour l'évaluation ?**  
R : Une licence temporaire est disponible sur la [page de licence temporaire](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je acheter une version sous licence ?**  
R : Achetez une licence complète depuis la [page d'achat](https://purchase.aspose.com/buy).

---

**Dernière mise à jour :** 2026-08-24  
**Testé avec :** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer des ressources – Gestion des ressources avec Aspose.Tasks pour Java](/tasks/java/resource-management/)
- [Ajouter une ressource au projet avec Aspose.Tasks pour Java](/tasks/java/resource-management/create-resources/)
- [Comment ajouter une ressource au projet et gérer les propriétés de délai de nivellement dans Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}