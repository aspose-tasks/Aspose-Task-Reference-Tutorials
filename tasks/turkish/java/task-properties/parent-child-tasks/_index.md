---
date: 2026-02-23
description: Aspose.Tasks for Java kullanarak proje başlangıç tarihini nasıl ayarlayacağınızı,
  görev süresini nasıl belirleyeceğinizi ve projeyi MPP olarak nasıl kaydedeceğinizi
  öğrenin. Üst ve alt görevleri verimli bir şekilde yönetin.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Proje Başlangıç Tarihini Belirleyin ve Üst ve Alt Görevleri
  Yönetin
url: /tr/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proje Başlangıç Tarihini Ayarlama ve Aspose.Tasks'te Üst ve Alt Görevleri Yönetme

## Introduction
Görev organizasyonu, başarılı proje yönetiminin temelini oluşturur ve **proje başlangıç tarihinin ayarlanması** doğru bir şekilde yapılması, iyi yapılandırılmış bir takvimin ilk adımıdır. Bu öğreticide **proje başlangıç tarihini ayarlama**, görev sürelerini yapılandırma ve Aspose.Tasks for Java kullanarak üst‑alt ilişkilerini yönetme konularını göreceksiniz. Sonunda **projeyi MPP olarak kaydetme**, görev tamamlama yüzdelerini güncelleme ve görev özelliklerini gerçek dünyadaki herhangi bir senaryoya uyacak şekilde özelleştirme konusunda hazır olacaksınız.

## Quick Answers
- **How do I set the project start date?** Use `proj.set(Prj.START_DATE, startDate);` after initializing the `Project` object.  
- **Can I add child tasks under a parent task?** Yes – call `parentTask.getChildren().add("Child Task")`.  
- **What format does Aspose.Tasks save the file in?** Use `SaveFileFormat.Mpp` to **save project as MPP**.  
- **How do I update task completion?** Set `Tsk.PERCENT_COMPLETE` on the task object.  
- **Where can I obtain a temporary license?** Visit the temporary‑license page linked in the FAQs.

## Prerequisites
Bu öğreticiye başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
- Java programlamaya temel bir anlayış.  
- Aspose.Tasks for Java kütüphanesi yüklü. İndirmek için [buraya](https://releases.aspose.com/tasks/java/) tıklayın.  
- Sisteminizde bir Java Entegre Geliştirme Ortamı (IDE) kurulmuş.

## Import Packages
Başlamak için gerekli paketleri Java projenize dahil edin. Bu paketler, Aspose.Tasks for Java işlevselliğiyle sorunsuz entegrasyonu sağlar.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
Projenin başlangıç tarihini ve diğer ilgili parametreleri ayarlayarak başlayın.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Step 2: Add Parent Task (Task 1)
"Task 1" adlı bir üst görev oluşturun ve **set task duration** dahil olmak üzere özelliklerini yapılandırın.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Step 3: Add Parent Task (Task 2) with Child Tasks
Şimdi "Task 2" adlı başka bir üst görev ekleyin ve alt görevleri (Task 3 ve Task 4) dahil edin.
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Step 4: Configure Child Tasks
Task 3 ve Task 4 için başlangıç tarihlerini, sürelerini ve kısıtlamalarını belirleyin.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Step 5: Update Task Completion Percentage
Task 3 ve Task 4 için tamamlama yüzdesini ayarlayın – işte **update task completion** nasıl yapılır.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Step 6: Save the Project
Son olarak, uygulanan değişikliklerle **save project as MPP** yapın.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Bu adım‑adım kılavuz, Aspose.Tasks for Java kullanarak üst ve alt görevleri etkili bir şekilde yönetmeyi gösterir. Projenizin gereksinimlerine uygun farklı yapılandırmalarla denemeler yapın.

## Why Customize Task Properties?
Başlangıç tarihleri, süreler, kısıtlamalar ve tamamlama yüzdeleri gibi görev özelliklerini özelleştirmek, takvim davranışı üzerinde ayrıntılı kontrol sağlar. Görevleri kaynak kullanılabilirliğiyle hizalamanız ya da iş kurallarını uygulamanız gerektiğinde, Aspose.Tasks **customize task properties** özelliğini programatik olarak sunar.

## Common Issues and Solutions
| Sorun | Çözüm |
|-------|----------|
| **Start date not applied** | `proj.set(Prj.START_DATE, …)` **after** `Project` nesnesi oluşturulduktan **sonra** ve görevler eklenmeden önce çağrıldığından emin olun. |
| **Child tasks inherit wrong constraints** | Her alt görevin `ConstraintType` ve `ConstraintDate` değerlerini Step 4'te gösterildiği gibi açıkça ayarlayın. |
| **Saved file cannot be opened in MS Project** | En son Aspose.Tasks sürümünü kullandığınızdan ve `SaveFileFormat.Mpp` ile kaydettiğinizden emin olun. |
| **Percentage not reflecting in UI** | `Tsk.PERCENT_COMPLETE` ayarlandıktan sonra, tarihlerin yeniden hesaplanması gerekiyorsa `proj.calculateTaskSchedule()` metodunu çağırın. |

## FAQs
### Is Aspose.Tasks for Java compatible with different project file formats?
Yes, Aspose.Tasks for Java supports various project file formats, including MPP and XML.

### Can I customize task properties beyond what is covered in this tutorial?
Absolutely! Aspose.Tasks for Java provides extensive customization options for task properties.

### Is there a community forum for Aspose.Tasks where I can seek support?
Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community support.

### How can I obtain a temporary license for Aspose.Tasks for Java?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Where can I find comprehensive documentation for Aspose.Tasks for Java?
The documentation is available [here](https://reference.aspose.com/tasks/java/).

**Additional Q&A**

**Q: How do I programmatically obtain a temporary license?**  
A: Load the temporary license file using `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q: Can I change the default task duration unit?**  
A: Yes – modify the `TimeUnitType` argument in `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q: What version of Aspose.Tasks is required to use `SaveFileFormat.Mpp`?**  
A: All recent versions (2022‑2026) support saving as MPP; check the release notes for any breaking changes.

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}