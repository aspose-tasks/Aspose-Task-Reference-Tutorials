---
title: إتقان حساب النطاق الزمني لمشروع MS في Aspose.Tasks
linktitle: قم بتعيين عدد النطاق الزمني في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية إدارة عدد النطاق الزمني بشكل فعال في MS Project باستخدام Aspose.Tasks لـ Java. تحسين تصور المشروع وإدارته دون عناء.
type: docs
weight: 22
url: /ar/java/project-file-operations/set-time-scale-count/
---
## مقدمة
يمكن أن تؤثر إدارة عدد النطاق الزمني في MS Project بشكل كبير على تصور المشروع وإدارته. باستخدام Aspose.Tasks for Java، وهي واجهة برمجة تطبيقات قوية للتعامل مع مهام إدارة المشروعات برمجيًا، يمكنك التعامل بكفاءة مع عدد النطاق الزمني لتخصيص طرق عرض المشروع وفقًا لاحتياجاتك المحددة.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر ما يلي:
1. بيئة تطوير Java: تأكد من تثبيت Java Development Kit (JDK) على نظامك.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة Java. يمكنك الحصول عليه من[هنا](https://releases.aspose.com/tasks/java/).
3. المعرفة الأساسية ببرمجة Java: الإلمام بلغة برمجة Java سيكون مفيدًا.

## حزم الاستيراد
قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## الخطوة 1: قم بتعيين دليل البيانات
حدد المسار إلى دليل البيانات حيث سيتم تخزين ملفات مشروعك:
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` مع المسار إلى دليل البيانات الخاص بك.
## الخطوة 2: إنشاء مثيل المشروع
 إنشاء مثيل جديد`Project` هدف:
```java
Project project = new Project();
```
يؤدي هذا إلى إنشاء كائن مشروع جديد.
## الخطوة 3: تكوين عرض مخطط جانت
 إنشاء`GanttChartView` كائن لتكوين عرض مخطط جانت:
```java
GanttChartView view = new GanttChartView();
```
## الخطوة 4: قم بتعيين عدد النطاق الزمني للطبقة السفلية
قم بتعيين رؤية العدد وعلامات التجزئة لطبقة النطاق الزمني السفلي:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
يحدد هذا عدد الفواصل الزمنية وما إذا كان سيتم عرض علامات التجزئة للطبقة السفلية.
## الخطوة 5: قم بتعيين عدد النطاق الزمني للطبقة المتوسطة
وبالمثل، قم بتكوين طبقة النطاق الزمني الأوسط:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## الخطوة 6: إضافة عرض إلى المشروع
أضف العرض المكوّن إلى المشروع:
```java
project.getViews().add(view);
```
يؤدي هذا إلى إضافة طريقة العرض المخصصة للمشروع.
## الخطوة 7: إضافة بيانات الاختبار إلى المشروع
أضف بعض بيانات الاختبار إلى المشروع للتوضيح:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
يؤدي هذا إلى إنشاء مهمتين بفترات محددة.
## الخطوة 8: حفظ المشروع بصيغة PDF
احفظ المشروع كملف PDF:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
يؤدي هذا إلى حفظ المشروع بالتكوينات المطبقة على ملف PDF.

## خاتمة
تتيح لك إدارة عدد النطاق الزمني بشكل فعال في MS Project باستخدام Aspose.Tasks for Java إمكانية تخصيص طرق عرض المشروع لتحسين التصور والإدارة.
## الأسئلة الشائعة
### س: هل يمكن لـ Aspose.Tasks لـ Java التعامل مع ملفات المشاريع واسعة النطاق؟
ج: نعم، Aspose.Tasks for Java قادر على التعامل مع ملفات المشاريع واسعة النطاق بكفاءة.
### س: هل Aspose.Tasks لـ Java متوافق مع بيئة Java IDEs المختلفة؟
ج: نعم، يعمل Aspose.Tasks for Java بسلاسة مع بيئات التطوير المتكاملة لـ Java الشائعة (IDEs) مثل Eclipse وIntelliJ IDEA.
### س: هل يمكنني تخصيص مظهر مخططات جانت باستخدام Aspose.Tasks لـ Java؟
ج: بالتأكيد، يوفر Aspose.Tasks for Java إمكانات واسعة لتخصيص مظهر مخططات جانت وفقًا لمتطلباتك.
### س: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks لـ Java؟
 ج: يمكنك العثور على الدعم والمساعدة في منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).