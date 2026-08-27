---
date: 2026-03-27
description: Lär dig hur du programatiskt hämtar outline‑koder i MS Project med Aspose.Tasks
  för Java. Förbättra dina projektledningsförmågor.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hämta MS Project Outline‑koder i Aspose.Tasks
url: /sv/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hämta MS Project Outline Codes i Aspose.Tasks

## Introduction
I den här handledningen kommer du att upptäcka **hur du hämtar MS Project outline codes** med Aspose.Tasks för Java. Outline codes i MS Project ger dig ett kraftfullt sätt att kategorisera uppgifter, resurser och tilldelningar, och att komma åt dem programmässigt låter dig bygga anpassade rapporter, automatisering eller integrationslösningar. Vi går igenom ett komplett, steg‑för‑steg‑exempel som du kan kopiera in i ditt eget projekt.

## Quick Answers
- **What does the code do?** It loads a Project file and prints every outline code definition, its masks, and its values.  
- **Which library is required?** Aspose.Tasks for Java (any recent version).  
- **Do I need a license?** A trial works for development; a full license is required for production.  
- **What Java version is supported?** Java 8 or higher.  
- **Can I modify the codes after retrieving them?** Yes – the same API lets you add, edit, or delete outline codes.

## What are ms project outline codes?
Outline codes är anpassade fält som låter projektledare gruppera och filtrera uppgifter utöver den standardhierarki som finns. De kan vara enkla numeriska värden, strängar eller till och med företagsomfattande anpassade koder som definieras på organisationsnivå. Genom att läsa dessa koder kan du driva instrumentpaneler, exportera data eller automatiskt upprätthålla namngivningskonventioner.

## Why retrieve ms project outline codes with Aspose.Tasks?
- **Automation:** Generera rapporter eller trigga arbetsflöden utan manuell export.  
- **Integration:** Synkronisera outline codes med ERP-, PPM- eller BI-verktyg.  
- **Customization:** Tillämpa affärsregler baserade på kodvärden (t.ex. kostnadsallokering).  
- **Cross‑platform:** Fungerar på Windows, Linux och macOS, oberoende av Microsoft Project UI.

## How to read MPP files for outline codes?
Att läsa en MPP‑fil (Microsoft Project) är det första steget för att extrahera outline codes. Aspose.Tasks abstraherar filformatet, så du behöver inte själv tolka den binära strukturen. Klassen `Project` sköter det tunga arbetet, så att du kan fokusera på den data du faktiskt behöver.

## Custom fields in MS Project
Outline codes är en typ av **custom fields** i MS Project. Medan standardfält täcker datum, varaktigheter och resurser, låter anpassade fält dig lagra organisationsspecifik information. Att komma åt dem via Aspose.Tasks ger dig samma flexibilitet programmässigt.

## Prerequisites
Before we begin, ensure you have the following prerequisites set up:

### 1. Java Development Environment
Make sure you have Java Development Kit (JDK) installed on your system. You can download and install JDK from the Oracle website.

### 2. Aspose.Tasks Library
Download and include the Aspose.Tasks library in your Java project. You can download the library from the [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/).

## Import Packages
First, import the necessary packages from Aspose.Tasks in your Java code:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Now let's break down the provided example code into multiple steps:

## Step 1: Load the Project
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
In this step, we load the Microsoft Project file into a `Project` object using the provided file name.

## Step 2: Retrieve Outline Codes
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
We iterate through each outline code definition in the project.

## Step 3: Access Outline Code Properties
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
We retrieve and print various properties of the outline code definition such as Alias, Field ID, and Field Name.

## Step 4: Check Enterprise Custom Code
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
We check if the outline code is an enterprise custom code and print the result accordingly.

## Step 5: Display Outline Code Masks
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
We iterate through each mask associated with the outline code and print its level and mask value.

## Step 6: Display Outline Code Values
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
We iterate through each outline code value and print its description, value ID, value, and type.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **No output** | Project file path incorrect | Verify `projectName` points to a valid `.mpp` file. |
| **Null values** | Outline code not defined in the file | Ensure the Project file actually contains outline codes (check in MS Project UI). |
| **LicenseException** | Using trial without proper activation | Apply a temporary or full license via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks for Java to modify outline codes in a Project file?**  
A: Yes, Aspose.Tasks for Java provides APIs to modify outline codes programmatically. You can add, edit, or delete definitions using the same `Project` object.

**Q: Is there a trial version available for Aspose.Tasks for Java?**  
A: Yes, you can download a free trial version of Aspose.Tasks for Java from the [Aspose.Tasks website](https://releases.aspose.com/).

**Q: How can I get technical support for Aspose.Tasks for Java?**  
A: You can get technical support by visiting the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) and posting your queries there.

**Q: Can I purchase a temporary license for Aspose.Tasks for Java?**  
A: Yes, you can purchase a temporary license for Aspose.Tasks for Java from the [purchase page](https://purchase.aspose.com/temporary-license/).

**Q: Where can I find the complete documentation for Aspose.Tasks for Java?**  
A: You can refer to the [documentation](https://reference.aspose.com/tasks/java/) for detailed information on using Aspose.Tasks for Java.

## Conclusion
In this tutorial, we have learned how to retrieve **ms project outline codes** using Aspose.Tasks for Java. By following the provided steps, you can effectively access and manipulate outline codes in your Java applications, enabling advanced project management capabilities such as custom reporting, automation, and integration with other enterprise systems.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}