---
date: 2026-02-18
description: Naučte se, jak uložit projekt jako PDF a číst databázi Microsoft Project
  pomocí Aspose.Tasks pro Javu, dále se připojit k Project Serveru, převést projekt
  do HTML a exportovat projekt do XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Uložit projekt jako PDF a číst databázi projektu pomocí Aspose.Tasks pro Javu
url: /cs/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uložte projekt jako PDF a načtěte databázi Microsoft Project pomocí Aspose.Tasks pro Java

## Úvod
V tomto tutoriálu se dozvíte, jak **číst databázi Microsoft Project** přímo z Microsoft Project Serveru a poté **uložit projekt jako PDF** pomocí Aspose.Tasks Java API. Ať už potřebujete generovat zprávy, migrovat data nebo integrovat informace o projektu do vlastních aplikací, tento průvodce vás provede každým krokem – od nastavení připojení k databázi až po export projektu do PDF, XML nebo HTML. Na konci budete mít solidní, produkčně připravené řešení, které funguje bez instalace Microsoft Project na hostitelském stroji.

## Rychlé odpovědi
- **Co dělá Aspose.Tasks?** Poskytuje čisté Java API pro čtení, zápis a manipulaci se soubory a databázemi Microsoft Project.  
- **Potřebuji mít nainstalovaný Microsoft Project?** Ne, Aspose.Tasks funguje nezávisle na Microsoft Project.  
- **Jaký typ databáze je podporován?** Microsoft SQL Server (backend Project Serveru).  
- **Mohu exportovat do jiných formátů?** Ano, kromě PDF můžete uložit do XML, HTML, CSV a dalších.  
- **Jaké jsou hlavní předpoklady?** JDK, knihovna Aspose.Tasks pro Java, JDBC ovladač pro SQL Server a přihlašovací údaje pro **připojení k Project Serveru**.

## Co znamená „číst databázi Microsoft Project“?
Čtení databáze Microsoft Project znamená připojení k úložišti SQL Serveru Project Serveru, extrakci uložených dat projektu a načtení do objektu `Project`, který může Aspose.Tasks manipulovat. Tento přístup je ideální pro automatizované reportování, migraci dat nebo vlastní analytiku.

## Proč používat Aspose.Tasks pro Java?
- **Žádná závislost na Microsoft Project** – běží na jakémkoli serveru nebo v CI prostředí.  
- **Bohatý objektový model** – programově přistupujte k úkolům, zdrojům, přiřazením, kalendářům a vlastním polím.  
- **Více možností exportu** – PDF, XML, HTML, PNG atd., pomocí jediného volání API.  
- **Vysoký výkon** – optimalizováno pro velké podnikové projekty.

## Předpoklady
Než začnete, ujistěte se, že máte:

1. Funkční vývojové prostředí Java (JDK 8 nebo novější).  
2. Knihovna Aspose.Tasks pro Java přidána do classpath vašeho projektu.  
3. Přístupové údaje k SQL databázi Project Serveru (název serveru, port, název databáze, uživatelské jméno, heslo) **pro připojení k Project Serveru**.  
4. Microsoft JDBC ovladač pro SQL Server (např. `sqljdbc4.jar`).  

## Import balíčků
Nejprve importujte třídy, které budete potřebovat. Seznam zahrnuje základní třídy Aspose.Tasks a standardní Java utility.

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

## Jak se připojit k Project Serveru
Zajištění spolehlivého připojení je základem pro čtení dat projektu. Ujistěte se, že instance SQL Serveru je dosažitelná z vašeho Java hosta a že přihlašovací údaje mají **SELECT** oprávnění na schématu Project Serveru.

## Krok 1: Nastavení připojení k databázi
Vytvořte instanci `MspDbSettings`, která obsahuje JDBC řetězec připojení. Nahraďte zástupné hodnoty skutečnými podrobnostmi vašeho serveru.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Uložte řetězec připojení do zabezpečeného konfiguračního souboru nebo proměnné prostředí místo tvrdého kódování přihlašovacích údajů.

## Krok 2: Přidání JDBC ovladače
Načtěte Microsoft SQL Server JDBC ovladač za běhu, aby JVM mohl komunikovat s databází.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Upozornění:** Ujistěte se, že verze ovladače odpovídá verzi vašeho SQL Serveru. Použití nekompatibilního ovladače může způsobit selhání připojení.

## Krok 3: Načtení dat projektu
Instancujte objekt `Project` předáním `MspDbSettings`. Aspose.Tasks automaticky načte data projektu z databáze.

```java
Project project = new Project(settings);
```

V tomto okamžiku můžete prozkoumat objekt `project` – vypsat úkoly, zdroje nebo upravit pole podle potřeby.

## Krok 4: Uložení projektu jako PDF
Exportujte načtený projekt do formátu podle vašeho výběru. Níže uvedený příklad ukládá projekt jako **PDF**, což je ideální pro tisknutelné zprávy. Můžete také **exportovat projekt do XML** nebo **převést projekt na HTML** změnou enumu `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Pokud dáváte přednost XML, jednoduše nahraďte `SaveFileFormat.Pdf` za `SaveFileFormat.Xml`. Pro výstup HTML použijte `SaveFileFormat.Html`.

## Časté problémy a řešení
| Problém | Typická příčina | Řešení |
|-------|---------------|-----|
| **Connection timeout** | Špatný server/port nebo firewall blokuje | Ověřte adresu serveru, otevřete port 1433 a otestujte připojení pomocí jednoduchého JDBC testovacího programu. |
| **Authentication error** | Neplatné uživatelské jméno/heslo nebo SQL Server není nastaven pro SQL autentizaci | Použijte platné SQL přihlášení nebo povolte smíšený režim autentizace na serveru. |
| **Driver not found** | JDBC jar není v classpath | Ujistěte se, že `addJDBCDriver` ukazuje na správný soubor `.jar` a že cesta používá dvojité zpětné lomítko (`\\`). |
| **Empty project after load** | Nedostatečná oprávnění pro čtení tabulek Project Serveru | Udělejte přihlášení práva SELECT na schéma databáze Project Serveru. |

## Často kladené otázky

**Q: Může být Aspose.Tasks použit k načtení dat projektu z jiných databází než Microsoft Project?**  
A: Ano, Aspose.Tasks podporuje čtení dat projektu z různých zdrojů, včetně XML souborů, Primavera a databází Microsoft Project.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi Microsoft Project?**  
A: Ano, Aspose.Tasks je navržen tak, aby fungoval s více verzemi Microsoft Project, což zajišťuje plynulou integraci.

**Q: Mohu manipulovat s daty projektu před jeho uložením?**  
A: Rozhodně, Aspose.Tasks poskytuje bohaté API pro přidávání úkolů, aktualizaci zdrojů a nastavení vlastností projektu před exportem.

**Q: Podporuje Aspose.Tasks více výstupních formátů?**  
A: Ano, můžete ukládat projekty jako PDF, XML, HTML, CSV, PNG, JPEG a další.

**Q: Kde mohu najít další podporu nebo pomoc s Aspose.Tasks?**  
A: Pro další pomoc navštivte fórum Aspose.Tasks nebo prozkoumejte dokumentaci dostupnou na webu [zde](https://forum.aspose.com/c/tasks/15).

## Závěr
Postupným dodržením tohoto průvodce nyní umíte **číst databázi Microsoft Project**, **uložit projekt jako PDF** a exportovat do dalších formátů pomocí Aspose.Tasks pro Java. Tento přístup odstraňuje závislost na Microsoft Project, zjednodušuje automatizované reportování a otevírá dveře k výkonným vlastním integracím.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}