---
title: إدارة المدة الأساسية للمهمة في Aspose.Tasks
linktitle: إدارة المدة الأساسية للمهمة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية إدارة الخطوط الأساسية للمهام بكفاءة في MS Project باستخدام Aspose.Tasks لـ Java. يرشدك هذا البرنامج التعليمي خطوة بخطوة خلال العملية.
weight: 12
url: /ar/java/task-baselines/task-baseline-duration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة المدة الأساسية للمهمة في Aspose.Tasks

## مقدمة
تعد إدارة الخطوط الأساسية للمهام في MS Project أمرًا بالغ الأهمية لتخطيط المشروع وتتبعه. في هذا البرنامج التعليمي، سوف نستكشف كيفية إدارة فترات خط الأساس للمهام بشكل فعال باستخدام Aspose.Tasks لـ Java.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. بيئة تطوير Java: تأكد من تثبيت Java Development Kit (JDK) على نظامك.
2.  مكتبة Aspose.Tasks: قم بتنزيل وتثبيت مكتبة Aspose.Tasks لـ Java من[هنا](https://releases.aspose.com/tasks/java/).

## حزم الاستيراد
أولاً، قم باستيراد الحزم اللازمة لمشروع Java الخاص بك:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## الخطوة 1: إنشاء مثيل المشروع
قم بتهيئة مثيل مشروع جديد باستخدام الكود التالي:
```java
Project project = new Project();
```
## الخطوة 2: إنشاء خط الأساس للمهمة
قم بإنشاء مهمة جديدة وقم بتعيين خط الأساس الخاص بها باستخدام الكود التالي:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## الخطوة 3: عرض المعلومات الأساسية للمهمة
استرداد وعرض المعلومات الأساسية للمهمة مثل المدة وتاريخ البدء وتاريخ الانتهاء والمزيد:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## الخطوة 4: التحقق من خط الأساس المؤقت والتكلفة الثابتة
تحقق مما إذا كان خط الأساس هو خط أساس مؤقت واسترد أي تكاليف ثابتة مرتبطة به:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## الخطوة 5: طباعة البيانات الموزعة على الوقت
طباعة البيانات الموزعة على الوقت المرتبطة بخط الأساس للمهمة:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
باتباع هذه الخطوات، يمكنك إدارة فترات خط الأساس للمهام بشكل فعال في MS Project باستخدام Aspose.Tasks لـ Java.

## خاتمة
تعد إدارة الخطوط الأساسية للمهام أمرًا ضروريًا لإدارة المشروع، مما يسمح لك بتتبع الانحرافات عن الجدول الزمني المخطط له. باستخدام Aspose.Tasks لـ Java، تصبح هذه العملية مبسطة وفعالة، مما يتيح تحكمًا أفضل في المشروع وتسليمه.
## الأسئلة الشائعة
### ما هو خط الأساس للمهمة في MS Project؟
يعد خط الأساس للمهمة في MS Project لقطة من الجدول الزمني الأولي المخطط لمهمة ما، بما في ذلك تاريخ البدء وتاريخ الانتهاء والمدة.
### لماذا تعتبر إدارة الخطوط الأساسية للمهمة مهمة؟
تساعد إدارة الخطوط الأساسية للمهام في مقارنة الجدول الزمني المخطط مع التقدم الفعلي للمشروع، مما يسهل التتبع واتخاذ القرار بشكل أفضل.
### هل يمكنني تعديل خط الأساس للمهمة بمجرد تعيينه؟
نعم، يمكنك تعديل الخطوط الأساسية للمهمة في MS Project لتعكس التغييرات في خطة المشروع. ومع ذلك، من الضروري توثيق أي انحرافات عن خط الأساس الأصلي.
### هل يدعم Aspose.Tasks وظائف إدارة المشاريع الأخرى؟
نعم، يقدم Aspose.Tasks مجموعة واسعة من الميزات لإدارة المشاريع، بما في ذلك جدولة المهام وتخصيص الموارد وإنشاء مخطط جانت.
### أين يمكنني العثور على الدعم لـ Aspose.Tasks؟
 يمكنك العثور على دعم لـ Aspose.Tasks على الموقع[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15)حيث يمكنك طرح الأسئلة والتفاعل مع المستخدمين الآخرين.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
