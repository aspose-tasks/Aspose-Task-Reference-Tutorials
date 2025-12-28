---
date: 2025-12-28
description: تعلم كيفية قراءة ملفات Primavera XML إلى MS Project باستخدام Aspose.Tasks
  للغة Java، مما يتيح تبادل بيانات سلس وتحسين إدارة المشاريع.
linktitle: Read Project from Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية قراءة ملف XML من Primavera إلى MS Project باستخدام Aspose.Tasks للغة
  Java
url: /ar/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة ملفات MS Project من Primavera باستخدام Aspose.Tasks for Java

## مقدمة
في إدارة المشاريع الحديثة، نقل البيانات بين الأدوات دون فقدان التفاصيل أمر أساسي. يوضح هذا الدليل **كيفية قراءة ملفات primavera xml** واستيرادها إلى Microsoft Project باستخدام Aspose.Tasks for Java. في النهاية، ستتمكن من استخراج خصائص المهام الخاصة بـ Primavera، مما يجعل التحليل عبر المنصات بسيطًا وفعالًا.

## إجابات سريعة
- **ماذا يفعل Aspose.Tasks for Java؟** يقرأ ويكتب العديد من صيغ ملفات المشاريع، بما في ذلك Primavera XML و Microsoft Project (MPP).  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ التر مطلوب للاستخدام في الإنتاج.  
- **ما نسخة Java المدعومة؟** يلزم Java 8 أو أعلى.  
- **هل يمكنني قراءة صيغ أخرى غير Primavera XML؟** نعم، يدعم Aspose.Tasks صيغ MPP، XML، والعديد غيرها.  
- **هل هذا النهج مناسب للمشاريع المؤسسية الكبيرة؟** بالتأكيد—تم تصميم Aspose.Tasks لأداء عالي وللبيئات المؤسسية.

## ما هو read primavera xml؟
قراءة Primavera XML تعني تحليل تصدير XML من Oracle Primavera P6 لاسترجاع بيانات جدول المشروع—المهام، المدد، الموارد، والخصائص الخاصة بـ Primavera—حتى يمكن استهلاكها بواسطة أدوات أخرى مثل Microsoft Project.

## لماذا نستخدم Aspose.Tasks for Java لقراءة primavera xml؟
- **دقة كاملة:** جميع الخصائص الخاصة بـ Primavera تُحفظ دون فقدان.  
- **بدون تبعيات خارجية:** مكتبة Java صافية، لا تحتاج إلى تثبيت Primavera أو MS Project.  
- **قابلة للتوسع:** تتعامل بكفاءة مع مشاريع ضخمة تحتوي على آلاف المهام.  
- **متعددة المنصات:** تعمل على Windows وLinux وmacOS.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:
1. **مجموعة تطوير Java (JDK)** – Java 8 أو أحدث مثبتة.  
2. **Aspose.Tasks for Java** – قم بتحميله من [هنا](https://releases.aspose.com/tasks/java/).  
3. ملف Primavera XML (مثال: `PrimaveraProject.xml`) تريد قراءته.

## كيف تقرأ ملف المشروع java باستخدام Aspose.Tasks؟
فيما يلي دليل خطوة بخطوة يشرح العملية بالكامل.

### استيراد الحزم
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### الخطوة 1: إعداد دليل البيانات
```java
String dataDir = "Your Data Directory";
```
استبدل `"Your Data Directory"` بالمسار المطلق حيث يوجد ملف Primavera XML الخاص بك.

### الخطوة 2: قراءة المشروع من Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
حدّث `"PrimaveraProject.xml"` باسم ملف تصدير Primavera الفعلي.

### الخطوة 3: التجول عبر المهام واسترجاع الخصائص الخاصة بـ Primavera
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
تقوم هذه الحلقة بطباعة تفاصيل كل مهمة خاصة بـ Primavera، مثل معرف النشاط، تسلسل WBS، أنواع المدد، تفاصيل التكلفة، وغيرها.

## المشكلات الشائعة والحلول
- **خطأ ملف غير موجود:** تأكد أن `dataDir` ينتهي بفاصل مسار (`/` أو `\\`) وأن اسم ملف XML صحيح.  
- **غياب خصائص Primavera:** تأكد من أن XML تم تصديره مع جميع الحقول المطلوبة؛ قد تُهمل الإصدارات القديمة من Primavera بعض الخصائص.  
- **الأداء مع الملفات الكبيرة:** فكر في زيادة حجم ذاكرة JVM (`-Xmx2g` أو أعلى) للمشاريع التي تحتوي على عشرات الآلاف من المهام.

## الأسئلة المتكررة
### س: هل يمكنني تعديل الخصائص الخاصة بـ Primavera للمهام باستخدام Aspose.Tasks for Java؟
ج: نعم، توفر Aspose.Tasks for Java واجهات برمجة تطبيقات لتعديل خصائص Primavera للمهام حسب الحاجة.

### س: هل يدعم Aspose.Tasks for Java قراءة صيغ ملفات مشروع أخرى؟
ج: نعم، يدعم Aspose.Tasks for Java قراءة صيغ ملفات مشروع متعددة بما في ذلك MPP، XML، وPrimavera XML.

### س: هل Aspose.Tasks for Java مناسب لتطبيقات إدارة المشاريع على مستوى المؤسسة؟
ج: بالتأكيد، يقدم Aspose.Tasks for Java ميزات قوية وقابلية توسع تجعله مناسبًا لتطبيقات إدارة المشاريع على مستوى المؤسسة.

### س: هل يمكنني استخراج معلومات الموارد من مشاريع Primavera باستخدام Aspose.Tasks for Java؟
ج: نعم، يتيح لك Aspose.Tasks for Java استخراج معلومات الموارد جنبًا إلى جنب مع تفاصيل المهام من مشاريع Primavera.

### س: أين يمكنني العثور على دعم إضافي أو وثائق لـ Aspose.Tasks for Java؟
ج: يمكنك العثور على وثائق شاملة والوصول إلى المنتديات للدعم على صفحة [توثيق Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/).

## الخلاصة
لقد تعلمت الآن **كيفية قراءة ملفات primavera xml** واستخراج معلومات تفصيلية عن المهام إلى تطبيق Java باستخدام Aspose.Tasks. هذه القدرة تجسر الفجوة بين Primavera وMicrosoft Project، مما يمنحك رؤية كاملة عبر المنصات ويعزز كفاءة إدارة المشاريع بشكل عام.

---

**آخر تحديث:** 2025-12-28  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}