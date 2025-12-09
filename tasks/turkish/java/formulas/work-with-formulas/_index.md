---
date: 2025-12-07
description: Aspose.Tasks for Java kullanarak Microsoft Project dosyalarını manipüle
  ederken **test projesi oluşturmayı** ve **özel alan eklemeyi** öğrenin.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Test Projesi Oluşturun ve Aspose.Tasks for Java ile Formülleri Kullanın
url: /tr/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Test Projesi Oluşturma ve Aspose.Tasks for Java ile Formüller Kullanma

## Introduction
Bu öğreticide **test projesi** dosyaları oluşturacak, özel bir alan ekleyecek ve Aspose.Tasks kütüphanesini kullanarak MS Project formülleriyle çalışacaksınız. Aspose.Tasks, **Microsoft Project** verilerini programatik olarak **manipüle etmeyi** kolaylaştırır—zaman çizelgeleri oluşturmak, tarihleri hesaplamak veya raporlamayı otomatikleştirmek istediğinizde. Kılavuzun sonunda, genişletilmiş bir öznitelik tanımlayan, bir göreve son tarih (deadline) atan ve projeyi MPP dosyası olarak kaydeden çalıştırılabilir bir örnek elde edeceksiniz.

## Quick Answers
- **What does the tutorial cover?** Creating a test project, adding a custom field, defining an extended attribute, and setting a task deadline with a formula.  
- **Which library is required?** Aspose.Tasks for Java (latest version).  
- **Do I need a license?** A free trial works for development; a license is required for production.  
- **What IDE can I use?** Any Java IDE (IntelliJ IDEA, Eclipse, VS Code) that supports JDK 8+.  
- **How long does the implementation take?** About 10‑15 minutes to copy the code and run it.

## What is a “Test Project” in Aspose.Tasks?
A **test project** is a lightweight Microsoft Project file created programmatically to demonstrate or validate functionality. It contains a minimal set of tasks, resources, and custom fields that you can manipulate without affecting real project data.

## Why Use Aspose.Tasks to Manipulate Microsoft Project?
- **Full API coverage** – access every Project, Task, and Resource property.  
- **No Office installation required** – works on servers, CI pipelines, and Docker containers.  
- **Cross‑platform** – runs on Windows, Linux, and macOS with the same Java code.  
- **Robust formula engine** – calculate dates, durations, and custom fields directly inside the project file.

## Prerequisites
Before you start, make sure you have the following:

- **Java Development Kit (JDK) 8+** – download from the Oracle website or adopt OpenJDK.  
- **Aspose.Tasks for Java** – obtain the latest JAR from the [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) and add it to your project’s classpath or Maven/Gradle dependencies.

## Import Packages
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Step‑by‑Step Guide

### Step 1: Create a Test Project with a Custom Field
We begin by **creating test project** and adding a custom field that will later hold our formula result.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` is a helper method that builds a minimal schedule and registers an extended attribute ready for formula assignment.

### Step 2: Define an Extended Attribute (Add Custom Field)
Next, we **define extended attribute** – essentially the custom field – and give it a friendly alias. This is where we **add custom field** logic.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** makes the field readable in Project.  
- **Formula** calculates the number of days between a task’s *Finish* date and its *Deadline*.

### Step 3: Set Deadline for a Task (Add Deadline Task & Set Task Deadline)
Now we **add deadline task** data by setting the *Deadline* property on a specific task.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- The `Calendar` instance defines the exact deadline moment.  
- `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.

### Step 4: Save the Project (Manipulate Microsoft Project File)
Finally, we **manipulate Microsoft Project** by persisting the changes to an MPP file.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

You can open `SaveFile.mpp` in Microsoft Project to see the custom field, formula result, and deadline reflected in the schedule.

## Common Issues and Solutions
| Sorun | Çözüm |
|-------|----------|
| **Formula not evaluating** | Özniteliğin `Formula` dizesinin doğru alan adlarını kullandığından emin olun (ör. `[Deadline]`, `[Finish]`). |
| **Task not found** | Görev kimliğinin (`1` örnekte) mevcut olduğunu doğrulayın; hata ayıklamak için `project.getRootTask().getChildren().size()` kullanın. |
| **License exception** | Her API metodunu çağırmadan önce geçerli bir Aspose.Tasks lisansı uygulayın (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing you to **manipulate Microsoft Project** files in the language of your choice.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Absolutely. Download a fully functional trial from the [Aspose.Tasks download page](https://releases.aspose.com/).

**Q: Where can I find detailed documentation for Aspose.Tasks?**  
A: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: How can I get support for Aspose.Tasks?**  
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to ask questions and share experiences with the community.

**Q: Do I need a temporary license for evaluation?**  
A: A temporary license is available for short‑term testing; you can request one [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}