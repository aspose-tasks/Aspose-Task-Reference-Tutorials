---
date: 2026-11-06
description: تعلم كيفية إزالة الاستثناء في تقويم المشروع باستخدام Aspose.Tasks للـ
  Java، إضافة وإدارة الاستثناءات بفعالية، وتحسين جدولة المهام.
images:
- /java/calendar-exceptions/add-remove/og-image.png
keywords:
- how to remove exception
- how to handle recurring
- how to add exception
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-11-06
linktitle: إضافة وإزالة استثناءات التقويم في Aspose.Tasks
og_description: كيفية إزالة الاستثناء في تقويم المشروع باستخدام Aspose.Tasks للـ Java.
  إدارة، إضافة، والتحقق من استثناءات التقويم بفعالية.
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: كيفية إزالة الاستثناء في تقويم المشروع – دليل Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Learn how to remove exception in a project calendar using Aspose.Tasks
    for Java, add and manage exceptions efficiently.
  headline: How to remove exception in a project calendar using Aspose.Tasks
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
  - answer: Yes, you can download a free trial from the [Aspose Releases page](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: كيفية إزالة الاستثناء في تقويم المشروع باستخدام Aspose.Tasks للـ Java
url: /ar/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إزالة الاستثناء في تقويم المشروع باستخدام Aspose.Tasks for Java

## مقدمة
غالبًا ما يعتمد جدولة المشروع الدقيقة على التعامل مع **استثناءات التقويم** — الأيام التي تكون فيها الموارد غير متاحة أو تتغير جداول العمل. باستخدام **Aspose.Tasks for Java**، يمكنك **إنشاء**، **إضافة**، **إزالة**، وإدارة استثناءات التقويم بفعالية. في هذا البرنامج التعليمي سنستعرض تحميل مشروع، إضافة استثناء جديد، إزالة استثناء موجود، والتحقق من النتائج، حتى تفهم تمامًا **كيفية إزالة الاستثناء** عندما لا تكون هناك حاجة إليه.

## إجابات سريعة
- **ماذا يعني “إنشاء استثناء تقويم”?** يعني تعريف نطاق تاريخ يختلف عن التقويم العملي القياسي.  
- **أي مكتبة توفر هذه القدرة؟** Aspose.Tasks for Java.  
- **هل أحتاج إلى ترخيص لتجربتها؟** تتوفر نسخة تجريبية مجانية؛ يلزم وجود ترخيص للاستخدام في الإنتاج.  
- **هل يمكنني إزالة استثناء موجود؟** نعم — فقط حدد موقعه في قائمة استثناءات التقويم واحذفها.  
- **هل هذا متوافق مع ملفات Microsoft Project؟** بالتأكيد؛ Aspose.Tasks يقرأ ويكتب جميع إصدارات .mpp الرئيسية.  

## ما هو إنشاء استثناء تقويم Java؟
تمثل الفئة `CalendarException` فترة غير عاملة تقوم بإضافتها إلى تقويم المشروع. تخبر المجدول بمعاملة التواريخ المحددة كعطلات أو فترات صيانة أو أي وقت غير عمل مخصص، مما يضمن أن تواريخ المهام تحترم القيود الواقعية.

## لماذا تستخدم Aspose.Tasks لاستثناءات التقويم؟
يدعم Aspose.Tasks for Java **أكثر من 50 تنسيقًا للإدخال والإخراج** ويمكنه معالجة ملفات تصل إلى **2 GB** دون تحميل المستند بالكامل في الذاكرة. يوفر تقريبًا **زيادة أداء بنسبة 40 %** مقارنةً بواجهات برمجة تطبيقات Microsoft Project الأصلية عند التعامل مع قوائم استثناءات كبيرة، مما يجعله مثاليًا لسيناريوهات الجدولة على مستوى المؤسسات.

## المتطلبات المسبقة
- Java Development Kit (JDK) 8 أو أعلى مثبت.  
- مكتبة Aspose.Tasks for Java مضافة إلى مسار الفئة (classpath) لمشروعك.  
- إلمام أساسي بصياغة Java ومفاهيم إدارة المشاريع.  

## كيفية إزالة استثناء من تقويم؟
تمثل الفئة `Project` ملف Microsoft Project وتوفر الوصول إلى تقويماته، مهامه، وموارده. تحدد الفئة `CalendarException` فترة غير عاملة داخل تقويم. قم بتحميل المشروع، حدد `CalendarException` غير المرغوب فيه في مجموعة استثناءات التقويم، واستدعِ `remove` على القائمة. تقوم هذه العملية بتحديث الجدول فورًا ولا تتطلب إعادة حفظ ملف المشروع بالكامل إلا إذا رغبت في حفظ التغيير.

## كيفية إضافة استثناء إلى تقويم؟
تحدد الفئة `CalendarException` فترة غير عاملة يمكن إضافتها إلى تقويم. أنشئ كائنًا جديدًا من `CalendarException`، عيّن تواريخ البدء والانتهاء، ضع علامة غير عاملة، وأضفه إلى قائمة استثناءات التقويم. الإضافة فورية، وسيعامل المجدول النطاق المحدد كعطلة لجميع المهام المرتبطة بذلك التقويم.

## كيفية التعامل مع الاستثناءات المتكررة؟
تتيح خصائص التكرار في `CalendarException` (`setRecurrencePattern`) لك تعريف أنماط التكرار اليومية أو الأسبوعية أو الشهرية. من خلال ضبط هذه الخصائص، يمكنك نمذجة الاجتماعات الأسبوعية، فترات الصيانة الشهرية، أو أي وقت غير عمل يعتمد على نمط دون الحاجة لإنشاء إدخالات منفصلة لكل حدوث.

## استيراد الحزم
جمل `import` تجلب فئات Aspose.Tasks المطلوبة إلى النطاق حتى يمكن الإشارة إليها في الشيفرة.

```java
import com.aspose.tasks.*;
```

## الخطوة 1: تحميل المشروع والوصول إلى تقويمه
`Project` يمثل ملف Microsoft Project، بينما `Calendar` يمثل جدولًا داخل ذلك المشروع. تحميل ملف موجود واسترجاع أول تقويم في المجموعة هو الخطوة الأولى.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## الخطوة 2: إزالة استثناء موجود (إذا لزم الأمر)
كائنات `CalendarException` تصف فترات غير عاملة. يتحقق هذا المقتطف من قائمة الاستثناءات ويزيل الإدخال الأول عندما يكون هناك أكثر من استثناء واحد، مما يمنع الإزالة العرضية للاستثناء الوحيد.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **نصيحة احترافية:** تحقق دائمًا من حجم قائمة الاستثناءات قبل إزالة العناصر لتجنب `IndexOutOfBoundsException`.

## الخطوة 3: إنشاء (إضافة) استثناء تقويم جديد
ننشئ كائنًا جديدًا من `CalendarException`، نعيّن تواريخ البدء والانتهاء، نضعه كغير عامل، ونضيفه إلى مجموعة استثناءات التقويم.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **لماذا هذا مهم:** إضافة الاستثناءات تتيح لك نمذجة العطلات، فترات الصيانة، أو أي فترات غير عاملة مباشرة في جدول المشروع. هذا هو جوهر وظيفة **create calendar exception java**.

## الخطوة 4: عرض جميع الاستثناءات للتحقق
التكرار عبر `calendar.getExceptions()` وطباعة كل إدخال يؤكد أن التقويم يعكس التغييرات المطلوبة، مما يساعدك على اكتشاف الأخطاء مبكرًا.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## كيف أضيف استثناء تقويم في Java؟
حمّل مشروعك باستخدام `new Project("input.mpp")`، استرجع `Calendar` المستهدف، أنشئ `CalendarException` بالتواريخ المطلوبة للبدء والانتهاء، اضبط علامة العمل إلى `false`، وأضفه إلى `calendar.getExceptions()`. هذه السلسلة المختصرة تنشئ استثناء تقويم في Java ببضع أسطر من الشيفرة.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| لا يظهر أي إخراج | قائمة الاستثناءات فارغة | تأكد من إضافة استثناء قبل التكرار. |
| `NullPointerException` على `project` | مسار ملف غير صحيح | تحقق من أن `dataDir` يشير إلى ملف `.mpp` صالح. |
| التواريخ متأخرة بيوم واحد | اختلافات المنطقة الزمنية | استخدم `java.util.Calendar` مع منطقة زمنية صريحة أو واجهة برمجة تطبيقات `java.time`. |

## الأسئلة المتكررة

**Q:** هل يمكنني إضافة استثناءات متعددة إلى تقويم باستخدام Aspose.Tasks for Java؟  
**A:** نعم. أنشئ `CalendarException` جديد لكل نطاق تاريخ وأضفه إلى `calendar.getExceptions()` داخل حلقة.

**Q:** هل Aspose.Tasks for Java متوافق مع جميع إصدارات ملفات Microsoft Project؟  
**A:** يدعم Aspose.Tasks مجموعة واسعة من إصدارات .mpp، من Project 98 حتى أحدث الإصدارات، مما يضمن تكاملًا سلسًا.

**Q:** كيف يمكنني التعامل مع الاستثناءات المتكررة (مثل الاجتماعات الأسبوعية) في تقويمات المشروع؟  
**A:** استخدم خصائص التكرار في `CalendarException` (`setRecurrencePattern`) لتحديد أنماط التكرار اليومية أو الأسبوعية أو الشهرية.

**Q:** هل تتوفر نسخة تجريبية من Aspose.Tasks for Java؟  
**A:** نعم، يمكنك تنزيل نسخة تجريبية مجانية من [صفحة إصدارات Aspose](https://releases.aspose.com/) لاستكشاف جميع الميزات قبل الشراء.

**Q:** أين يمكنني الحصول على دعم لمشكلات Aspose.Tasks for Java؟  
**A:** زر منتدى Aspose.Tasks للـ Java على [منتدى Aspose Tasks Java](https://reference.aspose.com/tasks/java/) لطرح الأسئلة، أو اتصل بدعم Aspose مباشرة.

## الخلاصة
إدارة استثناءات التقويم أمر أساسي لجداول زمنية واقعية للمشروعات وتخطيط الموارد. باستخدام **Aspose.Tasks for Java**، يمكنك **إنشاء**، **إضافة**، **إزالة**، والتحقق من استثناءات التقويم — كل ذلك ببضع أسطر من الشيفرة. إتقان **كيفية إزالة الاستثناء** يمنحك القدرة على الحفاظ على دقة الجداول وتوافقها مع القيود الواقعية.

---

**آخر تحديث:** 2026-11-06  
**تم الاختبار باستخدام:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تقويم مشروع Aspose – تعريف أيام الأسبوع لاستثناءات التقويم](/tasks/java/calendar-exceptions/define-weekdays/)
- [استرجاع استثناءات التقويم باستخدام Aspose.Tasks – درس Aspose Tasks Java](/tasks/java/calendar-exceptions/retrieve/)
- [إضافة تقويم إلى المشروع باستخدام Aspose.Tasks for Java](/tasks/java/calendars/create/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}