---
title: قراءة بيانات الجدول من ملف في Aspose.Tasks
linktitle: قراءة بيانات الجدول من ملف في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: أطلق العنان لقوة Aspose.Tasks لـ Java. تعلم كيفية استخراج بيانات الجدول من الملفات في هذا البرنامج التعليمي الشامل.
type: docs
weight: 17
url: /ar/java/project-data-reading/read-table-data/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية قراءة بيانات الجدول من ملف باستخدام Aspose.Tasks لـ Java. Aspose.Tasks هي مكتبة Java قوية تتيح للمطورين العمل مع مستندات Microsoft Project برمجياً.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله وتثبيته من موقع أوراكل.
2.  Aspose.Tasks for Java JAR File: قم بتنزيل مكتبة Aspose.Tasks for Java من ملف[رابط التحميل](https://releases.aspose.com/tasks/java/) وإدراجه في مشروع Java الخاص بك.

## حزم الاستيراد
قم باستيراد الحزم اللازمة للعمل مع Aspose.Tasks في مشروع Java الخاص بك:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```
## الخطوة 1: إعداد دليل البيانات
حدد المسار إلى الدليل الذي يوجد به ملف المشروع الخاص بك:
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` مع المسار الفعلي إلى دليل البيانات الخاص بك.
## الخطوة 2: تحميل ملف المشروع
قم بتحميل ملف المشروع باستخدام Aspose.Tasks:
```java
Project project = new Project(dataDir + "Project2003.mpp");
```
 تأكد من استبدال`"Project2003.mpp"` مع اسم ملف المشروع الخاص بك.
## الخطوة 3: استرجاع معلومات الجدول
احصل على الجدول من المشروع وكرر حقوله:
```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```
يسترد مقتطف التعليمات البرمجية هذا معلومات حول حقول الجدول مثل العرض والعنوان والمحاذاة.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية قراءة بيانات الجدول من ملف باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات، يمكنك استخراج البيانات ومعالجتها بكفاءة من مستندات Microsoft Project في تطبيقات Java الخاصة بك.
## الأسئلة الشائعة
### س: هل Aspose.Tasks متوافق مع كافة إصدارات Microsoft Project؟
ج: يدعم Aspose.Tasks إصدارات مختلفة من Microsoft Project، بما في ذلك Project 2003 و2007 و2010 و2013 و2016.
### س: هل يمكنني تعديل بيانات الجدول وحفظها مرة أخرى في ملف المشروع؟
ج: نعم، يمكنك استخدام Aspose.Tasks لتعديل بيانات الجدول برمجياً وحفظ التغييرات في ملف المشروع الأصلي.
### س: هل يتطلب Aspose.Tasks ترخيصًا منفصلاً للاستخدام التجاري؟
 ج: نعم، أنت بحاجة إلى شراء ترخيص لـ Aspose.Tasks إذا كنت تنوي استخدامه في بيئة تجارية. يمكنك الحصول على ترخيص من[صفحة الشراء](https://purchase.aspose.com/buy).
### س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks من الموقع[صفحة الإصدارات](https://releases.aspose.com/).
### س: أين يمكنني العثور على المساعدة والدعم فيما يتعلق بـ Aspose.Tasks؟
 ج: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15)للحصول على المساعدة والدعم من المجتمع وفريق Aspose.