---
title: قم بتحديث ملف MPP في Aspose.Tasks
linktitle: قم بتحديث ملف MPP في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تحديث ملفات MPP بسلاسة باستخدام Aspose.Tasks لـ Java. اتبع دليلنا خطوة بخطوة لمعالجة ملف المشروع بكفاءة.
weight: 19
url: /ar/java/project-management/update-mpp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتحديث ملف MPP في Aspose.Tasks

## مقدمة
في مجال إدارة المشاريع، يعد التعامل مع ملفات المشروع وتحديثها مهمة بالغة الأهمية. يوفر Aspose.Tasks for Java حلاً قويًا لمطوري Java للتعامل مع ملفات Microsoft Project بسلاسة. في هذا البرنامج التعليمي، سوف نتعمق في تحديث ملفات MPP باستخدام Aspose.Tasks لـ Java.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
1. بيئة تطوير Java: تأكد من تثبيت Java على نظامك.
2.  Aspose.Tasks لـ Java: قم بتنزيل Aspose.Tasks لـ Java وتثبيته من[صفحة التحميل](https://releases.aspose.com/tasks/java/).
3. المعرفة الأساسية بجافا: الإلمام بلغة برمجة جافا ضروري لمتابعة الأمثلة.

## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم اللازمة إلى مشروع Java الخاص بك للاستفادة من وظائف Aspose.Tasks بشكل فعال.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
يستورد سطر التعليمات البرمجية هذا جميع الفئات والأساليب الأساسية من مكتبة Aspose.Tasks، مما يسمح لك بالعمل مع ملفات Microsoft Project دون عناء.

الآن، دعنا نقسم عملية تحديث ملف MPP باستخدام Aspose.Tasks لـ Java إلى خطوات يمكن التحكم فيها.
## الخطوة 2: تحديد دليل البيانات
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` بالمسار الفعلي حيث يوجد ملف MPP الخاص بك.
## الخطوة 3: قراءة المشروع الحالي
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 يقرأ هذا الرمز ملف مشروع MPP الموجود المسمى`SampleMSP2010.mpp` من دليل البيانات المحدد.
## الخطوة 4: إنشاء مهمة جديدة
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
هنا، نضيف مهمة جديدة تسمى "Task1" إلى المهمة الجذرية للمشروع.
## الخطوة 5: تحديد تواريخ البدء والانتهاء
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
تقوم أسطر التعليمات البرمجية هذه بتعيين تاريخ البدء وتاريخ الانتهاء للمهمة التي تم إنشاؤها حديثًا.
## الخطوة 6: احفظ المشروع
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 أخيرًا، تقوم هذه الخطوة بحفظ المشروع المحدث بالمهمة المضافة حديثًا إلى ملف MPP جديد باسم`AfterLinking.mpp`.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية تحديث ملفات MPP باستخدام Aspose.Tasks لـ Java. باتباع الدليل الموضح خطوة بخطوة، يمكنك التعامل بكفاءة مع ملفات Microsoft Project داخل تطبيقات Java الخاصة بك.
## الأسئلة الشائعة
### س: هل يمكن لـ Aspose.Tasks لـ Java التعامل مع هياكل المشاريع المعقدة؟
ج: نعم، يوفر Aspose.Tasks for Java ميزات قوية للتعامل مع هياكل المشاريع المعقدة بكفاءة.
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من[موقع إلكتروني](https://releases.aspose.com/).
### س: هل يدعم Aspose.Tasks for Java إصدارات مختلفة من ملفات Microsoft Project؟
ج: بالتأكيد، يدعم Aspose.Tasks for Java إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك تنسيقات MPP وMPT وXML.
### س: هل يمكنني الحصول على تراخيص مؤقتة لـ Aspose.Tasks لـ Java؟
 ج: نعم، التراخيص المؤقتة متاحة لأغراض الاختبار. يمكنك الحصول عليها من[صفحة الترخيص المؤقتة](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني طلب المساعدة أو الدعم فيما يتعلق بـ Aspose.Tasks لـ Java؟
 ج: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لأية مساعدة أو استفسار.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
