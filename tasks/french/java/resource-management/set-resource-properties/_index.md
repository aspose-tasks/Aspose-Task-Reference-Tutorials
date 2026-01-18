---
date: 2026-01-18
description: Apprenez à définir le taux standard et d’autres propriétés des ressources
  dans MS Project à l’aide d’Aspose.Tasks pour Java, y compris comment ajouter des
  ressources à MS Project et gérer les ressources efficacement.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment définir le taux standard pour les ressources dans Aspose.Tasks
url: /fr/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir le taux standard pour les ressources dans Aspose.Tasks

## Introduction
Si vous développez des applications Java qui doivent interagir avec des fichiers Microsoft Project, **définir le taux standard** pour une ressource est l’une des tâches les plus courantes. Dans ce tutoriel, vous apprendrez comment **définir le taux standard** et d’autres propriétés de ressources en utilisant Aspose.Tasks pour Java. À la fin du guide, vous serez capable de créer un objet projet, d’ajouter une ressource à un fichier MS Project et de gérer les ressources MS Project en toute confiance.

## Quick Answers
- **Quel est la classe principale pour travailler avec un fichier Project ?** `Project`
- **Quelle méthode ajoute une nouvelle ressource ?** `project.getResources().add()`
- **Comment définir le taux standard ?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Ai‑je besoin d’une licence pour la production ?** Oui, une licence valide Aspose.Tasks est requise.
- **Quelle version de Java est prise en charge ?** Java 8+ (la dernière JDK est recommandée).

## What is “set standard rate”?
L’opération *set standard rate* attribue un coût horaire par défaut à une ressource. Les chefs de projet utilisent cette valeur pour calculer les coûts de main‑d’œuvre, générer des rapports de coûts et prévoir les budgets.

## Why set rates with Aspose.Tasks?
- **Pas d’installation de Microsoft Project requise** – manipulez les fichiers directement depuis Java.  
- **Fidélité totale** – tous les champs de ressources, y compris les heures supplémentaires et les taux de coût, sont conservés.  
- **Multi‑plateforme** – fonctionne sous Windows, Linux et macOS.  
- **Convient à l’automatisation** – idéal pour le traitement par lots ou l’intégration dans des pipelines CI.

## Prerequisites
Avant de commencer, assurez‑vous de disposer de ce qui suit :

### Java Development Environment Setup
1. **Installez le JDK** : assurez‑vous d’avoir le Java Development Kit (JDK) installé sur votre système. Vous pouvez le télécharger depuis le [site Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Configuration de l’IDE** : choisissez un environnement de développement intégré (IDE) tel qu’IntelliJ IDEA, Eclipse ou NetBeans et configurez‑le sur votre machine.

### Aspose.Tasks for Java Installation
1. **Téléchargez Aspose.Tasks pour Java** : rendez‑vous sur la [page de téléchargement](https://releases.aspose.com/tasks/java/) et obtenez la dernière version d’Aspose.Tasks pour Java.  
2. **Intégrez au projet** : incorporez la bibliothèque Aspose.Tasks pour Java dans votre projet Java en l’ajoutant comme dépendance.

## Import Packages
Pour commencer, vous devez importer les packages nécessaires d’Aspose.Tasks pour Java dans votre projet. Cette étape garantit que vous avez accès aux fonctionnalités requises.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Step 1: Create a Project Object
Créer un **project object** est la première étape de toute manipulation de MS Project. Il représente l’ensemble du fichier projet en mémoire.

```java
Project project = new Project();
```

## Step 2: Add a Resource (add resource ms project)
Nous allons maintenant **add resource MS Project** en utilisant la collection Resources. Le nom de la ressource peut être n’importe quel texte pertinent pour votre planning.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Step 3: Set Resource Properties (how to set rates)
C’est ici que nous **set the standard rate** et que nous montrons également comment définir un taux d’heures supplémentaires. Ces taux sont stockés sous forme de valeurs `BigDecimal` afin de préserver la précision.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Common Issues and Solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| `NullPointerException` lors de l’appel à `set` | La ressource n’a pas été ajoutée correctement. | Assurez‑vous que `project.getResources().add()` renvoie un `Resource` non nul. |
| Les taux apparaissent comme 0 dans le fichier enregistré | Utilisation d’un `int` au lieu de `BigDecimal`. | Utilisez toujours `BigDecimal.valueOf()` pour les valeurs monétaires. |
| Licence non trouvée | Le fichier de licence n’est pas chargé avant la création du `Project`. | Chargez la licence (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) au début de votre programme. |

## Conclusion
En suivant ces étapes, vous avez appris comment **create a project object**, **add a resource MS Project** et **set standard rate** ainsi que d’autres propriétés de ressources. Cela vous permet d’automatiser les calculs de coûts, de générer des rapports personnalisés et de gérer pleinement les ressources MS Project depuis Java.

## FAQ's
### Can Aspose.Tasks for Java handle complex MS Project files?
Oui, Aspose.Tasks pour Java est capable de gérer une large gamme de formats de fichiers MS Project, y compris des fichiers complexes avec des hiérarchies de tâches étendues.

### Is there a free trial available for Aspose.Tasks for Java?
Oui, vous pouvez accéder à un essai gratuit d’Aspose.Tasks pour Java depuis [ici](https://releases.aspose.com/).

### Where can I find support for Aspose.Tasks for Java?
Vous pouvez obtenir de l’aide et participer aux discussions relatives à Aspose.Tasks pour Java sur le [forum de support](https://forum.aspose.com/c/tasks/15).

### How can I obtain a temporary license for Aspose.Tasks for Java?
Vous pouvez obtenir une licence temporaire depuis la [page de licence temporaire](https://purchase.aspose.com/temporary-license/) à des fins d’évaluation.

### Where can I purchase a licensed version of Aspose.Tasks for Java?
Vous pouvez acheter une version sous licence d’Aspose.Tasks pour Java depuis la [page d’achat](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour:** 2026-01-18  
**Testé avec:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose