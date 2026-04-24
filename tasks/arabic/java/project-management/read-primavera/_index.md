---
date: 2026-04-24
description: تعلم كيفية استخدام Aspose.Tasks Java لاستيراد ملفات Primavera XML إلى
  MS Project، مما يتيح تبادل بيانات سلس وتحسين إدارة المشروع.
keywords:
- aspose tasks java
- import xml ms project
- java read project
- java project xml
linktitle: قراءة مشروع من Primavera في Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – قراءة ملف XML من Primavera إلى MS Project
url: /ar/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة MS Project من Primavera باستخدام Aspose.Tasks for Java

## مقدمة
في عالم إدارة المشاريع السريع اليوم، غالبًا ما تحتاج إلى نقل الجداول الزمنية بين Primavera P6 و Microsoft Project دون فقدان أي تفاصيل. يوضح هذا الدليل **كيفية قراءة Primavera XML** واستيرادها إلى MS Project باستخدام **aspose tasks java**. في نهاية الدليل، ستكون قادرًا على سحب خصائص المهام الخاصة بـ Primavera إلى تطبيق Java، مما يمنحك مصدرًا موحدًا للتحليل وإعداد التقارير أو الأتمتة الإضافية.

## إجابات سريعة
- **ماذا يفعل Aspose.Tasks for Java؟** إنه يقرأ ويكتب العديد من صيغ ملفات المشاريع، بما في ذلك Primavera XML و Microsoft Project (MPP).  
- **هل أحتاج إلى ترخيص؟** الإصدار التجريبي المجاني يعمل للتقييم؛ يتطلب الترخيص للاستخدام في الإنتاج.  
- **ما نسخة Java المدعومة؟** يتطلب Java 8 أو أعلى.  
- **هل يمكنني استيراد صيغ أخرى غير Primavera XML؟** نعم، aspose tasks java يدعم أيضًا MPP و XML والعديد غيرها.  
- **هل هذا النهج مناسب للمشاريع المؤسسية الكبيرة؟** بالطبع—تم تصميم Aspose.Tasks لأداء عالي وللسيناريوهات على مستوى المؤسسات.

## aspose tasks java – قراءة Primavera XML
قراءة Primavera XML تعني تحليل تصدير XML من Oracle Primavera P6 لاسترجاع بيانات جدول المشروع—المهام، والمدة، والموارد، والسمات الخاصة بـ Primavera—حتى يمكن استخدامها في أدوات أخرى مثل Microsoft Project.

## لماذا تستخدم Aspose.Tasks for Java لقراءة Primavera XML؟
- **دقة كاملة:** جميع الخصائص الخاصة بـ Primavera محفوظة.  
- **بدون تبعيات خارجية:** مكتبة Java صافية، لا حاجة لتثبيت Primavera أو MS Project.  
- **قابل للتوسع:** يتعامل بكفاءة مع المشاريع الكبيرة التي تحتوي على آلاف المهام.  
- **متعدد المنصات:** يعمل على Windows و Linux و macOS.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:
1. **Java Development Kit (JDK)** – تم تثبيت Java 8 أو أحدث.  
2. **Aspose.Tasks for Java** – قم بتنزيله من [here](https://releases.aspose.com/tasks/java/).  
3. ملف Primavera XML (مثال: `PrimaveraProject.xml`) تريد قراءته.

## كيفية قراءة ملف مشروع java باستخدام Aspose.Tasks؟
فيما يلي دليل خطوة بخطوة يوجهك خلال العملية بالكامل.

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
حدّث `"PrimaveraProject.xml"` باسم الملف الفعلي لتصدير Primavera الخاص بك.

### الخطوة 3: التكرار عبر المهام واسترجاع الخصائص الخاصة بـ Primavera
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
تطبع هذه الحلقة تفاصيل كل مهمة خاصة بـ Primavera، مثل معرف النشاط (Activity ID)، تسلسل WBS، أنواع المدة، تفصيل التكاليف، والمزيد.

## المشكلات الشائعة والحلول
- **خطأ ملف غير موجود:** تحقق من أن `dataDir` ينتهي بفاصل مسار (`/` أو `\\`) وأن اسم ملف XML صحيح.  
- **خصائص Primavera مفقودة:** تأكد من أن XML تم تصديره بجميع الحقول المطلوبة؛ قد تتجاهل إصدارات Primavera القديمة بعض السمات.  
- **الأداء على الملفات الكبيرة:** فكّر في زيادة حجم ذاكرة JVM (`-Xmx2g` أو أعلى) للمشاريع التي تحتوي على عشرات الآلاف من المهام.

## الأسئلة المتكررة
### س: هل يمكنني تعديل الخصائص الخاصة بـ Primavera للمهام باستخدام Aspose.Tasks for Java؟
ج: نعم، Aspose.Tasks for Java يوفر واجهات برمجة التطبيقات لتعديل الخصائص الخاصة بـ Primavera للمهام حسب الحاجة.

### س: هل يدعم Aspose.Tasks for Java قراءة صيغ ملفات مشروع أخرى؟
ج: نعم، Aspose.Tasks for Java يدعم قراءة صيغ ملفات مشروع مختلفة بما في ذلك MPP و XML و Primavera XML.

### س: هل Aspose.Tasks for Java مناسب لتطبيقات إدارة المشاريع على مستوى المؤسسة؟
ج: بالتأكيد، Aspose.Tasks for Java يقدم ميزات قوية وقابلية توسع، مما يجعله مناسبًا لتطبيقات إدارة المشاريع على مستوى المؤسسة.

### س: هل يمكنني استخراج معلومات الموارد من مشاريع Primavera باستخدام Aspose.Tasks for Java؟
ج: نعم، Aspose.Tasks for Java يتيح لك استخراج معلومات الموارد إلى جانب تفاصيل المهام من مشاريع Primavera.

### س: أين يمكنني العثور على دعم إضافي أو وثائق لـ Aspose.Tasks for Java؟
ج: يمكنك العثور على وثائق شاملة والوصول إلى المنتديات للحصول على الدعم في صفحة [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/).

## الخلاصة
لقد تعلمت الآن **كيفية قراءة primavera xml** واستخراج معلومات تفصيلية عن المهام إلى تطبيق Java باستخدام **aspose tasks java**. هذه القدرة تجسر الفجوة بين Primavera و Microsoft Project، وتمنحك رؤية كاملة عبر المنصات وتعزز كفاءة إدارة المشروع بشكل عام.

---

**آخر تحديث:** 2026-04-24  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}