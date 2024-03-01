---
title: حساب المسار الحرج لمشروع MS في Aspose.Tasks
linktitle: حساب المسار الحرج في مشاريع Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية حساب المسار الحرج في MS Project باستخدام Aspose.Tasks لـ Java. وهذا يوفر إرشادات خطوة بخطوة لإدارة المشروع بكفاءة.
type: docs
weight: 10
url: /ar/java/project-management/critical-path/
---
## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية حساب المسار الحرج في MS Project باستخدام Aspose.Tasks لـ Java. يعد المسار الحرج ضروريًا لإدارة المشروع لأنه يساعد في تحديد تسلسل المهام التي يجب إكمالها في الوقت المحدد لضمان عدم تأخير الجدول الزمني الإجمالي للمشروع.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2.  تم تنزيل Aspose.Tasks لمكتبة Java وإضافتها إلى مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/java/).

## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية في فئة Java الخاصة بك:
```java
import com.aspose.tasks.*;
```
## الخطوة 1: إعداد دليل البيانات
حدد المسار إلى دليل البيانات الخاص بك حيث يوجد ملف MS Project الخاص بك.
```java
String dataDir = "Your Data Directory";
```
## الخطوة 2: تحميل ملف مشروع MS
قم بتحميل ملف MS Project باستخدام مكتبة Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```
## الخطوة 3: ضبط وضع الحساب
اضبط وضع الحساب على تلقائي لتمكين حساب المسار الحرج.
```java
project.setCalculationMode(CalculationMode.Automatic);
```
## الخطوة 4: إضافة المهام
أضف المهام إلى مشروعك. في هذا المثال، نضيف ثلاث مهام فرعية.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```
## الخطوة 5: إنشاء روابط المهام
قم بإنشاء روابط المهام لتحديد التبعيات بين المهام.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
```
## الخطوة 6: عرض المسار الحرج
استرداد وعرض المسار الحرج للمشروع.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```
## الخطوة 7: عرض النتيجة
عرض رسالة تشير إلى إتمام العملية بنجاح.
```java
System.out.println("Process completed Successfully");
```

## خاتمة
يعد حساب المسار الحرج في MS Project باستخدام Aspose.Tasks لـ Java أمرًا ضروريًا لإدارة المشروع بشكل فعال. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تحديد تسلسل المهام المهمة للجدول الزمني لمشروعك بدقة.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ Java مع أي إصدار من ملفات MS Project؟
ج: نعم، يدعم Aspose.Tasks for Java إصدارات مختلفة من ملفات MS Project، بما في ذلك ملفات .mpp من MS Project 2003 إلى MS Project 2019.
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### س: أين يمكنني العثور على الدعم لـ Aspose.Tasks لـ Java؟
 ج: يمكنك العثور على الدعم على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).
### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك شراء ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).
### س: كيف يمكنني شراء Aspose.Tasks لـ Java؟
 ج: يمكنك شراء Aspose.Tasks لـ Java من موقع الويب[هنا](https://purchase.aspose.com/buy).