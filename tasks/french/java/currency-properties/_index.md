---
date: 2026-09-14
description: Apprenez comment modifier le format de la devise et lire les propriétés
  de la devise en Java avec Aspose.Tasks. Extrayez le code de la devise, récupérez
  le symbole de la devise et mettez à jour la devise du projet dans les fichiers MS
  Project.
keywords:
- change currency format
- retrieve currency symbol
- update project currency
- extract currency code java
lastmod: 2026-09-14
linktitle: Comment modifier le format de la devise
og_description: Apprenez comment modifier le format de la devise et lire les propriétés
  de la devise en Java avec Aspose.Tasks. Guide étape par étape pour extraire le code
  de la devise et mettre à jour la devise du projet.
og_image_alt: Tutorial showing how to change currency format in Aspose.Tasks for Java
og_title: Comment modifier le format de la devise en Java avec Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to change currency format and read currency properties in
    Java using Aspose.Tasks. Extract currency code, retrieve currency symbol, and
    update project currency in MS Project files.
  headline: How to change currency format in Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Use `Project.setCurrencyCode()` and related methods, then save the
      project again.
    question: Can I change the currency after the project is already saved?
  - answer: The numeric values remain unchanged; only the display format (symbol,
      decimal separator) is updated. You must recalculate costs if you need conversion
      between currencies.
    question: Does changing the currency affect existing cost values?
  - answer: Aspose.Tasks supports any ISO‑4217 currency code, so you’re effectively
      unlimited.
    question: Are there any limits on the number of currencies I can define?
  - answer: The library falls back to the default currency (USD) and logs a warning;
      you can override this by setting the desired currency manually.
    question: What happens if I open a project with an unsupported currency code?
  - answer: Absolutely. The same API works for both *.mpp* and *.xml* formats.
    question: Is it possible to read/write currency properties in a Project XML file?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- change currency format
- Aspose.Tasks
- Java project management
- currency handling
title: Comment modifier le format de la devise en Java avec Aspose.Tasks
url: /fr/java/currency-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire les propriétés de devise Java avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez comment **modifier le format de devise** et lire les propriétés de devise dans des projets Java utilisant Aspose.Tasks. Des données financières précises sont essentielles pour les équipes multinationales, et maîtriser ces API vous permet d'extraire le code ISO‑4217, de récupérer le symbole de la devise et de mettre à jour les paramètres monétaires du projet sans modifier manuellement les feuilles de calcul.

## Réponses rapides
- **Que signifie « lire la devise » ?** Cela signifie extraire le code de devise, le symbole et les paramètres de format numérique stockés dans un fichier Project.  
- **Pourquoi ajuster les paramètres de devise ?** Pour aligner les rapports de coûts avec les conventions régionales et éviter les erreurs de conversion.  
- **Ai-je besoin d’une licence ?** Oui – une licence valide d’Aspose.Tasks for Java est requise pour la production ; un essai gratuit suffit pour l’évaluation.  
- **Quelles versions de Project sont prises en charge ?** Les formats *.mpp* (Project 2007‑2024) et *.xml* sont entièrement supportés, couvrant plus de 20 ans de versions de fichiers.  
- **Une configuration supplémentaire est‑elle nécessaire ?** Il suffit d’ajouter le JAR Aspose.Tasks for Java à votre classpath et d’importer les classes pertinentes.

## Lire les propriétés de devise Java dans les projets Aspose.Tasks
Dans le domaine dynamique de la gestion de projet, extraire les détails de la devise est essentiel pour une analyse précise des coûts. Notre guide dédié **[Lire les propriétés de devise dans les projets Aspose.Tasks](./read-properties/)** vous accompagne à chaque étape — de l’ouverture d’un fichier de projet à la récupération du code de devise, du symbole et du format. En suivant le tutoriel, vous pourrez :

* Extraire le code de devise (par ex., USD, EUR) utilisé dans tout le projet.  
* Accéder au symbole de la devise et aux paramètres de format numérique.  
* Utiliser ces informations pour générer des rapports de coûts localisés ou alimenter des tableaux de bord financiers.

Comprendre comment lire la devise vous permet d’auditer les budgets de projet, de comparer les coûts entre les régions et de respecter les normes comptables.

## Comment extraire le code de devise en Java avec Aspose.Tasks
La méthode `Project.getCurrencyCode()` renvoie l’identifiant ISO‑4217 à trois lettres de l’unité monétaire du projet.

**Réponse directe :** Appelez `project.getCurrencyCode()` pour obtenir le code de devise tel que **USD** ou **EUR** ; vous pouvez ensuite stocker, consigner ou transmettre cette valeur à des services financiers externes pour conversion. Cet appel en une seule ligne vous fournit un identifiant fiable, conforme aux normes, qui fonctionne avec toutes les versions de Project prises en charge.

Cette méthode offre un moyen rapide de synchroniser les données du projet avec les systèmes ERP qui attendent un code standardisé.

## Comment ajuster le format de devise en Java avec Aspose.Tasks
Modifier la représentation visuelle des valeurs monétaires se fait via trois propriétés simples.

`project.setCurrencySymbol(String)` définit le symbole de devise affiché pour les valeurs monétaires.  
`project.setCurrencyDecimalSeparator(char)` définit le caractère utilisé pour séparer la partie entière de la partie fractionnaire.  
`project.setCurrencyThousandsSeparator(char)` définit le caractère utilisé pour séparer les groupes de milliers.

**Réponse directe :** Utilisez `project.setCurrencySymbol("€")`, `project.setCurrencyDecimalSeparator(",")` et `project.setCurrencyThousandsSeparator(".")` pour définir respectivement le symbole, le séparateur décimal et le séparateur des milliers — cela modifie entièrement le format de devise en une seule opération. Ajuster ces paramètres garantit que chaque partie prenante voit les nombres dans un style familier, réduisant les malentendus.

* `project.setCurrencySymbol("€")` – définit le symbole visuel.  
* `project.setCurrencyDecimalSeparator(",")` – définit le séparateur décimal.  
* `project.setCurrencyThousandsSeparator(".")` – définit le séparateur des milliers.  

## Comment définir les propriétés de devise dans les projets Aspose.Tasks
Lorsqu’un projet s’étend à un nouveau marché ou qu’un client demande un format monétaire différent, vous devrez mettre à jour la devise de manière programmatique.

`project.setCurrencyCode(String)` définit le code de devise ISO‑4217 pour le projet.

**Réponse directe :** Appelez `project.setCurrencyCode("GBP")` conjointement avec `project.setCurrencySymbol("£")` et les séparateurs appropriés, puis enregistrez le projet ; la bibliothèque met à jour tous les paramètres d’affichage tout en conservant les données de coûts existantes. Cette approche vous donne un contrôle complet sur la représentation financière de votre planning.

Notre guide étape‑par‑étape **[Définir les propriétés de devise dans les projets Aspose.Tasks](./set-properties/)** explique comment :

* Définir un nouveau code de devise et symbole pour l’ensemble du projet.  
* Ajuster le format numérique (décimales, séparateurs de milliers) pour correspondre aux conventions locales.  
* Enregistrer le fichier de projet mis à jour sans perdre aucune donnée existante.

En maîtrisant la définition de la devise, vous pouvez basculer entre USD, GBP, JPY ou toute devise prise en charge à la volée.

## Pourquoi maîtriser la gestion des devises dans Aspose.Tasks ?
Une gestion correcte des devises élimine les mauvaises interprétations coûteuses et simplifie la collaboration mondiale.

**Réponse directe :** Maîtriser la gestion des devises vous permet de présenter les coûts dans le format natif de chaque équipe, d’assurer des rapports précis, de respecter les normes comptables régionales et de permettre des flux de travail financiers automatisés — économisant des heures de reformatage manuel par projet.

* **Collaboration mondiale :** Les équipes de différents pays peuvent voir les coûts dans leur format natif.  
* **Rapports précis :** Éviter les erreurs d’arrondi ou de conversion qui pourraient affecter le budget.  
* **Conformité :** S’aligner sur les normes comptables régionales et les spécifications du client.  
* **Automatisation :** Réduire les modifications manuelles en appliquant programmétiquement les paramètres de devise lors de la génération du projet.

## Cas d’utilisation réels
* **Projets multinationaux :** Une entreprise de construction gérant des sites en Europe et en Amérique du Nord doit présenter les budgets à la fois en EUR et en USD.  
* **Audits financiers :** Les auditeurs exigent une vue claire du contexte de devise pour chaque entrée de coût.  
* **Modèles de tarification dynamique :** Les fournisseurs SaaS ajustent les coûts d’abonnement en fonction de la devise locale du client.

## Pièges courants et conseils
* **Piège :** Oublier de mettre à jour le symbole de devise après avoir changé le code.  
  **Conseil :** Toujours définir à la fois le code et le symbole ensemble pour éviter des affichages incohérents.  
* **Piège :** Se fier à la locale par défaut de la machine exécutant le code.  
  **Conseil :** Spécifiez explicitement le format de devise souhaité dans votre code Aspose.Tasks pour garantir la cohérence entre les environnements.  

## Tutoriels sur les propriétés de devise
### [Lire les propriétés de devise dans les projets Aspose.Tasks](./read-properties/)
Apprenez comment extraire les informations de devise des fichiers MS Project à l’aide d’Aspose.Tasks pour Java. Guide étape par étape fourni.

### [Définir les propriétés de devise dans les projets Aspose.Tasks](./set-properties/)
Apprenez comment définir les propriétés de devise dans les projets Aspose.Tasks en utilisant Java. Manipulez les fichiers Microsoft Project sans effort.

## Questions fréquentes

**Q : Puis-je changer la devise après que le projet a déjà été enregistré ?**  
R : Oui. Utilisez `Project.setCurrencyCode()` et les méthodes associées, puis enregistrez à nouveau le projet.

**Q : Le changement de devise affecte-t-il les valeurs de coût existantes ?**  
R : Les valeurs numériques restent inchangées ; seul le format d’affichage (symbole, séparateur décimal) est mis à jour. Vous devez recalculer les coûts si vous avez besoin d’une conversion entre devises.

**Q : Existe-t-il une limite au nombre de devises que je peux définir ?**  
R : Aspose.Tasks prend en charge n’importe quel code de devise ISO‑4217, vous êtes donc pratiquement illimité.

**Q : Que se passe-t-il si j’ouvre un projet avec un code de devise non pris en charge ?**  
R : La bibliothèque revient à la devise par défaut (USD) et consigne un avertissement ; vous pouvez remplacer cela en définissant manuellement la devise souhaitée.

**Q : Est‑il possible de lire/écrire les propriétés de devise dans un fichier Project XML ?**  
R : Absolument. La même API fonctionne pour les formats *.mpp* et *.xml*.

---

**Dernière mise à jour :** 2026-09-14  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [propriétés du projet Java – Extraire le symbole de devise d’un MPP avec Aspose.Tasks pour Java](/tasks/java/currency/currency-symbols/)
- [Comment récupérer la devise à partir de MS Project avec Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Propriétés du projet Java – Lire les métadonnées avec Aspose.Tasks](/tasks/java/project-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}