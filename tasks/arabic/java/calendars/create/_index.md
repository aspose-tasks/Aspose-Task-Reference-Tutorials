---
date: 2026-08-03
description: تعلم كيفية إنشاء تقويم ms project، إضافة calendar إلى project، وحفظ project
  كملف XML باستخدام Aspose.Tasks for Java.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: إضافة calendar إلى project باستخدام Aspose.Tasks
og_description: إنشاء تقويم ms project برمجيًا باستخدام Aspose.Tasks for Java. إضافة
  calendars، تخصيص schedules، وتصدير إلى XML في دقائق.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: إنشاء تقويم ms project باستخدام Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: إنشاء تقويم ms project باستخدام Aspose.Tasks for Java
url: /ar/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء تقويم ms project باستخدام Aspose.Tasks for Java

## المقدمة
في سير عمل إدارة المشاريع الحديثة، القدرة على **إنشاء تقويم ms project** برمجياً يمكن أن توفر ساعات من التحرير اليدوي. توفر Aspose.Tasks for Java واجهة برمجة تطبيقات نظيفة وآمنة من حيث النوع للتعامل مع ملفات Microsoft Project دون الحاجة لفتح العميل المكتبي. في هذا الدرس ستتعلم كيفية إضافة تقويم، وكيفية إنشاء تقويم MS Project، وكيفية حفظ المشروع كملف XML—كل ذلك ببضع أسطر من كود Java.

## الإجابات السريعة
- **ماذا يعني “إنشاء تقويم ms project”؟**  
  يعني إدراج تعريف جديد لوقت العمل (تقويم) في ملف Microsoft Project عبر الكود.  
- **أي مكتبة تتعامل مع ذلك؟**  
  توفر Aspose.Tasks for Java الفئة `Calendar` وحاوية `Project` لإدارة التقويمات.  
- **هل أحتاج إلى ترخيص؟**  
  رخصة تقييم مؤقتة تعمل للاختبار؛ يلزم الحصول على ترخيص كامل للاستخدام في الإنتاج.  
- **هل يمكنني حفظ الملف كـ XML؟**  
  نعم—استخدم `SaveFileFormat.Xml` لتصدير المشروع كملف XML.  
- **ما هي المتطلبات المسبقة؟**  
  Java JDK 8+ ومكتبة Aspose.Tasks for Java JAR في مسار الفئات الخاص بك.

## ما هو إنشاء تقويم ms project؟
إنشاء تقويم MS Project يعني إضافة تعريف تقويم جديد برمجياً إلى ملف مشروع، وتحديد أيام العمل، والاستثناءات، وساعات العمل اليومية، ثم تعيين ذلك التقويم للمهام أو الموارد أو المشروع بأكمله بحيث تحترم حسابات الجدول الزمني الوقت المحدد للعمل.

## لماذا تستخدم Aspose.Tasks for Java لإضافة تقويم إلى المشروع؟
يجب عليك استخدام Aspose.Tasks for Java لأنه يوفر واجهة برمجة تطبيقات آمنة من حيث النوع تعمل دون الحاجة إلى تثبيت Microsoft Project، يدعم جميع إصدارات Project الرئيسية (2007‑2021، أكثر من 5 إصدارات)، ويمكنه التصدير إلى XML، MPP، وأكثر من **10** صيغ أخرى، مما يتيح إنشاء تقويمات جماعية تلقائيًا على أي خادم.

## المتطلبات المسبقة
- **Java Development Kit (JDK) 8 أو أحدث** مثبت ومُكوَّن.  
- **مكتبة Aspose.Tasks for Java** – قم بتنزيلها من [الموقع الرسمي](https://releases.aspose.com/tasks/java/) وأضف الـ JAR إلى مسار الفئات في مشروعك.  
- بيئة تطوير متكاملة (IDE) أو أداة بناء (Maven/Gradle) حسب اختيارك.

## دليل خطوة بخطوة

### الخطوة 1: استيراد حزمة Aspose.Tasks المطلوبة
أولاً، استورد فئات Aspose.Tasks إلى النطاق حتى تتمكن من العمل مع المشاريع والتقويمات.

```java
import com.aspose.tasks.*;
```

### الخطوة 2: تعيين مسار دليل البيانات
حدد المكان الذي سيُكتب فيه ملف المشروع المُولد. استبدل العنصر النائب بمسار مطلق أو نسبي على جهازك.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 3: إنشاء مثيل Project جديد
`Project` هي الفئة الأساسية التي تمثل ملف Microsoft Project في الذاكرة.

```java
Project prj = new Project();
```

### الخطوة 4: تعريف التقويمات التي تريد إضافتها
`Calendar` يحدد جدولًا بأيام العمل، والاستثناءات، وأوقات العمل لمشروع.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **نصيحة احترافية:** بعد إضافة تقويم، يمكنك تخصيص أيام العمل باستخدام `cal1.getWeekDays().add(...)` وتحديد ساعات العمل اليومية باستخدام `cal1.getBaseCalendar().setWorkingTime(...)`.

### الخطوة 5: حفظ المشروع (حفظ المشروع كملف XML)
`SaveFileFormat.Xml` يخبر Aspose.Tasks بكتابة المشروع بصيغة XML.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### الخطوة 6: عرض رسالة إكمال
أخبر المستخدم أن العملية انتهت بنجاح.

```java
System.out.println("Process completed Successfully");
```

باتباع هذه الخطوات الست المختصرة، تكون قد **أضفت تقويمًا إلى مشروع** وحفظت النتيجة كملف XML.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **`NullPointerException` على `prj.getCalendars()`** | كائن Project لم يتم تهيئته بشكل صحيح. | تأكد من استدعاء `new Project()` قبل الوصول إلى التقويمات. |
| **الملف غير موجود عند الحفظ** | `dataDir` يشير إلى مجلد غير موجود. | أنشئ المجلد أولاً أو استخدم مسارًا مطلقًا. |
| **اسم التقويم يظهر كـ “no info”** | تم استخدام أسماء مؤقتة في العينة. | استبدلها بأسماء ذات معنى تعكس الجدول الزمني (مثال: “تقويم العطلات الأمريكية”). |
| **لا يمكن فتح ملف XML المحفوظ في MS Project** | استخدام نسخة قديمة من Aspose.Tasks. | قم بالتحديث إلى أحدث إصدار من Aspose.Tasks for Java. |

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks التعامل مع تقويمات معقدة تحتوي على استثناءات متعددة؟**  
ج: نعم – بعد إضافة تقويم يمكنك تعريف الاستثناءات، وساعات العمل، وأيام غير العمل باستخدام فئتي `WeekDay` و `Exception`.

**س: هل يمكن تعيين التقويم الجديد لمهام محددة؟**  
ج: بالتأكيد. استرجع مهمة عبر `prj.getRootTask().getChildren().add("Task Name")` ثم عيّن `task.set(Tsk.CALENDAR, cal3);`.

**س: هل تدعم المكتبة الحفظ بصيغ أخرى مثل MPP؟**  
ج: نعم. استبدل `SaveFileFormat.Xml` بـ `SaveFileFormat.Mpp` أو `SaveFileFormat.P6` حسب الحاجة؛ تدعم Aspose.Tasks **12** صيغة إخراج.

**س: هل أحتاج إلى ترخيص لبناءات التطوير؟**  
ج: رخصة تقييم مؤقتة كافية للاختبار؛ يلزم الحصول على ترخيص كامل للنشر في بيئات الإنتاج.

**س: أين يمكنني الحصول على مساعدة إذا واجهت مشاكل؟**  
ج: منتدى مجتمع Aspose.Tasks هو مصدر ممتاز: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**آخر تحديث:** 2026-08-03  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث إصدار وقت الكتابة)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## الدروس ذات الصلة

- [كيفية تعريف أيام الأسبوع في تقويمات MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [كيفية تعيين تقويم المشروع في Java باستخدام Aspose.Tasks](/tasks/java/calendars/properties/)
- [إنشاء استثناءات تقويم مخصصة باستخدام Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}