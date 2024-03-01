---
title: اكتب ملخص مشروع MPP في Aspose.Tasks
linktitle: اكتب ملخص مشروع MPP في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية كتابة ملخصات مشروع MPP في Java باستخدام Aspose.Tasks. قم بتعيين واسترجاع معلومات المشروع دون عناء.
type: docs
weight: 27
url: /ar/java/project-file-operations/write-mpp-project-summary/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نتعلم كيفية استخدام Aspose.Tasks لـ Java لكتابة ملخصات مشروع MPP. Aspose.Tasks هي مكتبة Java قوية للعمل مع ملفات Microsoft Project. باتباع الخطوات الموضحة أدناه، ستتمكن من تعيين واسترجاع معلومات تلخيصية متنوعة حول مشروع باستخدام هذه المكتبة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Tasks لـ Java: قم بتنزيل وتثبيت مكتبة Aspose.Tasks لـ Java. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/java/).
3. بيئة التطوير المتكاملة (IDE): اختر بيئة التطوير المتكاملة المفضلة لديك لتطوير Java، مثل IntelliJ IDEA أو Eclipse أو NetBeans.

## حزم الاستيراد
أولاً، قم باستيراد الحزم الضرورية إلى فئة Java الخاصة بك:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## الخطوة 1: إعداد المشروع وتحديد المعلومات الموجزة
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Data Directory";
//قم بتهيئة كائن مشروع جديد بالمسار إلى ملف المشروع الخاص بك
Project project = new Project(dataDir + "project.mpp");
// قم بتعيين معلومات موجزة عن المشروع
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// تحديد تاريخ إنشاء المشروع
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// تعيين الكلمات الرئيسية للمشروع
project.set(Prj.KEYWORDS, "MPP Aspose");
// تحديد تاريخ الطباعة الأخير للمشروع
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## الخطوة 2: حفظ معلومات ملخص المشروع
```java
// احفظ المشروع مرة أخرى بتنسيق MPP
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// عرض رسالة النجاح
System.out.println("Process completed Successfully");
```
## الخطوة 3: اقرأ معلومات ملخص المشروع
```java
// قراءة معلومات ملخص المشروع
project = new Project(dataDir + "MppAspose.xml");
// طباعة مؤلف المشروع
System.out.println("Author: " + project.get(Prj.AUTHOR));
// طباعة المؤلف الأخير للمشروع
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// طباعة رقم المراجعة للمشروع
System.out.println("Revision: " + project.get(Prj.REVISION));
// طباعة الكلمات الرئيسية للمشروع
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// طباعة تعليقات المشروع
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// طباعة تاريخ إنشاء المشروع
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// طباعة الكلمات الرئيسية للمشروع (مرة أخرى)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// طباعة تاريخ آخر طباعة للمشروع
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## خاتمة
في هذا البرنامج التعليمي، تناولنا كيفية كتابة ملخصات مشروع MPP باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات، يمكنك تعيين واسترجاع معلومات تلخيصية متنوعة حول ملفات مشروعك بكفاءة. يعمل Aspose.Tasks على تبسيط عملية العمل مع ملفات Microsoft Project في تطبيقات Java، مما يوفر وظائف قوية وسهولة الاستخدام.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ Java مع مكتبات Java الأخرى؟
ج: نعم، يمكن دمج Aspose.Tasks for Java بسلاسة مع مكتبات Java الأخرى لتعزيز قدرات إدارة مشروعك.
### س: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### س: ما مدى تكرار تحديث Aspose.Tasks لـ Java؟
ج: يتم تحديث Aspose.Tasks for Java بانتظام لضمان التوافق مع أحدث إصدارات ملفات Java وMicrosoft Project.
### س: هل يمكنني تخصيص معلومات ملخص المشروع بشكل أكبر؟
ج: بالتأكيد، يوفر Aspose.Tasks for Java خيارات شاملة لتخصيص معلومات ملخص المشروع وفقًا لمتطلباتك المحددة.
### س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks لـ Java؟
ج: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).