---
date: 2026-06-05
description: تعلم كيفية إنشاء تعيين موارد باستخدام Aspose.Tasks لـ Java، إضافة موارد
  إلى مشروع، وإدارة خصائص تأخير التسوية.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: معالجة خصائص تأخير التسوية لتعيينات الموارد في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: إنشاء تعيين موارد باستخدام Aspose.Tasks لـ Java
url: /ar/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء تعيين مورد باستخدام Aspose.Tasks للغة Java

في هذا الدليل الشامل ستتعلم **كيفية إنشاء تعيين مورد aspotasks** باستخدام مكتبة Aspose.Tasks للغة Java. سواء كنت تبني محرك جدولة مخصص، أو تقوم بأتمتة تحديثات المشاريع الضخمة، أو تحتاج ببساطة إلى التعامل مع ملفات Microsoft Project دون تطبيق سطح المكتب، فإن إتقان هذه الخطوات يتيح لك الحفاظ على دقة بيانات مشروعك والتحكم الكامل فيها.

## إجابات سريعة
- **ماذا يعني “add resource to project”؟** إنه ينشئ إدخال مورد جديد يمكن لاحقًا تعيينه للمهام.  
- **هل يمكنني ضبط تأخير التسوية بعد التعيين؟** نعم، باستخدام حقول `Asn.DELAY` أو `Asn.LEVELING_DELAY`.  
- **هل أحتاج إلى ترخيص لتشغيل هذا الكود؟** الإصدار التجريبي المجاني يعمل للتطوير؛ يلزم ترخيص مدفوع للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أحدث.  
- **هل هذا متوافق مع جميع صيغ ملفات MS Project؟** Aspose.Tasks يدعم أكثر من 12 صيغة — بما في ذلك .MPP، .XML، .XER، .CSV، .PDF، وغيرها.

## ما هو “add resource to project” في Aspose.Tasks؟
إضافة مورد إلى مشروع يعني إنشاء كائن `Resource` داخل نموذج `Project`. يمكن ربط هذا الكائن لاحقًا بالمهام عبر `ResourceAssignment`، مما يتيح لك تتبع العمل والتكاليف وإعدادات التسوية. بإدراج مورد، تزود المجدول بشيء لتخصيصه، ويمكنك لاحقًا الاستعلام أو تعديل خصائصه مثل التوافر، الأسعار، وتعيينات التقويم.

## لماذا التعامل مع خصائص تأخير التسوية؟
تأخير التسوية يخبر المجدول بتأجيل بدء تعيين مفرط التخصيص، مما يوزع العمل بشكل أكثر تساويًا عبر الجدول الزمني. من خلال تكوين هذا التأخير، تتجنب تواريخ بدء غير واقعية، وتقلل تحذيرات الإفراط في التخصيص، وتنتج جدولًا يعكس قيود الموارد في الواقع. تعديل التأخير يمنحك أيضًا تحكمًا دقيقًا في مقدار الفائض الذي قد يضيفه المحرك، مما يساعدك على الوفاء بمواعيد المشروع مع احترام حدود الموارد.

## كيفية إنشاء تعيين مورد aspotasks؟
حمّل كائن `Project` الخاص بك، أضف مهمة، أنشئ موردًا، ثم اربطهم معًا باستخدام `ResourceAssignment`. يتيح لك هذا التدفق من البداية إلى النهاية بناء هيكل مشروع كامل برمجيًا والتحكم فورًا في تأخير التسوية على التعيين. تُظهر العملية سير العمل الأساسي: تهيئة المشروع، تعريف المهمة، إنشاء المورد، ربط التعيين، وأخيرًا تطبيق معلمات الجدولة مثل تأخير التسوية.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر المتطلبات التالية:
1. Java Development Kit (JDK): تأكد من تثبيت Java JDK على نظامك. يمكنك تنزيله وتثبيته من [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Aspose.Tasks for Java Library: قم بتنزيل مكتبة Aspose.Tasks للغة Java من [download page](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
تستورد الاستيرادات التالية الفئات الأساسية في Aspose.Tasks اللازمة للتعامل مع المشروع.  
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

## كيفية إنشاء تعيين مورد aspotasks؟
حمّل كائن `Project` الخاص بك، أضف مهمة، أنشئ موردًا، ثم اربطهم معًا باستخدام `ResourceAssignment`. يتيح لك هذا التدفق من البداية إلى النهاية بناء هيكل مشروع كامل برمجيًا والتحكم فورًا في تأخير التسوية على التعيين. تُظهر العملية سير العمل الأساسي: تهيئة المشروع، تعريف المهمة، إنشاء المورد، ربط التعيين، وأخيرًا تطبيق معلمات الجدولة مثل تأخير التسوية.

## الخطوة 1: إنشاء كائن Project
فئة `Project` هي الحاوية العليا في Aspose.Tasks التي تمثل ملف مشروع كامل في الذاكرة. إنشاء مثال منها يمنحك مساحة فارغة لإضافة المهام والموارد والتعيينات.
```java
Project prj = new Project();
```

## الخطوة 2: إنشاء مهمة
فئة `Task` تمثل عنصر عمل واحد في الجدول. إضافة مهمة توضح **كيفية إضافة مهمة** برمجيًا وتوفر هدفًا لتعيين المورد القادم.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## الخطوة 3: تعيين تاريخ بدء المهمة والمدة
حدد متى تبدأ المهمة ومدة تشغيلها. تواريخ البدء الصحيحة ضرورية لأن حسابات التسوية تستخدمها كأساس لأي تأخير تحدده لاحقًا.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## الخطوة 4: إضافة مورد
الآن نقوم **بإضافة مورد إلى المشروع** بإنشاء إدخال `Resource` جديد. فئة `Resource` تمثل شخصًا أو معدات أو مادة يمكن تعيينها للمهام.
```java
Resource resource = prj.getResources().add("Resource 1");
```

## الخطوة 5: إنشاء تعيين مورد
`ResourceAssignment` يربط بين `Task` و `Resource`. هذه العلاقة تتيح لك تسجيل العمل، التكلفة، وتفاصيل التسوية لمورد معين على مهمة معينة.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## الخطوة 6: تعيين تأخير التسوية
قم بتكوين تأخير التسوية للتعيين. ضبطه على الصفر يعني عدم وجود تأخير إضافي، لكن يمكنك تعديل القيمة حسب الحاجة. حقل `Asn.DELAY` يحتوي على التأخير بالدقائق؛ `Asn.LEVELING_DELAY` هو اسم بديل يعمل بنفس الطريقة.
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## الخطوة 7: عرض النتائج
اطبع الخصائص المهمة للتحقق من ضبط كل شيء بشكل صحيح. تساعدك هذه الخطوة على التأكد من أن قيم المورد، المهمة، والتأخير هي بالضبط ما تتوقعه قبل حفظ الملف.
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## الأخطاء الشائعة والنصائح
- **مشكلة:** نسيان تعيين تاريخ بدء المهمة قد يؤدي إلى تعيين التعيين افتراضيًا إلى بداية المشروع.  
- **نصيحة:** استخدم `prj.getDuration(value, TimeUnitType.Day)` للتحكم في دقة التأخير.  
- **نصيحة:** بعد إضافة موارد متعددة، استدعِ `prj.updateResourceAssignments()` للسماح للمجدول بإعادة حساب التسوية.  
- **نصيحة احترافية:** للمشاريع الكبيرة (أكثر من 10,000 مهمة) فعّل `prj.setAutoCalculate(false)` قبل التحديثات الجماعية، ثم استدعِ `prj.calculate()` مرة واحدة في النهاية لتحسين الأداء.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع مكتبات Java أخرى؟**  
ج: نعم، يتكامل Aspose.Tasks بسلاسة مع مكتبات مثل Jackson لمعالجة JSON أو Apache POI للعمليات الإضافية على جداول البيانات، مما يتيح لك بناء حلول إدارة مشاريع أكثر غنى.

**س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟**  
ج: Aspose.Tasks يدعم أكثر من 12 صيغة — بما في ذلك .MPP (2003‑2021)، .XML، .XER، .CSV، .PDF، .HTML، و .MPP12 — مما يضمن تحريرًا سلسًا عبر جميع إصدارات Project الرئيسية.

**س: أين يمكنني العثور على دعم إضافي لـ Aspose.Tasks؟**  
ج: يمكنك العثور على الدعم ومناقشات المجتمع في [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**س: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟**  
ج: نعم، نسخة تجريبية مجانية كاملة الوظائف متاحة من [releases page](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت للتقييم؟**  
ج: اطلب ترخيصًا مؤقتًا من [temporary license page](https://purchase.aspose.com/temporary-license/) لتشغيل المكتبة دون قيود التقييم.

---

**آخر تحديث:** 2026-06-05  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تعيينات موارد في Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [إدارة ميزانية التعيين Java باستخدام Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)
- [كيفية إيقاف التعيين واستئناف تعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}