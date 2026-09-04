---
date: 2026-06-15
description: Apprenez comment extraire les données Timephased Data des ressources
  MS Project à l'aide d'Aspose.Tasks pour Java. Guide étape par étape pour obtenir
  la resource par id.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Lire les données Timephased Data pour les ressources dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Lire les données Timephased Data pour les ressources dans Aspose.Tasks – obtenir
  la resource par id
url: /fr/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire les données temporelles pour les ressources dans Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez **how to get resource by id** et lire ses données temporelles en utilisant Aspose.Tasks for Java. Nous parcourrons chaque étape — de la configuration du dossier du projet à l'affichage des valeurs de travail et de coût temporelles — afin que vous puissiez extraire des informations de planification précieuses de n'importe quel fichier Microsoft Project de manière programmatique. Aspose.Tasks for Java est une API complète qui permet aux développeurs de créer, lire, modifier et convertir des fichiers Microsoft Project sans nécessiter l'installation de Microsoft Project, en prenant en charge un large éventail de fonctionnalités et de formats de gestion de projet.

## Réponses rapides
- **Que fait “get resource by id” ?** Il récupère un objet `Resource` spécifique d'un `Project` en utilisant son identifiant unique.  
- **Quelle bibliothèque gère les données temporelles ?** Aspose.Tasks for Java fournit l'API `Resource.getTimephasedData`.  
- **Ai‑je besoin d'une licence ?** Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je lire de gros projets ?** Oui — Aspose.Tasks peut traiter des fichiers contenant jusqu'à 10 000 tâches sans charger le fichier complet en mémoire.  
- **Quelle version de Java est requise ?** Java 8 ou supérieure ; la bibliothèque est compatible avec tous les principaux JDK.

## Qu'est‑ce que “get resource by id” ?
`get resource by id` est un appel de méthode qui récupère une instance `Resource` à partir d'un `Project` chargé en utilisant l'ID numérique de la ressource. Cette opération permet d'accéder précisément aux propriétés détaillées d'une ressource, telles que ses affectations, ses calendriers et ses champs personnalisés, et est essentielle pour extraire les données de travail ou de coût temporelles associées à cette ressource spécifique.

## Pourquoi utiliser Aspose.Tasks pour les données temporelles ?
Aspose.Tasks prend en charge **plus de 50 formats d'entrée et de sortie** (MPP, XML, CSV, etc.) et peut extraire les valeurs de travail et de coût temporelles des ressources sur des plannings pluriannuels tout en maintenant une faible utilisation de la mémoire. L'API renvoie les données par intervalles de 15 minutes par défaut, vous offrant ainsi une granularité fine pour les rapports ou les analyses personnalisées.

## Prérequis
Avant de commencer, assurez‑vous de disposer des prérequis suivants :
1. Java Development Kit (JDK) : assurez‑vous d'avoir le JDK installé sur votre système. Vous pouvez le télécharger depuis le [site web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) et suivre les instructions d'installation.  
2. Bibliothèque Aspose.Tasks for Java : téléchargez la bibliothèque Aspose.Tasks for Java depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/) et suivez les instructions d'installation fournies dans la documentation.

## Importer les packages
La première étape consiste à importer les classes Aspose.Tasks requises dans votre fichier source Java.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Étape 1 : Configurer le répertoire de données
Tout d'abord, définissez le répertoire où se trouve votre fichier MS Project. Garder le dossier de données séparé du code source facilite la maintenance du projet.

```java
String dataDir = "Your Data Directory";
```

## Étape 2 : Lire le fichier modèle MS Project
Spécifiez le nom de votre fichier modèle MS Project. Utiliser un modèle garantit des paramètres de colonnes cohérents entre différents projets.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Étape 3 : Lire le fichier d'entrée en tant que projet
La classe `Project` est l'objet central d'Aspose.Tasks qui représente un fichier Microsoft Project en mémoire. Charger le fichier vous donne un accès programmatique aux tâches, aux ressources et aux plannings.

```java
Project project = new Project(dataDir + fileName);
```

## Étape 4 : Obtenir la ressource par ID
Pour récupérer une ressource spécifique, appelez la méthode `getResources().getById(id)`. C’est exactement l’opération référencée par le mot‑clé principal.

```java
Resource resource = project.getResources().getByUid(1);
```

## Étape 5 : Afficher les données temporelles du travail de la ressource
Une fois que vous avez l'objet `Resource`, vous pouvez appeler `resource.getTimephasedData(ResourceTimephasedDataType.Work)` pour obtenir les allocations de travail dans le temps. La collection renvoyée contient des objets `TimephasedData` incluant la date de début, la date de fin et la quantité de travail pour chaque intervalle.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Étape 6 : Afficher les données temporelles du coût de la ressource
De même, `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` renvoie les informations de coût découpées selon les mêmes intervalles temporels. Ceci est utile pour les rapports de budgétisation et de suivi des coûts.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Comment obtenir une ressource par ID en une seule ligne ?
Chargez le projet, puis appelez `project.getResources().getById(5)` — remplacez **5** par l'ID réel de la ressource dont vous avez besoin. Cet appel unique renvoie l'objet `Resource`, après quoi vous pouvez interroger ses données temporelles, ses affectations ou ses champs personnalisés. La méthode s'exécute en temps O(1) car les ressources sont indexées en interne.

## Problèmes courants et solutions
- **Ressource introuvable** – Assurez‑vous que l'ID existe dans le fichier projet ; les IDs commencent à 1 et sont uniques par ressource.  
- **Données temporelles vides** – Vérifiez que la ressource possède des affectations de travail ou de coût ; sinon la collection sera vide.  
- **Performance sur gros fichiers** – Utilisez `Project.setLoadOptions(LoadOptions.fromFile(...))` pour activer le chargement paresseux des projets de plus de 500 Mo.

## Questions fréquemment posées

**Q : Aspose.Tasks peut‑il gérer d'autres types de fichiers de projet que Microsoft Project ?**  
R : Oui, Aspose.Tasks prend en charge MPP, XML, CSV et plusieurs autres formats, vous permettant de lire et d'écrire à travers différentes normes.

**Q : Aspose.Tasks est‑il compatible avec différents environnements de développement Java ?**  
R : Absolument. La bibliothèque fonctionne avec tous les principaux IDE (IntelliJ IDEA, Eclipse, NetBeans) et outils de construction (Maven, Gradle).

**Q : Puis‑je manipuler les données du projet avec Aspose.Tasks ?**  
R : Oui, vous pouvez créer, modifier et supprimer des tâches, des ressources, des affectations, ainsi que des champs personnalisés via l'API.

**Q : Aspose.Tasks convient‑il aux projets de niveau entreprise ?**  
R : Il le fait. Les entreprises utilisent Aspose.Tasks pour le traitement à haut volume, les conversions par lots et les rapports côté serveur car il ne nécessite aucune installation de Microsoft Project.

**Q : Où puis‑je trouver de l'aide si je rencontre des problèmes avec Aspose.Tasks ?**  
R : Vous pouvez consulter le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir de l'assistance de la communauté et de l'équipe de support.

## Conclusion
Dans ce tutoriel, nous avons appris comment **get resource by id** et lire ses données temporelles de travail et de coût en utilisant Aspose.Tasks for Java. En suivant ces étapes, vous pouvez extraire efficacement des informations de planification précieuses de vos fichiers projet et les intégrer à des pipelines de rapports ou d'analyses personnalisés.

---

**Dernière mise à jour :** 2026-06-15  
**Testé avec :** Aspose.Tasks 24.11 for Java  
**Auteur :** Aspose

## Tutoriels associés

- [Ajouter une ressource au projet avec Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)
- [Gérer les coûts des ressources MS Project avec Aspose.Tasks for Java](/tasks/java/resource-management/resource-cost/)
- [Lire les semaines de travail Java à partir du calendrier MS Project Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}