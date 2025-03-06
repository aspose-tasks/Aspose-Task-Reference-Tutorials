---
title: قم بإنشاء خط الأساس لمهمة مشروع MS في Aspose.Tasks
linktitle: إنشاء خط الأساس للمهمة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية إنشاء خط أساس لمهمة Microsoft Project في Java باستخدام Aspose.Tasks، وهي مكتبة قوية لإدارة بيانات المشروع دون عناء.
weight: 11
url: /ar/java/task-baselines/create-task-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بإنشاء خط الأساس لمهمة مشروع MS في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سنتعمق في عملية إنشاء خط أساسي لمهمة Microsoft Project باستخدام Aspose.Tasks لـ Java. Aspose.Tasks هي مكتبة Java قوية تمكن المطورين من العمل مع ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project. باستخدام Aspose.Tasks، يمكنك التعامل بسهولة مع بيانات المشروع، بما في ذلك المهام والموارد والتقويمات، لتبسيط مهام إدارة المشروع.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): يتطلب Aspose.Tasks for Java تثبيت JDK على نظامك. يمكنك تنزيل JDK وتثبيته من موقع Oracle الإلكتروني.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل مكتبة Aspose.Tasks لـ Java من[رابط التحميل](https://releases.aspose.com/tasks/java/) متاح.

## حزم الاستيراد
لبدء العمل مع Aspose.Tasks في مشروع Java الخاص بك، قم باستيراد الحزم الضرورية:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## الخطوة 1: إنشاء كائن المشروع
```java
Project project = new Project();
```
 أولاً، قم بإنشاء جديد`Project` هدف. يمثل هذا الكائن ملف Microsoft Project الذي ستعمل معه.
## الخطوة 2: إضافة مهمة إلى المشروع
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 باستخدام`getRootTask()` الطريقة، قم بالوصول إلى المهمة الجذرية للمشروع ثم قم بإضافة مهمة جديدة إليها باستخدام`add()` طريقة. أدخل اسمًا للمهمة بين قوسين.
## الخطوة 3: تعيين خط الأساس للمهام المحددة
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
لتعيين أساس لمهام محددة، قم بإنشاء قائمة مهام (`myList` في هذه الحالة) وقم بتعبئته بالمهام التي تريد تعيين خط الأساس لها. ثم استخدم`setBaseline()` الطريقة، مع تحديد نوع خط الأساس وقائمة المهام.
## الخطوة 4: تعيين خط الأساس للمشروع بأكمله
```java
project.setBaseline(BaselineType.Baseline);
```
 وبدلاً من ذلك، يمكنك تعيين خط أساس للمشروع بأكمله بمجرد الاتصال بـ`setBaseline()` الطريقة مع نوع خط الأساس المحدد.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية إنشاء خط أساسي لمهمة Microsoft Project باستخدام Aspose.Tasks لـ Java. باتباع الخطوات الموضحة أعلاه، يمكنك إدارة بيانات المشروع بكفاءة وتبسيط مهام إدارة المشروع بسهولة.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Tasks لـ Java دون تثبيت Microsoft Project؟
نعم، يتيح لك Aspose.Tasks for Java العمل مع ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project على نظامك.
### هل Aspose.Tasks لـ Java متوافق مع الإصدارات المختلفة من Microsoft Project؟
نعم، يدعم Aspose.Tasks for Java إصدارات مختلفة من Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.
### هل يمكنني التعامل مع موارد المشروع باستخدام Aspose.Tasks لـ Java؟
بالتأكيد، يوفر Aspose.Tasks for Java ميزات قوية لمعالجة موارد المشروع، بما في ذلك إضافة الموارد وتحديثها وإزالتها حسب الحاجة.
### هل يدعم Aspose.Tasks for Java تحديد تبعيات المهام؟
نعم، يمكنك تعيين تبعيات المهام بسهولة باستخدام Aspose.Tasks لـ Java، مما يتيح لك إنشاء تسلسل المهام داخل مشروعك.
### هل يتوفر الدعم الفني لـ Aspose.Tasks لـ Java؟
 نعم، يمكنك الوصول إلى الدعم الفني لـ Aspose.Tasks لـ Java عبر[منتدى الدعم](https://forum.aspose.com/c/tasks/15)حيث يمكنك طرح الأسئلة وطلب المساعدة من المجتمع وموظفي الدعم في Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
