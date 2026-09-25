---
date: 2026-09-25
description: Apprenez comment récupérer les codes de devise à partir des fichiers
  MS Project en utilisant Aspose.Tasks pour Java – la méthode rapide pour obtenir
  le code de devise dont les développeurs Java ont besoin.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Gérer les codes de devise dans Aspose.Tasks
og_description: Récupérez le code de devise Java à partir des fichiers MS Project
  en utilisant Aspose.Tasks. Ce guide vous montre comment lire le projet, extraire
  l'identifiant de devise ISO et l'appliquer dans les applications Java.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Récupérer le code de devise Java depuis MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Récupérer le code de devise Java depuis MS Project avec Aspose.Tasks
url: /fr/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Récupérer le code de devise java à partir de MS Project avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez **comment récupérer le code de devise java** à partir d’un fichier MS Project en utilisant l’API Aspose.Tasks Java. Que vous ayez besoin de générer des rapports financiers multi‑devises, de consolider des projets provenant de différentes régions, ou simplement d’afficher le symbole monétaire correct dans un système en aval, les étapes ci‑dessous vous guideront depuis la configuration de l’environnement jusqu’à l’appel en une seule ligne qui renvoie l’identifiant ISO de la devise. À la fin du guide, vous serez à l’aise pour charger n’importe quel format de fichier Project pris en charge et extraire le code de devise à trois lettres tel que `USD`, `EUR` ou `GBP`.

## Réponses rapides
- **Que fait l'API ?** Elle lit les fichiers MS Project et expose des propriétés telles que le code de devise.  
- **Quel langage est utilisé ?** Java, via la bibliothèque Aspose.Tasks pour Java.  
- **Ai-je besoin d'une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis-je récupérer le code en une ligne ?** Oui—`prj.get(Prj.CURRENCY_CODE)` renvoie immédiatement la chaîne du code de devise.  
- **Est‑il compatible avec toutes les versions de Project ?** Aspose.Tasks prend en charge plus de 20 formats d'entrée, y compris les anciens fichiers MPP, XML et XER.

## Qu'est-ce que la lecture d'un fichier MS Project ?
Lire un fichier MS Project signifie ouvrir programmatiquement un *.mpp* (ou tout autre format pris en charge tel que XML ou XER) et accéder à ses structures de données internes. Ces structures comprennent les tâches, les ressources, les calendriers, les tableaux de coûts et les paramètres financiers. En analysant le fichier, vous pouvez extraire des informations sans lancer Microsoft Project, ce qui permet des flux de travail automatisés de reporting, de migration et d’intégration.

## Pourquoi utiliser Aspose.Tasks pour lire les fichiers msproject ?
Aspose.Tasks offre une solution pure‑Java qui élimine le besoin d’interopérabilité COM ou d’une installation locale de Microsoft Project. Il prend en charge plus de 20 formats de fichiers, peut gérer des projets contenant des milliers de tâches tout en utilisant moins de 100 Mo de mémoire, et fournit un modèle d’objet riche. L’accès direct à des constantes comme `Prj.CURRENCY_CODE` vous permet de récupérer les informations de devise instantanément et de manière fiable.

## Prérequis
Avant de plonger dans le code, assurez‑vous de disposer de ce qui suit :

### Kit de développement Java (JDK) installé
Un JDK récent (11 ou supérieur) est requis. Téléchargez‑le depuis le site officiel d'Oracle : [ici](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Bibliothèque Aspose.Tasks pour Java
Obtenez les dernières binaires Aspose.Tasks pour Java et ajoutez‑les au classpath de votre projet. La documentation complète et les liens de téléchargement sont disponibles [ici](https://reference.aspose.com/tasks/java/).

## Importer les packages
La classe `Project` et les constantes `Prj` se trouvent dans l’espace de noms `com.aspose.tasks`. Importez‑les en haut de votre fichier source Java :

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Guide étape par étape

### Étape 1 : configurer le répertoire de données
Définissez le dossier qui contient votre fichier *.mpp*. Ajustez le chemin pour qu’il corresponde à votre environnement afin que le runtime puisse localiser le fichier de projet.

```java
String dataDir = "Your Data Directory";
```

### Étape 2 : charger le fichier de projet
La classe `Project` est l’objet de niveau supérieur d’Aspose.Tasks qui représente un fichier MS Project unique en mémoire. Créer une instance lit le fichier et construit un modèle en mémoire que vous pouvez interroger.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Étape 3 : récupérer le code de devise
La constante `Prj.CURRENCY_CODE` identifie la propriété qui stocke l’identifiant ISO de la devise. Appeler `prj.get(Prj.CURRENCY_CODE)` renvoie le code à trois lettres en une seule opération.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
La sortie sera le code ISO à trois lettres (par ex., `USD`, `EUR`, `GBP`) que le projet est configuré à utiliser.

### Étape 4 : comment récupérer le code de devise en Java (contexte supplémentaire)
Chargez votre projet, appelez `prj.get(Prj.CURRENCY_CODE)`, et stockez le résultat dans une `String`. Vous pouvez ensuite transmettre cette valeur à tout service financier, moteur de reporting ou composant UI qui nécessite un identifiant de devise.

### Étape 5 : (optionnel) utiliser le code de devise
Les scénarios en aval typiques incluent :

- **Génération de rapports** – préfixer le code aux colonnes de coûts (`USD 1,200`).  
- **Intégration d'API** – envoyer le code ISO aux passerelles de paiement qui exigent un paramètre de devise.  
- **Consolidation de données** – regrouper plusieurs projets par devise pour une analyse au niveau du portefeuille.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Sortie nulle** | Le fichier de projet ne définit pas de devise (la valeur par défaut est vide). | Définissez la devise dans Microsoft Project ou assignez‑la via `prj.set(Prj.CURRENCY_CODE, "USD");` avant la lecture. |
| **Fichier non trouvé** | Chemin `dataDir` incorrect. | Vérifiez le chemin et assurez‑vous que le nom du fichier correspond exactement, y compris la sensibilité à la casse. |
| **Version de fichier non prise en charge** | Fichier *.mpp* très ancien ou corrompu. | Mettez à jour vers la dernière version d'Aspose.Tasks ou convertissez le fichier dans un format plus récent avec Microsoft Project d'abord. |

## Questions fréquemment posées

**Q : Aspose.Tasks peut‑il gérer des structures de projet complexes ?**  
R : Oui, l’API lit les hiérarchies de tâches multi‑niveaux, les pools de ressources, les champs personnalisés et les calendriers sans limitation.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de fichiers MS Project ?**  
R : Absolument. Il prend en charge les formats MPP, XML, XER et autres depuis Project 98 jusqu’aux dernières versions Office.

**Q : Aspose.Tasks fournit‑il de la documentation et du support ?**  
R : Une référence API complète, des exemples de code et un support technique dédié sont disponibles sur le site web d’Aspose.

**Q : Puis‑je essayer Aspose.Tasks avant d’acheter ?**  
R : Un essai gratuit est proposé afin que vous puissiez évaluer toutes les fonctionnalités, y compris l’extraction du code de devise.

**Q : Où puis‑je obtenir une licence temporaire pour l’évaluation ?**  
R : Les licences temporaires sont disponibles depuis le [site web](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2026-09-25  
**Testé avec :** Aspose.Tasks for Java (latest version)  
**Auteur :** Aspose

## Tutoriels associés

- [Propriétés du projet Java – Lire les métadonnées avec Aspose.Tasks](/tasks/java/project-properties/)
- [Comment lire les informations du projet à partir de Microsoft Project avec Aspose.Tasks pour Java](/tasks/java/project-properties/read-project-info/)
- [Récupérer les codes de plan du projet MS dans Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}