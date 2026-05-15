---
date: 2026-01-13
description: Apprenez comment itérer les ressources non racine dans les fichiers Microsoft
  Project à l’aide d’Aspose.Tasks pour Java.
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Parcourir les ressources non racines avec Aspose.Tasks pour Java
url: /fr/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Parcourir les ressources non‑racine avec Aspose.Tasks pour Java

## Introduction
Aspose.Tasks pour Java est une bibliothèque puissante qui offre aux développeurs une façon propre et orientée objet de travailler avec les fichiers Microsoft Project. Dans ce tutoriel, vous apprendrez **comment parcourir les ressources non‑racine** afin de lire, modifier ou analyser les données de ressources sans gérer le nœud racine factice. Que vous construisiez un outil de reporting, un script de migration ou un planificateur personnalisé, maîtriser cette technique rendra votre code plus précis et plus efficace.

## Réponses rapides
- **Que signifie « ressource non‑racine » ?** Une ressource qui n’est pas le repère « Project » par défaut (le nœud racine).  
- **Pourquoi filtrer la ressource racine ?** La racine ne contient aucune donnée de planification utile et peut encombrer les rapports.  
- **Quelle classe Aspose.Tasks fournit la collection de ressources ?** `Project.getResources()`.  
- **Ai‑je besoin d’une licence pour ce code ?** Une version d’essai gratuite suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je utiliser cela avec Java 17 ?** Oui – Aspose.Tasks prend en charge Java 8 et versions supérieures.

## Prérequis
Avant de plonger dans le code, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – Installez le dernier JDK depuis le [site Web d'Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Bibliothèque Aspose.Tasks pour Java** – Téléchargez le JAR le plus récent depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/).  

## Importer les packages
Dans votre projet Java, importez les classes Aspose.Tasks nécessaires :

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Étape 1 : Configurer le répertoire de données
```java
String dataDir = "Your Data Directory";
```
Remplacez `"Your Data Directory"` par le chemin absolu où résident vos fichiers `.mpp`.

## Étape 2 : Charger le fichier de projet
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
Cette instruction crée une instance `Project` en chargeant **ResourceCosts.mpp** depuis le dossier que vous avez indiqué.

## Étape 3 : Parcourir les ressources non‑racine
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
La boucle parcourt chaque objet `Resource` du projet. La vérification `isRoot()` ignore la ressource racine intégrée, et l’instruction `System.out.println` affiche le nom de chaque **ressource non‑racine**.

## Comment parcourir les ressources non‑racine
L’extrait ci‑dessus montre le schéma de base :

1. Récupérez la collection complète avec `prj.getResources()`.  
2. Utilisez `isRoot()` pour filtrer le repère.  
3. Accédez à n’importe quel champ de ressource (par ex., `Rsc.NAME`, `Rsc.COST`) selon vos besoins.

Vous pouvez étendre ce schéma pour agréger les coûts, exporter vers CSV ou appliquer des règles métier personnalisées.

## Pièges courants et conseils
- **Vérifications de null** – Certaines ressources peuvent contenir des champs optionnels ; protégez toujours les appels à `get()` contre les valeurs `null`.  
- **Performance** – Pour des projets très volumineux, envisagez une boucle basée sur les index afin d’éviter la création de collections intermédiaires.  
- **Licence** – Exécuter le code sans licence valide ajoutera un filigrane aux fichiers exportés ; assurez‑vous d’activer votre licence dès le démarrage de l’application.

## Conclusion
En suivant ces étapes, vous savez maintenant **comment parcourir les ressources non‑racine** avec Aspose.Tasks pour Java. Cette technique vous aide à vous concentrer sur les véritables ressources du projet, à nettoyer les extractions de données et à créer des solutions de gestion de projet plus fiables.

## FAQ
### Puis‑je utiliser Aspose.Tasks pour Java afin de créer de nouveaux fichiers de projet ?
Oui, Aspose.Tasks offre des capacités CRUD complètes (Create, Read, Update, Delete) pour les formats de projet MPP, MPT et XML.  

### Aspose.Tasks prend‑il en charge toutes les versions des fichiers Microsoft Project ?
Absolument. Il gère les fichiers Project 2003‑2019, y compris les dernières spécifications MPP.  

### Aspose.Tasks est‑il compatible avec les frameworks Java comme Spring ?
Oui, vous pouvez injecter la bibliothèque dans des beans Spring ou l’utiliser dans toute application Java standard.  

### Puis‑je personnaliser les champs de données du projet avec Aspose.Tasks ?
Définitivement. L’API vous permet d’ajouter, de modifier ou de supprimer des champs personnalisés sur les tâches, les ressources et les affectations.  

### Aspose.Tasks fournit‑il un support et une documentation pour les développeurs ?
Le produit comprend une documentation API exhaustive, des exemples de code et un forum de support dédié pour une assistance rapide.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-01-13  
**Testé avec :** Aspose.Tasks pour Java 24.12  
**Auteur :** Aspose  

---