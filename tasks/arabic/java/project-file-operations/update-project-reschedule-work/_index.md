---
date: 2025-12-23
description: تعلم كيفية تحديث ملفات MS Project وإعادة جدولة العمل غير المكتمل باستخدام
  Aspose.Tasks للـ Java. كما يمكنك الاطلاع على كيفية حفظ ملف XML الخاص بـ MS Project.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: تحديث MS Project وإعادة جدولة العمل باستخدام Aspose.Tasks
url: /ar/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحديث MS Project وإعادة جدولة العمل باستخدام Aspose.Tasks

## Introduction
Microsoft Project هو أداة إدارة مشاريع واسعة الاستخدام تساعد الفرق على التخطيط والمتابعة وتسليم العمل في الوقت المحدد. عندما تتغير الجداول، غالبًا ما تحتاج إلى **تحديث ملفات MS Project** برمجيًا — وضع علامة على العمل كمنجز، نقل المهام المتبقية، والحفاظ على خط الأساس للمشروع دقيقًا. Aspose.Tasks for Java يزودك بواجهة برمجة تطبيقات نظيفة وآمنة من النوع للقيام بذلك دون فتح الواجهة الرسومية. في هذا الدرس ستتعرف على كيفية تحديث مشروع، وضع علامة على العمل كمنتهي حتى تاريخ معين، ثم **كيفية إعادة جدولة عمل MS Project** الذي لا يزال معلقًا.

## Quick Answers
- **ماذا يعني “تحديث MS Project”؟** يضع علامة على المهام كمنجزة حتى تاريخ معين ويكتب التغييرات مرة أخرى إلى الملف.  
- **هل يمكنني إعادة جدولة العمل المتبقي تلقائيًا؟** نعم — استخدم `rescheduleUncompletedWorkToStartAfter` لدفع المهام غير المكتملة إلى الأمام.  
- **ما هو تنسيق الملف الذي يتم حفظه؟** الأمثلة تحفظ المشروع كملف XML (`SaveFileFormat.Xml`).  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** النسخة التجريبية المجانية تكفي للتطوير؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما نسخة Java المطلوبة؟** JDK 8 أو أعلى.

## What is “update MS Project” in code?
تحديث مشروع يعني تغيير تواريخ المهام أو مدتها أو نسب إكمالها برمجيًا وحفظ هذه التغييرات. Aspose.Tasks يوفر طرقًا مثل `updateProjectWorkAsComplete` التي تطبق التغييرات بناءً على تاريخ مرجعي `Date` تقدمه.

## Why use Aspose.Tasks for Java to update MS Project?
- **لا يعتمد على واجهة المستخدم** – أتمتة تغييرات جماعية عبر العديد من الملفات.  
- **دقة عالية** – المكتبة تحافظ على جميع بيانات Project الأصلية (الموارد، التقويمات، الحقول المخصصة).  
- **متعدد المنصات** – تشغيل نفس الكود على Windows أو Linux أو macOS.  
- **حفظ MS Project بصيغة XML** – يمكنك تصدير المشروع المحدث إلى صيغة XML المدعومة على نطاق واسع للأدوات اللاحقة.

## Prerequisites
1. تثبيت Java Development Kit (JDK).  
2. مكتبة Aspose.Tasks for Java – حمّلها من [here](https://releases.aspose.com/tasks/java/).  
3. إلمام أساسي بصياغة Java ومفاهيم البرمجة الكائنية.

## Import Packages
First, import the necessary Aspose.Tasks classes and Java utilities:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Set up the Project
Create a new `Project` instance, define a few sample tasks, set their durations, and establish dependencies. Then persist the initial state so you can see the before‑and‑after effect.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Step 2: Update Project Work
Mark work as complete up to a specific cutoff date. This is the core of **update MS Project**—the API will adjust task progress and dates automatically.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Step 3: Reschedule Uncompleted Work
After marking completed work, you often need to push the remaining tasks forward. The following call moves any unfinished work to start after the same cutoff date, effectively **how to reschedule MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
| المشكلة | السبب | الحل |
|-------|--------|-----|
| المهام لا تظهر تواريخ محدثة | تم حفظ المشروع بصيغة مختلفة (مثال: `.mpp`) | استخدم `SaveFileFormat.Xml` للحفاظ على بنية XML. |
| `updateProjectWorkAsComplete` يبدو أنه لا يفعل شيئًا | تاريخ المرجع أبكر من بدء المشروع | تأكد من أن تاريخ `Calendar` ضمن جدول المشروع. |
| تداخل المهام المعاد جدولتها | لا يوجد تقويم أو تسوية موارد مطبقة | طبق تقويم `Project` أو استخدم `Task.setStart` يدويًا بعد إعادة الجدولة. |

## Frequently Asked Questions (Extended)

**س: هل يمكن لـ Aspose.Tasks for Java التعامل مع هياكل مشاريع معقدة؟**  
ج: نعم، Aspose.Tasks for Java يوفر واجهات برمجة تطبيقات قوية لإدارة المهام والاعتمادات والموارد وعناصر المشروع الأخرى بكفاءة.

**س: هل تتوفر نسخة تجريبية من Aspose.Tasks for Java؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من [here](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.Tasks for Java؟**  
ج: يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) لأي مساعدة أو استفسارات.

**س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks for Java؟**  
ج: نعم، التراخيص المؤقتة متاحة للشراء [here](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني العثور على وثائق مفصلة لـ Aspose.Tasks for Java؟**  
ج: يمكنك الرجوع إلى الوثائق [here](https://reference.aspose.com/tasks/java/) للحصول على أدلة شاملة ومراجع API.

## Conclusion
في هذا الدرس استعرضنا العملية الكاملة **لتحديث ملفات MS Project**، وضع علامة على العمل كمنجز، ثم **كيفية إعادة جدولة مهام MS Project** التي لا تزال غير مكتملة. بحفظ المشروع بصيغة XML تحتفظ بالتوافق مع الأدوات الأخرى وتضمن سجل تدقيق واضح للتغييرات. استخدم هذه الأنماط لأتمتة تعديل الجداول في محافظ المشاريع الكبيرة، أو دمجها مع خطوط أنابيب CI، أو بناء لوحات تقارير مخصصة.

---

**آخر تحديث:** 2025-12-23  
**تم الاختبار باستخدام:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}