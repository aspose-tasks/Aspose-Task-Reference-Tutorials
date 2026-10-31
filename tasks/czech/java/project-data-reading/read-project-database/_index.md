---
date: 2026-10-31
description: Zjistěte, jak uložit projekt jako PDF a načíst databázi Microsoft Project
  pomocí Aspose.Tasks for Java, dále se připojit k Project Server, převést projekt
  do HTML a exportovat projekt do XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Čtení dat projektu z databáze Microsoft Project v Aspose.Tasks
og_description: Uložte projekt jako PDF a načtěte databázi Microsoft Project pomocí
  Aspose.Tasks for Java. Naučte se připojit k Project Server, exportovat do HTML,
  XML a CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Uložte projekt jako PDF a načtěte databázi Microsoft Project pomocí Aspose.Tasks
  for Java
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
title: Uložte projekt jako PDF a načtěte databázi Microsoft Project pomocí Aspose.Tasks
  for Java
url: /cs/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uložte projekt jako PDF a načtěte databázi Microsoft Project pomocí Aspose.Tasks pro Java

## Úvod
V tomto tutoriálu se dozvíte, jak **read Microsoft Project database** přímo ze serveru Microsoft Project a poté **save the project as PDF** pomocí Aspose.Tasks Java API. Ať už potřebujete generovat tisknutelné zprávy, migrovat stará data nebo vložit informace o projektu do vlastního portálu, tento průvodce vás provede každým krokem – od nastavení JDBC připojení po export projektu do PDF, XML nebo HTML. Na konci budete mít připravené řešení připravené pro produkci, které běží na libovolném Java serveru bez instalace Microsoft Project.

## Rychlé odpovědi
- **Co dělá Aspose.Tasks?** Poskytuje čisté Java API pro čtení, zápis a manipulaci se soubory a databázemi Microsoft Project.  
- **Potřebuji mít nainstalovaný Microsoft Project?** Ne, Aspose.Tasks funguje nezávisle na Microsoft Project.  
- **Jaký typ databáze je podporován?** Microsoft SQL Server, backend Project Serveru.  
- **Mohu exportovat do jiných formátů?** Ano—PDF, XML, HTML, CSV, PNG, JPEG a další.  
- **Jaké jsou hlavní předpoklady?** JDK 8 nebo novější, knihovna Aspose.Tasks pro Java, JDBC ovladač pro SQL Server a platné přihlašovací údaje k Project Serveru.

## Co znamená „read Microsoft Project database“?
Čtení databáze Microsoft Project znamená připojení k úložišti SQL Serveru Project Serveru, extrahování uložených dat projektu a načtení do objektu `Project`, který může Aspose.Tasks manipulovat. Tento přístup je ideální pro automatizované reportování, migraci dat nebo vlastní analytiku.

## Proč používat Aspose.Tasks pro Java?
Aspose.Tasks pro Java vám umožňuje pracovat s daty Microsoft Project bez potřeby desktopové aplikace, nabízí čisté Java řešení, které běží na jakékoli platformě. Poskytuje komplexní objektový model pro úkoly, zdroje, kalendáře a vlastní pole a dokáže efektivně zpracovávat velké podnikového projekty, což ho činí ideálním pro automatizované reportování, migraci a integrační scénáře.

- **Žádná závislost na Microsoft Project** – běží na libovolném serveru nebo v CI prostředí.  
- **Bohatý objektový model** – programově přistupujte k úkolům, zdrojům, přiřazením, kalendářům a vlastním polím.  
- **Více exportních možností** – Aspose.Tasks podporuje export do **více než 20 formátů souborů**, včetně PDF, XML, HTML, CSV, PNG a JPEG, jedním voláním API.  
- **Vysoký výkon** – knihovna dokáže zpracovat projekty obsahující **až 10 000 úkolů** za méně než minutu a streamuje data, aby se předešlo načtení celého souboru do paměti.

## Požadavky
Než začnete, ujistěte se, že máte:

1. Fungující vývojové prostředí Java (JDK 8 nebo novější).  
2. Knihovnu Aspose.Tasks pro Java přidanou do classpath vašeho projektu.  
3. Přístupové údaje k SQL databázi Project Serveru (název serveru, port, název databáze, uživatelské jméno, heslo) pro připojení k Project Serveru.  
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
Zajištění spolehlivého připojení je základem pro čtení dat projektu. Ujistěte se, že instance SQL Serveru je dostupná z vašeho Java hosta a že přihlašovací údaje, které používáte, mají oprávnění **SELECT** na schématu Project Serveru. Také byste měli ověřit latenci sítě a nakonfigurovat případná SSL nastavení pro zajištění zabezpečené komunikace.

## Krok 1: nastavení databázového připojení
Třída `MspDbSettings` zapouzdřuje podrobnosti JDBC připojení potřebné pro přístup k databázi Microsoft Project Serveru. Vytvořte instanci `MspDbSettings`, která obsahuje JDBC řetězec připojení. Nahraďte zástupné hodnoty skutečnými údaji o vašem serveru.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Tip:** Uložte řetězec připojení do zabezpečeného konfiguračního souboru nebo proměnné prostředí místo tvrdého kódování přihlašovacích údajů.

## Krok 2: přidání JDBC ovladače
Načtěte Microsoft SQL Server JDBC ovladač za běhu, aby JVM mohl komunikovat s databází.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Varování:** Ujistěte se, že verze ovladače odpovídá verzi vašeho SQL Serveru. Použití nekompatibilního ovladače může způsobit selhání připojení.

## Krok 3: načtení dat projektu
Třída `Project` představuje soubor Microsoft Project načtený do paměti, který zpřístupňuje úkoly, zdroje a přiřazení. Vytvořte objekt `Project` předáním `MspDbSettings`. Aspose.Tasks automaticky načte data projektu z databáze.

```java
Project project = new Project(settings);
```

V tomto okamžiku můžete prozkoumat objekt `project` – vypsat úkoly, zdroje nebo podle potřeby upravit pole.

## Krok 4: uložení projektu jako PDF
Výčtový typ `SaveFileFormat` definuje výstupní formát pro metodu `Project.save`, například PDF, XML nebo HTML. Exportujte načtený projekt do formátu dle vašeho výběru. Níže uvedený příklad ukládá projekt jako **PDF**, což je ideální pro tiskové zprávy. Můžete také **exportovat projekt do XML** nebo **převést projekt na HTML** změnou výčtu `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Pokud dáváte přednost XML, jednoduše nahraďte `SaveFileFormat.Pdf` za `SaveFileFormat.Xml`. Pro výstup HTML použijte `SaveFileFormat.Html`.

## Časté problémy a řešení
| Problém | Typická příčina | Řešení |
|-------|---------------|-----|
| **Connection timeout** | Špatný server/port nebo blokování firewallem | Ověřte adresu serveru, otevřete port 1433 a otestujte konektivitu jednoduchým JDBC testovacím programem. |
| **Authentication error** | Neplatné uživatelské jméno/heslo nebo SQL Server není nastaven pro SQL ověřování | Použijte platné SQL přihlášení nebo povolte smíšený režim ověřování na serveru. |
| **Driver not found** | JDBC jar není v classpath | Ujistěte se, že `addJDBCDriver` ukazuje na správný `.jar` soubor a že cesta používá dvojité zpětné lomítko (`\\`). |
| **Empty project after load** | Nedostatečná oprávnění pro čtení tabulek Project Serveru | Udělejte přihlášení práva SELECT na schéma databáze Project Serveru. |

## Často kladené otázky

**Q: Lze Aspose.Tasks použít k načtení dat projektu z jiných databází než Microsoft Project?**  
A: Ano, Aspose.Tasks podporuje čtení dat projektu z XML souborů, databází Primavera a dalších standardních formátů projektů.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi Microsoft Project?**  
A: Ano, knihovna funguje s Microsoft Project 2007 až po nejnovější verze 2024, což zajišťuje bezproblémovou integraci napříč verzemi.

**Q: Mohu manipulovat s daty projektu před jeho uložením?**  
A: Rozhodně, můžete pomocí bohatého API přidávat, aktualizovat nebo mazat úkoly, zdroje a vlastní pole před exportem.

**Q: Podporuje Aspose.Tasks více výstupních formátů?**  
A: Ano, můžete ukládat projekty jako PDF, XML, HTML, CSV, PNG, JPEG a další – celkem více než 20 formátů.

**Q: Kde mohu najít další podporu nebo pomoc s Aspose.Tasks?**  
A: Pro další pomoc navštivte fórum Aspose.Tasks nebo prozkoumejte dokumentaci dostupnou na webu [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Závěr
Podle tohoto krok‑za‑krokem průvodce nyní víte, jak **read Microsoft Project database**, **save the project as PDF** a exportovat do dalších formátů pomocí Aspose.Tasks pro Java. Tento přístup eliminuje závislost na Microsoft Project, zjednodušuje automatizované reportování a otevírá cestu k výkonným vlastním integracím.

---

**Poslední aktualizace:** 2026-10-31  
**Testováno s:** Aspose.Tasks for Java 24.5 (nejnovější v době psaní)  
**Autor:** Aspose

## Související tutoriály

- [Jak uložit projekt jako PDF s Aspose.Tasks – Průvodce exportem](/tasks/java/project-file-operations/save-as-pdf/)
- [Uložit projekt jako PDF – Vykreslit list úkolů s Aspose.Tasks pro Java](/tasks/java/task-properties/render-task-sheet/)
- [Exportovat projekt do PDF a snížit mezeru mezi seznamem úkolů a patičkou v Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}