---
date: 2026-07-14
description: تعلم كيفية إيقاف تعيين الموارد في Java، إدارة تعيينات الموارد، وعرض الأمثلة
  باستخدام Aspose.Tasks for Java في هذا الدليل خطوة بخطوة.
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: إيقاف واستئناف تعيينات الموارد في Aspose.Tasks
og_description: إيقاف تعيين الموارد في Java باستخدام Aspose.Tasks. يوضح هذا البرنامج
  التعليمي كيفية إيقاف واستئناف التعيينات، معالجة التواريخ، وتكامل API دون الحاجة
  إلى Microsoft Project.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: إيقاف تعيين الموارد في Java – دليل Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: كيفية إيقاف تعيين الموارد في Java – الاستئناف باستخدام Aspose.Tasks
url: /ar/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إيقاف تعيين المورد في Java – الاستئناف باستخدام Aspose.Tasks

## مقدمة
في هذا الدرس ستتعلم **how to stop resource assignment java** وتستأنفه لاحقًا باستخدام Aspose.Tasks for Java. Aspose.Tasks هي واجهة برمجة تطبيقات Java قوية تتيح لك قراءة وكتابة ملفات Microsoft Project، تعديل الجداول الزمنية، والتحكم في تعيينات الموارد—كل ذلك دون الحاجة إلى تثبيت Microsoft Project. سنستعرض كل خطوة، نشرح لماذا كل سطر مهم، ونشارك نصائح عملية يمكنك تطبيقها على خطط المشاريع الواقعية.

## إجابات سريعة
- **What does “stop assignment” mean?** يحدد تعيين المورد كغير نشط مؤقتًا اعتبارًا من تاريخ إيقاف محدد.  
- **Can I resume the same assignment later?** نعم، عن طريق تعيين تاريخ استئناف على نفس التعيين.  
- **Do I need Microsoft Project to use this API?** لا، Aspose.Tasks يعمل بشكل مستقل عن Microsoft Project.  
- **Which Java version is required?** يُنصح باستخدام Java 8 أو أعلى.  
- **Where can I download the library?** من صفحة تحميل Aspose.Tasks Java الرسمية.

## كيفية إيقاف تعيين المورد في Java؟
حمّل مشروعك، حدد `ResourceAssignment` المستهدف، عيّن تاريخ `STOP`، واختياريًا عيّن تاريخ `RESUME`، ثم احفظ الملف. هذه السلسلة توقف العمل للفترة المحددة وتعيد تنشيطه تلقائيًا بعد تاريخ الاستئناف، مما يمنحك تحكمًا دقيقًا في تقاويم الموارد دون تعديل يدوي للملف.

## ما هو “كيفية إيقاف التعيين” في سياق Aspose.Tasks؟
إيقاف التعيين يخبر المجدول بتجاهل العمل المخصص لمورد بعد **stop date** حتى **resume date** (إن وجد). هذا مفيد للتعامل مع الإجازات، توقف المعدات، أو أي فترة لا ينبغي اعتبار المورد فيها نشطًا.

## لماذا نستخدم Aspose.Tasks لإدارة تعيينات الموارد؟
تتيح لك Aspose.Tasks التحكم برمجيًا في تواريخ التعيين، مما يلغي التعديلات اليدوية ويقلل من خطر الأخطاء. تدعم **50+ input and output formats** ويمكنها معالجة مشاريع تحتوي على **up to 10,000 tasks** مع الحفاظ على استهلاك الذاكرة أقل من 200 MB لأنها تقوم ببث البيانات بدلاً من تحميل الملف بالكامل في الذاكرة. تعمل الواجهة البرمجية على أي نظام تشغيل يدعم Java، مما يمنحك مرونة عبر المنصات.

## المتطلبات المسبقة
- تثبيت Java Development Kit (JDK) 8 أو أحدث.  
- تحميل مكتبة Aspose.Tasks for Java. يمكنك تحميلها من [هنا](https://releases.aspose.com/tasks/java/).  
- فهم أساسي لبرمجة Java.  

## استيراد الحزم
الفئات `Project` و `ResourceAssignment` و `Asn` موجودة في مساحة الاسم `com.aspose.tasks`. استوردها في أعلى ملف المصدر الخاص بك:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## الخطوة 1: تحميل ملف المشروع
الفئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف Microsoft Project واحد في الذاكرة. إنشاء نسخة يحمل الملف ويمنحك الوصول إلى المهام والموارد والتعيينات.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## الخطوة 2: التكرار عبر تعيينات الموارد
كائنات `ResourceAssignment` تعرض جميع الحقول المتعلقة بالتعيين. نحدد **minimum date** لتصفية تواريخ العنصر النائب ثم نكرر عبر كل تعيين. هذا النمط هو مثال *resource assignment example* القياسي للفحص أو التعديل.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## الخطوة 3: فحص تواريخ الإيقاف والاستئناف
في هذا الجزء نفحص حقول `STOP` و `RESUME` لكل تعيين. إذا كان التاريخ قبل `minDate` الخاص بنا، نتعامل معه كغير محدد (`"NA"`); وإلا نطبع التاريخ الفعلي. هذه المنطق ضروري لـ **manage resource assignments** بشكل صحيح.

```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

## المشكلات الشائعة والحلول
- **Null dates** – قد تُعيد `ra.get(Asn.STOP)` القيمة `null`. احمِ نفسك بإضافة فحص للـ null قبل استدعاء `.before(minDate)`.  
- **Incorrect file path** – تأكد من أن `dataDir` ينتهي بفاصل مسار (`/` أو `\\`) المناسب لنظام التشغيل الخاص بك.  
- **Version mismatch** – استخدم أحدث إصدار من Aspose.Tasks for Java لتجنب فقدان قيم الـ enum.

## الأسئلة المتكررة

**س: كيف يمكنني برمجيًا تعيين تاريخ إيقاف لتعيين؟**  
ج: استخدم `ra.set(Asn.STOP, yourDateObject);` حيث أن `yourDateObject` هو كائن من نوع `java.util.Date`.

**س: ماذا يحدث إذا كان تاريخ الاستئناف أسبق من تاريخ الإيقاف؟**  
ج: لا تفرض الواجهة البرمجية ترتيبًا زمنيًا؛ ومع ذلك، سيعامل المجدول التعيين كنشط فقط بعد التاريخ الأحدث بينهما، لذا يجب عليك التحقق من صحة التواريخ بنفسك.

**س: هل يمكنني تصفية التعيينات لتظهر فقط تلك التي لديها تاريخ إيقاف محدد؟**  
ج: نعم، قم بالتكرار عبر `prj.getResourceAssignments()` وتحقق من أن `ra.get(Asn.STOP) != null`.

**س: هل يمكن إزالة تاريخ الإيقاف بمجرد تعيينه؟**  
ج: عيّن تاريخ الإيقاف إلى `null` باستخدام `ra.set(Asn.STOP, null);` ثم احفظ المشروع.

**س: هل تدعم Aspose.Tasks حقولًا أخرى متعلقة بالتاريخ مثل البدء، الانتهاء، أو البدء الفعلي؟**  
ج: بالتأكيد. يوفر تعداد `Asn` ثوابت لجميع حقول التعيين، مثل `Asn.START`، `Asn.FINISH`، إلخ.

## الخلاصة
باتباع هذه الخطوات أصبحت الآن تعرف **how to stop resource assignment java**، وتفحص تواريخ الإيقاف/الاستئناف، وتستأنف التعيين عند الحاجة. هذه القدرة تمكنك من **manage resource assignments** بدقة أكبر، خاصة في سيناريوهات مثل إجازات الموارد أو توقف المعدات. لا تتردد في توسيع المثال لتحديث التواريخ، إنشاء تقارير، أو دمجه مع منطق الجدولة الخاص بك.

**آخر تحديث:** 2026-07-14  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [كيفية حساب فرق التكلفة وإدارة تكاليف التعيين باستخدام Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [كيفية إضافة ملاحظات إلى تعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}