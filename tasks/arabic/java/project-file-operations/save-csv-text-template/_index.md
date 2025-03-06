---
title: احفظ بتنسيق CSV ونص ونموذج في Aspose.Tasks
linktitle: احفظ بتنسيق CSV ونص ونموذج في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية حفظ ملفات Microsoft Project بتنسيقات CSV، والنص، والقوالب باستخدام Aspose.Tasks لـ Java.
type: docs
weight: 16
url: /ar/java/project-file-operations/save-csv-text-template/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية حفظ ملفات المشروع بتنسيقات مختلفة مثل CSV، والنص، والقالب باستخدام Aspose.Tasks لـ Java. Aspose.Tasks هي مكتبة Java قوية تتيح للمطورين العمل مع ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2.  تم تنزيل Aspose.Tasks لمكتبة Java وتكوينها في مشروع Java الخاص بك. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/java/).
3. المعرفة الأساسية بلغة البرمجة جافا.

## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم الضرورية في ملف Java الخاص بك:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## حفظ المشروع بتنسيق CSV
دعونا نقسم الخطوات لحفظ المشروع كملف CSV:
### الخطوة 1: تحميل المشروع
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### الخطوة 2: احفظ بتنسيق CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## حفظ المشروع كنص
إليك كيفية حفظ المشروع كنص:
### الخطوة 1: تحميل المشروع
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### الخطوة 2: حفظ كنص
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## حفظ المشروع كقالب
يتضمن حفظ المشروع كقالب الخطوات التالية:
### الخطوة 1: تحميل المشروع
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### الخطوة 2: تعيين خيارات القالب
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### الخطوة 3: حفظ كقالب
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية حفظ ملفات Microsoft Project بتنسيق CSV ونص ونموذج باستخدام Aspose.Tasks لـ Java. من خلال هذه الخطوات البسيطة، يمكنك إدارة ملفات مشروعك بكفاءة بتنسيقات مختلفة، مما يعزز إنتاجيتك كمطور Java.
## الأسئلة الشائعة
### س: هل يمكن لـ Aspose.Tasks لـ Java التعامل مع ملفات المشاريع المعقدة؟
ج: بالتأكيد! يمكن لـ Aspose.Tasks for Java التعامل مع المشاريع ذات التعقيد المتفاوت بسهولة، مما يوفر دعمًا شاملاً لتنسيقات ملفات Microsoft Project.
### س: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks لـ Java من[هنا](https://releases.aspose.com/).
### س: أين يمكنني العثور على الدعم لـ Aspose.Tasks لـ Java؟
 ج: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للحصول على أي مساعدة أو استفسارات بخصوص Aspose.Tasks لـ Java.
### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك شراء ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/)مما يسمح لك بتقييم الإمكانات الكاملة للمكتبة.
### س: هل Aspose.Tasks لـ Java متوافق مع أنظمة التشغيل المختلفة؟
ج: نعم، Aspose.Tasks for Java متوافق مع أنظمة التشغيل المختلفة، بما في ذلك Windows وmacOS وLinux.