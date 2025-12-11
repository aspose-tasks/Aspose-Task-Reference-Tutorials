---
date: 2025-12-09
description: Apprenez à lire les fichiers MS Project et à gérer les codes de devise
  efficacement avec Aspose.Tasks pour Java. Rationalisez vos tâches de gestion de
  projet en toute simplicité.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment lire un fichier MS Project et gérer les codes de devise avec Aspose.Tasks
url: /fr/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire un fichier MS Project et gérer les codes de devise avec Aspose.Tasks

## Introduction
Bienvenue ! Dans ce tutoriel, vous découvrirez **comment lire les données d’un fichier MS Project** et, plus spécifiquement, **gérer les codes de devise** en utilisant l’API Aspose.Tasks pour Java. Que vous génériez des rapports, consolidiez des projets multi‑devises, ou ayez simplement besoin de vous assurer que les symboles financiers corrects apparaissent, ce guide vous accompagne à chaque étape — de la configuration de votre environnement à la récupération du code de devise par programme. À la fin, vous serez à l’aise pour lire les fichiers MS Project et extraire les informations de devise dont vous avez besoin.

## Réponses rapides
- **Que fait l'API ?** Elle lit les fichiers MS Project et expose des propriétés telles que le code de devise.  
- **Quel langage est utilisé ?** Java, via la bibliothèque Aspose.Tasks pour Java.  
- **Ai-je besoin d'une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis-je récupérer le code en une seule ligne ?** Oui—`prj.get(Prj.CURRENCY_CODE)` renvoie la chaîne du code de devise.  
- **Est‑il compatible avec toutes les versions de Project ?** Aspose.Tasks prend en charge les formats anciens (MPP) et récents (XML, XER).

## Qu'est‑ce que **read ms project file** ?
Lire un fichier MS Project signifie ouvrir programmétiquement un document de projet *.mpp* (ou autre format supporté) et accéder à ses structures de données — tâches, ressources, calendriers et paramètres financiers — sans interaction manuelle avec Microsoft Project lui‑même.

## Pourquoi utiliser Aspose.Tasks pour **read msproject** les fichiers ?
- **Prise en charge complète des formats** – fonctionne avec les fichiers de Project 98 jusqu'aux dernières versions d'Office.  
- **Pas besoin de COM ou d'installation d'Office** – pure Java, parfait pour l'automatisation côté serveur.  
- **API riche** – donne un accès direct aux propriétés comme `Prj.CURRENCY_CODE`, vous permettant de **how to retrieve currency** instantanément.  
- **Performance** – analyse légère, idéale pour le traitement par lots de nombreux projets.

## Prérequis
Avant de plonger dans le code, assurez‑vous de disposer de ce qui suit :

### Java Development Kit (JDK) installé
Assurez‑vous qu'un JDK récent est disponible sur votre machine. Vous pouvez télécharger et installer la dernière version du JDK depuis [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Bibliothèque Aspose.Tasks pour Java
Téléchargez et configurez la bibliothèque Aspose.Tasks pour Java. La documentation détaillée et les derniers binaires sont disponibles [here](https://reference.aspose.com/tasks/java/).

## Importer les packages
Pour commencer, importons les packages nécessaires dans votre projet Java :
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Guide étape par étape

### Étape 1 : Configurer le répertoire de données
Définissez le dossier qui contient votre fichier *.mpp*. Ajustez le chemin pour qu’il corresponde à votre environnement.
```java
String dataDir = "Your Data Directory";
```

### Étape 2 : Charger le fichier de projet
Créez une instance `Project` en chargeant le fichier MS Project. C’est à ce moment que vous **read msproject** les données en mémoire.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Étape 3 : Récupérer le code de devise
Maintenant que le projet est chargé, vous pouvez **how to retrieve currency** les informations avec un appel unique. Cela illustre l’utilisation de **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
La sortie sera le code ISO à trois lettres (par ex., `USD`, `EUR`, `GBP`) que le projet a configuré.

### Étape 4 : (Optionnel) Utiliser le code de devise
Vous pourriez vouloir appliquer le code récupéré ailleurs — par exemple pour formater les valeurs de coût dans un rapport personnalisé ou le transmettre à une API financière. Voici une illustration rapide (pas de bloc de code supplémentaire nécessaire) :
- Stockez le code dans une variable.  
- Utilisez‑le lors de la construction de chaînes monétaires.  
- Transmettez‑le aux services en aval qui nécessitent un identifiant de devise.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Sortie nulle** | Le fichier de projet ne définit pas de devise (la valeur par défaut est vide). | Définissez la devise dans Microsoft Project ou assignez‑la via `prj.set(Prj.CURRENCY_CODE, "USD");` avant la lecture. |
| **Fichier non trouvé** | Chemin `dataDir` incorrect. | Vérifiez le chemin et assurez‑vous que le nom du fichier correspond exactement, y compris la sensibilité à la casse. |
| **Version de fichier non prise en charge** | Fichier *.mpp* très ancien ou corrompu. | Utilisez la dernière version d’Aspose.Tasks ou convertissez le fichier dans un format plus récent avec Microsoft Project d’abord. |

## Questions fréquentes

**Q : Aspose.Tasks peut‑il gérer des structures de projet complexes ?**  
R : Oui, l’API peut lire et manipuler des hiérarchies de tâches à plusieurs niveaux, des pools de ressources et des champs personnalisés sans problème.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de fichiers MS Project ?**  
R : Absolument. Il prend en charge les formats MPP, XML, XER et d’autres formats à travers de nombreuses versions de Microsoft Project.

**Q : Aspose.Tasks fournit‑il de la documentation et du support ?**  
R : Une documentation complète, des exemples de code et un support dédié sont disponibles sur le site Web d’Aspose.

**Q : Puis‑je essayer Aspose.Tasks avant d’acheter ?**  
R : Un essai gratuit est proposé afin que vous puissiez évaluer toutes les fonctionnalités, y compris la lecture des codes de devise.

**Q : Où puis‑je obtenir des licences temporaires pour Aspose.Tasks ?**  
R : Des licences temporaires peuvent être obtenues depuis le [website](https://purchase.aspose.com/temporary-license/) pour une évaluation à court terme.

---

**Dernière mise à jour :** 2025-12-09  
**Testé avec :** Aspose.Tasks pour Java (dernière version)  
**Auteur :** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
