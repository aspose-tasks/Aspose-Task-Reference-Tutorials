---
date: 2026-02-18
description: Apprenez à enregistrer le projet au format PDF et à lire la base de données
  Microsoft Project avec Aspose.Tasks pour Java, ainsi qu’à vous connecter à Project
  Server, convertir le projet en HTML et exporter le projet en XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Enregistrer le projet au format PDF et lire la base de données du projet avec
  Aspose.Tasks pour Java
url: /fr/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer le projet au format PDF et lire la base de données Microsoft Project avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous découvrirez comment **lire la base de données Microsoft Project** directement depuis un serveur Microsoft Project, puis **enregistrer le projet au format PDF** à l’aide de l’API Aspose.Tasks Java. Que vous ayez besoin de générer des rapports, de migrer des données ou d’intégrer les informations de projet dans vos propres applications, ce guide vous accompagne à chaque étape — de la configuration de la connexion à la base de données à l’exportation du projet en PDF, XML ou HTML. À la fin, vous disposerez d’une solution solide, prête pour la production, qui fonctionne sans installer Microsoft Project sur la machine hôte.

## Quick Answers
- **Que fait Aspose.Tasks ?** Il fournit une API pure Java pour lire, écrire et manipuler les fichiers et bases de données Microsoft Project.  
- **Dois‑je installer Microsoft Project ?** Non, Aspose.Tasks fonctionne indépendamment de Microsoft Project.  
- **Quel type de base de données est pris en charge ?** Microsoft SQL Server (le backend de Project Server).  
- **Puis‑je exporter vers d’autres formats ?** Oui, en plus du PDF vous pouvez enregistrer en XML, HTML, CSV, et plus encore.  
- **Quelles sont les principales prérequis ?** JDK, bibliothèque Aspose.Tasks pour Java, le pilote JDBC SQL Server, et les informations d’identification pour **se connecter à Project Server**.

## Qu’est‑ce que « lire la base de données Microsoft Project » ?
Lire une base de données Microsoft Project signifie se connecter au référentiel SQL Server de Project Server, extraire les données de projet stockées et les charger dans un objet `Project` qu’Aspose.Tasks peut manipuler. Cette approche est idéale pour les rapports automatisés, la migration de données ou les analyses personnalisées.

## Pourquoi utiliser Aspose.Tasks pour Java ?
- **Aucune dépendance à Microsoft Project** – fonctionne sur n’importe quel serveur ou environnement CI.  
- **Modèle d’objet riche** – accès programmatique aux tâches, ressources, affectations, calendriers et champs personnalisés.  
- **Multiples options d’exportation** – PDF, XML, HTML, PNG, etc., avec un seul appel d’API.  
- **Haute performance** – optimisé pour les projets d’entreprise de grande taille.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. Un environnement de développement Java fonctionnel (JDK 8 ou plus récent).  
2. La bibliothèque Aspose.Tasks pour Java ajoutée au classpath de votre projet.  
3. Les informations d’identification d’accès à la base de données SQL du Project Server (nom du serveur, port, nom de la base, nom d’utilisateur, mot de passe) **pour se connecter à Project Server**.  
4. Le pilote JDBC Microsoft pour SQL Server (par ex., `sqljdbc4.jar`).  

## Import Packages
First, import the classes you’ll need. The list includes Aspose.Tasks core classes and standard Java utilities.

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

## How to connect to Project Server
Establishing a reliable connection is the foundation for reading project data. Make sure the SQL Server instance is reachable from your Java host and that the login you use has **SELECT** permissions on the Project Server schema.

## Step 1: Set Up Database Connection
Create an `MspDbSettings` instance that holds the JDBC connection string. Replace the placeholder values with your actual server details.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Store the connection string in a secure configuration file or environment variable rather than hard‑coding credentials.

## Step 2: Add JDBC Driver
Load the Microsoft SQL Server JDBC driver at runtime so the JVM can communicate with the database.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** Ensure the driver version matches your SQL Server version. Using an incompatible driver may cause connection failures.

## Step 3: Read Project Data
Instantiate a `Project` object by passing the `MspDbSettings`. Aspose.Tasks will fetch the project data from the database automatically.

```java
Project project = new Project(settings);
```

At this point you can explore the `project` object—list tasks, resources, or modify fields as needed.

## Step 4: Save project as PDF
Export the loaded project to a file format of your choice. The example below saves the project as **PDF**, which is perfect for printable reports. You can also **export project to XML** or **convert project to HTML** by changing the `SaveFileFormat` enum.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

If you prefer XML, simply replace `SaveFileFormat.Pdf` with `SaveFileFormat.Xml`. For HTML output, use `SaveFileFormat.Html`.

## Common Issues & Solutions
| Problème | Cause typique | Solution |
|----------|---------------|----------|
| **Timeout de connexion** | Mauvais serveur/port ou pare‑feu bloquant | Vérifiez l’adresse du serveur, ouvrez le port 1433, et testez la connectivité avec un simple programme de test JDBC. |
| **Erreur d’authentification** | Nom d’utilisateur/mot de passe invalide ou SQL Server non configuré pour l’authentification SQL | Utilisez un login SQL valide ou activez l’authentification mixte sur le serveur. |
| **Pilote introuvable** | JAR JDBC absent du classpath | Assurez‑vous que `addJDBCDriver` pointe vers le bon fichier `.jar` et que le chemin utilise des doubles barres obliques inverses (`\\`). |
| **Projet vide après le chargement** | Permissions insuffisantes pour lire les tables du Project Server | Accordez au login les droits SELECT sur le schéma de la base de données Project Server. |

## Frequently Asked Questions

**Q : Aspose.Tasks peut‑il lire les données de projet depuis d’autres bases que Microsoft Project ?**  
R : Oui, Aspose.Tasks prend en charge la lecture des données de projet depuis diverses sources, y compris les fichiers XML, Primavera et les bases de données Microsoft Project.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de Microsoft Project ?**  
R : Oui, Aspose.Tasks est conçu pour fonctionner avec plusieurs versions de Microsoft Project, assurant une intégration fluide.

**Q : Puis‑je manipuler les données du projet avant de les enregistrer ?**  
R : Absolument, Aspose.Tasks offre une API riche pour ajouter des tâches, mettre à jour des ressources et définir des propriétés de projet avant l’exportation.

**Q : Aspose.Tasks prend‑il en charge plusieurs formats de sortie ?**  
R : Oui, vous pouvez enregistrer les projets en PDF, XML, HTML, CSV, PNG, JPEG, et plus encore.

**Q : Où puis‑je trouver davantage de support ou d’assistance pour Aspose.Tasks ?**  
R : Pour plus d’aide, visitez le forum Aspose.Tasks ou explorez la documentation disponible sur le site [here](https://forum.aspose.com/c/tasks/15).

## Conclusion
En suivant ce guide pas à pas, vous savez maintenant comment **lire la base de données Microsoft Project**, **enregistrer le projet au format PDF**, et exporter vers d’autres formats à l’aide d’Aspose.Tasks pour Java. Cette approche élimine la dépendance à Microsoft Project, simplifie les rapports automatisés et ouvre la voie à des intégrations personnalisées puissantes.

---

**Dernière mise à jour :** 2026-02-18  
**Testé avec :** Aspose.Tasks pour Java 24.5 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}