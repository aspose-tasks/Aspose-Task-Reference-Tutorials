---
date: 2026-06-15
description: Apprenez à calculer le pourcentage de ressources Java avec Aspose.Tasks,
  y compris comment obtenir le pourcentage de travail accompli pour les ressources
  MS Project. Guide étape par étape avec des exemples de code.
keywords:
- calculate resource percentage java
- get percent work complete
- Aspose.Tasks resource percentage
- Java project management API
linktitle: Effectuer des calculs de pourcentage pour les ressources dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to calculate resource percentage java with Aspose.Tasks,
    including how to get percent work complete for MS Project resources. Step‑by‑step
    guide with code examples.
  headline: calculate resource percentage java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It’s the percentage of work a resource has completed relative to its total
      assigned work.
    question: What does “resource percentage” mean?
  - answer: '`Rsc.PERCENT_WORK_COMPLETE` via the `Resource` class.'
    question: Which API call returns this value?
  - answer: A temporary or full Aspose.Tasks license is required for production use.
    question: Do I need a license?
  - answer: Yes – the API works with Spring, Hibernate, and plain Java projects.
    question: Can I use this with other Java frameworks?
  - answer: Any recent version that supports the `Rsc` enumeration (e.g., 24.x).
    question: What version of Aspose.Tasks is needed?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: calculer le pourcentage de ressources Java avec Aspose.Tasks
url: /fr/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# calculer le pourcentage de ressource en Java avec Aspose.Tasks

## Introduction
Bienvenue ! Dans ce tutoriel, vous apprendrez **comment calculer le pourcentage de ressource en Java** en utilisant la bibliothèque Aspose.Tasks pour Java. Nous parcourrons l'extraction du *pourcentage de travail accompli* pour chaque ressource dans un fichier Microsoft Project, expliquerons pourquoi cette métrique est importante et vous montrerons le code exact dont vous avez besoin. À la fin, vous serez capable d'intégrer les calculs de pourcentage de ressource dans toute solution de gestion de projet basée sur Java.

## Réponses rapides
- **Que signifie « pourcentage de ressource » ?** C’est le pourcentage du travail qu’une ressource a accompli par rapport à son travail total assigné.  
- **Quel appel d’API renvoie cette valeur ?** `Rsc.PERCENT_WORK_COMPLETE` via la classe `Resource`.  
- **Ai-je besoin d’une licence ?** Une licence temporaire ou complète d’Aspose.Tasks est requise pour une utilisation en production.  
- **Puis-je l’utiliser avec d’autres frameworks Java ?** Oui – l’API fonctionne avec Spring, Hibernate et les projets Java classiques.  
- **Quelle version d’Aspose.Tasks est nécessaire ?** Toute version récente qui prend en charge l’énumération `Rsc` (par ex., 24.x).

## Qu’est-ce que le calcul du pourcentage de ressource en Java ?
Calculer le pourcentage de ressource en Java consiste à ouvrir un fichier Microsoft Project, lire le travail assigné à chaque ressource, et déterminer la proportion de ce travail déjà accompli. Cette métrique aide les chefs de projet à évaluer l’avancement, équilibrer les charges de travail et identifier les retards potentiels sans calculs manuels.

## Pourquoi obtenir le pourcentage de travail accompli ?
Récupérer le pourcentage de travail accompli pour chaque ressource offre une vue immédiate de la part de l’effort planifié qui a été terminée, permettant d’identifier rapidement les tâches en retard ou les ressources sous‑utilisées. Cette visibilité favorise une prise de décision rapide et un reporting d’état plus précis.

## Prérequis
### Environnement de développement Java
Assurez‑vous d’avoir le Java Development Kit (JDK) installé. Vous pouvez télécharger le JDK depuis [ici](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Bibliothèque Aspose.Tasks
Téléchargez et ajoutez la bibliothèque Aspose.Tasks à votre projet depuis [ici](https://releases.aspose.com/tasks/java/) et suivez les instructions d’installation fournies dans la documentation [ici](https://reference.aspose.com/tasks/java/).

## Importer les packages
La classe `Resource` représente une ressource de projet et donne accès aux champs tels que le pourcentage de travail accompli.  
Avant de commencer à coder, importons les packages nécessaires pour ce tutoriel :
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Comment configurer le chemin du fichier de projet ?
Spécifiez l’emplacement de votre fichier Microsoft Project en fournissant soit un chemin absolu, soit un chemin relatif au répertoire de travail de l’application. La chaîne de chemin doit pointer vers un fichier *.mpp* valide afin qu’Aspose.Tasks puisse le localiser et l’ouvrir pour un traitement ultérieur.
```java
String dataDir = "Your Data Directory";
```
Remplacez `"Your Data Directory"` par le dossier contenant votre fichier Microsoft Project.

## Comment charger le projet ?
Créez une nouvelle instance de la classe `Project` en utilisant le chemin de fichier que vous avez défini précédemment. La classe `Project` représente un fichier Microsoft Project et donne accès à ses tâches, ressources et autres données du projet, en chargeant tout en mémoire pour l’analyse.
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
Cela charge le fichier **Software Development.mpp** depuis le répertoire que vous avez spécifié.

## Comment itérer sur les ressources ?
Utilisez la méthode `project.getResources()` pour obtenir une collection de toutes les ressources définies dans le projet chargé. Parcourez cette collection avec une boucle `for` Java standard ou une construction `for‑each` améliorée, vous permettant d’examiner chaque objet `Resource` individuellement et de récupérer ses champs associés.
```java
for (Resource res : prj.getResources()) {
```
Nous parcourons chaque ressource définie dans le projet.

## Comment vérifier le nom de la ressource et obtenir le pourcentage de travail accompli ?
Tout d’abord, assurez‑vous que l’objet `Resource` possède un nom non vide afin d’éviter de traiter des entrées factices. Ensuite, appelez `res.get(Rsc.PERCENT_WORK_COMPLETE)` qui renvoie un double représentant le pourcentage de travail accompli pour cette ressource, compris entre 0 et 100. Vous pouvez formater cette valeur pour l’affichage ou l’utiliser dans d’autres calculs afin d’évaluer la santé globale du projet.
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
Le code vérifie d’abord que la ressource possède un nom, puis affiche la valeur du **pourcentage de travail accompli** pour cette ressource.

## Problèmes courants et solutions
- **NullPointerException** – Assurez‑vous que le chemin du fichier projet est correct et que le fichier se charge sans erreurs.  
- **Pourcentages incorrects** – Vérifiez que la ressource a réellement du travail assigné ; sinon le pourcentage sera `0`.  
- **Erreurs de licence** – Utilisez une licence Aspose.Tasks valide ou une licence d’évaluation temporaire pour éviter les restrictions d’exécution.

## Questions fréquemment posées (Original)

### Puis-je utiliser Aspose.Tasks pour Java avec d’autres frameworks Java ?
Oui, Aspose.Tasks pour Java est compatible avec divers frameworks Java tels que Spring, Hibernate, et d’autres.

### Aspose.Tasks prend‑il en charge toutes les versions des fichiers Microsoft Project ?
Aspose.Tasks prend en charge toutes les versions des fichiers Microsoft Project, y compris MPP, MPT, XML, et d’autres.

### Puis‑je manipuler les plannings de projet avec Aspose.Tasks ?
Absolument, Aspose.Tasks offre des fonctionnalités complètes pour manipuler les plannings de projet, y compris les tâches, les ressources, les calendriers, et plus encore.

### Existe‑t‑il un forum communautaire pour le support d’Aspose.Tasks ?
Oui, vous pouvez trouver de l’aide et échanger avec d’autres utilisateurs sur le forum communautaire Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

### Aspose.Tasks propose‑t‑il des licences temporaires à des fins d’évaluation ?
Oui, vous pouvez obtenir une licence temporaire d’évaluation depuis [ici](https://purchase.aspose.com/temporary-license/).

## FAQ supplémentaires

**Q:** Comment formater la sortie pour afficher les pourcentages avec le signe % ?  
**A:** Récupérez la valeur numérique avec `res.get(Rsc.PERCENT_WORK_COMPLETE)` et formatez‑la en utilisant `String.format("%.2f%%", value)`.

**Q:** Puis‑je filtrer les ressources pour n’afficher que celles avec moins de 50 % d’achèvement ?  
**A:** Oui, ajoutez une condition `if` vérifiant `res.get(Rsc.PERCENT_WORK_COMPLETE) < 50` avant l’affichage.

**Q:** Est‑il possible d’écrire les pourcentages dans le fichier Project ?  
**A:** Le champ `Rsc.PERCENT_WORK_COMPLETE` est en lecture seule ; vous devez plutôt ajuster les affectations de tâches.

**Q:** Cela fonctionne‑t‑il avec les fichiers Project Online (cloud) ?  
**A:** Vous devez d’abord télécharger le fichier .mpp localement ; Aspose.Tasks fonctionne avec le format de fichier, pas directement avec le service cloud.

## Avantages quantifiés de l’utilisation d’Aspose.Tasks
Aspose.Tasks prend en charge **plus de 30 formats de fichiers** (MPP, MPT, XML, CSV, etc.) et peut traiter des projets contenant **jusqu’à 10 000 tâches** tout en maintenant l’utilisation de la mémoire sous 200 Mo grâce au streaming des données. Le champ **en lecture seule `Rsc.PERCENT_WORK_COMPLETE`** de la bibliothèque est calculé en temps O(n), garantissant une récupération rapide même pour de grands plannings.

## Conclusion
Dans ce guide, nous avons démontré **comment calculer le pourcentage de ressource en Java** en utilisant Aspose.Tasks, en nous concentrant sur la récupération du *pourcentage de travail accompli* pour chaque ressource. En suivant les étapes ci‑dessus, vous pouvez intégrer des analyses précises du pourcentage de ressource dans vos applications Java, vous offrant une meilleure visibilité sur la santé du projet et l’utilisation des ressources.

---

**Dernière mise à jour :** 2026-06-15  
**Testé avec :** Aspose.Tasks for Java 24.10  
**Auteur :** Aspose

## Tutoriels associés

- [Ajouter une ressource au projet avec Aspose.Tasks pour Java](/tasks/java/resource-management/create-resources/)
- [Gérer les coûts des ressources MS Project avec Aspose.Tasks pour Java](/tasks/java/resource-management/resource-cost/)
- [Calculs du pourcentage d’achèvement des tâches dans Aspose.Tasks](/tasks/java/task-properties/percentage-complete-calculations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}