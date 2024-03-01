---
title: خصائص أيام الأسبوع في Aspose.Tasks
linktitle: خصائص أيام الأسبوع في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعلم كيفية إدارة خصائص أيام الأسبوع بكفاءة في Aspose.Tasks لـ Java. قم بتخصيص تواريخ بدء الأسبوع والأيام في الشهر والمزيد بسهولة.
type: docs
weight: 25
url: /ar/java/project-file-operations/weekday-properties/
---
## مقدمة
Aspose.Tasks for Java عبارة عن واجهة برمجة تطبيقات قوية تمكن مطوري Java من العمل مع ملفات Microsoft Project دون تثبيت Microsoft Project على الجهاز. إحدى وظائفه الرئيسية هي إدارة خصائص أيام الأسبوع، مما يسمح للمستخدمين بتخصيص تواريخ بدء الأسبوع، والأيام في الشهر، والدقائق في اليوم، والدقائق في الأسبوع. سيوفر هذا البرنامج التعليمي دليلاً تفصيليًا حول كيفية استخدام هذه الميزات بشكل فعال.
## المتطلبات الأساسية
قبل الغوص في Aspose.Tasks لـ Java، تأكد من أن لديك المتطلبات الأساسية التالية:
### مجموعة تطوير جافا (JDK)
تأكد من تثبيت JDK على نظامك. يمكنك تنزيل أحدث إصدار من JDK وتثبيته من موقع Oracle الإلكتروني.
### Aspose.Tasks لمكتبة جافا
 قم بتنزيل وتثبيت مكتبة Aspose.Tasks لـ Java من موقع الويب. يمكنك الوصول إلى رابط التحميل[هنا](https://releases.aspose.com/tasks/java/).
### بيئة التطوير المتكاملة (IDE)
اختر IDE الذي تفضله لتطوير Java. تشمل الاختيارات الشائعة IntelliJ IDEA أو Eclipse أو NetBeans.
## حزم الاستيراد
للبدء، قم باستيراد حزم Aspose.Tasks الضرورية إلى مشروع Java الخاص بك. إليك الطريقة:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة لفهم أفضل.
## الخطوة 1: تحميل ملف المشروع
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
تتضمن هذه الخطوة تحميل ملف مشروع يسمى "project.mpp" من دليل البيانات المحدد.
## الخطوة 2: عرض خصائص أيام الأسبوع
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
هنا، نقوم باسترجاع وطباعة خصائص تاريخ بدء الأسبوع، والأيام في الشهر، والدقائق في اليوم، والدقائق في الأسبوع للمشروع المحمل.
## الخطوة 3: تحديد خصائص أيام الأسبوع
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
تتضمن هذه الخطوة إنشاء مثيل مشروع جديد وتعيين خصائص أيام الأسبوع المخصصة مثل يوم بداية الأسبوع والأيام في الشهر والدقائق في اليوم والدقائق في الأسبوع.
## الخطوة 4: حفظ المشروع
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
وأخيرًا، نقوم بحفظ المشروع المعدل بخصائص أيام الأسبوع المحدثة كملف XML.
## الخطوة 5: عرض النتيجة
```java
System.out.println("Process completed Successfully");
```
تؤكد هذه الخطوة إتمام العملية بنجاح.
## خاتمة
يعد إتقان خصائص أيام الأسبوع في Aspose.Tasks لـ Java أمرًا ضروريًا لإدارة المشاريع بشكل فعال. باتباع هذا البرنامج التعليمي، تعلمت كيفية التعامل مع خصائص أيام الأسبوع وتخصيصها بسهولة. استكشف المزيد من الوثائق والأمثلة لتعزيز قدرات إدارة مشروعك.
## الأسئلة الشائعة
### س: هل يمكن لـ Aspose.Tasks لـ Java التعامل مع هياكل المشاريع المعقدة؟
ج: نعم، يوفر Aspose.Tasks for Java دعمًا شاملاً للتعامل مع هياكل المشاريع المعقدة بسهولة.
### س: هل يتوافق Aspose.Tasks for Java مع الإصدارات المختلفة من ملفات Microsoft Project؟
ج: بالتأكيد، يدعم Aspose.Tasks for Java إصدارات مختلفة من ملفات Microsoft Project، مما يضمن التوافق عبر الأنظمة الأساسية.
### س: هل يمكنني دمج Aspose.Tasks for Java في تطبيقات Java الموجودة لدي؟
ج: نعم، يوفر Aspose.Tasks for Java إمكانات تكامل سلسة، مما يسمح لك بتحسين تطبيقات Java لديك بميزات قوية لإدارة المشاريع.
### س: هل يوفر Aspose.Tasks لـ Java الوثائق والدعم؟
 ج: نعم، يمكنك الوصول إلى الوثائق الشاملة والدعم المجتمعي لـ Aspose.Tasks for Java على موقعهم[موقع إلكتروني](https://releases.aspose.com/).
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ Java؟
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks لـ Java من موقعهم[موقع إلكتروني](https://reference.aspose.com/tasks/java/) لاستكشاف ميزاته قبل إجراء عملية الشراء.