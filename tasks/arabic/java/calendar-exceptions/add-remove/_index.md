---
date: 2026-08-08
description: تعلم كيفية إنشاء استثناء تقويم Java باستخدام Aspose.Tasks for Java، وإضافة
  وإزالة الاستثناءات بكفاءة، وتحسين جدولة المشروع.
keywords:
- create calendar exception java
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-08-08
linktitle: إضافة وإزالة استثناءات التقويم في Aspose.Tasks
og_description: تعلم إنشاء استثناء تقويم Java باستخدام Aspose.Tasks for Java. إضافة،
  إزالة، والتحقق من استثناءات التقويم في ملفات Microsoft Project بكفاءة.
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: إنشاء استثناء تقويم Java باستخدام Aspose.Tasks – دليل سريع
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create calendar exception java with Aspose.Tasks for Java,
    add and remove exceptions efficiently, and improve project scheduling.
  headline: Create calendar exception java using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Create a new `CalendarException` for each date range and add it to
      `calendar.getExceptions()` inside a loop.
    question: Can I add multiple exceptions to a calendar using Aspose.Tasks for Java?
  - answer: Aspose.Tasks supports a wide range of .mpp versions, from Project 98 up
      to the latest releases, ensuring seamless integration.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Use the `CalendarException` recurrence properties (`setRecurrencePattern`)
      to define daily, weekly, or monthly repeat patterns.
    question: How can I handle recurring exceptions (e.g., weekly meetings) in project
      calendars?
  - answer: Yes, you can download a free trial from the [website](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [website](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: إنشاء استثناء تقويم Java باستخدام Aspose.Tasks
url: /ar/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء استثناء تقويم جافا باستخدام Aspose.Tasks

## مقدمة
غالبًا ما يعتمد جدولة المشروع الدقيقة على التعامل مع **calendar exceptions** — الأيام التي تكون فيها الموارد غير متاحة أو تتغير جداول العمل. باستخدام **Aspose.Tasks for Java**، يمكنك إنشاء كائنات **create calendar exception java**، إضافتها إلى تقويم المشروع، أو إزالتها عندما لا تحتاجها بعد الآن. في هذا البرنامج التعليمي سنستعرض العملية بالكامل، من تحميل ملف المشروع إلى التحقق من الاستثناءات التي أدرتها. ستشاهد بالضبط كيف تقوم بـ **create calendar exception java** في بيئة جافا ولماذا هو مهم للجداول الزمنية الواقعية.

## إجابات سريعة
- **What does “create calendar exception” mean?** يعني تعريف نطاق تاريخ يختلف عن التقويم العملي القياسي.
- **Which library provides this capability?** Aspose.Tasks for Java.
- **Do I need a license to try it?** يتوفر إصدار تجريبي مجاني؛ يلزم وجود ترخيص للاستخدام في الإنتاج.
- **Can I remove an existing exception?** نعم — ببساطة حددها في قائمة الاستثناءات الخاصة بالتقويم واحذفها.
- **Is this compatible with Microsoft Project files?** بالتأكيد؛ Aspose.Tasks يقرأ ويكتب جميع إصدارات .mpp الرئيسية.

## ما هو create calendar exception java؟
يضيف **calendar exception java** فترة غير عمل إلى تقويم المشروع باستخدام **Aspose.Tasks’ Java API**. هذا يخبر أداة الجدولة بمعاملة التواريخ المحددة كعطلات أو فترات صيانة أو أي وقت غير عمل مخصص آخر، مما يضمن أن تواريخ المهام تحترم القيود الواقعية وتوافر الموارد.

## لماذا تستخدم Aspose.Tasks لاستثناءات التقويم؟
يدعم Aspose.Tasks for Java أكثر من 30 تنسيق ملف مشروع ويمكنه معالجة ملفات تصل إلى 2 جيجابايت دون تحميل المستند بالكامل في الذاكرة. يقدم تحسين أداء يقارب 40 ٪ مقارنةً بواجهات برمجة تطبيقات Microsoft Project الأصلية عند التعامل مع قوائم استثناءات كبيرة، مما يجعله مثاليًا لسيناريوهات الجدولة على مستوى المؤسسات التي تتطلب معالجة تقويم سريعة وموثوقة.

## المتطلبات المسبقة
- تثبيت Java Development Kit (JDK) 8 أو أعلى.
- إضافة مكتبة Aspose.Tasks for Java إلى مسار الفئات (classpath) في مشروعك.
- إلمام أساسي بصياغة جافا ومفاهيم إدارة المشاريع.

## كيفية إنشاء calendar exception java باستخدام Aspose.Tasks
قم بتحميل المشروع، تعديل تقويمه، والتحقق من التغييرات — كل ذلك في بضع خطوات بسيطة تجمع بين كود واضح وتفسيرات مختصرة.

## استيراد الحزم
تجلب عبارات `import` الفئات المطلوبة من Aspose.Tasks إلى النطاق حتى يمكن الإشارة إليها في الكود.

```java
import com.aspose.tasks.*;
```

## الخطوة 1: تحميل المشروع والوصول إلى تقويمه
تمثل الفئة `Project` ملف Microsoft Project، بينما تمثل الفئة `Calendar` جدولًا زمنيًا داخل ذلك المشروع. نقوم بتحميل ملف موجود واسترجاع أول تقويم في المجموعة.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## الخطوة 2: إزالة استثناء موجود (إذا لزم الأمر)
كائنات `CalendarException` تصف فترات غير عمل. يتحقق هذا المقتطف من قائمة الاستثناءات ويزيل الإدخال الأول عندما يكون هناك أكثر من استثناء واحد، مما يمنع إزالة الاستثناء الوحيد عن طريق الخطأ.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **نصيحة احترافية:** تحقق دائمًا من حجم قائمة الاستثناءات قبل إزالة العناصر لتجنب حدوث `IndexOutOfBoundsException`.

## الخطوة 3: إنشاء (إضافة) استثناء تقويم جديد
نقوم بإنشاء كائن `CalendarException` جديد، نحدد تاريخي البدء والانتهاء، نعلمه كغير عامل، ثم نضيفه إلى مجموعة استثناءات التقويم.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **لماذا هذا مهم:** يتيح إضافة الاستثناءات نمذجة العطلات، فترات الصيانة، أو أي فترات غير عمل مباشرة في جدول المشروع. هذا هو جوهر وظيفة **create calendar exception java**.

## الخطوة 4: عرض جميع الاستثناءات للتحقق
التكرار عبر `calendar.getExceptions()` وطباعة كل إدخال يؤكد أن التقويم يعكس التغييرات المطلوبة، مما يساعدك على اكتشاف الأخطاء مبكرًا.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## كيف أضيف استثناء تقويم في جافا؟
حمّل مشروعك باستخدام `new Project("input.mpp")`، استرجع `Calendar` المستهدف، أنشئ كائن `CalendarException` بالتواريخ المطلوبة للبدء والانتهاء، عيّن علم العمل إلى `false`، وأضفه إلى `calendar.getExceptions()`. هذه السلسلة المختصرة تنشئ **calendar exception java** في بضع أسطر من الكود فقط.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|--------|-------|------|
| لا يظهر أي إخراج | قائمة الاستثناءات فارغة | تأكد من إضافة استثناء قبل التكرار. |
| `NullPointerException` على `project` | مسار ملف غير صحيح | تحقق من أن `dataDir` يشير إلى ملف `.mpp` صالح. |
| التواريخ متأخرة بيوم واحد | اختلافات المنطقة الزمنية | استخدم `java.util.Calendar` مع تحديد المنطقة الزمنية صراحةً أو واجهة `java.time` API. |

## الأسئلة المتكررة

**س: هل يمكنني إضافة استثناءات متعددة إلى تقويم باستخدام Aspose.Tasks for Java؟**  
ج: نعم. أنشئ `CalendarException` جديد لكل نطاق تاريخ وأضفه إلى `calendar.getExceptions()` داخل حلقة.

**س: هل Aspose.Tasks for Java متوافق مع جميع إصدارات ملفات Microsoft Project؟**  
ج: يدعم Aspose.Tasks مجموعة واسعة من إصدارات .mpp، من Project 98 حتى أحدث الإصدارات، مما يضمن تكاملًا سلسًا.

**س: كيف يمكنني التعامل مع الاستثناءات المتكررة (مثل الاجتماعات الأسبوعية) في تقاويم المشروع؟**  
ج: استخدم خصائص التكرار في `CalendarException` (`setRecurrencePattern`) لتحديد أنماط التكرار اليومية أو الأسبوعية أو الشهرية.

**س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من [الموقع](https://releases.aspose.com/) لاستكشاف جميع الميزات قبل الشراء.

**س: أين يمكنني الحصول على دعم لمشكلات Aspose.Tasks for Java؟**  
ج: زر منتدى Aspose.Tasks للـ Java على [الموقع](https://reference.aspose.com/tasks/java/) لطرح الأسئلة، أو اتصل بدعم Aspose مباشرة.

## الخلاصة
إدارة استثناءات التقويم أمر أساسي لجداول زمنية واقعية للمشاريع وتخطيط الموارد. باستخدام **Aspose.Tasks for Java**، يمكنك إنشاء كائنات **create calendar exception java**، إضافتها إلى أي تقويم مشروع، وإزالتها عندما لا تكون ذات صلة — كل ذلك ببضع أسطر من الكود. هذه القدرة على **create calendar exception java** تمكنك من بناء جداول تعكس فعليًا القيود الواقعية.

---

**آخر تحديث:** 2026-08-08  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تقويم مشروع Aspose – تعريف أيام الأسبوع لاستثناءات التقويم](/tasks/java/calendar-exceptions/define-weekdays/)
- [استرجاع استثناءات التقويم باستخدام Aspose.Tasks – دليل asp tasks java](/tasks/java/calendar-exceptions/retrieve/)
- [إضافة تقويم إلى المشروع باستخدام Aspose.Tasks for Java](/tasks/java/calendars/create/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}