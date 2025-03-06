---
title: التكرار على الموارد غير الجذرية في Aspose.Tasks
linktitle: التكرار على الموارد غير الجذرية في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية التكرار بكفاءة عبر الموارد غير الجذرية في ملفات Microsoft Project باستخدام Aspose.Tasks لـ Java. تعزيز عملية التطوير الخاصة بك.
weight: 12
url: /ar/java/resource-management/iterate-non-root-resources/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# التكرار على الموارد غير الجذرية في Aspose.Tasks

## مقدمة
Aspose.Tasks for Java هي مكتبة قوية توفر للمطورين الأدوات التي يحتاجونها للتعامل مع ملفات Microsoft Project بكفاءة. بفضل واجهته البديهية ووظائفه الواسعة، يعمل Aspose.Tasks على تبسيط عملية العمل مع بيانات المشروع، مما يسمح للمطورين بالتركيز على بناء تطبيقات قوية.
## المتطلبات الأساسية
قبل الغوص في استخدام Aspose.Tasks لـ Java، تأكد من أن لديك ما يلي:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks لمكتبة Java: قم بتنزيل Aspose.Tasks لمكتبة Java وتثبيته من[صفحة التحميل](https://releases.aspose.com/tasks/java/).

## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد الحزم اللازمة لبدء العمل مع Aspose.Tasks:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## الخطوة 1: إعداد دليل البيانات
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` مع المسار إلى الدليل حيث يتم تخزين ملفات المشروع الخاص بك.
## الخطوة 2: تحميل ملف المشروع
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
 يقوم هذا الخط بتهيئة ملف جديد`Project` الكائن عن طريق تحميل ملف المشروع المسمى`"ResourceCosts.mpp"` من دليل البيانات المحدد.
## الخطوة 3: التكرار على الموارد غير الجذرية
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
تتكرر هذه الحلقة على كل مورد في المشروع (`prj.getResources()`). إذا كان المورد موردًا جذرًا، فإنه ينتقل إلى التكرار التالي. وإلا، فإنه يطبع اسم المورد غير الجذر.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية التكرار على الموارد غير الجذرية باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات، يمكنك التعامل بشكل فعال مع بيانات المشروع وتبسيط عملية التطوير الخاصة بك.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Tasks لـ Java لإنشاء ملفات مشروع جديدة؟
نعم، يوفر Aspose.Tasks وظائف لإنشاء ملفات المشروع وتعديلها وحفظها بتنسيقات مختلفة.
### هل يدعم Aspose.Tasks كافة إصدارات ملفات Microsoft Project؟
يدعم Aspose.Tasks تنسيقات ملفات Microsoft Project 2003-2019، بما في ذلك MPP وMPT وXML.
### هل Aspose.Tasks متوافق مع أطر عمل Java مثل Spring؟
نعم، يمكن دمج Aspose.Tasks بسلاسة في أطر عمل Java مثل Spring للتطبيقات على مستوى المؤسسات.
### هل يمكنني تخصيص حقول بيانات المشروع باستخدام Aspose.Tasks؟
بالتأكيد، يقدم Aspose.Tasks واجهات برمجة تطبيقات واسعة النطاق لتخصيص حقول بيانات المشروع وفقًا لمتطلباتك.
### هل يوفر Aspose.Tasks الدعم والوثائق للمطورين؟
نعم، يقدم Aspose.Tasks وثائق شاملة ومنتدى دعم مخصص لمساعدة المطورين في الرد على أي استفسارات أو مشكلات يواجهونها.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
