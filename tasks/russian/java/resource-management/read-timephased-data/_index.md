---
date: 2026-01-20
description: Узнайте, как получить ресурс по идентификатору и извлечь временно‑фазированные
  данные из ресурсов MS Project с помощью Aspose.Tasks для Java.
linktitle: Get resource by id and read timephased data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Получить ресурс по идентификатору и прочитать данные с временным распределением
  в Aspose.Tasks
url: /ru/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Получить ресурс по идентификатору и прочитать данные с временными интервалами в Aspose.Tasks

## Introduction
В этом руководстве мы покажем, **как получить ресурс по идентификатору** и прочитать данные с временными интервалами для ресурсов MS Project, используя Aspose.Tasks for Java. Независимо от того, нужно ли вам проанализировать нагруз этой информации экономит бесчисленные часы ручной работы.

## Quick Answers
- **What is the primary class to load a project?** ` work and cost data?** Yes – call `resource.getTimephasedData` with the appropriate `TimephasedDataType`.
 выз объект `Resource` из `Project`, используя уникальный идентификатор ресурса (UID). Этот UID назначается Microsoft Project при создании ресурса и остаётся неизменным на протяжении всего жизненного цикла проекта.

## Why read timephased data?
Зачем читать данные с временными интервалами?
- Создавать пользовательские отчёты об использовании ресурсов.
- Раннее выявлять пере‑распределения.
- Передавать данные в инструменты прогнозирования или бюджетирования.

## Prerequisites
Перед началом убедитесь, что у вас есть следующие требования:

1. **Java Development Kit (JDK)** – Установите JDK 8 или более позднюю версию. Вы можете скачать её с [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) и следовать инструкциям по установке.  
2. **Aspose.Tasks for Java Library** – Скачайте библиотеку Aspose.Tasks for Java со [download page](https://releases.aspose.com/tasks/java/) и выполните инструкции по установке, предоставленные в документации.  

## Import Packages
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Step 1: Set up Data Directory
First, define the directory where your MS Project file is located.

```java
String dataDir = "Your Data Directory";
```

## Step 2: Read MS Project Template File
Specify the name of your MS Project template file.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Step 3: Load the Project (java read project resources)
Read the input file using Aspose.Tasks and load it as a `Project` object.

```java
Project project = new Project(dataDir + fileName);
```

## Step 4: **Get resource by id**
Retrieve the desired resource from the project by its unique identifier (ID). In this example we fetch the resource with UID = 1.

```java
Resource resource = project.getResources().getByUid(1);
```

## Step 5: Print Timephased Data for Resource Work
Print the timephased data for resource work.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Step 6: Print Timephased Data for Resource Cost
Print the timephased data for resource cost.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **NullPointerException when calling `resource.getTimephasedData`** | The project’s start or finish date may be missing. | Ensure the project file contains valid start/finish dates or supply explicit dates. |
| **Incorrect UID** | Resources in the file may have different UIDs than expected. | Use `project.getResources().toList()` to enumerate available UIDs before fetching. |
| **Missing license** | Aspose.Tasks throws an exception if a valid license isn’t loaded in a production build. | Load your license file via `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` |

## FAQ's
### Can Aspose.Tasks handle other types of project files apart from Microsoft Project?
Yes, Aspose.Tasks supports various file formats, including MPP, XML, and CSV.

### Is Aspose.Tasks compatible with different Java development environments?
Yes, Aspose.Tasks is compatible with all major Java IDEs and frameworks.

### Can I manipulate project data using Aspose.Tasks?
Absolutely, Aspose.Tasks provides extensive APIs for creating, modifying, and analyzing project data.

### Is Aspose.Tasks suitable for enterprise‑level projects?
Yes, Aspose.Tasks is widely used in enterprise environments due to its reliability and scalability.

### Where can I find support if I encounter issues while using Aspose.Tasks?
You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15 (напримерA: Yes, pass a `TimephasedDataType` such as `TimephasedDataType.ResourceWork` together with a `TimephasedData` collection that youA: After retrieving the data, write it to a CSV file using standard Java I/O (`FileWriter`/`BufferedWriter`).

**Q: Поддерживает ли Aspose.Tasks чтение файлов проектов, созданных в более новых версиях MS Project?**  
A: The library is regularly updated to support the latest MPP formats; always use the latest Aspose.Tasks version.

**Q: Какие соображения по производительности существуют для больших проектов?**  
A: Load the project once, reuse the `Project` instance, and avoid repeated calls to `getTimephasedData` for the same interval.

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}