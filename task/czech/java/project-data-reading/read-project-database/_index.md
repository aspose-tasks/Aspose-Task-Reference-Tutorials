---
title: Čtení dat projektu z databáze MS Project v Aspose.Tasks
linktitle: Čtení dat projektu z databáze Microsoft Project v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se číst data projektu z databáze Microsoft Project pomocí Aspose.Tasks for Java. Podrobný průvodce s příklady kódu.
type: docs
weight: 12
url: /cs/java/project-data-reading/read-project-database/
---
## Úvod
V tomto tutoriálu prozkoumáme, jak číst data projektu z databáze Microsoft Project pomocí Aspose.Tasks for Java. Aspose.Tasks je výkonné Java API, které umožňuje vývojářům manipulovat s dokumenty Microsoft Project bez nutnosti instalace Microsoft Project. Podle kroků uvedených v této příručce se naučíte, jak efektivně extrahovat data projektu z databáze a uložit je v požadovaném formátu.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Základní znalost programování v Javě.
2. Java Development Kit (JDK) nainstalovaný ve vašem systému.
3. Aspose.Tasks pro knihovnu Java staženou a nakonfigurovanou ve vašem projektu.

## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky:
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
## Krok 1: Nastavte připojení k databázi
Nejprve musíte nastavit připojení k databázi Microsoft Project. To zahrnuje zadání adresy URL databáze, názvu serveru, čísla portu, názvu databáze, uživatelského jména a hesla.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## Krok 2: Přidejte ovladač JDBC
Dále musíte do projektu přidat ovladač JDBC. Tento ovladač usnadňuje komunikaci mezi Java aplikacemi a databází Microsoft SQL Server.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## Krok 3: Přečtěte si data projektu
 Nyní vytvořte a`Project` objekt a načíst data projektu z databáze pomocí dříve definovaných nastavení.
```java
Project project = new Project(settings);
```
## Krok 4: Uložte data projektu
Nakonec uložte data projektu do požadovaného formátu. V tomto příkladu jej uložíme jako soubor XML.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Gratulujeme! Úspěšně jste přečetli data projektu z databáze Microsoft Project pomocí Aspose.Tasks for Java.

## Závěr
tomto tutoriálu jsme se zabývali procesem čtení projektových dat z databáze Microsoft Project pomocí Aspose.Tasks for Java. Dodržováním nastíněných kroků můžete plynule extrahovat informace o projektu a manipulovat s nimi podle vašich požadavků. Aspose.Tasks zjednodušuje manipulaci s dokumenty Microsoft Project a umožňuje efektivní extrakci dat a manipulaci s nimi.
## FAQ
### Otázka: Lze Aspose.Tasks použít ke čtení projektových dat z jiných databází kromě Microsoft Project?
Odpověď: Ano, Aspose.Tasks podporuje čtení projektových dat z různých zdrojů, včetně souborů XML, databází Primavera a Microsoft Project.
### Otázka: Je Aspose.Tasks kompatibilní s různými verzemi Microsoft Project?
Odpověď: Ano, Aspose.Tasks je navržena tak, aby fungovala s různými verzemi Microsoft Project, což zajišťuje kompatibilitu a bezproblémovou integraci.
### Otázka: Mohu s daty projektu před uložením manipulovat?
Odpověď: Aspose.Tasks rozhodně poskytuje širokou škálu funkcí pro manipulaci s daty projektu, jako je přidávání úkolů, aktualizace zdrojů a nastavení vlastností projektu.
### Otázka: Podporuje Aspose.Tasks více výstupních formátů?
Odpověď: Ano, Aspose.Tasks podporuje různé výstupní formáty, včetně XML, PDF, HTML a obrazových formátů jako PNG a JPEG.
### Otázka: Kde najdu další podporu nebo pomoc s Aspose.Tasks?
 Odpověď: Pro další podporu nebo pomoc můžete navštívit fórum Aspose.Tasks nebo prozkoumat dokumentaci dostupnou na webu[tady](https://forum.aspose.com/c/tasks/15).