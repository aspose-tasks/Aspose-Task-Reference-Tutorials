---
title: حساب النسبة المئوية لموارد مشروع MS باستخدام Aspose.Tasks
linktitle: إجراء حسابات النسبة المئوية للموارد في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية حساب النسب المئوية لموارد MS Project باستخدام Aspose.Tasks لـ Java. تم تضمين دليل خطوة بخطوة مع أمثلة التعليمات البرمجية.
type: docs
weight: 14
url: /ar/java/resource-management/percentage-calculations/
---
## مقدمة
مرحبًا بك في دليلنا خطوة بخطوة حول إجراء حسابات النسبة المئوية لموارد MS Project باستخدام Aspose.Tasks لـ Java. في هذا البرنامج التعليمي، سوف نتعمق في عملية الاستفادة من Aspose.Tasks لمعالجة واستخراج بيانات الموارد من ملفات Microsoft Project بكفاءة. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات Java قوية توفر ميزات شاملة للعمل مع مستندات Microsoft Project، مما يسمح للمطورين بدمج وظائف إدارة المشروع بسلاسة في تطبيقات Java الخاصة بهم.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من إعداد المتطلبات الأساسية التالية:
### بيئة تطوير جافا
 تأكد من تثبيت Java Development Kit (JDK) على نظامك. يمكنك تنزيل وتثبيت JDK من[هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Aspose.مكتبة المهام
يجب أن تكون مكتبة Aspose.Tasks مدمجة في مشروع Java الخاص بك. إذا لم تكن قد قمت بذلك بالفعل، يمكنك تنزيل المكتبة من[هنا](https://releases.aspose.com/tasks/java/) واتبع تعليمات التثبيت المتوفرة في الوثائق[هنا](https://reference.aspose.com/tasks/java/).

## حزم الاستيراد
قبل أن نبدأ البرمجة، فلنستورد الحزم الضرورية المطلوبة لهذا البرنامج التعليمي:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
## الخطوة 1: إعداد مسار ملف المشروع
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` مع المسار إلى ملف Microsoft Project الخاص بك.
## الخطوة 2: تحميل المشروع
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
يقوم هذا الرمز بتحميل ملف Microsoft Project المسمى "Software Development.mpp" الموجود في دليل البيانات المحدد.
## الخطوة 3: التكرار من خلال الموارد
```java
for (Resource res : prj.getResources()) {
```
نحن نمر عبر كل مورد في المشروع.
## الخطوة 4: التحقق من اسم المورد والنسبة المئوية لاكتمال العمل
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
نتحقق مما إذا كان اسم المورد ليس فارغًا ثم نطبع النسبة المئوية للعمل المنجز لكل مورد.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استخدام Aspose.Tasks لـ Java لإجراء حسابات النسبة المئوية لموارد MS Project بكفاءة. باتباع هذه الخطوات، يمكنك دمج وظائف إدارة المشروع بسلاسة في تطبيقات Java الخاصة بك، مما يوفر تحكمًا محسنًا ورؤى حول استخدام موارد المشروع.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Tasks لـ Java مع أطر عمل Java الأخرى؟
نعم، Aspose.Tasks for Java متوافق مع أطر عمل Java المختلفة مثل Spring وHbernate والمزيد.
### هل يدعم Aspose.Tasks كافة إصدارات ملفات Microsoft Project؟
يوفر Aspose.Tasks الدعم لجميع إصدارات ملفات Microsoft Project، بما في ذلك MPP وMPT وXML والمزيد.
### هل يمكنني التعامل مع جداول المشروع باستخدام Aspose.Tasks؟
بالتأكيد، يقدم Aspose.Tasks ميزات شاملة للتعامل مع جداول المشروع، بما في ذلك المهام والموارد والتقويمات والمزيد.
### هل يوجد منتدى مجتمعي لدعم Aspose.Tasks؟
 نعم، يمكنك العثور على المساعدة والتفاعل مع المستخدمين الآخرين في منتدى مجتمع Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).
### هل يقدم Aspose.Tasks تراخيص مؤقتة لأغراض التقييم؟
 نعم يمكنك الحصول على ترخيص مؤقت للتقييم من[هنا](https://purchase.aspose.com/temporary-license/).