---
date: 2026-10-31
description: Apprenez à enregistrer le projet au format PDF et à lire la base de données
  Microsoft Project avec Aspose.Tasks for Java, ainsi qu'à vous connecter à Project
  Server, convertir le projet en HTML et exporter le projet en XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Lecture des données de projet depuis la base de données Microsoft Project
  dans Aspose.Tasks
og_description: Enregistrer le projet au format PDF et lire la base de données Microsoft
  Project avec Aspose.Tasks for Java. Apprenez à vous connecter à Project Server,
  à exporter en HTML, XML et CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Enregistrer le projet au format PDF et lire la base de données Microsoft
  Project avec Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Enregistrer le projet au format PDF et lire la base de données Microsoft Project
  avec Aspose.Tasks for Java
url: /fr/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer le projet au format PDF et lire la base de données Microsoft Project avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous découvrirez comment **lire la base de données Microsoft Project** directement depuis un serveur Microsoft Project et ensuite **enregistrer le projet au format PDF** en utilisant l'API Java d'Aspose.Tasks. Que vous ayez besoin de générer des rapports imprimables, de migrer des données héritées ou d'intégrer des informations de projet dans un portail personnalisé, ce guide vous accompagne à chaque étape — de la configuration de la connexion JDBC à l'exportation du projet en PDF, XML ou HTML. À la fin, vous disposerez d'une solution prête pour la production qui fonctionne sur n'importe quel serveur Java sans installer Microsoft Project.

## Réponses rapides
- **Que fait Aspose.Tasks ?** Il fournit une API pure‑Java pour lire, écrire et manipuler les fichiers et bases de données Microsoft Project.  
- **Ai‑je besoin d’installer Microsoft Project ?** Non, Aspose.Tasks fonctionne indépendamment de Microsoft Project.  
- **Quel type de base de données est pris en charge ?** Microsoft SQL Server, le backend de Project Server.  
- **Puis‑je exporter vers d’autres formats ?** Oui — PDF, XML, HTML, CSV, PNG, JPEG, et plus encore.  
- **Quelles sont les principales conditions préalables ?** JDK 8 ou supérieur, la bibliothèque Aspose.Tasks pour Java, le pilote JDBC SQL Server, et des identifiants valides pour Project Server.

## Qu’est‑ce que « lire la base de données Microsoft Project » ?
Lire une base de données Microsoft Project signifie se connecter au référentiel SQL Server du Project Server, extraire les données de projet stockées et les charger dans un objet `Project` qu'Aspose.Tasks peut manipuler. Cette approche est idéale pour les rapports automatisés, la migration de données ou les analyses personnalisées.

## Pourquoi utiliser Aspose.Tasks pour Java ?
Aspose.Tasks pour Java vous permet de travailler avec les données Microsoft Project sans nécessiter l'application de bureau, offrant une solution pure‑Java qui s'exécute sur n'importe quelle plateforme. Il fournit un modèle d'objet complet pour les tâches, les ressources, les calendriers et les champs personnalisés, et peut gérer efficacement de grands projets d'entreprise, ce qui le rend idéal pour les scénarios de rapports automatisés, de migration et d'intégration.

- **Pas de dépendance à Microsoft Project** – s'exécute sur n'importe quel serveur ou environnement CI.  
- **Modèle d'objet riche** – accéder aux tâches, ressources, affectations, calendriers et champs personnalisés par programmation.  
- **Options d'exportation multiples** – Aspose.Tasks prend en charge l'exportation vers **plus de 20 formats de fichiers**, dont PDF, XML, HTML, CSV, PNG et JPEG, avec un seul appel d'API.  
- **Haute performance** – la bibliothèque peut traiter des projets contenant **jusqu'à 10 000 tâches** en moins d'une minute, et elle diffuse les données pour éviter de charger le fichier complet en mémoire.

## Prérequis
Avant de commencer, assurez-vous d'avoir :

1. Un environnement de développement Java fonctionnel (JDK 8 ou supérieur).  
2. La bibliothèque Aspose.Tasks pour Java ajoutée au classpath de votre projet.  
3. Les identifiants d'accès à la base de données SQL du Project Server (nom du serveur, port, nom de la base, nom d'utilisateur, mot de passe) pour se connecter à Project Server.  
4. Le pilote JDBC Microsoft pour SQL Server (par ex., `sqljdbc4.jar`).  

## Importer les packages
Tout d'abord, importez les classes dont vous aurez besoin. La liste comprend les classes principales d'Aspose.Tasks et les utilitaires Java standard.

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## Comment se connecter à Project Server
Établir une connexion fiable est la base pour lire les données du projet. Assurez‑vous que l'instance SQL Server est accessible depuis votre hôte Java et que le compte que vous utilisez possède les permissions **SELECT** sur le schéma du Project Server. Vous devez également vérifier la latence réseau et configurer les paramètres SSL nécessaires pour garantir une communication sécurisée.

## Étape 1 : configurer la connexion à la base de données
La classe `MspDbSettings` encapsule les détails de connexion JDBC nécessaires pour accéder à une base de données Microsoft Project Server. Créez une instance `MspDbSettings` qui contient la chaîne de connexion JDBC. Remplacez les valeurs de substitution par les détails réels de votre serveur.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Conseil :** Stockez la chaîne de connexion dans un fichier de configuration sécurisé ou une variable d'environnement plutôt que d'encoder en dur les identifiants.

## Étape 2 : ajouter le pilote JDBC
Chargez le pilote JDBC Microsoft SQL Server à l'exécution afin que la JVM puisse communiquer avec la base de données.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Avertissement :** Assurez‑vous que la version du pilote correspond à votre version de SQL Server. L'utilisation d'un pilote incompatible peut entraîner des échecs de connexion.

## Étape 3 : lire les données du projet
La classe `Project` représente un fichier Microsoft Project chargé en mémoire, exposant les tâches, ressources et affectations. Instanciez un objet `Project` en passant le `MspDbSettings`. Aspose.Tasks récupérera automatiquement les données du projet depuis la base de données.

```java
Project project = new Project(settings);
```

À ce stade, vous pouvez explorer l'objet `project` — lister les tâches, les ressources, ou modifier les champs selon les besoins.

## Étape 4 : enregistrer le projet au format PDF
L'énumération `SaveFileFormat` définit le format de sortie pour la méthode `Project.save`, tel que PDF, XML ou HTML. Exportez le projet chargé dans le format de fichier de votre choix. L'exemple ci‑dessous enregistre le projet au format **PDF**, idéal pour les rapports imprimables. Vous pouvez également **exporter le projet en XML** ou **convertir le projet en HTML** en modifiant l'énumération `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Si vous préférez XML, remplacez simplement `SaveFileFormat.Pdf` par `SaveFileFormat.Xml`. Pour une sortie HTML, utilisez `SaveFileFormat.Html`.

## Problèmes courants & solutions
| Problème | Cause typique | Solution |
|----------|---------------|----------|
| **Timeout de connexion** | Serveur/port incorrect ou pare‑feu bloquant | Vérifiez l'adresse du serveur, ouvrez le port 1433 et testez la connectivité avec un simple programme de test JDBC. |
| **Erreur d'authentification** | Nom d'utilisateur/mot de passe invalide ou SQL Server non configuré pour l'authentification SQL | Utilisez un login SQL valide ou activez l'authentification en mode mixte sur le serveur. |
| **Pilote introuvable** | JAR JDBC absent du classpath | Assurez‑vous que `addJDBCDriver` pointe vers le bon fichier `.jar` et que le chemin utilise des doubles barres obliques inverses (`\\`). |
| **Projet vide après chargement** | Permissions insuffisantes pour lire les tables du Project Server | Accordez au login les droits SELECT sur le schéma de la base de données du Project Server. |

## Questions fréquemment posées

**Q : Aspose.Tasks peut‑il être utilisé pour lire les données de projet à partir d'autres bases de données que Microsoft Project ?**  
R : Oui, Aspose.Tasks prend en charge la lecture des données de projet à partir de fichiers XML, de bases de données Primavera et d'autres formats de projet standard.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de Microsoft Project ?**  
R : Oui, la bibliothèque fonctionne avec Microsoft Project 2007 jusqu'aux dernières versions 2024, assurant une intégration transparente entre les versions.

**Q : Puis‑je manipuler les données du projet avant de les enregistrer ?**  
R : Absolument, vous pouvez ajouter, mettre à jour ou supprimer des tâches, des ressources et des champs personnalisés à l'aide de l'API riche avant l'exportation.

**Q : Aspose.Tasks prend‑il en charge plusieurs formats de sortie ?**  
R : Oui, vous pouvez enregistrer les projets au format PDF, XML, HTML, CSV, PNG, JPEG, et plus — plus de 20 formats au total.

**Q : Où puis‑je trouver davantage de support ou d'assistance pour Aspose.Tasks ?**  
R : Pour plus d'aide, consultez le forum Aspose.Tasks ou explorez la documentation disponible sur le site web [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
En suivant ce guide étape par étape, vous savez maintenant comment **lire la base de données Microsoft Project**, **enregistrer le projet au format PDF**, et exporter vers d'autres formats en utilisant Aspose.Tasks pour Java. Cette approche élimine la dépendance à Microsoft Project, simplifie les rapports automatisés et ouvre la voie à des intégrations personnalisées puissantes.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Author:** Aspose

## Tutoriels associés

- [Comment enregistrer le projet au format PDF avec Aspose.Tasks – Guide d'exportation](/tasks/java/project-file-operations/save-as-pdf/)
- [Enregistrer le projet au format PDF – Rendu de la feuille de tâches avec Aspose.Tasks pour Java](/tasks/java/task-properties/render-task-sheet/)
- [Exporter le projet en PDF et réduire l'écart entre la liste des tâches et le pied de page dans Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}