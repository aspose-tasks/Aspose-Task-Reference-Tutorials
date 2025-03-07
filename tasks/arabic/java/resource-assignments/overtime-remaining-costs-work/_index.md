---
title: مراقبة العمل الإضافي والتكاليف المتبقية والعمل في Aspose.Tasks
linktitle: مراقبة العمل الإضافي والتكاليف المتبقية والعمل في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية مراقبة العمل الإضافي والتكاليف المتبقية والعمل في مشاريع Java باستخدام Aspose.Tasks. خطوات سهلة لإدارة المشاريع بفعالية.
weight: 18
url: /ar/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# مراقبة العمل الإضافي والتكاليف المتبقية والعمل في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سنتعلم كيفية استخدام Aspose.Tasks لـ Java لمراقبة العمل الإضافي والتكاليف المتبقية والعمل في المشروع. يمكن أن يكون هذا أمرًا لا يقدر بثمن بالنسبة لمديري المشاريع وقادة الفريق لضمان بقاء المشاريع على المسار الصحيح وفي حدود الميزانية.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. Java Development Kit (JDK): يتطلب Aspose.Tasks لـ Java Java SE 6 أو إصدار أحدث.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل المكتبة وتثبيتها من[هنا](https://releases.aspose.com/tasks/java/).
3. بيئة التطوير المتكاملة (IDE): أي Java IDE مثل Eclipse أو IntelliJ IDEA أو NetBeans.

## حزم الاستيراد
ابدأ باستيراد الحزم الضرورية في ملف Java الخاص بك:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## الخطوة 1: إعداد دليل البيانات
حدد الدليل الذي يوجد به ملف مشروعك:
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` مع المسار إلى ملف المشروع الخاص بك.
## الخطوة 2: تحميل المشروع
 إنشاء مثيل أ`Project` الكائن وتحميل ملف المشروع:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 يستبدل`"ResourceAssignmentOvertimes.mpp"` مع اسم ملف المشروع الخاص بك.
## الخطوة 3: التكرار من خلال تعيينات الموارد
قم بالتكرار خلال كل تعيين مورد في المشروع:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## الخطوة 4: طباعة تكاليف العمل الإضافي والعمل
استرداد وطباعة تكاليف العمل الإضافي والعمل لكل تعيين موارد:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## الخطوة 5: طباعة التكاليف المتبقية والعمل
استرداد وطباعة التكاليف المتبقية والعمل على كل تعيين موارد:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## الخطوة 6: طباعة تكاليف العمل الإضافي المتبقية والعمل
استرداد وطباعة تكاليف العمل الإضافي المتبقية والعمل على كل تعيين من الموارد:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## خاتمة
تعد مراقبة العمل الإضافي والتكاليف المتبقية والعمل في المشروع أمرًا بالغ الأهمية لإدارة المشروع بنجاح. باستخدام Aspose.Tasks for Java، يمكنك الوصول بسهولة إلى هذه المعلومات وتتبعها، مما يضمن بقاء مشاريعك في الموعد المحدد وفي حدود الميزانية.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Tasks لـ Java مع مكتبات Java الأخرى؟
نعم، Aspose.Tasks for Java متوافق مع مكتبات وأطر عمل Java الأخرى.
### هل يدعم Aspose.Tasks تنسيقات ملفات المشروع المختلفة؟
نعم، يدعم Aspose.Tasks العديد من تنسيقات ملفات المشروع بما في ذلك MPP وXML والمزيد.
### هل هناك نسخة تجريبية متاحة؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم إذا واجهت مشاكل؟
 يمكنك زيارة منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15) للدعم.
### كيف يمكنني شراء ترخيص Aspose.Tasks؟
 يمكنك شراء ترخيص من[هنا](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
