---
date: 2026-09-09
description: Apprenez à identifier les tâches inter‑projets en utilisant Aspose.Tasks
  pour Java. Découvrez une intégration transparente, une gestion efficace et des exemples
  concrets.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Identifier les tâches inter‑projets dans Aspose.Tasks
og_description: Identifier les tâches inter‑projets dans Aspose.Tasks pour Java. Apprenez
  à définir le répertoire des documents, à récupérer les ID des tâches et à gérer
  efficacement les projets liés.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Identifier les tâches inter‑projets dans Aspose.Tasks – Guide Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Identifier les tâches inter‑projets dans Aspose.Tasks
url: /fr/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Identifier les tâches inter‑projets dans Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez **comment identifier les tâches inter‑projets** avec Aspose.Tasks pour Java. Que vous gériez un portefeuille d’échéanciers interdépendants ou que vous deviez auditer des dépendances externes, les étapes ci‑dessous vous montrent comment localiser les tâches qui font référence à d’autres fichiers de projet, récupérer leurs identifiants et les manipuler programmétiquement.

## Réponses rapides
- **Que signifie « identifier les tâches inter‑projets » ?** Cela signifie localiser les tâches qui font référence ou dépendent de tâches dans un autre fichier de projet.  
- **Quelle méthode affiche l’ID de la tâche ?** Utilisez `externalTask.get(Tsk.ID)` pour afficher l’ID de la tâche.  
- **Comment définir le répertoire du document ?** Assignez le chemin du dossier à une variable `String` (par ex., `dataDir`).  
- **Quelle propriété récupère une tâche par UID ?** Appelez `getChildren().getByUid(yourUid)`.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Oui, une licence valide d’Aspose.Tasks est requise pour les déploiements commerciaux.

## Qu’est‑ce que « identifier les tâches inter‑projets » ?
Identifier les tâches inter‑projets vous permet de tracer les relations entre des tâches réparties sur plusieurs fichiers Microsoft Project. En localisant les tâches qui font référence ou dépendent d’échéanciers externes, vous pouvez comprendre comment les éléments de travail interagissent au‑delà des limites de projet, éviter les doublons et maintenir des chronologies précises. Cette fonctionnalité est essentielle pour les portefeuilles à grande échelle où les tâches sont partagées ou dépendent d’échéanciers externes.

## Pourquoi utiliser Aspose.Tasks pour Java ?
Aspose.Tasks pour Java prend en charge **plus de 50 formats d’entrée et de sortie** (y compris MPP, MPX, XML et CSV) et peut traiter des projets contenant **jusqu’à 10 000 tâches** sans charger le fichier complet en mémoire. La bibliothèque fonctionne sur toute plateforme compatible JVM, ne nécessite aucune installation de Microsoft Project et offre un accès complet à l’API aux ID, UID, ID externes et métadonnées de liaison.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Un environnement de développement Java fonctionnel (JDK 8 ou supérieur).  
- Aspose.Tasks pour Java installé. Vous pouvez le télécharger **[ici](https://releases.aspose.com/tasks/java/)**.  
- Un fichier de licence Aspose.Tasks valide si vous prévoyez d’exécuter le code en production.

## Importer les packages
La classe `Project` représente un fichier Microsoft Project, `Task` représente une tâche individuelle, et `Tsk` fournit les constantes de champs de tâche.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Étape 1 : définir le répertoire du document
La chaîne `dataDir` contient le chemin du dossier contenant vos fichiers `.mpp`.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Étape 2 : charger le projet externe
`Project externalProject` charge le fichier de projet externe spécifié pour inspection.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Étape 3 : récupérer la tâche externe par UID
`externalProject.getChildren().getByUid(uid)` récupère une tâche de la collection de tâches du projet externe en utilisant son identifiant unique.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Étape 4 : afficher l’ID de la tâche (cas d’utilisation principal)
`externalTask.get(Tsk.ID)` renvoie l’ID interne attribué par Aspose.Tasks pour la tâche donnée.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Étape 5 : afficher l’ID de la tâche originale (externe)
`externalTask.get(Tsk.ExternalID)` récupère l’ID original de la tâche tel qu’il est défini dans le fichier de projet source.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Répétez les étapes ci‑dessus pour toutes les tâches supplémentaires que vous devez suivre entre les projets.

## Problèmes courants et conseils
- **Erreurs de chemin** – Assurez‑vous que `dataDir` se termine par le séparateur de fichiers approprié (`/` ou `\\`).  
- **UID introuvable** – Vérifiez que l’UID existe dans le projet externe ; utilisez `externalProject.getRootTask().getChildren().size()` pour lister les UID disponibles.  
- **Exceptions de licence** – Une licence manquante ou invalide déclenchera une exception de licence à l’exécution.  
- **Grands projets** – Pour des projets de plus de 5 000 tâches, envisagez d’utiliser `ProjectReader` avec le drapeau `LoadOptions` pour diffuser les données et réduire la consommation de mémoire.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks avec d’autres langages de programmation ?**  
R : Oui, Aspose.Tasks prend en charge plusieurs langages, dont Java, .NET et d’autres.

**Q : Où puis‑je trouver la documentation détaillée d’Aspose.Tasks pour Java ?**  
R : Consultez la documentation **[ici](https://reference.aspose.com/tasks/java/)**.

**Q : Existe‑t‑il un essai gratuit d’Aspose.Tasks pour Java ?**  
R : Oui, vous pouvez obtenir un essai gratuit **[ici](https://releases.aspose.com/)**.

**Q : Comment obtenir une licence temporaire pour Aspose.Tasks ?**  
R : Obtenez une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)**.

**Q : Besoin d’aide ou avez‑vous des questions spécifiques ?**  
R : Visitez le forum de support Aspose.Tasks **[ici](https://forum.aspose.com/c/tasks/15)**.

---

**Dernière mise à jour :** 2026-09-09  
**Testé avec :** Aspose.Tasks pour Java 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose

## Tutoriels associés

- [Créer des dépendances de tâches de gestion de projet dans Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Définir la date de début du projet et gérer les tâches parentes et enfants dans Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Créer un projet MPP Java – Modifier la progression des tâches avec Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}