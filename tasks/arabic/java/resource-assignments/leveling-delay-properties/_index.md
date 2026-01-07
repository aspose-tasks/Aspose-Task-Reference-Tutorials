---
date: 2026-01-07
description: تعلم كيفية إضافة مورد إلى المشروع ومعالجة خصائص تأخير التوازن لتعيينات
  الموارد باستخدام Aspose.Tasks للغة Java.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية إضافة مورد إلى المشروع ومعالجة خصائص تأخير التسوية في Aspose.Tasks
url: /ar/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة مورد إلى المشروع ومعالجة خصائص تأخير التسوية في Aspose.Tasks

## المقدمة
في هذا البرنامج التعليمي، ستتعلم **كيفية إضافة مورد إلى المشروع** مع إدارة خصائص تأخير التسوية لتعيينات الموارد باستخدام Aspose.Tasks for Java. سواءً كنت تبني محرك جدولة أو تقوم بأتمتة تحديثات المشروع، فإن إتقان هذه الخطوات يتيح لك الحفاظ على دقة بيانات المشروع دون الحاجة إلى تثبيت Microsoft Project.

## إجابات سريعة
- **ماذا يعني “إضافة مورد إلى المشروع”؟** ينشئ إدخال مورد جديد يمكن تعيينه للمهام.  
- **هل يمكنني ضبط تأخير التسوية بعد التعيين؟** نعم، باستخدام حقول `Asn.DELAY` أو `Asn.LEVELING_DELAY`.  
- **هل أحتاج إلى ترخيص لتشغيل هذا الكود؟** النسخة التجريبية المجانية تكفي للتطوير؛ الترخيص المدفوع مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أحدث.  
- **هل هذا متوافق مع جميع صيغ ملفات MS Project؟** Aspose.Tasks يدعم .MPP، .XML، .XER، وأكثر.

## ما معنى “إضافة مورد إلى المشروع” في Aspose.Tasks؟
إضافة مورد إلى المشروع تعني إنشاء كائن `Resource` داخل نموذج `Project`. يمكن ربط هذا الكائن لاحقًا بالمهام عبر `ResourceAssignment`، مما يتيح لك تتبع العمل، التكاليف، وإعدادات التسوية.

## لماذا نتعامل مع خصائص تأخير التسوية؟
تأخير التسوية يساعد جدولة العمل على توزيع المهام عندما تكون الموارد مُفرطة التخصيص. من خلال ضبط تأخير، تخبر المحرك بتأخير بدء التعيين، مما يجنّب التعارضات ويحافظ على واقعية المشروع.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر المتطلبات التالية:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت Java JDK على نظامك. يمكنك تنزيله وتثبيته من [الموقع الإلكتروني](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. مكتبة Aspose.Tasks for Java: حمّل مكتبة Aspose.Tasks for Java من [صفحة التحميل](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
أولاً، استورد الحزم اللازمة إلى مشروع Java الخاص بك لاستخدام وظائف Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## الخطوة 1: إنشاء كائن Project
أنشئ كائن `Project`، والذي سيعمل كحاوية لجميع المهام والموارد والتعيينات:
```java
Project prj = new Project();
```

## الخطوة 2: إنشاء مهمة
أضف مهمة إلى المشروع. هذا يوضح **كيفية إضافة مهمة** برمجيًا:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## الخطوة 3: ضبط تاريخ بدء المهمة والمدة
حدد متى تبدأ المهمة وكم ستستمر:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## الخطوة 4: إضافة مورد
الآن **نضيف موردًا إلى المشروع** بإنشاء إدخال `Resource` جديد:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## الخطوة 5: إنشاء تعيين مورد
اربط المهمة بالمورد الذي أُضيف حديثًا:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## الخطوة 6: ضبط تأخير التسوية
قم بتكوين تأخير التسوية للتعيين. ضبطه على صفر يعني عدم وجود تأخير إضافي، لكن يمكنك تعديل القيمة حسب الحاجة:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## الخطوة 7: عرض النتائج
اطبع الخصائص المهمة للتحقق من ضبط كل شيء بشكل صحيح:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## المشكلات الشائعة والنصائح
- **المشكلة:** نسيان ضبط تاريخ بدء المهمة قد يؤدي إلى تعيين التعيين إلى تاريخ بدء المشروع افتراضيًا.  
- **النصيحة:** استخدم `prj.getDuration(value, TimeUnitType.Day)` للتحكم في دقة التأخير.  
- **النصيحة:** بعد إضافة موارد متعددة، استدعِ `prj.updateResourceAssignments()` للسماح للجدولة بإعادة حساب التسوية.

## الخلاصة
باتباع هذه الخطوات، أصبحت الآن تعرف **كيفية إضافة مورد إلى المشروع**، وتعيينه إلى مهمة، وإدارة خصائص تأخير التسوية باستخدام Aspose.Tasks for Java. هذه المعرفة تمكنك من بناء حلول أتمتة مشروع قوية تظل متوافقة مع قيود الموارد الواقعية.

## الأسئلة المتكررة
### س: هل يمكنني استخدام Aspose.Tasks مع مكتبات Java أخرى؟

ج: نعم، يمكن دمج Aspose.Tasks مع مكتبات Java أخرى لتعزيز قدرات إدارة المشروع.

### س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟

ج: نعم، يدعم Aspose.Tasks إصدارات متعددة من ملفات Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.

### س: أين يمكنني العثور على دعم إضافي لـ Aspose.Tasks؟

ج: يمكنك العثور على الدعم والموارد في [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### س: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟

ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks عبر [صفحة الإصدارات](https://releases.aspose.com/).

### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟

ج: يمكنك طلب ترخيص مؤقت من [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) لأغراض التقييم.

## أسئلة شائعة إضافية

**س: ماذا يحدث إذا ضبطت تأخير تسوية غير صفري؟**  
ج: سيؤخر المجدول بدء التعيين بالمدة المحددة، مما يساعد على حل حالات الإفراط في تخصيص الموارد.

**س: هل يمكنني استرجاع تأخير التسوية بعد حفظ المشروع؟**  
ج: نعم، يمكنك إعادة فتح ملف المشروع وقراءة خاصية `Asn.DELAY` من التعيين.

**س: هل هناك طريقة لتطبيق تأخير التسوية على جميع التعيينات مرة واحدة؟**  
ج: يمكنك التجول عبر `prj.getResourceAssignments()` وضبط التأخير لكل تعيين داخل حلقة.

---

**آخر تحديث:** 2026-01-07  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}