---
title: Lecture des données de projet à partir de la base de données MS Project dans Aspose.Tasks
linktitle: Lecture des données de projet à partir de la base de données Microsoft Project dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment lire les données d'un projet à partir de la base de données Microsoft Project à l'aide d'Aspose.Tasks pour Java. Guide étape par étape avec des exemples de code.
type: docs
weight: 12
url: /fr/java/project-data-reading/read-project-database/
---
## Introduction
Dans ce didacticiel, nous verrons comment lire les données d'un projet à partir d'une base de données Microsoft Project à l'aide d'Aspose.Tasks pour Java. Aspose.Tasks est une API Java puissante qui permet aux développeurs de manipuler des documents Microsoft Project sans avoir besoin d'installer Microsoft Project. En suivant les étapes décrites dans ce guide, vous apprendrez comment extraire efficacement les données d'un projet d'une base de données et les enregistrer dans le format souhaité.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Connaissance de base de la programmation Java.
2. Kit de développement Java (JDK) installé sur votre système.
3. Bibliothèque Aspose.Tasks pour Java téléchargée et configurée dans votre projet.

## Importer des packages
Pour commencer, importez les packages nécessaires :
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
## Étape 1 : Configurer la connexion à la base de données
Tout d'abord, vous devez configurer la connexion à la base de données Microsoft Project. Cela inclut la spécification de l'URL de la base de données, du nom du serveur, du numéro de port, du nom de la base de données, du nom d'utilisateur et du mot de passe.
```java
String url = "jdbc:sqlserver://" ;
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## Étape 2 : Ajouter le pilote JDBC
Ensuite, vous devez ajouter le pilote JDBC à votre projet. Ce pilote facilite la communication entre les applications Java et la base de données Microsoft SQL Server.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## Étape 3 : Lire les données du projet
 Maintenant, créez un`Project` objet et charger les données du projet à partir de la base de données en utilisant les paramètres définis précédemment.
```java
Project project = new Project(settings);
```
## Étape 4 : Enregistrer les données du projet
Enfin, enregistrez les données du projet dans le format souhaité. Dans cet exemple, nous l'enregistrons sous forme de fichier XML.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Toutes nos félicitations! Vous avez réussi à lire les données du projet à partir d'une base de données Microsoft Project à l'aide d'Aspose.Tasks pour Java.

## Conclusion
Dans ce didacticiel, nous avons couvert le processus de lecture des données de projet à partir d'une base de données Microsoft Project à l'aide d'Aspose.Tasks pour Java. En suivant les étapes décrites, vous pouvez extraire de manière transparente les informations du projet et les manipuler selon vos besoins. Aspose.Tasks simplifie la gestion des documents Microsoft Project, permettant une extraction et une manipulation efficaces des données.
## FAQ
### Q : Aspose.Tasks peut-il être utilisé pour lire les données de projet à partir d'autres bases de données que Microsoft Project ?
R : Oui, Aspose.Tasks prend en charge la lecture des données de projet à partir de diverses sources, notamment les fichiers XML, Primavera et les bases de données Microsoft Project.
### Q : Aspose.Tasks est-il compatible avec différentes versions de Microsoft Project ?
R : Oui, Aspose.Tasks est conçu pour fonctionner avec différentes versions de Microsoft Project, garantissant ainsi une compatibilité et une intégration transparente.
### Q : Puis-je manipuler les données du projet avant de les enregistrer ?
: Absolument, Aspose.Tasks fournit un large éventail de fonctionnalités pour manipuler les données du projet, telles que l'ajout de tâches, la mise à jour des ressources et la définition des propriétés du projet.
### Q : Aspose.Tasks prend-il en charge plusieurs formats de sortie ?
R : Oui, Aspose.Tasks prend en charge divers formats de sortie, notamment XML, PDF, HTML et les formats d'image tels que PNG et JPEG.
### Q : Où puis-je trouver une assistance ou une assistance supplémentaire concernant Aspose.Tasks ?
 R : Pour obtenir une assistance ou une assistance supplémentaire, vous pouvez visiter le forum Aspose.Tasks ou explorer la documentation disponible sur le site Web.[ici](https://forum.aspose.com/c/tasks/15).