---
date: 2026-01-28
description: تعلم كيفية قراءة سمات المهمة الموسعة باستخدام Aspose.Tasks للغة Java
  وتبديل نوع الحقل المخصص بكفاءة.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: قراءة سمات المهمة الموسَّعة باستخدام Aspose.Tasks للغة Java
url: /ar/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة سمات المهمة الموسعة باستخدام Aspose.Tasks للـ Java

## المقدمة
في هذا الدليل الشامل ستكتشف كيفية **قراءة سمات المهمة الموسعة** من ملفات Microsoft Project باستخدام مكتبة Aspose.Tasks للـ Java. سواءً كنت تبني أداة تقارير، أو تقوم بمزامنة البيانات، أو تحتاج ببساطة إلى رؤية أعمق للحقول المخصصة، فإن إتقان هذه الميزة سيمكنك من استخراج كل قطعة من المعلومات المخزنة في المشروع. سنستعرض الإعداد المطلوب، ونوضح لك كيفية تبديل نوع الحقل المخصص عند معالجة السمات، ونقدم لك نصائح عملية لتجنب المشكلات الشائعة.

## إجابات سريعة
- **ماذا يعني “قراءة سمات المهمة الموسعة”؟** يشير إلى استخراج قيم الحقول المخصصة التي تتجاوز خصائص المهمة الافتراضية في ملف المشروع.  
- **أي فئة توفر الوصول إلى هذه السمات؟** فئة `ExtendedAttribute` في Aspose.Tasks.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكنني تغيير نوع السمة أثناء التشغيل؟** نعم – استخدم جملة `switch` لت **تبديل نوع الحقل المخصص** بناءً على `CustomFieldType`.  
- **هل هذا متوافق مع Java 8 وما بعده؟** بالتأكيد، الـ API يدعم JDK 8+.

## ما هي قراءة سمات المهمة الموسعة؟
سمات المهمة الموسعة هي حقول يحددها المستخدم (نص، تاريخ، رقم، علم، إلخ) تُضيف إلى خصائص المهمة القياسية في Microsoft Project. تُظهرها Aspose.Tasks من خلال مجموعة `ExtendedAttribute` المرتبطة بكل كائن `Task`، مما يتيح لك قراءة أو تعديل قيمها برمجيًا.

## لماذا نقرأ سمات المهمة الموسعة؟
- **رؤية كاملة:** احصل على نظرة عميقة للبيانات المخصصة التي أضافها أصحاب المصلحة إلى الجدول الزمني.  
- **الأتمتة:** املأ لوحات المعلومات، أنشئ تقارير مخصصة، أو انقل البيانات إلى أنظمة أخرى دون تصدير يدوي.  
- **المرونة:** تعامل مع أي نوع حقل مخصص—نص، تاريخ، مدة، تكلفة، علم—من خلال معالجة كل حالة بشكل مناسب.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:
- معرفة أساسية ببرمجة Java.  
- مجموعة تطوير Java (JDK) مثبتة على جهازك.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.  

## استيراد الحزم
ابدأ باستيراد الفئات الضرورية لمشروع Aspose.Tasks:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## الخطوة 1: الوصول إلى المهمة والسمات الموسعة
حمّل ملف Project وتجوّل عبر كل مهمة للوصول إلى سماتها الموسعة:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## الخطوة 2: استرجاع معرف الحقل وGUID القيمة
اطبع المعرفات الداخلية التي تساعدك على فهم الحقل المخصص الذي تتعامل معه:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## الخطوة 3: كيفية تبديل نوع الحقل المخصص عند قراءة سمات المهمة الموسعة
استخدم جملة `switch` على `CustomFieldType` لمعالجة كل نوع بيانات محتمل بشكل صحيح:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

كرر هذه الخطوات لكل مهمة في مشروعك لاستكشاف وتعديل كل سمة مهمة موسعة.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **إرجاع قيم فارغة** | تحقق من أن الحقل المخصص مُعبأ فعليًا في ملف .mpp المصدر. |
| **عرض نوع غير صحيح** | تأكد من أنك تستخدم `CustomFieldType` المناسب في جملة `switch`؛ الأنواع غير المتطابقة ستؤدي إلى قيم افتراضية. |
| **تباطؤ الأداء في المشاريع الكبيرة** | عالج المهام على دفعات أو صَفِّ فقط المهام التي تحتاجها باستخدام `project.getRootTask().getChildren().stream()` مع الشروط المناسبة. |

## الأسئلة المتكررة
### هل يمكنني تعديل سمات المهمة الموسعة برمجيًا؟
نعم، يمكنك تعديل سمات المهمة الموسعة باستخدام Aspose.Tasks للـ Java. راجع الوثائق للحصول على تعليمات مفصلة.

### هل هناك نسخة تجريبية متاحة؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الدعم لـ Aspose.Tasks للـ Java؟
للحصول على الدعم، زر منتدى [Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### كيف يمكنني الحصول على ترخيص مؤقت؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني شراء النسخة الكاملة من Aspose.Tasks للـ Java؟
يمكنك شراء النسخة الكاملة [هنا](https://purchase.aspose.com/buy).

---

**آخر تحديث:** 2026-01-28  
**تم الاختبار مع:** Aspose.Tasks Java API (أحدث إصدار ثابت)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}