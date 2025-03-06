---
title: إيقاف واستئناف تعيينات الموارد في Aspose.Tasks
linktitle: إيقاف واستئناف تعيينات الموارد في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية إدارة تعيينات الموارد بشكل فعال في Aspose.Tasks لـ Java باستخدام هذا البرنامج التعليمي خطوة بخطوة.
weight: 23
url: /ar/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إيقاف واستئناف تعيينات الموارد في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سوف نتعلم كيفية إيقاف واستئناف تعيينات الموارد باستخدام Aspose.Tasks لـ Java. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات Java قوية تتيح للمطورين العمل مع ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project على أنظمتهم. سنقوم بتقسيم العملية إلى خطوات يمكن التحكم فيها لتسهيل متابعتها.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك.
-  تم تنزيل Aspose.Tasks لمكتبة Java. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/java/).
- الفهم الأساسي لبرمجة جافا.
## حزم الاستيراد
أولاً، لنستورد الحزم الضرورية إلى مشروع Java الخاص بنا:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## الخطوة 1: تحميل ملف المشروع
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Data Directory";
// قم بتحميل ملف المشروع
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 في هذه الخطوة، نقوم بتحميل ملف المشروع إلى ملف`Project` كائن باستخدام مسار الملف.
## الخطوة 2: التكرار من خلال تعيينات الموارد
```java
// تحديد الحد الأدنى للتاريخ
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// التكرار من خلال تعيينات الموارد
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
هنا، نحدد الحد الأدنى للتاريخ ونبدأ بالتكرار خلال كل تعيين مورد في المشروع.
## الخطوة 3: التحقق من تواريخ التوقف والاستئناف
```java
    // التحقق من تاريخ التوقف
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // التحقق من تاريخ السيرة الذاتية
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
في هذه الخطوة، نتحقق مما إذا كانت تواريخ التوقف والاستئناف لكل تعيين مورد قبل الحد الأدنى للتاريخ. إذا كانت كذلك، فإننا نطبع "NA"، وإلا فإننا نطبع التواريخ المعنية.
## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إيقاف واستئناف تعيينات الموارد في Aspose.Tasks لـ Java. باتباع الخطوات المتوفرة، يمكنك بسهولة تنفيذ هذه الوظيفة في مشاريع Java الخاصة بك.

## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Tasks دون تثبيت Microsoft Project؟
نعم، يتيح لك Aspose.Tasks العمل مع ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project على نظامك.
### أين يمكنني العثور على المزيد من الوثائق؟
 يمكنك العثور على وثائق مفصلة[هنا](https://reference.aspose.com/tasks/java/).
### هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم إذا واجهت أي مشاكل؟
يمكنك الحصول على الدعم من المجتمع[هنا](https://forum.aspose.com/c/tasks/15).
### هل يمكنني شراء ترخيص مؤقت؟
 نعم، يمكنك شراء ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
