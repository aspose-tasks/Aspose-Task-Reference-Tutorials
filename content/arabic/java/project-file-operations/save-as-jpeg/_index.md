---
title: تحويل MS Project إلى JPEG في Aspose.Tasks
linktitle: احفظ المشروع بتنسيق JPEG في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تحويل ملفات Microsoft Project بسهولة إلى صور JPEG باستخدام Aspose.Tasks لـ Java. تعزيز إنتاجيتك.
type: docs
weight: 20
url: /ar/java/project-file-operations/save-as-jpeg/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية حفظ ملف Microsoft Project كصورة JPEG باستخدام Aspose.Tasks لـ Java. يمكن أن يكون هذا مفيدًا بشكل خاص لمشاركة تصورات المشروع أو دمج بيانات المشروع في التقارير أو العروض التقديمية.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1.  Java Development Kit (JDK): تأكد من تثبيت Java على نظامك. يمكنك تنزيل وتثبيت أحدث إصدار من[موقع جافا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks لـ Java: قم بتنزيل Aspose.Tasks لـ Java وإعداده باتباع الإرشادات الواردة في[توثيق](https://reference.aspose.com/tasks/java/).

## حزم الاستيراد
أولاً، قم باستيراد الحزم الضرورية إلى ملف Java الخاص بك:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## الخطوة 1: تحديد دليل البيانات
قم بتعيين المسار إلى دليل البيانات الخاص بك حيث يوجد ملف MS Project الخاص بك.
```java
String dataDir = "Your Data Directory";
```
## الخطوة 2: تحميل ملف مشروع MS
قم بتحميل ملف MS Project باستخدام Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## الخطوة 3: تكوين جودة JPEG (اختياري)
 إذا كنت تريد ضبط جودة JPEG، فيمكنك ضبطها باستخدام`ImageSaveOptions` فصل. تتراوح الجودة من 0 إلى 100.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // اضبط جودة JPEG على 50
```
## الخطوة 4: احفظ المشروع بصيغة JPEG
احفظ ملف MS Project كصورة JPEG.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية حفظ ملف Microsoft Project كصورة JPEG باستخدام Aspose.Tasks لـ Java. تتيح هذه الميزة سهولة مشاركة بيانات المشروع ودمجها في المستندات والعروض التقديمية المختلفة.
## الأسئلة الشائعة
### س: هل يمكنني ضبط جودة صورة JPEG؟
 ج: نعم، يمكنك ضبط الجودة باستخدام`setJpegQuality()` الطريقة، مع نطاق من 0 إلى 100.
### س: ماذا لو لم أحدد جودة JPEG؟
ج: إذا لم تحدد الجودة، فسيتم استخدام الجودة الافتراضية.
### س: هل Aspose.Tasks لـ Java مجاني للاستخدام؟
 ج: Aspose.Tasks for Java هي مكتبة تجارية، ولكن يمكنك استكشاف ميزاتها من خلال النسخة التجريبية المجانية. قم بزيارة[صفحة تجريبية مجانية](https://releases.aspose.com/) للمزيد من المعلومات.
### س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks لـ Java؟
ج: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).
### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks؟
 ج: نعم، يمكنك شراء ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).