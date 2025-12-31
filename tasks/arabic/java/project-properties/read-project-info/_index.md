---
date: 2025-12-31
description: تعلم كيفية قراءة معلومات المشروع، بما في ذلك الجدول الزمني من البداية،
  باستخدام Aspose.Tasks للغة Java. اكتشف كيفية استخراج خصائص المشروع في Java بسرعة.
linktitle: Read Project Info with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية قراءة معلومات المشروع من Microsoft Project باستخدام Aspose.Tasks لجافا
url: /ar/java/project-properties/read-project-info/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قراءة معلومات المشروع من Microsoft Project باستخدام Aspose.Tasks for Java

## مقدمة
إذا كنت بحاجة إلى **how to read project** تفاصيل مثل تواريخ البدء، تواريخ الانتهاء، أو إعدادات التقويم مباشرةً من ملف Microsoft Project، فإن Aspose.Tasks for Java توفر لك نهجًا نظيفًا يعتمد على الشيفرة أولاً. في هذا البرنامج التعليمي ستشاهد بالضبط **how to read project** البيانات الوصفية، وتفهم **project schedule from start**، وتتعلم سحب خصائص أخرى رئيسية—كل ذلك خلال بضع أسطر من كود Java.

## إجابات سريعة
- **What does Aspose.Tasks for Java do?** يتيح الوصول البرمجي إلى ملفات Microsoft Project (MPP، XML، إلخ) دون الحاجة إلى تثبيت Microsoft Project.  
- **Which property tells if the schedule is based on start?** `Prj.SCHEDULE_FROM_START` – true يعني جدولة من البداية، false يعني من النهاية.  
- **Can I extract project properties in Java?** نعم، يمكنك قراءة تاريخ البدء، تاريخ الانتهاء، التاريخ الحالي، تاريخ الحالة، واسم التقويم.  
- **Do I need a license for development?** ترخيص مؤقت مجاني يكفي للتقييم؛ ترخيص كامل مطلوب للإنتاج.  
- **What Java version is required?** Java 8 أو أعلى مع وجود ملف Aspose.Tasks JAR في مسار الفئات.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من أن لديك:

1. **Java Development Environment** – JDK 8 أو أحدث مثبت ومُكوَّن.  
2. **Aspose.Tasks for Java** – قم بتنزيل أحدث مكتبة من الـ[الموقع](https://releases.aspose.com/tasks/java/).  

## استيراد الحزم
للتفاعل مع ملفات المشروع، استورد مساحة الأسماء الأساسية لـ Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## دليل خطوة بخطوة

### الخطوة 1: تحديد دليل البيانات
حدد المجلد الذي يحتوي على ملف `.mpp` الخاص بك. استبدل العنصر النائب بالمسار الفعلي على جهازك.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 2: تحميل ملف المشروع
أنشئ كائن `Project` بتحميل ملف Microsoft Project الذي تريد فحصه.

```java
Project project = new Project(dataDir + "ReadProjectInfo.mpp");
```

### الخطوة 3: تحديد أساس جدول المشروع
تحقق مما إذا كان الجدول محسوبًا من تاريخ بدء المشروع أو من تاريخ الانتهاء. هذا هو جوهر **how to read project** معلومات الجدولة.

```java
if (project.get(Prj.SCHEDULE_FROM_START).getValue()) {
    System.out.println("Project Start Date: " + project.get(Prj.START_DATE));
} else {
    System.out.println("Project Finish Date: " + project.get(Prj.FINISH_DATE));
}
```

> **نصيحة احترافية:** `Prj.SCHEDULE_FROM_START` تُعيد قيمة منطقية؛ `true` يعني *جدولة المشروع من البداية*.

### الخطوة 4: استرجاع معلومات إضافية عن جدول المشروع
إلى جانب تواريخ البدء/الانتهاء، غالبًا ما تحتاج إلى التاريخ الحالي، تاريخ الحالة، والتقويم المرتبط بالمشروع. هذا يوضح **read project properties java** عمليًا.

```java
String strSchdl = (project.get(Prj.SCHEDULE_FROM_START).getValue()) ? "Project Start Date" : "Project Finish Date";
System.out.println("Project Schedule From: " + strSchdl);
System.out.println("Current Date: " + project.get(Prj.CURRENT_DATE));
System.out.println("Status Date: " + project.get(Prj.STATUS_DATE));
System.out.println("Calendar: " + project.get(Prj.CALENDAR).getName());
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| `NullPointerException` on `project.get(Prj.CALENDAR)` | ملف المشروع يفتقد تقويمًا افتراضيًا. | تأكد من أن ملف MPP يحدد تقويمًا أو عالج فحوصات `null`. |
| Dates printed as `null` | ملف المشروع تالف أو يفتقد حقول التاريخ. | تحقق من صحة ملف المصدر في Microsoft Project قبل المعالجة. |
| Compilation error: `cannot find symbol Prj` | ملف Aspose.Tasks JAR غير موجود في مسار الفئات. | أضف `aspose-tasks-xx.jar` إلى مسار بناء مشروعك. |

## الأسئلة المتكررة

### س: هل يمكنني استخدام Aspose.Tasks for Java مع أي إصدار من ملفات Microsoft Project؟
ج: نعم، يدعم Aspose.Tasks for Java إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك صيغ MPP و XML.

### س: هل Aspose.Tasks for Java متوافق مع جميع بيئات تطوير Java؟
ج: نعم، Aspose.Tasks for Java متوافق مع معظم بيئات تطوير Java، مما يضمن مرونة في التكامل.

### س: هل يوفر Aspose.Tasks for Java دعمًا للتعامل مع بيانات المشروع بما يتجاوز قراءة المعلومات؟
ج: بالطبع، يقدم Aspose.Tasks for Java وظائف واسعة للتعامل مع بيانات المشروع، بما في ذلك التحرير، الحفظ، والتصدير.

### س: هل يمكنني أتمتة استخراج معلومات المشروع باستخدام Aspose.Tasks for Java؟
ج: نعم، يتيح Aspose.Tasks for Java الأتمتة عبر API الشامل الخاص به، مما يمكّن من عمليات مبسطة لاستخراج البيانات وتحليلها.

### س: هل هناك منتدى مجتمع أو قناة دعم متاحة لمستخدمي Aspose.Tasks for Java؟
ج: نعم، يمكنك العثور على موارد مفيدة والتفاعل مع المجتمع على الـ[منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### س: كيف يمكنني قراءة خصائص المشروع في Java دون تحميل شجرة المهام بالكامل؟
ج: استخدم طريقة `Project.get` مع قيم تعداد `Prj` المطلوبة؛ هذا يسترجع فقط البيانات الوصفية المطلوبة، مما يحافظ على انخفاض استهلاك الذاكرة.

### س: ما هي أفضل طريقة للتعامل مع ملفات MPP الكبيرة عند استخراج الخصائص؟
ج: حمّل المشروع في وضع *للقراءة فقط* (`new Project(filePath, LoadOptions)`) واستعلم فقط عن الخصائص المطلوبة لتجنب استهلاك الذاكرة العالي.

## الخلاصة
باتباع هذا الدليل، أصبحت الآن تعرف **how to read project** معلومات مثل أصل الجدول، التواريخ، وتفاصيل التقويم باستخدام Aspose.Tasks for Java. دمج هذه المقاطع في تطبيقاتك يتيح تقارير آلية، لوحات تحكم مخصصة، واتخاذ قرارات أذكى دون تفاعل يدوي مع Microsoft Project.

---

**آخر تحديث:** 2025-12-31  
**تم الاختبار مع:** Aspose.Tasks for Java 24.10  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}