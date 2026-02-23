---
date: 2026-02-23
description: استكشف Aspose.Tasks للـ Java لتبسيط إدارة المشاريع، وتعلم كيفية حساب
  نسبة المهمة وتتبع التقدم بكفاءة.
linktitle: Percentage Complete Calculations for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'إدارة المشاريع جافا: نسبة إكمال المهمة باستخدام Aspose.Tasks'
url: /ar/java/task-properties/percentage-complete-calculations/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة المشاريع Java: حساب نسبة إكمال المهمة باستخدام Aspose.Tasks

## المقدمة
مرحبًا بكم في دليلنا الشامل حول **project management java** باستخدام Aspose.Tasks for Java. في هذا البرنامج التعليمي ستتعلم كيفية قراءة ملف Microsoft Project، حساب العمل المكتمل، والحصول على نسب تقدم دقيقة لكل مهمة. إتقان هذه الحسابات يساعدك على إبقاء أصحاب المصلحة على اطلاع ويضمن بقاء مشروعك على الجدول الزمني.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع ملفات Microsoft Project في Java؟** Aspose.Tasks for Java.  
- **أي خاصية تُظهر التقدم الكلي؟** `Tsk.PERCENT_COMPLETE`.  
- **كيف أقوم بقراءة ملف .mpp؟** قم بتحميله باستخدام `new Project(filePath)`.  
- **هل يمكنني حساب العمل المكتمل؟** نعم، استخدم `Tsk.PERCENT_WORK_COMPLETE`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم وجود ترخيص Aspose.Tasks صالح.

## ما هو Project Management Java؟
يشير Project management java إلى استخدام أدوات ومكتبات مبنية على Java — مثل Aspose.Tasks — لإنشاء، قراءة، وتعديل جداول المشاريع برمجيًا. يتيح هذا النهج إعداد تقارير آلية، لوحات معلومات مخصصة، وتكامل سلس مع تطبيقات Java الحالية.

## لماذا تستخدم Aspose.Tasks لحساب نسبة إكمال المهمة؟
- **تتبع تقدم دقيق** – استرجاع حقول Project الأصلية دون تحليل يدوي.  
- **دعم كامل لملفات .mpp** – قراءة، تعديل، وحفظ ملفات Microsoft Project مباشرة.  
- **أتمتة قابلة للتوسع** – معالجة آلاف المهام في ثوانٍ، مثالية للمحافظ الكبيرة.  
- **متعدد المنصات** – يعمل على أي بيئة تشغيل Java، من سطح المكتب إلى خدمات السحابة.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من أن لديك:

- **Java Development Kit (JDK)** مثبت (Java 8 أو أحدث).  
- **Aspose.Tasks for Java** المكتبة – قم بتنزيلها من [this link](https://releases.aspose.com/tasks/java/).  
- ملف Microsoft Project تجريبي (مثال: *Software Development.mpp*) موضوع في دليل معروف.

## استيراد الحزم
أولاً، استورد الفئات التي ستحتاجها. يجب إضافة هذا المقتطف إلى أي فئة Java تتعامل مع Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```

### الخطوة 1: تعيين دليل المستند
حدد المجلد الذي يحتوي على ملف *.mpp* الخاص بك. استبدل العنصر النائب بالمسار الفعلي على جهازك.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### الخطوة 2: تحميل ملف المشروع
أنشئ كائن `Project` وحمّل ملف Microsoft Project. هذه الخطوة **تقرأ ملف Microsoft Project** حتى تتمكن من الوصول إلى مهامه.

```java
Project project = new Project(dataDir + "Software Development.mpp");
```

### الخطوة 3: استرجاع مجموعة المهام
احصل على المهمة الجذرية ثم مهامها الفرعية. تمثل هذه المجموعة جميع المهام ذات المستوى العلوي في المشروع.

```java
TaskCollection alTasks = project.getRootTask().getChildren();
```

### الخطوة 4: طباعة قيم نسبة الإكمال
تكرار عبر كل مهمة وعرض ثلاث مقاييس رئيسية للتقدم:

- **Percentage Complete** – تقدم المهمة الإجمالي.  
- **Percentage Work Complete** – التقدم بناءً على العمل.  
- **Physical Percentage Complete** – التقدم الفعلي (إذا تم ضبطه).

```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```

شغّل هذه الحلقة لكل مهمة تحتاج إلى مراقبتها. يعطيك الناتج لمحة واضحة عن **كيفية الحصول على التقدم** لكل عنصر عمل.

## حالات الاستخدام الشائعة
- **تقارير لوحة القيادة:** سحب النسب وإدخالها في أدوات ذكاء الأعمال.  
- **تنبيهات آلية:** تفعيل الإشعارات عندما ينخفض `PERCENT_COMPLETE` للمهمة عن حد معين.  
- **تسوية الموارد:** تعديل التعيينات بناءً على `PERCENT_WORK_COMPLETE` للحفاظ على جدولة واقعية.

## استكشاف الأخطاء والنصائح
- **قيم Null:** تأكد من أن ملف المشروع يحتوي فعليًا على الحقول التي تستعلم عنها؛ قد تفتقر بعض ملفات .mpp القديمة إلى `PHYSICAL_PERCENT_COMPLETE`.  
- **الأداء:** للمشاريع الكبيرة جدًا، فكر في تقسيم `TaskCollection` إلى صفحات أو تصفية حسب معرف المهمة لتقليل استهلاك الذاكرة.  
- **أخطاء الترخيص:** إذا رأيت تحذيرات ترخيص، تحقق من تحميل ملف ترخيص Aspose.Tasks صالح قبل إنشاء كائن `Project`.

## الأسئلة المتكررة

**س: أين يمكنني العثور على وثائق Aspose.Tasks؟**  
ج: الوثائق متاحة [here](https://reference.aspose.com/tasks/java/).

**س: كيف يمكنني تنزيل مكتبة Aspose.Tasks للـ Java؟**  
ج: يمكنك تنزيلها [here](https://releases.aspose.com/tasks/java/).

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية [here](https://releases.aspose.com/).

**س: أين يمكنني الحصول على دعم Aspose.Tasks؟**  
ج: زر منتدى الدعم [here](https://forum.aspose.com/c/tasks/15).

**س: كيف أحصل على ترخيص مؤقت؟**  
ج: يمكنك الحصول على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/).

**أسئلة وإجابات إضافية**

**س: هل يمكنني حساب نسبة إكمال المهمة بدون Aspose.Tasks؟**  
ج: يمكنك تحليل ملف .mpp الثنائي بنفسك، لكن Aspose.Tasks يوفر API موثوقًا ومدعومًا بالكامل يتعامل مع جميع الحالات الخاصة.

**س: هل يدعم Aspose.Tasks قراءة ملفات Project Online؟**  
ج: نعم، يمكنك تحميل الملفات المصدرة من Project Online طالما أنها محفوظة بصيغة .mpp.

---

**آخر تحديث:** 2026-02-23  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}