---
date: 2025-12-21
description: Μάθετε πώς να αποθηκεύετε το έργο ως πρότυπο, να εξάγετε MPP σε CSV και
  να μετατρέπετε MPP σε κείμενο χρησιμοποιώντας το Aspose.Tasks για Java.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Αποθήκευση έργου ως πρότυπο, CSV και κείμενο με το Aspose.Tasks για Java
url: /el/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αποθήκευση Έργου ως Πρότυπο, CSV και Κείμενο με Aspise.Tasks

## Introduction
Σε αυτό το tutorial, θα ανακαλύψετε **πώς να αποθηκεύσετε ένα έργο ως πρότυπο** και επίσης πώς να εξάγετε τα αρχεία Microsoft Project (MPP) σας σε μορφές CSV και απλού‑κειμένου χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για Java. Είτε χρειάζεστε να δημιουργήσετε ένα επαναχρησιμοποιήσιμο πρότυπο έργου, να δημιουργήσετε αναφορές CSV για ανάλυση, είτε να παραγάγετε απλές εξαγωγές κειμένου για ενσωμάτωση, αυτά τα βήματα θα σας καθοδηγήσουν γρήγορα και αποδοτικά.

## Quick Answers
- **Can I export MPP to CSV?** Yes – use `project.save(..., SaveFileFormat.CSV)`.  
- **How to export text?** Save with `SaveFileFormat.TEXT`.  
- **What does “save project as template” do?** It creates an `.mpt` file that strips actual and baseline values, ready for reuse.  
- **Do I need a license?** A trial is available; a commercial license is required for production.  
- **Which Java version is required?** Java 8+ is supported.

## What is “save project as template”?
Η αποθήκευση ενός έργου ως πρότυπο (`.mpt`) καταγράφει τη δομή, την ιεραρχία εργασιών και τις αναθέσεις πόρων, ενώ αφαιρεί τις πραγματικές ημερομηνίες έναρξης/λήξης και τα δεδομένα βάσης. Αυτό κάνει το πρότυπο ιδανικό για επαναχρησιμοποίηση ενός τυπικού σχεδίου έργου σε πολλά νέα έργα.

## Why use Aspose.Tasks for Java?
Το Aspose.Tasks σας επιτρέπει να χειρίζεστε αρχεία Microsoft Project χωρίς να εγκαταστήσετε το ίδιο το Microsoft Project. Υποστηρίζει **πώς να εξάγετε MPP**, **πώς να εξάγετε κείμενο**, και **μετατροπή MPP σε CSV**, όλα από καθαρό κώδικα Java, κάτι που είναι τέλειο για αυτοματισμούς στο διακομιστή, CI pipelines ή επιτραπέζιες εφαρμογές.

## Prerequisites
Before we begin, ensure you have:

1. Java Development Kit (JDK) 8 or higher installed.  
2. Aspose.Tasks for Java library added to your project. Download it from [εδώ](https://releases.aspose.com/tasks/java/).  
3. Basic familiarity with Java syntax and Maven/Gradle project setup.

## Import Packages
First, import the required classes in your Java source file:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Save Project as CSV (Export MPP to CSV)
Exporting an MPP file to CSV is useful for data analysis in Excel or BI tools.

### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Step 2: Save as CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Save Project as Text (How to Export Text)
If you need a plain‑text representation of tasks, resources, or assignments, save the project as a text file.

### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Step 2: Save as Text
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Save Project as Template (Create Project Template Java)
Creating a reusable template removes actual dates and baselines, leaving a clean skeleton for new projects.

### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Step 2: Set Template Options
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Step 3: Save as Template
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Common Issues & Tips
- **File Not Found:** Ensure the path to `YourProject.mpp` is correct or use an absolute path.  
- **License Exceptions:** Without a valid license, the library runs in evaluation mode and may add watermarks. Apply your license early in the code (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Large Projects:** For very large MPP files, consider increasing the JVM heap size (`-Xmx2g`) to avoid `OutOfMemoryError`.

## Conclusion
We've covered **how to save project as template**, as well as how to **export MPP to CSV** and **convert MPP to text** using Aspose.Tasks for Java. These capabilities let you automate project data handling, generate reusable templates, and integrate project information into other systems—all without needing Microsoft Project installed.

## FAQ's
### Q: Can Aspose.Tasks for Java handle complex project files?
A: Absolutely! Aspose.Tasks for Java can handle projects of varying complexity with ease, providing comprehensive support for Microsoft Project file formats.  
### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Yes, you can get a free trial of Aspose.Tasks for Java from [εδώ](https://releases.aspose.com/).  
### Q: Where can I find support for Aspose.Tasks for Java?
A: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any assistance or queries regarding Aspose.Tasks for Java.  
### Q: Can I purchase a temporary license for Aspose.Tasks for Java?
A: Yes, you can purchase a temporary license from [εδώ](https://purchase.aspose.com/temporary-license/), allowing you to evaluate the full potential of the library.  
### Q: Is Aspose.Tasks for Java compatible with different operating systems?
A: Yes, Aspose.Tasks for Java is compatible with various operating systems, including Windows, macOS, and Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose