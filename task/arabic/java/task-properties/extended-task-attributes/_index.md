---
title: سمات المهام الموسعة في Aspose.Tasks
linktitle: سمات المهام الموسعة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: استكشف سمات المهام الموسعة في Aspose.Tasks لـ Java. دليل خطوة بخطوة والأسئلة الشائعة والدعم. تحسين إدارة المشروع الخاص بك اليوم!
type: docs
weight: 16
url: /ar/java/task-properties/extended-task-attributes/
---
## مقدمة
مرحبًا بك في دليلنا الشامل حول الاستفادة من سمات المهام الموسعة في Aspose.Tasks لـ Java. Aspose.Tasks هي مكتبة Java قوية تتيح لك العمل مع مستندات Microsoft Project بسلاسة. في هذا البرنامج التعليمي، سوف نتعمق في سمات المهمة الموسعة ونوضح كيف يمكنك الاستفادة منها لتعزيز قدرات إدارة مشروعك.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على جهازك.
- بيئة تطوير متكاملة (IDE) مثل IntelliJ أو Eclipse.
## حزم الاستيراد
ابدأ باستيراد الحزم اللازمة لبدء مشروع Aspose.Tasks الخاص بك:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
الآن، دعنا نقسم المثال إلى خطوات متعددة لإرشادك خلال العملية:
## الخطوة 1: الوصول إلى المهام والسمات الموسعة
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## الخطوة 2: استرداد معرف الحقل ومعرف القيمة GUID
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## الخطوة 3: التعامل مع أنواع السمات المختلفة
```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```
كرر هذه الخطوات لكل مهمة في مشروعك لاستكشاف سمات المهام الموسعة ومعالجتها.
## خاتمة
في الختام، فإن فهم واستخدام سمات المهام الموسعة في Aspose.Tasks لـ Java يمكن أن يعزز بشكل كبير قدرات إدارة مشروعك. يوفر هذا الدليل أساسًا متينًا للبدء في هذه الرحلة.
## أسئلة مكررة
### هل يمكنني تعديل سمات المهمة الموسعة برمجياً؟
نعم، يمكنك تعديل سمات المهام الموسعة باستخدام Aspose.Tasks لـ Java. الرجوع إلى الوثائق للحصول على تعليمات مفصلة.
### هل هناك نسخة تجريبية متاحة؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم لـ Aspose.Tasks لـ Java؟
 للحصول على الدعم، قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).
### كيف يمكنني الحصول على ترخيص مؤقت؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني شراء الإصدار الكامل من Aspose.Tasks لـ Java؟
 يمكنك شراء النسخة الكاملة[هنا](https://purchase.aspose.com/buy).