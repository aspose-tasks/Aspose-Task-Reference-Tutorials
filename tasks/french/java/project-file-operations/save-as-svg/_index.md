---
date: 2026-03-27
description: Apprenez à exporter MPP en SVG en Java avec Aspose.Tasks. Guide étape
  par étape, exemples de code et astuces pour enregistrer rapidement un projet au
  format SVG.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment exporter un MPP en SVG en Java avec Aspose.Tasks
url: /fr/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment exporter MPP en SVG avec Java

## Exportation de MPP en SVG – Introduction
Dans ce tutoriel, vous apprendrez comment **exporter MPP en SVG** à l'aide d'Aspose.Tasks pour Java. Convertir un fichier Microsoft Project (MPP) en une image Scalable Vector Graphics (SVG) vous permet d'intégrer des diagrammes haute‑qualité, indépendants de la résolution, directement dans des pages web, des rapports ou des tableaux de bord. Nous parcourrons la configuration requise, montrerons le code exact dont vous avez besoin, et expliquerons chaque étape afin que vous puissiez **enregistrer le projet en SVG** en toute confiance dans vos propres applications.

## Réponses rapides
- **Que signifie « exporter MPP en SVG » ?**  
  Cela convertit un fichier Microsoft Project (.mpp) en une image SVG qui peut être affichée dans n'importe quel navigateur sans perte de qualité.  
- **Quelle bibliothèque gère la conversion ?**  
  Aspose.Tasks pour Java fournit une méthode `save` en une seule ligne pour effectuer la conversion.  
- **Ai‑je besoin d'une licence ?**  
  Une licence temporaire est requise pour une utilisation commerciale ; un essai gratuit est disponible.  
- **Quelles sont les prérequis ?**  
  Java JDK 8+ et le JAR Aspose.Tasks pour Java.  
- **Combien de temps prend la conversion ?**  
  Généralement moins d'une seconde pour les fichiers de projet standards.

## Qu’est‑ce que « exporter MPP en SVG » ?
Exporter MPP en SVG signifie prendre la représentation visuelle d'un planning de projet — tâches, chronologies et ressources — et l'écrire sous forme de fichier SVG. SVG est basé sur XML, léger et s'adapte parfaitement aux écrans haute résolution.

## Pourquoi exporter MPP en SVG avec Aspose.Tasks ?
- **Aucune installation de Microsoft Project requise** – la bibliothèque fonctionne de manière indépendante.  
- **Fidélité totale** – les graphiques, barres Gantt et jalons conservent leurs styles.  
- **Cross‑platform** – exécutez le code sous Windows, Linux ou macOS.  
- **API en une ligne** – un appel unique enregistre le projet en SVG, s'intégrant naturellement aux pipelines Java existants.

## Prérequis
- **Java Development Kit (JDK)** – version 8 ou supérieure. Téléchargez-le depuis le site d'Oracle.  
- **Aspose.Tasks pour Java** – obtenez la bibliothèque depuis la page officielle de téléchargement **[ici](https://releases.aspose.com/tasks/java/)**.  

## Importer les packages
Tout d'abord, importez les classes dont vous avez besoin. Le bloc d'importation reste inchangé.

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

## Étape 3 : Enregistrer le projet en SVG
Vous pouvez maintenant **exporter MPP en SVG** avec une seule commande.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

La méthode écrit `project5.svg` dans le même répertoire. Le SVG résultant peut être ouvert dans n'importe quel navigateur moderne ou intégré directement dans du HTML.

## Cas d’utilisation courants
- **Tableaux de bord de projet** – intégrez des diagrammes Gantt en direct dans des portails web sans que le client n'ait besoin d'installer Microsoft Project.  
- **Rapports automatisés** – générez des images SVG à la volée pour des rapports PDF ou HTML.  
- **Collaboration inter‑équipes** – partagez un planning visuel avec les parties prenantes qui n'ont besoin que d'un navigateur pour le visualiser.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Fichier non trouvé** | Chemin `dataDir` incorrect | Vérifiez que la chaîne du répertoire se termine par un séparateur (`/` ou `\\`). |
| **Sortie SVG vide** | Projet chargé sans vues | Assurez‑vous que le fichier MPP contient une vue Gantt avant l'enregistrement. |
| **Exception de licence** | Aucune licence valide appliquée | Appliquez une licence temporaire en utilisant `License.setLicense("path/to/license.xml")` avant d'appeler `save`. |

## Questions fréquemment posées

**Q : Aspose.Tasks pour Java est‑il compatible avec toutes les versions des fichiers Microsoft Project ?**  
R : Oui, il prend en charge les formats MPP, MPT et XML, des versions anciennes aux dernières versions de Project.

**Q : Puis‑je personnaliser l'apparence du SVG généré ?**  
R : Absolument. Utilisez `SvgOptions` pour définir les polices, les couleurs et les options de mise en page avant d’appeler `save`.

**Q : Aspose.Tasks pour Java nécessite‑t‑il une licence pour une utilisation commerciale ?**  
R : Oui, une licence valide est requise pour la production. Vous pouvez obtenir une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)**.

**Q : Puis‑je essayer Aspose.Tasks pour Java avant d'acheter ?**  
R : Oui, un essai gratuit est disponible **[ici](https://purchase.aspose.com/buy)**.

**Q : Où puis‑je obtenir du support pour Aspose.Tasks pour Java ?**  
R : Visitez le forum communautaire **[ici](https://forum.aspose.com/c/tasks/15)** pour poser des questions et partager vos retours.

## Conclusion
Vous savez maintenant comment **exporter MPP en SVG** avec Java et comment **enregistrer le projet en SVG** efficacement à l'aide d'Aspose.Tasks. Cette fonctionnalité vous permet d'intégrer des visualisations de projet riches dans des portails web, des tableaux de bord de reporting ou tout autre endroit où des graphiques évolutifs sont nécessaires. Expérimentez avec `SvgOptions` pour affiner la sortie, et vous disposerez d'un outil puissant dans votre boîte à outils de développement.

---

**Dernière mise à jour :** 2026-03-27  
**Testé avec :** Aspose.Tasks for Java 24.10  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}