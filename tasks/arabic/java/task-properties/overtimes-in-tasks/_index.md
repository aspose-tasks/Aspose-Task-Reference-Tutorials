---
date: 2026-02-23
description: تعرّف على كيفية إدارة العمل الإضافي في مهام المشروع باستخدام Aspose.Tasks
  للغة Java، بما في ذلك كيفية حساب تكلفة العمل الإضافي وتبسيط تتبع الموارد.
linktitle: Overtimes in Tasks with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية إدارة العمل الإضافي في المهام باستخدام Aspose.Tasks
url: /ar/java/task-properties/overtimes-in-tasks/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إدارة الوقت الإضافي في المهام باستخدام Aspose.Tasks

## Introduction
إذا كنت تبحث **عن كيفية إدارة الوقت الإضافي** في ملف Microsoft Project، فقد وجدت المكان المناسب. في هذا البرنامج التعليمي سنظهر لك كيف يتيح لك Aspose.Tasks for Java قراءة وتعديل والإبلاغ عن الخصائص المتعلقة بالوقت الإضافي لكل مهمة، حتى تتمكن من الحفاظ على دقة الجدول الزمني والميزانية.  

## Quick Answers
- **ماذا يعني “الوقت الإضافي” في المشروع؟** ساعات عمل إضافية تتجاوز السعة العادية للمورد.  
- **أي فئة API توفر بيانات الوقت الإضافي؟** `Task` مع مجموعة حقول `Tsk` (مثال: `Tsk.OVERTIME_COST`).  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** نعم، يلزم وجود ترخيص مؤقت أو كامل لـ Aspose.Tasks للاستخدام في الإنتاج.  
- **هل يمكنني حساب تكلفة الوقت الإضافي تلقائيًا؟** بالتأكيد – استرجع `Tsk.OVERTIME_COST` وطبق منطق معدل التكلفة الخاص بك.  
- **هل هذا متوافق مع Java 17؟** نعم، يدعم Aspose.Tasks for Java Java 8 والإصدارات الأحدث.

## What is Overtime Management in Project Tasks?
إدارة الوقت الإضافي تعني تتبع العمل الإضافي والتكلفة التي تحدث عندما يتجاوز الموارد وقت عملهم الطبيعي. يساعد التقاط هذه البيانات بدقة على توقع الميزانيات، تعديل الجداول، وتقرير صحة المشروع بشكل واقعي.

## Why Use Aspose.Tasks for Overtime?
* **لا حاجة لـ Microsoft Project** – العمل مباشرةً مع ملفات .MPP.  
* **الوصول الكامل إلى حقول الوقت الإضافي** – التكلفة، العمل، ونسب الإنجاز معروضة عبر تعداد `Tsk`.  
* **تحكم برمجي** – يمكنك قراءة، تعديل، أو حساب تكلفة الوقت الإضافي دون خطوات يدوية في الواجهة.

## Prerequisites
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات التالية:
- بيئة تطوير Java: تأكد من إعداد بيئة تطوير Java على جهازك.  
- Aspose.Tasks for Java: قم بتحميل وتثبيت مكتبة Aspose.Tasks. يمكنك العثور على المكتبة ووثائقها [هنا](https://reference.aspose.com/tasks/java/).  
- ملف المشروع: حضّر ملف مشروع (مثال: TaskOvertimes.mpp) للعمل معه خلال البرنامج التعليمي.

## Import Packages
في مشروع Java الخاص بك، استورد الحزم اللازمة من Aspose.Tasks للاستفادة من وظائفها. أضف عبارات الاستيراد التالية:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Step 1: Create a New Project
إنشاء مشروع جديد (أو تحميل مشروع موجود) هو الخطوة الأولى لأي تحليل. هذا أيضًا يحقق الكلمة المفتاحية الثانوية **create new project**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```

## Step 2: Iterate Through Tasks and Print Overtime Details
الآن سنستعرض كل مهمة من المستوى الأعلى، نعرض معلومات الوقت الإضافي الخاصة بها، ونوضح كيفية **حساب تكلفة الوقت الإضافي** بقراءة الحقل `OVERTIME_COST`.

```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    // Set percent complete
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```

> **نصيحة:** قيمة `OVERTIME_COST` يتم حسابها بالفعل بواسطة Aspose.Tasks بناءً على معدل الوقت الإضافي للمورد. إذا كنت بحاجة إلى حساب مخصص، اضرب `OVERTIME_WORK` في المعدل الخاص بك وقم بتحديث الحقل باستخدام `tsk.set(Tsk.OVERTIME_COST, yourValue);`.

## Common Issues and Solutions
| المشكلة | الحل |
|-------|----------|
| **قيم فارغة لحقول الوقت الإضافي** | تأكد من أن ملف .MPP المصدر يحتوي فعليًا على بيانات الوقت الإضافي؛ وإلا ستعيد الحقول `null`. |
| **تكلفة غير صحيحة بعد التعديل** | بعد تغيير عمل أو تكلفة الوقت الإضافي، استدعِ `project.save()` لحفظ التغييرات. |
| **الترخيص غير موجود** | ضع ملف `Aspose.Tasks.lic` في جذر المشروع أو اضبط الترخيص برمجياً قبل تحميل المشروع. |

## Frequently Asked Questions

**س: هل Aspose.Tasks مناسب لإدارة المشاريع على نطاق واسع؟**  
ج: نعم، تم تصميم Aspose.Tasks للتعامل مع مشاريع بأحجام مختلفة، من المبادرات الصغيرة إلى البرامج الكبيرة والمعقدة.

**س: هل يمكنني دمج Aspose.Tasks مع أطر Java أخرى؟**  
ج: بالتأكيد! يتكامل Aspose.Tasks بسلاسة مع Spring و Jakarta EE وغيرها من بيئات Java، مما يعزز مرونته.

**س: هل هناك أية اعتبارات ترخيص لاستخدام Aspose.Tasks؟**  
ج: نعم، يمكنك العثور على تفاصيل الترخيص والحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني طلب المساعدة أو مناقشة الاستفسارات المتعلقة بـ Aspose.Tasks؟**  
ج: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للتفاعل مع المجتمع وطلب الدعم.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟**  
ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

**س: كيف أحسب تكلفة الوقت الإضافي لمورد معين؟**  
ج: استخرج معدل الوقت الإضافي للمورد، اضربه في `OVERTIME_WORK` (بالساعات)، وعيّن النتيجة مرة أخرى في `OVERTIME_COST` إذا كنت تحتاج إلى حساب مخصص.

## Conclusion
يبسط Aspose.Tasks for Java **كيفية إدارة الوقت الإضافي** في مهام المشروع، حيث يمنح المطورين وصولًا برمجيًا مباشرًا إلى تكلفة الوقت الإضافي والعمل والنسب المئوية للتقدم. باتباع هذا الدليل يمكنك تحميل مشروع، قراءة تفاصيل الوقت الإضافي، تعديل النسب، وحتى حساب تكاليف الوقت الإضافي المخصصة—كل ذلك دون الحاجة لفتح Microsoft Project.

---

**آخر تحديث:** 2026-02-23  
**تم الاختبار مع:** Aspose.Tasks for Java (الإصدار الأخير)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}