---
title: اقرأ MS Project من Primavera باستخدام Aspose.Tasks لـ Java
linktitle: قراءة المشروع من بريمافيرا في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية قراءة ملفات MS Project من Primavera XML بسلاسة باستخدام Aspose.Tasks لـ Java. تعزيز كفاءة إدارة المشروع الخاص بك.
weight: 20
url: /ar/java/project-management/read-primavera/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# اقرأ MS Project من Primavera باستخدام Aspose.Tasks لـ Java

## مقدمة
في إدارة المشاريع، تعد قابلية التشغيل البيني بين منصات البرامج المختلفة أمرًا بالغ الأهمية لسير العمل السلس. يوفر Aspose.Tasks for Java وظائف قوية لقراءة ملفات Microsoft Project من Primavera XML. سيرشدك هذا البرنامج التعليمي خلال عملية قراءة ملفات MS Project من Primavera باستخدام Aspose.Tasks لـ Java، مما يسمح لك بفحص خصائص Primavera الخاصة بالمهام بكفاءة.
## المتطلبات الأساسية
قبل المتابعة، تأكد من تثبيت المتطلبات الأساسية التالية وإعدادها:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Tasks لـ Java: قم بتنزيل Aspose.Tasks لـ Java وتثبيته من[هنا](https://releases.aspose.com/tasks/java/).

## حزم الاستيراد
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## الخطوة 1: إعداد دليل البيانات
```java
String dataDir = "Your Data Directory";
```
 تأكد من الاستبدال`"Your Data Directory"` مع المسار الفعلي إلى دليل البيانات الخاص بك.
## الخطوة 2: قراءة المشروع من Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 تأكد من الاستبدال`"PrimaveraProject.xml"` بالاسم الفعلي لملف Primavera XML الخاص بك.
## الخطوة 3: التكرار خلال المهام واسترداد الخصائص الخاصة ببرنامج بريمافيرا
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
يتكرر هذا الرمز خلال كل مهمة في المشروع، مما يؤدي إلى طباعة الخصائص ذات الصلة الخاصة ببرنامج Primavera.

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية قراءة ملفات MS Project من Primavera XML باستخدام Aspose.Tasks لـ Java. تتيح هذه الوظيفة التكامل والتحليل السلس لبيانات المشروع عبر منصات مختلفة، مما يعزز كفاءة إدارة المشروع بشكل عام.
## الأسئلة الشائعة
### س: هل يمكنني تعديل خصائص المهام الخاصة ببرنامج Primavera باستخدام Aspose.Tasks لـ Java؟
ج: نعم، يوفر Aspose.Tasks for Java واجهات برمجة التطبيقات لتعديل خصائص المهام الخاصة بـ Primavera حسب الحاجة.
### س: هل يدعم Aspose.Tasks for Java قراءة تنسيقات ملفات المشروع الأخرى؟
ج: نعم، يدعم Aspose.Tasks for Java قراءة تنسيقات ملفات المشروع المختلفة بما في ذلك MPP وXML وPrimavera XML.
### س: هل Aspose.Tasks for Java مناسب لتطبيقات إدارة المشاريع على مستوى المؤسسة؟
ج: بالتأكيد، يوفر Aspose.Tasks for Java ميزات قوية وقابلية للتوسع، مما يجعله مناسبًا لتطبيقات إدارة المشاريع على مستوى المؤسسة.
### س: هل يمكنني استخراج معلومات الموارد من مشاريع Primavera باستخدام Aspose.Tasks لـ Java؟
ج: نعم، يتيح لك Aspose.Tasks for Java استخراج معلومات الموارد بالإضافة إلى تفاصيل المهام من مشاريع Primavera.
### س: أين يمكنني العثور على دعم أو وثائق إضافية لـ Aspose.Tasks لـ Java؟
 ج: يمكنك العثور على وثائق شاملة والوصول إلى المنتديات للحصول على الدعم على[Aspose.Tasks لوثائق جافا](https://reference.aspose.com/tasks/java/) صفحة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
