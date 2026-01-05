---
date: 2026-01-05
description: تعلم كيفية إضافة مورد إلى المشروع وإنشاء تعيينات الموارد في Aspose.Tasks
  للغة Java. اتقن تقنيات تخصيص الموارد في Java من خلال هذا الدليل خطوة بخطوة.
linktitle: Add Resource to Project – Create Resource Assignments with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إضافة مورد إلى المشروع – إنشاء تعيينات الموارد باستخدام Aspose.Tasks
url: /ar/java/resource-assignments/create-resource-assignments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مورد إلى المشروع – إنشاء تعيينات الموارد باستخدام Aspose.Tasks

## مقدمة
في إدارة المشاريع، تلعب تعيينات الموارد دورًا حاسمًا في تخصيص الموارد بفعالية للمهام المختلفة. توفر Aspose.Tasks for Java حلاً قويًا لإدارة موارد المشروع وتعييناتها برمجيًا. في هذا البرنامج التعليمي، ستتعلم كيفية **إضافة مورد إلى المشروع** وتعيين الموارد للمهام باستخدام نهج واضح خطوة بخطوة.

## إجابات سريعة
- **ماذا يعني “إضافة مورد إلى المشروع”?** يعني إنشاء كيان مورد في ملف المشروع وربطه بواحدة أو أكثر من المهام.  
- **ما هي طريقة API التي تنشئ التعيين؟** `project.getResourceAssignments().add(task, resource)`.  
- **هل أحتاج إلى ترخيص؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Tasks for Java للاستخدام في الإنتاج.  
- **هل يمكنني استخدام هذا مع Maven؟** بالطبع – فقط أضف تبعية Aspose.Tasks إلى ملف `pom.xml` الخاص بك.  
- **هل الكود متوافق مع Java 11+؟** نعم، الأمثلة تعمل مع Java 8 والإصدارات الأحدث.

## كيفية إضافة مورد إلى المشروع باستخدام Aspose.Tasks
ستجد أدناه سير العمل الكامل، من إعداد البيئة إلى إنشاء التعيين. كل خطوة تتضمن شرحًا مختصرًا يليه الكود الدقيق الذي تحتاج إلى نسخه.

## المتطلبات المسبقة
قبل أن نغوص في إنشاء تعيينات الموارد باستخدام Aspose.Tasks for Java، تأكد من توفر ما يلي:

### بيئة تطوير جافا
تأكد من تثبيت مجموعة تطوير جافا (JDK) على نظامك. يمكنك تنزيل وتثبيت JDK من [هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### مكتبة Aspose.Tasks for Java
قم بتنزيل مكتبة Aspose.Tasks for Java من [صفحة التحميل](https://releases.aspose.com/tasks/java/). اتبع تعليمات التثبيت لإعداد المكتبة في مشروع جافا الخاص بك.

## استيراد الحزم
في كود جافا الخاص بك، استورد الحزم الضرورية من Aspose.Tasks for Java لاستخدام وظائفها:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

## الخطوة 1: إنشاء كائن Project
أنشئ كائن `Project`، الذي يمثل ملف المشروع الذي تعمل عليه:
```java
Project project = new Project();
```

## الخطوة 2: إضافة مهمة إلى المشروع
أضف مهمة إلى المشروع باستخدام طريقة `addChild` للمهمة الجذرية. هذا يوضح عملية **إضافة مهمة إلى المشروع**:
```java
Task task = project.getRootTask().getChildren().add("Task");
```

## الخطوة 3: إضافة مورد إلى المشروع
أضف موردًا إلى المشروع باستخدام طريقة `add` لمجموعة `Resources`. هذا هو جوهر **تخصيص الموارد java**:
```java
Resource rsc = project.getResources().add("Rsc");
```

## الخطوة 4: إنشاء تعيين مورد
أنشئ تعيين مورد للمهمة والموارد باستخدام طريقة `add` لمجموعة `ResourceAssignments`. هذه الخطوة **تُعيّن الموارد للمهام**:
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```

## المشكلات الشائعة والحلول
- **NullPointerException عند إضافة مهمة** – تأكد من إنشاء المشروع قبل الوصول إلى `getRootTask()`.  
- **استثناء الترخيص** – حمّل ترخيص Aspose.Tasks مبكرًا في التطبيق (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`).  
- **معرفات موارد غير صحيحة** – استخدم كائن المورد الذي تُعيده طريقة `add` بدلاً من إنشاء `Resource` جديد يدويًا.

## الأسئلة المتكررة
### س: هل يمكنني تعديل تعيينات الموارد بعد الإنشاء؟
نعم، يمكنك تحديث تعيينات الموارد باستخدام طرق Aspose.Tasks for Java المتوفرة في المكتبة.

### س: هل Aspose.Tasks for Java متوافق مع صيغ ملفات المشروع المختلفة؟
بالطبع، يدعم Aspose.Tasks for Java صيغ ملفات مشروع متعددة بما في ذلك MPP و XML وغيرها.

### س: هل يتطلب Aspose.Tasks for Java ترخيصًا للاستخدام التجاري؟
نعم، تحتاج إلى ترخيص صالح لاستخدام Aspose.Tasks for Java في المشاريع التجارية. يمكنك الحصول على الترخيص من موقع Aspose.

### س: هل يمكنني استخدام Aspose.Tasks for Java في تطبيقاتي الويب؟
نعم، يمكنك دمج Aspose.Tasks for Java في تطبيقات الويب الخاصة بك لإدارة موارد المشروع بشكل ديناميكي.

### س: أين يمكنني العثور على دعم إضافي لـ Aspose.Tasks for Java؟
يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على أي مساعدة تقنية أو استفسارات بخصوص المكتبة.

## الأسئلة المتكررة
**س: كيف أحفظ المشروع بعد إضافة التعيينات؟**  
ج: استدعِ `project.save("MyProject.mpp", SaveFileFormat.MPP);` لحفظ التغييرات.

**س: هل يمكنني تعيين نفس المورد لعدة مهام؟**  
ج: نعم، فقط استدعِ `project.getResourceAssignments().add(anotherTask, rsc);` لكل مهمة إضافية.

**س: هل يمكن تحديد العمل أو التكلفة لتعيين؟**  
ج: بالطبع – استخدم `assn.setWork(work);` أو `assn.setCost(cost);` بعد إنشاء التعيين.

## الخاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية **إضافة مورد إلى المشروع**، وإنشاء المهام، و**تعيين الموارد للمهام** باستخدام Aspose.Tasks for Java. باتباع هذه الخطوات، يمكنك إدارة تخصيصات الموارد بفعالية في تطبيقات إدارة المشاريع الخاصة بك والاستفادة من القوة الكاملة لواجهات برمجة تطبيقات تخصيص الموارد Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**آخر تحديث:** 2026-01-05  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

---