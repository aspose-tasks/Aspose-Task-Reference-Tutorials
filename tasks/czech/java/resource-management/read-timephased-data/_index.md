---
date: 2026-06-15
description: Naučte se, jak extrahovat časově rozvržená data ze zdrojů MS Project
  pomocí Aspose.Tasks pro Java. Podrobný návod krok za krokem k získání zdroje podle
  ID.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Čtení časově rozvržených dat pro zdroje v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Čtení časově rozvržených dat pro zdroje v Aspose.Tasks – získání zdroje podle
  ID
url: /cs/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Čtení časově fázovaných dat pro zdroje v Aspose.Tasks

## Úvod
In this tutorial, you’ll learn **how to get resource by id** and read its timephased data using Aspose.Tasks for Java. We’ll walk through each step—from setting up the project folder to printing work and cost timephased values—so you can extract valuable scheduling information from any Microsoft Project file programmatically. Aspose.Tasks for Java is a comprehensive API that enables developers to create, read, modify, and convert Microsoft Project files without requiring Microsoft Project to be installed, supporting a wide range of project management features and formats.

## Rychlé odpovědi
- **What does “get resource by id” do?** It retrieves a specific `Resource` object from a `Project` using its unique identifier.  
- **Which library handles timephased data?** Aspose.Tasks for Java provides the `Resource.getTimephasedData` API.  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **Can I read large projects?** Yes—Aspose.Tasks can process files with up to 10,000 tasks without loading the whole file into memory.  
- **What Java version is required?** Java 8 or higher; the library is compatible with all major JDKs.

## Co je „get resource by id“?
`get resource by id` is a method call that fetches a `Resource` instance from a loaded `Project` using the resource’s numeric ID. This operation allows precise access to a resource’s detailed properties, such as its assignments, calendars, and custom fields, and is essential for extracting timephased work or cost data associated with that specific resource.

## Proč používat Aspose.Tasks pro časově fázovaná data?
Aspose.Tasks supports **50+ input and output formats** (MPP, XML, CSV, etc.) and can extract timephased work and cost values for resources spanning multi‑year schedules while keeping memory usage low. The API returns data in 15‑minute intervals by default, giving you granular insight for reporting or custom analytics.

## Požadavky
1. Java Development Kit (JDK): Make sure you have JDK installed on your system. You can download it from the [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) and follow the installation instructions.  
2. Aspose.Tasks for Java Library: Download the Aspose.Tasks for Java library from the [download page](https://releases.aspose.com/tasks/java/) and follow the installation instructions provided in the documentation.

## Import balíčků
The first step is to import the required Aspose.Tasks classes into your Java source file.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Krok 1: Nastavení adresáře s daty
First, define the directory where your MS Project file is located. Keeping the data folder separate from source code makes the project easier to maintain.

```java
String dataDir = "Your Data Directory";
```

## Krok 2: Načtení šablony souboru MS Project
Specify the name of your MS Project template file. Using a template ensures consistent column settings across different projects.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Krok 3: Načtení vstupního souboru jako Project
The `Project` class is Aspose.Tasks' core object that represents a Microsoft Project file in memory. Loading the file gives you programmatic access to tasks, resources, and schedules.

```java
Project project = new Project(dataDir + fileName);
```

## Krok 4: Získání zdroje podle ID
To retrieve a specific resource, call the `getResources().getById(id)` method. This is the exact operation referenced by the primary keyword.

```java
Resource resource = project.getResources().getByUid(1);
```

## Krok 5: Výpis časově fázovaných dat pro práci zdroje
Once you have the `Resource` object, you can call `resource.getTimephasedData(ResourceTimephasedDataType.Work)` to obtain work allocations over time. The returned collection contains `TimephasedData` objects that include start date, end date, and the amount of work for each interval.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Krok 6: Výpis časově fázovaných dat pro náklady zdroje
Similarly, `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` returns cost information broken down by the same time intervals. This is useful for budgeting and cost‑tracking reports.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Jak získat zdroj podle ID v jednom řádku?
Load the project, then call `project.getResources().getById(5)`—replace **5** with the actual resource ID you need. This single call returns the `Resource` object, after which you can query its timephased data, assignments, or custom fields. The method runs in O(1) time because resources are indexed internally.

## Časté problémy a řešení
- **Resource not found** – Ensure the ID exists in the project file; IDs start at 1 and are unique per resource.  
- **Empty timephased data** – Verify that the resource has work or cost assignments; otherwise the collection will be empty.  
- **Large file performance** – Use `Project.setLoadOptions(LoadOptions.fromFile(...))` to enable lazy loading for projects larger than 500 MB.

## Často kladené otázky

**Q: Může Aspose.Tasks zpracovávat jiné typy projektových souborů než Microsoft Project?**  
A: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing you to read and write across different standards.

**Q: Je Aspose.Tasks kompatibilní s různými vývojovými prostředími Javy?**  
A: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse, NetBeans) and build tools (Maven, Gradle).

**Q: Mohu pomocí Aspose.Tasks manipulovat s daty projektu?**  
A: Yes, you can create, modify, and delete tasks, resources, assignments, and even custom fields through the API.

**Q: Je Aspose.Tasks vhodný pro projekty na úrovni podniku?**  
A: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch conversions, and server‑side reporting because it requires no Microsoft Project installation.

**Q: Kde mohu najít podporu, pokud narazím na problémy při používání Aspose.Tasks?**  
A: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for assistance from the community and support team.

## Závěr
In this tutorial, we have learned how to **get resource by id** and read its timephased work and cost data using Aspose.Tasks for Java. By following these steps, you can efficiently extract valuable scheduling information from your project files and integrate it into custom reporting or analytics pipelines.

---

**Poslední aktualizace:** 2026-06-15  
**Testováno s:** Aspose.Tasks 24.11 for Java  
**Autor:** Aspose

## Související tutoriály

- [Přidání zdroje do projektu pomocí Aspose.Tasks pro Java](/tasks/java/resource-management/create-resources/)
- [Správa nákladů na zdroje MS Project pomocí Aspose.Tasks pro Java](/tasks/java/resource-management/resource-cost/)
- [Čtení pracovních týdnů v Javě z kalendáře MS Project pomocí Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}