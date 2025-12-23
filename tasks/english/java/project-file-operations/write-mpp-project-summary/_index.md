---
title: How to Create MPP Summary and Update Project Author with Aspose.Tasks
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to create MPP summary and update project author using Aspose.Tasks for Java. Set and retrieve project information effortlessly.
weight: 27
url: /java/project-file-operations/write-mpp-project-summary/
date: 2025-12-23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Write MPP Project Summary in Aspose.Tasks

## Introduction
In this tutorial, you’ll **create MPP summary** information for a Microsoft Project file and learn how to **update project author** details using the Aspose.Tasks library for Java. Whether you’re building a project‑management tool or automating reporting, controlling summary properties programmatically saves time and ensures consistency across your projects.

## Quick Answers
- **What does “create MPP summary” mean?** It means setting the high‑level project properties (author, revision, keywords, etc.) that appear in the Project Summary Information dialog of Microsoft Project.  
- **Which library handles this?** Aspose.Tasks for Java provides a fluent API to read and write those properties.  
- **Do I need a license?** A free trial is available, but a commercial license is required for production use.  
- **Can I also change the author after the file is saved?** Yes – you can **update project author** by calling `project.set(Prj.AUTHOR, "New Author")` and then re‑saving the file.  
- **What file formats are supported?** Both MPP and XML (SaveFileFormat.Xml) are fully supported.

## What is create MPP summary?
Creating an MPP summary involves populating the project’s metadata—author, revision number, keywords, comments, creation date, and printed date. This metadata is stored inside the Project Summary Information record and is displayed in Microsoft Project’s **File → Info** section.

## Why update project author?
Keeping the **project author** information accurate is essential for audit trails, collaboration, and reporting. When multiple team members contribute, you may need to **update project author** to reflect the latest changes or to attribute work correctly.

## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. Java Development Kit (JDK) installed on your machine.  
2. Aspose.Tasks for Java – download it from [here](https://releases.aspose.com/tasks/java/).  
3. An IDE such as IntelliJ IDEA, Eclipse, or NetBeans.

## Import Packages
Firstly, import the necessary packages into your Java class:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Step 1: Set Up Project and Define Summary Information
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
In the code above we **create MPP summary** fields such as author, revision, and keywords. You can also **update project author** later by calling `project.set(Prj.AUTHOR, "New Name")`.

## Step 2: Save Project Summary Information
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Saving the project persists all the summary data you just defined.

## Step 3: Read Project Summary Information
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
This snippet demonstrates how to **read back** the summary information, confirming that the **create MPP summary** operation succeeded.

## Common Issues and Solutions
- **Null values after reading:** Ensure the project was saved successfully before re‑loading. Check file paths and permissions.  
- **Date formatting differences:** `project.get(Prj.CREATION_DATE)` returns a `java.util.Date`. Use `SimpleDateFormat` if you need a custom display format.  
- **License not set:** Without a valid license, Aspose.Tasks runs in evaluation mode and may embed a watermark. Register your license early in the code.

## Frequently Asked Questions
**Q: Can I use Aspose.Tasks for Java with other Java libraries?**  
A: Yes, Aspose.Tasks for Java can be seamlessly integrated with other Java libraries to enhance your project management capabilities.

**Q: Is there a trial version available for Aspose.Tasks for Java?**  
A: Yes, you can download a free trial version from [here](https://releases.aspose.com/).

**Q: How frequently is Aspose.Tasks for Java updated?**  
A: Aspose.Tasks for Java is regularly updated to ensure compatibility with the latest versions of Java and Microsoft Project files.

**Q: Can I customize the project summary information further?**  
A: Absolutely, Aspose.Tasks for Java provides extensive options for customizing project summary information according to your specific requirements.

**Q: Where can I get support for Aspose.Tasks for Java?**  
A: You can get support from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

## Conclusion
In this tutorial we’ve shown you how to **create MPP summary** data, **update project author**, and verify those changes using Aspose.Tasks for Java. By automating these steps you gain full control over project metadata, making your applications more robust and your project reports more accurate.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}