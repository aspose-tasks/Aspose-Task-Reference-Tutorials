---
date: 2026-03-29
description: تعرّف على كيفية إعادة جدولة العمل غير المكتمل، وتحديث عمل المشروع، وحفظ
  ملفات MS Project بصيغة XML باستخدام Aspose.Tasks للغة Java.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إعادة جدولة العمل غير المكتمل وتحديث ملفات MS Project باستخدام Aspose.Tasks
url: /ar/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إعادة جدولة العمل غير المكتمل وتحديث ملفات MS Project باستخدام Aspose.Tasks

## مقدمة
Microsoft Project هو أداة إدارة مشاريع واسعة الاستخدام تساعد الفرق على تخطيط المهام، وتخصيص الموارد، وتتبع الجداول الزمنية. توفر Aspose.Tasks for Java للمطورين API غني للتعامل مع ملفات Microsoft Project برمجيًا. في هذا الدرس، ستتعلم كيفية **تحديث عمل المشروع**، **إعادة جدولة العمل غير المكتمل**، و**حفظ ملف MS Project** بصيغة XML باستخدام Aspose.Tasks for Java.

## إجابات سريعة
- **ماذا يعني “إعادة جدولة العمل غير المكتمل”؟** ينقل أي عمل متبقي في المهمة لتبدأ بعد تاريخ مختار، مع الحفاظ على الأجزاء المكتملة دون تغيير.  
- **ما الطريقة التي تُعلم العمل بأنه مكتمل؟** `project.updateProjectWorkAsComplete(date, false)`.  
- **كيف أحفظ التغييرات؟** استخدم `project.save(<path>, SaveFileFormat.Xml)`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم وجود ترخيص Aspose.Tasks صالح للاستخدام التجاري.  
- **ما نسخة Java المدعومة؟** Java 8 وما بعدها مدعومة بالكامل.

## ما هو “إعادة جدولة العمل غير المكتمل”؟
تقوم إعادة جدولة العمل غير المكتمل بتعديل تواريخ بدء جميع المهام التي لم تُستكمل بعد، حيث يتم دفعها للبدء بعد تاريخ قطع محدد. يكون ذلك مفيدًا عندما يتغير جدول المشروع بسبب تأخيرات أو تغييرات في النطاق.

## لماذا نستخدم Aspose.Tasks لتحديث عمل المشروع وإعادة جدولة المهام؟
- **تحكم دقيق:** ضبط نسب إكمال العمل وتواريخها مباشرة.  
- **لا حاجة لواجهة المستخدم:** أتمتة التحديثات الجماعية عبر العديد من ملفات المشروع.  
- **متعدد المنصات:** يعمل على أي نظام يشغل Java.  
- **يحافظ على سلامة البيانات:** جميع الاعتمادات والقيود والموارد تظل متسقة.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:
1. مجموعة تطوير Java (JDK) مثبتة على نظامك.  
2. مكتبة Aspose.Tasks for Java. يمكنك تنزيلها من [هنا](https://releases.aspose.com/tasks/java/).  
3. فهم أساسي للغة برمجة Java.

## استيراد الحزم
أولاً، استورد الحزم الضرورية في كود Java الخاص بك:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## الخطوة 1: إعداد المشروع
أنشئ كائن `Project` جديدًا، عرّف المهام، حدد المدد، وأسس الاعتمادات. هذا ينشئ مشروع الأساس الذي سنقوم لاحقًا بتحديثه وإعادة جدولته.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## الخطوة 2: تحديث عمل المشروع
علّم العمل كمكتمل حتى تاريخ محدد. تُظهر هذه الخطوة عملية **تحديث عمل المشروع**، والتي غالبًا ما تكون الإجراء الأول قبل إعادة الجدولة.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## الخطوة 3: إعادة جدولة العمل غير المكتمل
الآن نقوم بنقل أي عمل متبقٍ (غير مكتمل) بحيث يبدأ بعد نفس تاريخ القطع. هذه هي الوظيفة الأساسية لـ **إعادة جدولة العمل غير المكتمل**.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## الخاتمة
في هذا الدرس، غطينا كيفية **تحديث عمل المشروع**، **إعادة جدولة العمل غير المكتمل**، و**حفظ ملف MS Project** بصيغة XML باستخدام Aspose.Tasks for Java. هذه القدرات أساسية عندما تحتاج جداول المشروع إلى تعديل بناءً على التقدم الفعلي أو تغير أولويات الأعمال.

## الأسئلة المتكررة
### س: هل يمكن لـ Aspose.Tasks for Java التعامل مع هياكل مشاريع معقدة؟
ج: نعم، توفر Aspose.Tasks for Java واجهات برمجة تطبيقات قوية لإدارة المهام، والاعتمادات، والموارد، وعناصر المشروع الأخرى بكفاءة.  
### س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks for Java؟
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).  
### س: كيف يمكنني الحصول على دعم لـ Aspose.Tasks for Java؟
ج: يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على أي مساعدة أو استفسارات.  
### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks for Java؟
ج: نعم، الترخيصات المؤقتة متاحة للشراء [هنا](https://purchase.aspose.com/temporary-license/).  
### س: أين يمكنني العثور على وثائق مفصلة لـ Aspose.Tasks for Java؟
ج: يمكنك الرجوع إلى الوثائق [هنا](https://reference.aspose.com/tasks/java/) للحصول على أدلة شاملة ومراجع API.

## أسئلة متكررة إضافية

**س: كيف أضمن أن الملف المحفوظ متوافق مع إصدارات Microsoft Project القديمة؟**  
**ج: احفظ المشروع باستخدام `SaveFileFormat.Xml`؛ XML مدعومة على نطاق واسع عبر إصدارات Project.**  

**س: هل يمكنني إعادة جدولة جزء فقط من المهام بدلاً من المشروع بأكمله؟**  
**ج: نعم، يمكنك التكرار على مهام محددة واستدعاء `task.setStart(date)` بعد حساب تاريخ البدء الجديد.**  

**س: ماذا يحدث لتخصيصات الموارد عندما أقوم بإعادة جدولة العمل غير المكتمل؟**  
**ج: يتم نقل تعيينات الموارد تلقائيًا لتتناسب مع تواريخ بدء المهام الجديدة، مع الحفاظ على منطق التخصيص.**  

**س: هل يمكن التراجع عن عملية إعادة الجدولة برمجيًا؟**  
**ج: يمكنك إعادة تحميل ملف المشروع الأصلي (أو نسخة احتياطية) للعودة إلى أي تغييرات.**  

**س: هل يدعم Aspose.Tasks الحفظ إلى صيغ أخرى مثل .mpp؟**  
**ج: بالتأكيد. استخدم `SaveFileFormat.MPP` للحفظ بصيغة Microsoft Project الأصلية.**  

---

**آخر تحديث:** 2026-03-29  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}