---
title: تحديث وإعادة جدولة مشروع MS في Aspose.Tasks
linktitle: قم بتحديث المشروع وإعادة جدولة العمل غير المكتمل في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تحديث ملفات MS Project وإعادة جدولتها برمجيًا باستخدام Aspose.Tasks لـ Java.
weight: 23
url: /ar/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحديث وإعادة جدولة مشروع MS في Aspose.Tasks

## مقدمة
Microsoft Project هو برنامج لإدارة المشاريع يستخدم على نطاق واسع ويسمح للمستخدمين بإدارة المهام والموارد والجداول الزمنية بكفاءة. يوفر Aspose.Tasks for Java مجموعة قوية من واجهات برمجة التطبيقات لمعالجة ملفات Microsoft Project برمجياً. في هذا البرنامج التعليمي، سنتعلم كيفية تحديث ملفات MS Project وإعادة جدولة العمل غير المكتمل باستخدام Aspose.Tasks لـ Java.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2.  Aspose.Tasks لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/java/).
3. الفهم الأساسي للغة البرمجة جافا.

## حزم الاستيراد
أولاً، قم باستيراد الحزم الضرورية في كود Java الخاص بك:
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
## الخطوة 1: إعداد المشروع
قم بتهيئة كائن مشروع جديد وحدد المهام بداخله مع فتراتها وتبعياتها.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// تحديد المهام ومدتها
// ...
// تحديد تبعيات المهمة
// ...
// حفظ حالة المشروع الأولية
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## الخطوة 2: تحديث عمل المشروع
قم بتحديث عمل المشروع لوضع علامة عليه كمكتمل حتى تاريخ معين.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// احفظ المشروع المحدث
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## الخطوة 3: إعادة جدولة العمل غير المكتمل
إعادة جدولة أي عمل غير مكتمل للبدء بعد تاريخ محدد.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// احفظ المشروع المعاد جدولته
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تحديث ملفات MS Project وإعادة جدولة العمل غير المكتمل باستخدام Aspose.Tasks لـ Java. يمكن أن يكون هذا مفيدًا بشكل خاص في السيناريوهات التي تحتاج فيها الجداول الزمنية للمشروع إلى التعديل بناءً على التقدم أو الأولويات المتغيرة.

## الأسئلة الشائعة
### س: هل يمكن لـ Aspose.Tasks لـ Java التعامل مع هياكل المشاريع المعقدة؟
ج: نعم، يوفر Aspose.Tasks for Java واجهات برمجة تطبيقات قوية لإدارة المهام والتبعيات والموارد وعناصر المشروع الأخرى بكفاءة.
### س: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على دعم Aspose.Tasks لـ Java؟
 ج: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لأية مساعدة أو استفسار.
### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks لـ Java؟
 ج: نعم، التراخيص المؤقتة متاحة للشراء[هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.Tasks لـ Java؟
 ج: يمكنك الرجوع إلى الوثائق[هنا](https://reference.aspose.com/tasks/java/) للحصول على أدلة شاملة ومراجع API.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
