---
title: How to Set Keywords in MPP Project Summary with Aspose.Tasks
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to set keywords and set creation date java in an MPP project using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
weight: 27
url: /java/project-file-operations/write-mpp-project-summary/
date: 2026-03-29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Set Keywords in MPP Project Summary with Aspose.Tasks

## Introduction
In this tutorial you’ll discover **how to set keywords** and other summary information for an MPP project file by using Aspose.Tasks for Java. Whether you need to embed author details, revision numbers, or a custom creation date, this guide walks you through the exact steps, complete with ready‑to‑run code. By the end you’ll be able to set keywords, set creation date java, and retrieve the data back from the file.

## Quick Answers
- **What library is used?** Aspose.Tasks for Java  
- **Primary purpose?** Set keywords, author info, and creation date in an MPP file  
- **How many code steps?** Three simple code blocks (initialize, save, read)  
- **Do I need a license?** A free trial works for development; a commercial license is required for production  
- **Supported Java version?** Java 8 and higher  

## What is “how to set keywords” in an MPP file?
Keywords are metadata fields stored inside a Microsoft Project (MPP) file. They help categorize projects, enable quick searching, and provide contextual information for downstream tools. Aspose.Tasks exposes the `Prj.KEYWORDS` property, making it straightforward to write or update this value programmatically.

## Why use Aspose.Tasks for Java to set keywords and creation date?
* **Full .MPP compatibility** – works with all Project 2007‑2023 formats.  
* **No COM or Office installation required** – pure Java, perfect for server‑side environments.  
* **Rich API** – besides keywords you can set author, revision, comments, and dates in a single call.  
* **Performance‑optimized** – fast read/write even for large project files.

## Prerequisites
Before you start, make sure you have:
1. **Java Development Kit (JDK)** – JDK 8 or newer installed.  
2. **Aspose.Tasks for Java** – download the latest JAR from [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans, or any editor you prefer.

## Import Packages
First, import the classes you’ll need. These imports give you access to the `Project` object, the `Prj` enumeration for summary fields, and the `SaveFileFormat` enum for saving.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Step 1: Set Up Project and Define Summary Information
Create a `Project` instance, then use the `set` method to write the desired metadata. Notice how we **set the keywords** and **set creation date java** using a `Calendar` object.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Step 2: Save Project Summary Information
After populating the fields, persist the changes. Here we save the project as XML for easy inspection, but you can also save back to MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Step 3: Read Project Summary Information
To verify that the metadata was written correctly, reload the file and read each property back. This step demonstrates that **how to set keywords** really works end‑to‑end.

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
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **NullPointerException on `project.get(Prj.CREATION_DATE)`** | The calendar was never set before saving. | Ensure you call `project.set(Prj.CREATION_DATE, cal.getTime())` before `save()`. |
| **Keywords not appearing in Microsoft Project UI** | The file was saved as XML and opened directly in Project. | Save back to MPP (`SaveFileFormat.MPP`) or open the XML via *Import* in Project. |
| **Date values shifted by timezone** | Java `Date` includes timezone information. | Use `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` if you need UTC dates. |

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

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}