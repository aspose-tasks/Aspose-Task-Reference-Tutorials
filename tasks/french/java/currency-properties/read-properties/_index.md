---
date: 2025-12-04
description: Apprenez à lire les propriétés de devise Java à partir des fichiers MS Project
  en utilisant Aspose.Tasks pour Java. Suivez ce guide étape par étape pour extraire
  le code de devise, le symbole, le nombre de décimales et la position de manière
  programmatique.
language: fr
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Lire les propriétés de devise Java avec les projets Aspose.Tasks
url: /java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire les propriétés de devise Java avec les projets Aspose.Tasks

## Introduction
Dans ce tutoriel, vous allez **lire les propriétés de devise Java** à partir de fichiers Microsoft Project en utilisant l'API Aspose.Tasks pour Java. Aspose.Tasks vous permet de travailler avec des fichiers .mpp sans avoir Microsoft Project installé, ce qui le rend idéal pour les rapports automatisés, la migration de données ou l'intégration dans des applications d'entreprise basées sur Java. À la fin de ce guide, vous serez capable d'extraire le code de devise, le symbole, le nombre de décimales et la position du symbole directement depuis un fichier de projet.

## Réponses rapides
- **Que signifie « read currency properties java » ?** Il s'agit de récupérer les métadonnées liées à la devise (code, symbole, décimales, position) d'un fichier MS Project à l'aide de code Java.  
- **Ai‑je besoin d'une licence pour essayer cela ?** Une version d'essai gratuite d'Aspose.Tasks est disponible ; une licence commerciale est requise pour une utilisation en production.  
- **Quelle version du JDK est requise ?** Java 8 ou supérieur.  
- **Puis‑je modifier les paramètres de devise après les avoir lus ?** Oui, Aspose.Tasks permet les opérations de lecture et d'écriture sur les propriétés de devise.  
- **Cette fonctionnalité est‑elle compatible avec toutes les versions .mpp ?** L'API prend en charge les fichiers créés avec Microsoft Project 2003‑2021.

## Qu’est‑ce que « read currency properties java » ?
Lire les propriétés de devise en Java signifie accéder aux paramètres au niveau du projet qui définissent comment les valeurs monétaires sont affichées dans un fichier Microsoft Project. Ces paramètres comprennent le code ISO de la devise (par ex., **USD**), le symbole (**$**), le nombre de décimales et si le symbole apparaît avant ou après le montant.

## Pourquoi lire les propriétés de devise Java avec Aspose.Tasks ?
- **Pas besoin d’installer Microsoft Project** – l'API fonctionne sur n'importe quelle plateforme supportant Java.  
- **Extraction rapide en‑processus** – idéal pour le traitement par lots d’un grand nombre de fichiers de projet.  
- **Contrôle total** – vous pouvez combiner les valeurs récupérées avec des rapports personnalisés ou les intégrer à des systèmes ERP.  
- **Prise en charge multi‑versions** – fonctionne avec les fichiers .mpp de Project 2003 jusqu’à la dernière version 2021.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – Java 8 ou plus récent installé et configuré dans votre `PATH`.  
2. **Aspose.Tasks for Java JAR** – téléchargez la dernière bibliothèque depuis [ici](https://releases.aspose.com/tasks/java/) et ajoutez‑la au classpath de votre projet.  

## Importer les packages
Commencez par importer l’espace de noms Aspose.Tasks requis pour la manipulation de projets :

```java
import com.aspose.tasks.*;
```

## Étape 1 : Configurer votre répertoire de projet
Définissez le dossier contenant le fichier `.mpp` que vous souhaitez analyser. Conserver le chemin dans une variable rend le code réutilisable :

```java
String dataDir = "Your Data Directory";
```

*Remplacez `"Your Data Directory"` par le chemin absolu ou relatif du dossier où se trouve `project.mpp`.*

## Étape 2 : Créer une instance de lecteur de projet
Chargez le fichier Microsoft Project dans un objet `Project`. Cet objet vous donne accès à toutes les propriétés du projet, y compris les paramètres de devise :

```java
Project project = new Project(dataDir + "project.mpp");
```

*Si votre fichier porte un autre nom, modifiez `"project.mpp"` en conséquence.*

## Étape 3 : Afficher les propriétés de devise
Récupérez maintenant chaque attribut de devise à l’aide de l’énumération `Prj` et affichez les résultats dans la console. L'API renvoie des objets que vous pouvez convertir en chaînes pour l’affichage :

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Ce que vous verrez :**  
- **Currency Code** – code ISO‑4217 tel que `USD`, `EUR`, `JPY`.  
- **Currency Digits** – généralement `2` pour la plupart des devises, `0` pour le yen japonais.  
- **Currency Symbol** – le caractère affiché dans les rapports (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` pour **avant** le montant, `1` pour **après**.

## Étape 4 : Fin du traitement
Indiquez que l’extraction s’est terminée avec succès. Ce message simple est utile lorsque le code s’exécute dans le cadre d’un travail par lots plus important :

```java
System.out.println("Process completed Successfully");
```

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **FileNotFoundException** | Le chemin `dataDir` est incorrect ou le nom du fichier est mal orthographié. | Vérifiez la chaîne du répertoire et assurez‑vous que le fichier `.mpp` existe à l’emplacement indiqué. |
| **NullPointerException sur `project.get(...)`** | Le fichier de projet ne contient pas d’informations de devise (peu probable) ou la clé de propriété est erronée. | Utilisez `project.contains(Prj.CURRENCY_CODE)` pour vérifier l’existence avant la lecture. |
| **LicenseException** | Exécution sans licence Aspose.Tasks valide en environnement de production. | Appliquez un fichier de licence avec `License license = new License(); license.setLicense("Aspose.Tasks.lic");` avant de créer l’objet `Project`. |

## Questions fréquentes

**Q : Aspose.Tasks est‑il compatible avec toutes les versions de Microsoft Project ?**  
R : Aspose.Tasks prend en charge les fichiers .mpp générés par Microsoft Project 2003‑2021, couvrant à la fois les anciens et les derniers formats.

**Q : Puis‑je modifier les propriétés de devise avec Aspose.Tasks ?**  
R : Oui, vous pouvez lire et écrire les paramètres de devise. Utilisez `project.set(Prj.CURRENCY_CODE, "EUR");` puis enregistrez le projet.

**Q : Aspose.Tasks convient‑il à un usage commercial ?**  
R : Absolument. C’est une bibliothèque commerciale ; vous pouvez acheter une licence [ici](https://purchase.aspose.com/buy).

**Q : Aspose.Tasks propose‑t‑il une version d’essai gratuite ?**  
R : Oui, une version d’essai pleinement fonctionnelle est disponible [ici](https://releases.aspose.com/).

**Q : Où puis‑je obtenir de l’aide ou du support pour Aspose.Tasks ?**  
R : Le forum officiel d’Aspose.Tasks est le meilleur endroit pour obtenir de l’assistance – visitez‑le [ici](https://forum.aspose.com/c/tasks/15).

## Conclusion
Vous avez maintenant appris comment **lire les propriétés de devise Java** à partir d’un fichier MS Project en utilisant Aspose.Tasks pour Java. Cette capacité vous permet d’intégrer les métadonnées de devise dans des rapports personnalisés, des analyses financières ou des pipelines d’intégration sans dépendre de Microsoft Project. N’hésitez pas à expérimenter la modification des propriétés ou à combiner ces données avec d’autres attributs de projet pour créer des solutions plus riches.

---

**Dernière mise à jour :** 2025-12-04  
**Testé avec :** Aspose.Tasks for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}