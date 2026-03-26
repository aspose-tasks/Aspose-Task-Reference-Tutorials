---
date: 2025-12-21
description: Apprenez comment créer des SVG à partir de fichiers MPP en Java et enregistrer
  le projet au format SVG en utilisant la bibliothèque Aspose.Tasks. Guide étape par
  étape avec des exemples de code.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment créer un SVG à partir d'un MPP en Java avec Aspose.Tasks
url: /fr/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un SVG à partir d'un MPP en Java

## Introduction
Dans ce tutoriel, vous apprendrez comment **créer un SVG à partir d'un MPP** en utilisant Aspose.Tasks for Java. Convertir un fichier Microsoft Project (MPP) en graphiques vectoriels évolutifs (SVG) vous permet d'intégrer des diagrammes de haute qualité, indépendants de la résolution, directement dans des pages web, des rapports ou des tableaux de bord. Nous parcourrons la configuration requise, montrerons le code exact dont vous avez besoin, et expliquerons chaque étape afin que vous puissiez **enregistrer le projet au format SVG** dans vos propres applications.

## Réponses rapides
- **Que signifie « créer un SVG à partir d'un MPP » ?**  
  Cela convertit un fichier Microsoft Project (.mpp) en une image SVG qui peut être affichée dans n'importe quel navigateur sans perte de qualité.  
- **Quelle bibliothèque gère la conversion ?**  
  Aspose.Tasks for Java fournit une méthode `save` en une seule ligne pour effectuer la conversion.  
- **Ai‑je besoin d'une licence ?**  
  Une licence temporaire est requise pour une utilisation commerciale ; un essai gratuit est disponible.  
- **Quelles sont les conditions préalables ?**  
  Java JDK 8+ et le JAR Aspose.Tasks for Java.  
- **Combien de temps prend la conversion ?**  
  Généralement moins d'une seconde pour les fichiers de projet standards.

## Qu’est‑ce que « créer un SVG à partir d'un MPP » ?
Créer un SVG à partir d'un fichier MPP signifie exporter la représentation visuelle d'un planning de projet — tâches, chronologies et ressources — au format Scalable Vector Graphics. Le SVG est basé sur XML, léger et s'adapte parfaitement aux écrans haute résolution.

## Pourquoi utiliser Aspose.Tasks pour enregistrer le projet au format SVG ?
- **Aucune installation de Microsoft Project requise** – la bibliothèque fonctionne de manière indépendante.  
- **Fidélité totale** – les graphiques, barres Gantt et jalons conservent leurs styles.  
- **Multi‑plateforme** – exécutez le code sous Windows, Linux ou macOS.  
- **Intégration facile** – un appel API en une ligne s'intègre naturellement aux pipelines Java existants.

## Prérequis
- **Java Development Kit (JDK)** – version 8 ou supérieure. Téléchargez-le depuis le site d'Oracle.  
- **Aspose.Tasks for Java** – obtenez la bibliothèque depuis la page officielle de téléchargement **[ici](https://releases.aspose.com/tasks/java/)**.  

## Importer les packages
Tout d'abord, importez les classes dont vous aurez besoin. Le bloc d'importation reste inchangé.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Étape 1 : Définir le répertoire de données
Spécifiez où se trouve votre fichier MPP source et où le SVG sera écrit.

```java
String dataDir = "Your Data Directory";
```

> **Astuce :** Utilisez un chemin absolu ou un chemin relatif au dossier des ressources de votre projet pour éviter `FileNotFoundException`.

## Étape 2 : Charger le fichier MPP
Créez une instance `Project` en chargeant le fichier Microsoft Project existant.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Cette ligne lit *HomeMovePlan.mpp* depuis le dossier que vous avez défini précédemment.

## Étape 3 : Enregistrer le projet au format SVG
Vous pouvez maintenant **enregistrer le projet au format SVG** avec une seule commande.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

La méthode écrit `project5.svg` dans le même répertoire. Le SVG résultant peut être ouvert dans n'importe quel navigateur moderne ou intégré directement dans du HTML.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **File not found** | Chemin `dataDir` incorrect | Vérifiez que la chaîne du répertoire se termine par un séparateur (`/` ou `\\`). |
| **Blank SVG output** | Projet chargé sans vues | Assurez‑vous que le fichier MPP contient une vue Gantt avant l'enregistrement. |
| **License exception** | Aucune licence valide appliquée | Appliquez une licence temporaire avec `License.setLicense("path/to/license.xml")` avant d'appeler `save`. |

## Questions fréquentes

**Q : Aspose.Tasks for Java est‑il compatible avec toutes les versions des fichiers Microsoft Project ?**  
R : Oui, il prend en charge les formats MPP, MPT et XML, des versions anciennes aux dernières versions de Project.

**Q : Puis‑je personnaliser l'apparence du SVG généré ?**  
R : Absolument. Utilisez `SvgOptions` pour définir les polices, les couleurs et les options de mise en page avant d'appeler `save`.

**Q : Aspose.Tasks for Java nécessite‑t‑il une licence pour une utilisation commerciale ?**  
R : Oui, une licence valide est requise pour la production. Vous pouvez obtenir une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)**.

**Q : Puis‑je essayer Aspose.Tasks for Java avant d'acheter ?**  
R : Oui, un essai gratuit est disponible **[ici](https://purchase.aspose.com/buy)**.

**Q : Où puis‑je obtenir du support pour Aspose.Tasks for Java ?**  
R : Visitez le forum communautaire **[ici](https://forum.aspose.com/c/tasks/15)** pour poser des questions et partager vos retours.

## Conclusion
Vous savez maintenant comment **créer un SVG à partir d'un MPP** en Java et comment **enregistrer le projet au format SVG** efficacement avec Aspose.Tasks. Cette fonctionnalité vous permet d'intégrer des visualisations de projet riches dans des portails web, des tableaux de bord de reporting ou tout endroit où des graphiques évolutifs sont nécessaires. Expérimentez avec `SvgOptions` pour affiner la sortie, et vous disposerez d'un outil puissant dans votre boîte à outils de développement.

---

**Dernière mise à jour :** 2025-12-21  
**Testé avec :** Aspose.Tasks for Java 24.10  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}