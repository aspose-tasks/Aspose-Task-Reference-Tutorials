---
title: تعيين سمات مشروع MS للمهام الجديدة في Aspose.Tasks
linktitle: قم بتعيين سمات للمهام الجديدة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تعيين سمات MS Project للمهام الجديدة باستخدام Aspose.Tasks لـ Java. قم بتخصيص خصائص المهمة دون عناء باستخدام هذا الدليل الشامل.
type: docs
weight: 21
url: /ar/java/project-file-operations/set-attributes-new-tasks/
---
## مقدمة
مرحبًا بك في برنامجنا التعليمي الشامل حول إعداد سمات MS Project للمهام الجديدة في Aspose.Tasks لـ Java! في هذا الدليل، سنرشدك خلال العملية خطوة بخطوة، مما يضمن أنه يمكنك بسهولة إدارة مهامك وتخصيصها باستخدام مكتبة Java القوية هذه.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1. بيئة تطوير Java: تأكد من تثبيت Java على نظامك وأنك على دراية بمفاهيم برمجة Java الأساسية.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة Java من[رابط التحميل](https://releases.aspose.com/tasks/java/).
3. Java IDE: اختر بيئة تطوير Java المتكاملة (IDE) مثل Eclipse أو IntelliJ IDEA للبرمجة.

## حزم الاستيراد
قبل أن نبدأ في تعيين سمات MS Project للمهام الجديدة، فلنستورد الحزم الضرورية:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;
```

## الخطوة 1: تحديد دليل البيانات
أولاً، حدد المسار إلى الدليل الذي تريد حفظ ملفات مشروعك فيه:
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` مع المسار إلى الدليل المطلوب.
## الخطوة 2: إنشاء مثيل المشروع
قم بإنشاء مثيل لكائن مشروع جديد لبدء العمل مع مشروعك:
```java
Project prj = new Project();
```
يؤدي هذا إلى إنشاء مثيل مشروع جديد.
## الخطوة 3: تعيين خاصية مهمة جديدة
الآن، دعونا نحدد تاريخ البدء للمهام الجديدة. في هذا المثال، قمنا بتعيينه على التاريخ الحالي:
```java
prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);
```
 هذا الخط يحدد الخاصية`NEW_TASK_START_DATE` ل`TaskStartDateType.CurrentDate`.
## الخطوة 4: احفظ المشروع
احفظ المشروع بسمات المهمة الجديدة بتنسيق XML:
```java
prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
يحفظ هذا السطر المشروع باسم الملف المحدد في الدليل المحدد مسبقًا.
## الخطوة 5: عرض النتيجة
أخيرًا، لنطبع رسالة لتأكيد إنشاء ملف المشروع بنجاح:
```java
System.out.println("Project file generated Successfully");
```
يعرض هذا السطر رسالة النجاح في وحدة التحكم.

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تعيين سمات MS Project للمهام الجديدة باستخدام Aspose.Tasks لـ Java. ومن خلال هذه المعرفة، يمكنك الآن تخصيص خصائص المهمة وفقًا لمتطلباتك، مما يعزز قدرات إدارة المشروع لديك.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ Java لمعالجة ملفات المشروع الموجودة؟
ج: نعم، يوفر Aspose.Tasks for Java وظائف واسعة النطاق لمعالجة ملفات المشروع الموجودة، بما في ذلك قراءتها وتعديلها وحفظها بتنسيقات مختلفة.
### س: أين يمكنني العثور على المزيد من الوثائق والموارد الخاصة بـ Aspose.Tasks لـ Java؟
 ج: يمكنك استكشاف الوثائق والموارد الموجودة على الموقع[Aspose.Tasks لصفحة وثائق Java](https://reference.aspose.com/tasks/java/).
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks لـ Java من[هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على تراخيص مؤقتة لـ Aspose.Tasks لـ Java؟
 ج: يمكن الحصول على تراخيص مؤقتة لـ Aspose.Tasks لـ Java من[صفحة الترخيص المؤقتة](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني الحصول على الدعم لأية مشكلات أو استفسارات تتعلق بـ Aspose.Tasks لـ Java؟
 ج: يمكنك الحصول على الدعم والتفاعل مع المجتمع على[Aspose.Tasks لمنتدى دعم جافا](https://forum.aspose.com/c/tasks/15).