---
date: 2026-03-29
description: تعلم كيفية تغيير عدد الأيام في كل شهر وإدارة خصائص أيام الأسبوع الأخرى
  في Aspose.Tasks للغة Java. خصّص تواريخ بدء الأسبوع، عدّل تقويم المشروع، واحفظ المشروع
  كملف XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: تغيير عدد الأيام في الشهر باستخدام خصائص أيام الأسبوع في Aspose.Tasks
url: /ar/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تغيير عدد الأيام في الشهر باستخدام خصائص أيام الأسبوع في Aspose.Tasks

## مقدمة
تتيح لك Aspose.Tasks for Java **تغيير عدد الأيام في الشهر** وضبط إعدادات أيام الأسبوع الأخرى دون الحاجة إلى تثبيت Microsoft Project. سواءً كنت تقوم بمواءمة تقويم المشروع مع شهر مالي غير قياسي أو تحتاج ببساطة إلى تعديل يوم بدء الأسبوع، فإن هذا البرنامج التعليمي يشرح لك أكثر السيناريوهات شيوعًا — استرجاع يوم بدء الأسبوع الحالي، تخصيص تاريخ بدء الأسبوع، تعديل تقويم المشروع، وحفظ المشروع كملف XML.

## إجابات سريعة
- **هل يمكنني تغيير عدد الأيام في الشهر؟** نعم، استخدم `Prj.DAYS_PER_MONTH` على كائن `Project`.  
- **كيف يمكنني تخصيص تاريخ بدء الأسبوع؟** اضبط `Prj.WEEK_START_DAY` إلى قيمة `DayType` (مثال: `DayType.Monday`).  
- **ما الصيغة التي يمكنني استخدامها لتصدير المشروع؟** المثال يحفظ الملف كملف XML باستخدام `SaveFileFormat.Xml`.  
- **هل يلزم وجود ترخيص للاستخدام في الإنتاج؟** يلزم وجود ترخيص صالح لـ Aspose.Tasks للنشر غير التجريبي.  
- **ما هي بيئات التطوير المتكاملة المدعومة؟** أي بيئة تطوير Java مثل IntelliJ IDEA أو Eclipse أو NetBeans تعمل.

## ما هو “تغيير عدد الأيام في الشهر” في Aspose.Tasks؟
يعني تغيير عدد الأيام في الشهر تحديث الخاصية `Prj.DAYS_PER_MONTH` لكائن `Project`. تخبر هذه الخاصية المحرك بعدد أيام العمل التي يجب أن يعتبرها في كل شهر، مما يؤثر مباشرة على جدولة المهام وحساب التكاليف.

## لماذا تعديل خصائص تقويم المشروع؟
تخصيص تقويم المشروع — مثل تعيين يوم بدء أسبوع مختلف أو تعديل الدقائق في اليوم — يساعدك على:
- مواءمة الجداول مع أسابيع العمل الإقليمية.  
- نمذجة أنماط العمل غير القياسية (مثال: أسابيع من 4 أيام).  
- ضمان تقارير دقيقة للعقود التي تستخدم تقاويم مخصصة.

## المتطلبات المسبقة
- **Java Development Kit (JDK)** – قم بتثبيت أحدث JDK من Oracle.  
- **Aspose.Tasks for Java library** – قم بتنزيله من الموقع الرسمي [هنا](https://releases.aspose.com/tasks/java/).  
- **IDE من اختيارك** – IntelliJ IDEA أو Eclipse أو NetBeans.

## استيراد الحزم
أولاً، استورد الفئات الأساسية في Aspose.Tasks:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## الخطوة 1: تحميل ملف المشروع
يقوم هذا بتحميل ملف Microsoft Project موجود (`project.mpp`) من المجلد الذي تحدده.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## الخطوة 2: عرض خصائص أيام الأسبوع
هنا نسترجع ونطبع إعدادات أيام الأسبوع الحالية، بما في ذلك **يوم بدء الأسبوع** و**عدد الأيام في الشهر**.

```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```

## الخطوة 3: تعيين خصائص أيام الأسبوع
في هذه الخطوة نقوم **بتغيير عدد الأيام في الشهر** إلى 24، وتعيين بدء الأسبوع يوم الاثنين، وتعديل الدقائق في اليوم/الأسبوع. هذا يوضح كيفية **تعديل تقويم المشروع** برمجيًا.

```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```

## الخطوة 4: حفظ المشروع
يتم حفظ المشروع المعدل باستخدام صيغة **حفظ المشروع كملف XML**، وهو مفيد للتكامل مع أدوات أخرى أو لتخزين خاضع للتحكم بالإصدارات.

```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```

## الخطوة 5: عرض النتيجة
تأكيد بسيط على أن العمليات انتهت دون أخطاء.

```java
System.out.println("Process completed Successfully");
```

## كيفية تخصيص تاريخ بدء الأسبوع
إذا كانت مؤسستك تتبع تقويم يبدأ بالأحد، استبدل `DayType.Monday` بـ `DayType.Sunday`. تُستخدم نفس الخاصية (`Prj.WEEK_START_DAY`)، مما يجعل التغيير بسيطًا.

## كيفية استرجاع يوم بدء الأسبوع
يمكنك استدعاء `project.get(Prj.WEEK_START_DAY)` في أي وقت لاسترجاع معلومات **يوم بدء الأسبوع**، كما هو موضح في الخطوة 2.

## كيفية تعديل تقويم المشروع
إلى جانب يوم بدء الأسبوع، يمكنك أيضًا تعديل `Prj.MINUTES_PER_DAY` و `Prj.MINUTES_PER_WEEK` لتعكس ساعات عمل مخصصة أو أنماط نوبات.

## المشكلات الشائعة والحلول
- **قيمة نوع اليوم غير صحيحة** – تأكد من استخدام تعداد `DayType` (مثال: `DayType.Monday`).  
- **أخطاء مسار الملف** – تحقق من أن `dataDir` ينتهي بالفاصل المناسب للملفات (`/` أو `\`).  
- **لم يتم تعيين الترخيص** – إذا رأيت تحذيرات الترخيص، سجّل ترخيص Aspose.Tasks الخاص بك قبل إنشاء كائن `Project`.

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks for Java التعامل مع هياكل مشاريع معقدة؟**  
**ج:** نعم، توفر Aspose.Tasks for Java دعمًا شاملاً للتعامل مع هياكل المشاريع المعقدة بسهولة.

**س: هل Aspose.Tasks for Java متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟**  
**ج:** بالتأكيد، يدعم Aspose.Tasks for Java إصدارات متعددة من ملفات Microsoft Project، مما يضمن التوافق عبر المنصات.

**س: هل يمكنني دمج Aspose.Tasks for Java في تطبيقاتي الجافا الحالية؟**  
**ج:** نعم، يقدم Aspose.Tasks for Java إمكانيات دمج سلسة، مما يتيح لك تعزيز تطبيقات الجافا الخاصة بك بميزات إدارة مشاريع قوية.

**س: هل يوفر Aspose.Tasks for Java وثائق ودعمًا؟**  
**ج:** نعم، يمكنك الوصول إلى وثائق واسعة ودعم المجتمع لـ Aspose.Tasks for Java على موقعهم [الويب](https://releases.aspose.com/).

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks for Java؟**  
**ج:** نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks for Java من موقعهم [الويب](https://reference.aspose.com/tasks/java/) لاستكشاف ميزاته قبل الشراء.

---

**آخر تحديث:** 2026-03-29  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}