---
date: 2025-12-23
description: تعلم كيفية إنشاء تبعيات المهام وحساب المسار الحرج في MS Project باستخدام
  Aspose.Tasks للغة Java. دليل خطوة بخطوة لإدارة المشاريع.
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: إنشاء تبعيات المهام وحساب المسار الحرج في Aspose.Tasks
url: /ar/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء تبعيات المهام وحساب المسار الحرج في Aspose.Tasks

## Introduction
في هذا الدرس، **ستتعلم كيفية إنشاء تبعيات المهام** وحساب المسار الحرج في ملف MS Project باستخدام Aspose.Tasks for Java. يساعدك فهم وتصور المسار الحرج على إبقاء مشروعك على الجدول الزمني، بينما يضمن ربط المهام بشكل صحيح أن أي تأخير يصبح مرئياً فوراً. دعنا نتبع العملية بالكامل، من إعداد البيئة إلى عرض المسار الحرج النهائي.

## Quick Answers
- **ما هي الخطوة الأولى؟** إعداد مشروع Java الخاص بك وإضافة مكتبة Aspose.Tasks.  
- **ما الوضع الذي يجب تمكينه؟** `CalculationMode.Automatic` (تعيين الحساب التلقائي).  
- **كيف أقوم بربط المهام؟** استخدم `project.getTaskLinks().add(...)` لإنشاء تبعيات المهام.  
- **كيف يمكنني عرض المسار الحرج؟** قم بالتكرار على `project.getCriticalPath()` وطباعة اسم كل مهمة.  
- **هل أحتاج إلى ترخيص؟** نعم، يلزم وجود ترخيص Aspose.Tasks صالح للاستخدام في الإنتاج.

## What is “create task dependencies”?
إنشاء تبعيات المهام يعني تعريف العلاقات (مثل الانتهاء‑لبدء) بين المهام بحيث يعكس الجدول الزمني القيود الواقعية. في Aspose.Tasks، يتم ذلك عبر كائنات `TaskLink`.

## Why calculate the critical path in MS Project?
يظهر **المسار الحرج في MS Project** أطول تسلسل من المهام المرتبطة التي تحدد الحد الأدنى لمدة المشروع. بحسابه، يمكنك بسرعة تحديد المهام التي لا يمكن تأخيرها دون التأثير على الجدول الزمني العام—وهو أمر أساسي لتطبيقات **إدارة المشاريع Java** الفعّالة.

## Prerequisites
قبل أن نبدأ، تأكد من أن لديك:

1. مجموعة تطوير جافا (JDK) مثبتة على نظامك.  
2. مكتبة Aspose.Tasks for Java تم تحميلها وإضافتها إلى مشروعك. يمكنك تحميلها من [هنا](https://releases.aspose.com/tasks/java/).  

## Import Packages
لبدء العمل، استورد الحزم اللازمة في فئة Java الخاصة بك:
```java
import com.aspose.tasks.*;
```

## How to set automatic calculation?
كيف يتم تعيين الحساب التلقائي؟
تعيين وضع الحساب إلى تلقائي يضمن أن أي تغيير في المهام أو الروابط يحدث تحديثًا فوريًا للجدول الزمني، بما في ذلك المسار الحرج.
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## Step‑by‑Step Guide

### Step 1: Set Up Data Directory
الخطوة 1: إعداد دليل البيانات
حدد المسار إلى المجلد الذي يحتوي على ملف MS Project الخاص بك.
```java
String dataDir = "Your Data Directory";
```

### Step 2: Load MS Project File
الخطوة 2: تحميل ملف MS Project
حمّل ملف المشروع الموجود (مثال: *New project 2013.mpp*) باستخدام Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### Step 3: Add Tasks
الخطوة 3: إضافة مهام
إنشاء ثلاث مهام فرعية بسيطة سنقوم بربطها لاحقًا.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### Step 4: Create Task Links (create task dependencies)
الخطوة 4: إنشاء روابط المهام (إنشاء تبعيات المهام)
حدد التبعيات بين المهام. هنا نستخدم رابط انتهاء‑لبدء، وهو النوع الأكثر شيوعًا.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### Step 5: Display Critical Path (display critical path)
الخطوة 5: عرض المسار الحرج (عرض المسار الحرج)
استرجع واطبع المسار الحرج. تُعيد طريقة `getCriticalPath()` قائمة المهام التي تشكل السلسلة الحرجة.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### Step 6: Confirm Completion
الخطوة 6: تأكيد الانتهاء
اعرض رسالة ودية بمجرد انتهاء العملية.
```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| المشكلة | الحل |
|-------|----------|
| **المسار الحرج فارغ** | تأكد من تعيين `CalculationMode.Automatic` قبل إضافة الروابط. |
| **المهام غير مرتبطة** | تحقق من أنك أضفت كائنات `TaskLink` لكل تبعية. |
| **استثناء الترخيص** | حمّل ترخيص Aspose.Tasks صالح قبل إنشاء كائن `Project`. |

## FAQ's
### Q: Can I use Aspose.Tasks for Java with any version of MS Project files?
س: هل يمكنني استخدام Aspose.Tasks for Java مع أي نسخة من ملفات MS Project؟
ج: نعم، يدعم Aspose.Tasks for Java إصدارات مختلفة من ملفات MS Project، بما في ذلك ملفات .mpp من MS Project 2003 إلى MS Project 2019.  

### Q: Is there a free trial available for Aspose.Tasks for Java?
س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks for Java؟
ج: نعم، يمكنك تحميل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).  

### Q: Where can I find support for Aspose.Tasks for Java?
س: أين يمكنني العثور على الدعم لـ Aspose.Tasks for Java؟
ج: يمكنك العثور على الدعم في [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).  

### Q: Can I purchase a temporary license for Aspose.Tasks for Java?
س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks for Java؟
ج: نعم، يمكنك شراء ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/).  

### Q: How can I buy Aspose.Tasks for Java?
س: كيف يمكنني شراء Aspose.Tasks for Java؟
ج: يمكنك شراء Aspose.Tasks for Java من الموقع [هنا](https://purchase.aspose.com/buy).  

## Conclusion
باستخدام هذه الخطوات، قمت **بإنشاء تبعيات المهام**، وتعيين **الحساب التلقائي**، وعرض **المسار الحرج** بنجاح لملف MS Project الخاص بك. يمنحك هذا سير العمل تحكمًا كاملاً في منطق الجدول الزمني ويساعدك على إبقاء المشاريع على المسار الصحيح باستخدام كود **إدارة المشاريع** القائم على Java.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}