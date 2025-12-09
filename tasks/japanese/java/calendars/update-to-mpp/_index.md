---
date: 2025-12-03
description: Aspose.Tasks for Java を使用して、カレンダー MS Project の作成方法、プロジェクトを MPP に変換する方法、そしてプロジェクト
  MPP を簡単に保存する方法を学びましょう。
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks でカレンダーを作成し、MS Project を MPP として保存
url: /ja/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Calendar MS Project and Save as MPP with Aspose.Tasks

## Introduction

現代のプロジェクト管理では、**カレンダー MS Project** ファイルを作成し、ネイティブな MPP 形式で共有する必要が頻繁にあります。複数のソースからスケジュールを統合したり、レガシーデータを移行したりする際に、プログラムでカレンダーを生成できれば、時間を節約でき、手作業によるミスも防げます。このチュートリアルでは、MS Project でカレンダーを作成し、カスタマイズし、最終的に **convert[ing] project to MPP** を Aspose.Tasks Java API を使って実行する手順をすべて解説します。

## Quick Answers
- **What does this tutorial cover?** Creating a calendar in MS Project and saving it as an MPP file with Aspose.Tasks for Java.  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **Which Java version is required?** Java 8 or higher (JDK 8+).  
- **Can I customize the calendar?** Yes – you can add working times, exceptions, and holidays.  
- **How long does implementation take?** About 10‑15 minutes for a basic calendar.

## What is “create calendar MS Project”?

Creating a calendar MS Project means programmatically defining the working days, hours, and exceptions that drive task scheduling within a Microsoft Project file. By using Aspose.Tasks you can build, modify, and persist these calendars without ever opening the Microsoft Project UI.

## Why use Aspose.Tasks for this task?

- **Full .NET/Java compatibility** – works on any platform that supports Java.  
- **No COM or Office installation needed** – ideal for server‑side automation.  
- **Rich API** – supports every calendar property, including custom work weeks and holidays.  
- **Direct MPP output** – you can **save project MPP** without intermediate conversions.

## Prerequisites

1. **Java Development Kit (JDK) 8+** – ensure `java -version` reports 1.8 or newer.  
2. **Aspose.Tasks for Java** – download the latest JAR from the [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, or any editor you prefer.  
4. **Basic Java knowledge** – familiarity with classes, methods, and file I/O.

## Step‑by‑Step Guide

### Step 1: Import Required Packages

First, bring the Aspose.Tasks classes and Java utilities into scope.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Step 2: Set Up the Data Directory

Define where your input template and output files will live. Replace the placeholder with the actual path on your machine.

```java
String dataDir = "Your Data Directory";
```

### Step 3: Define Input and Output File Names

We’ll load an existing MPP file (or a blank project) and write the result to a new file.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Step 4: Load the Project and Add a New Calendar

Create a `Project` instance from the source file and add a calendar named **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Step 5: Customize the Calendar (Optional)

If you need specific working times, holidays, or exceptions, call your own helper method. The sample uses `GetTestCalendar` as a placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set working hours for each day of the week.

### Step 6: Assign the Calendar to the Project

Tell the project to use the newly created calendar for all its scheduling calculations.

```java
project.set(Prj.CALENDAR, cal1);
```

### Step 7: Save the Project as MPP

Now **convert project to MPP** by saving it with the `SaveFileFormat.Mpp` option.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Step 8: Confirm Successful Completion

A simple console message lets you know the process finished without errors.

```java
System.out.println("Process completed Successfully");
```

## Common Use Cases

- **Automated schedule generation** for recurring projects (e.g., weekly sprints).  
- **Migrating legacy CSV or Excel calendars** into a fully‑featured MS Project file.  
- **Server‑side reporting** where a web service returns an MPP file on demand.  

## Troubleshooting & Common Pitfalls

| Issue | Cause | Fix |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` points to a non‑existent folder | Ensure the directory exists or create it programmatically. |
| Calendar not applied to tasks | Tasks still reference the default calendar | After setting `Prj.CALENDAR`, also update each task’s `Task.CALENDAR` if they were previously overridden. |
| Output file is 0 KB | Missing write permissions | Run the JVM with appropriate file system rights or choose a writable path. |

## Frequently Asked Questions

**Q: Is Aspose.Tasks for Java compatible with different versions of MS?**  
A: Yes, Aspose.Tasks for Java supports a wide range of MS Project versions, from Project 2007 up to the latest release, ensuring seamless compatibility.

**Q: Can I customize calendars according to specific project requirements?**  
A: Absolutely. You can define working days, set custom work weeks, add holidays, and even create multiple calendars within a single project file.

**Q: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?**  
A: Yes, you can get help from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

**Q: Is there a free trial available for Aspose.Tasks for Java?**  
A: Yes, a fully functional free trial is available [here](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Tasks for Java?**  
A: Temporary licenses can be requested via the Aspose website [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}