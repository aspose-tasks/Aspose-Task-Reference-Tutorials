---
date: 2026-02-26
description: تعلم كيفية استئناف المهمة وإيقافها في Aspose.Tasks للـ Java، بما في ذلك
  تصفية المهام حسب التاريخ للتحكم الدقيق في المشروع.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية استئناف المهمة وإيقاف المهمة في Aspose.Tasks
url: /ar/java/task-properties/stop-resume-task/
weight: 30
---

 Task and Stop Task in Aspose.Tasks" translate to Arabic: "# كيفية استئناف المهمة وإيقاف المهمة في Aspose.Tasks"

Similarly subheadings.

Proceed.

Translate bullet points.

In tables, translate each cell.

Make sure not to translate URLs.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استئناف المهمة وإيقاف المهمة في Aspose.Tasks

## مقدمة
إذا كنت تبني حلاً لإدارة المشاريع يعتمد على Java، فستحتاج غالبًا إلى **إيقاف** مهمة مؤقتًا ثم **متابعتها** لاحقًا. تجعل لك Aspose.Tasks for Java ذلك سهلًا عبر خصائص مدمجة لإيقاف واستئناف المهام. في هذا البرنامج التعليمي ستتعرف على **كيفية استئناف المهمة** و**كيفية إيقاف المهمة** برمجيًا، وسترى أيضًا كيفية **تصفية المهام حسب التاريخ** لتعمل فقط على العناصر ذات الصلة في جدولك الزمني.

## إجابات سريعة
- **ماذا يعني “إيقاف” المهمة؟** يحدد تاريخ إيقاف، مما يوقف العمل بعد تلك النقطة.  
- **كيف يمكنني استئناف مهمة موقوفة؟** عن طريق تعيين تاريخ استئناف يكون لاحقًا لتاريخ الإيقاف.  
- **هل يمكنني حصر العملية ضمن نطاق تاريخ معين؟** نعم – استخدم تاريخًا حدًا أدنى لتصفية المهام.  
- **ما نسخة المكتبة المطلوبة؟** أي إصدار حديث من Aspose.Tasks for Java (واجهة البرمجة ثابتة).  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للاختبار؛ الترخيص مطلوب للإنتاج.

## ما هو “كيفية استئناف المهمة” في Aspose.Tasks؟
استئناف المهمة يعني ببساطة توفير تاريخ **RESUME** على كائن `Task`. عندما يعالج محرك المشروع الجدول الزمني، سيستمر العمل من ذلك التاريخ فصاعدًا. هذا مفيد بشكل خاص للتعامل مع الانقطاعات مثل عدم توفر الموارد أو الاعتماديات الخارجية.

## لماذا نستخدم ميزة الإيقاف/الاستئناف؟
- **التحكم في الجداول الزمنية:** إيقاف العمل دون حذف المهمة.  
- **تقارير دقيقة:** إظهار تواريخ بدء/انتهاء واقعية في مخططات جانت.  
- **أتمتة سهلة:** دمج مع فلاتر التاريخ لتحديث العديد من المهام دفعة واحدة.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

- فهم قوي لأساسيات Java.  
- تثبيت JDK على جهازك.  
- إضافة مكتبة Aspose.Tasks for Java إلى مشروعك (حمّلها من [هنا](https://releases.aspose.com/tasks/java/)).  

## استيراد الحزم
أولاً، استورد الفئات المطلوبة لتتمكن من العمل مع المشاريع والمهام.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## الخطوة 1: تهيئة المشروع وجامع المهام
أنشئ كائن `Project` يشير إلى ملف MPP الخاص بك، وأعدد `ChildTasksCollector` لجمع كل مهمة في الهيكل الهرمي.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## الخطوة 2: تعريف تاريخ حد أدنى للتصفية
إذا كنت تريد العمل فقط على المهام التي لديها تواريخ إيقاف أو استئناف ذات معنى، عرّف **تاريخ حد أدنى**. هذا هو جوهر تقنية *تصفية المهام حسب التاريخ*.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## الخطوة 3: التكرار، الفحص، وعرض قيم الإيقاف/الاستئناف
الآن قم بالتكرار عبر المهام المجمعة، طبّق منطق **كيفية إيقاف المهمة**، واطبع التواريخ. يوضح الكود أيضًا **كيفية استئناف المهمة** بقراءة خاصية `RESUME`.

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **نصيحة احترافية:** استبدل استدعاءات `System.out.println` بمنطقك الخاص (مثل تحديث التواريخ، أو تسجيلها في ملف، أو تعديل كائنات المهمة) لتقوم فعليًا *بإيقاف* أو *استئناف* المهام حسب الحاجة.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| `NullPointerException` على `tsk.get(Tsk.STOP)` | لم يتم تعيين تاريخ إيقاف للمهمة. | تحقق من وجود `null` قبل استدعاء `.before(minDate)`. |
| التواريخ تظهر كـ `NA` حتى بعد التعيين | تاريخ الحد الأدنى حديث جدًا. | استخدم `minDate` أقدم أو أزل الفلتر. |
| التغييرات لا تظهر في ملف MPP المحفوظ | لم يتم حفظ المشروع بعد التعديل. | استدعِ `project.save("output.mpp");` بعد تحديث المهام. |

## الأسئلة المتكررة

### هل Aspose.Tasks for Java مناسبة للمشاريع الكبيرة؟
بالطبع! تم تصميم Aspose.Tasks for Java للتعامل مع مشاريع بأحجام مختلفة، مع ضمان الكفاءة والموثوقية.

### هل يمكنني تخصيص تاريخ الإيقاف والاستئناف للمهام؟
نعم، يتيح المثال المقدم مرونة في تعيين تاريخ الحد الأدنى وفقًا لمتطلبات مشروعك.

### أين يمكنني العثور على دعم إضافي لـ Aspose.Tasks for Java؟
تفضل بزيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على دعم المجتمع والنقاشات.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks for Java؟
نعم، يمكنك الوصول إلى [النسخة التجريبية](https://releases.aspose.com/) لاستكشاف الميزات قبل الشراء.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks for Java؟
يمكنك الحصول على ترخيص مؤقت [من هنا](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار.

**أسئلة وإجابات إضافية**

**س: كيف يمكنني تعيين تاريخ إيقاف جديد لمهمة؟**  
ج: استخدم `tsk.set(Tsk.STOP, new Date(...));` ثم احفظ المشروع.

**س: هل يمكنني تصفية المهام بنطاق تاريخ محدد بدلاً من حد أدنى فقط؟**  
ج: نعم—قارن كل من `before` و `after` مع تواريخ البداية والنهاية الخاصة بك.

**س: هل تقوم API بإعادة حساب الجدول الزمني تلقائيًا بعد تغيير تواريخ الإيقاف/الاستئناف؟**  
ج: بعد تعديل التواريخ، استدعِ `project.calculateCriticalPath();` لتحديث الجدول الزمني.

## الخاتمة
في هذا الدليل غطينا **كيفية استئناف المهمة** و**كيفية إيقاف المهمة** باستخدام Aspose.Tasks for Java، بالإضافة إلى طريقة عملية **لتصفية المهام حسب التاريخ**. من خلال دمج هذه المقاطع في تطبيقك، ستحصل على تحكم دقيق في جداول المشروع وتستطيع أتمتة تعديل الجداول الزمنية بثقة.

---

**آخر تحديث:** 2026-02-26  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}