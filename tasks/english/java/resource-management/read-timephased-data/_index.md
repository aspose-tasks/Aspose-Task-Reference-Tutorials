---
title: Get resource by id and read timephased data in Aspose.Tasks
linktitle: Get resource by id and read timephased data in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to get resource by id and extract timephased data from MS Project resources using Aspose.Tasks for Java.
weight: 15
url: /java/resource-management/read-timephased-data/
date: 2026-01-20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Get resource by id and read timephased data in Aspose.Tasks

## Introduction
In this tutorial, we'll guide you through **how to get resource by id** and read timephased data for MS Project resources using Aspose.Tasks for Java. Whether you need to analyze resource workloads or cost distribution, extracting this information programmatically saves countless manual hours.

## Quick Answers
- **What is the primary class to load a project?** `Project` from `com.aspose.tasks`.
- **How do I locate a specific resource?** Use `project.getResources().getByUid(resourceId)`.
- **Can I read both work and cost data?** Yes – call `resource.getTimephasedData` with the appropriate `TimephasedDataType`.
- **Do I need a license for development?** A free evaluation license works for testing; a full license is required for production.
- **Which Java version is supported?** Aspose.Tasks for Java supports JDK 8 and newer.

## What is **get resource by id**?
`get resource by id` is a method call that retrieves a `Resource` object from a `Project` using the resource’s unique identifier (UID). This UID is assigned by Microsoft Project when the resource is created and remains constant throughout the project’s lifecycle.

## Why read timephased data?
Timephased data breaks down a resource’s work or cost into discrete time intervals (daily, weekly, monthly). This granularity lets you:
- Generate custom reports on resource utilization.
- Identify over‑allocations early.
- Feed data into forecasting or budgeting tools.

## Prerequisites
Before we begin, ensure you have the following prerequisites:

1. **Java Development Kit (JDK)** – Install JDK 8 or later. You can download it from the [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) and follow the installation instructions.  
2. **Aspose.Tasks for Java Library** – Download the Aspose.Tasks for Java library from the [download page](https://releases.aspose.com/tasks/java/) and follow the installation instructions provided in the documentation.  

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
You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for assistance from the community and support team.

## Frequently Asked Questions

**Q: How do I **how to extract project** data for multiple resources at once?**  
A: Loop through `project.getResources()` and call `getTimephasedData` for each resource inside the loop.

**Q: Is there a way to change the time interval (e.g., daily → weekly)?**  
A: Yes, pass a `TimephasedDataType` such as `TimephasedDataType.ResourceWork` together with a `TimephasedData` collection that you can aggregate manually.

**Q: Can I export the timephased data to CSV?**  
A: After retrieving the data, write it to a CSV file using standard Java I/O (`FileWriter`/`BufferedWriter`).

**Q: Does Aspose.Tasks support reading project files created in newer MS Project versions?**  
A: The library is regularly updated to support the latest MPP formats; always use the latest Aspose.Tasks version.

**Q: What performance considerations are there for large projects?**  
A: Load the project once, reuse the `Project` instance, and avoid repeated calls to `getTimephasedData` for the same interval.

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}