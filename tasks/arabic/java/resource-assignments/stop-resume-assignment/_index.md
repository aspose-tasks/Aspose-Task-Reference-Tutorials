---
date: 2026-01-10
description: تعلم كيفية إيقاف التعيين، وإدارة تعيينات الموارد، وعرض مثال لتعيين الموارد
  في Aspose.Tasks للغة Java من خلال هذا الدليل خطوة بخطوة.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية إيقاف التعيين واستئناف تعيين الموارد في Aspose.Tasks
url: /ar/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إيقاف التعيين واستئناف تعيينات الموارد في Aspose.Tasks

## المقدمة
في هذا البرنامج التعليمي، **ستكتشف كيفية إيقاف التعيين** ثم استئنافه لاحقًا باستخدام Aspose.Tasks للـ Java. Aspose.Tasks هي واجهة برمجة تطبيقات Java قوية تتيح لك قراءة ملفات المشروع بصيغ Java، ومعالجة بيانات Microsoft Project، وإدارة تعيينات الموارد دون الحاجة إلى تثبيت Microsoft Project. سنستعرض كل خطوة، نشرح لماذا كل سطر مهم، ونقدم لك نصائح عملية يمكنك تطبيقها على مشاريع العالم الحقيقي.

## إجابات سريعة
- **ماذا يعني “إيقاف التعيين”؟** يعني وضع علامة على تعيين المورد كغير نشط مؤقتًا اعتبارًا من تاريخ إيقاف محدد.  
- **هل يمكنني استئناف نفس التعيين لاحقًا؟** نعم، عن طريق تعيين تاريخ استئناف على نفس التعيين.  
- **هل أحتاج إلى Microsoft Project لاستخدام هذه الواجهة؟** لا، Aspose.Tasks تعمل بشكل مستقل عن Microsoft Project.  
- **ما نسخة Java المطلوبة؟** يُنصح باستخدام Java 8 أو أعلى.  
- **أين يمكنني تنزيل المكتبة؟** من صفحة تنزيل Aspose.Tasks Java الرسمية.

## ما هو “إيقاف التعيين” في سياق Aspose.Tasks؟
إيقاف التعيين يخبر المجدول بتجاهل العمل المخصص لمورد بعد **تاريخ الإيقاف** حتى **تاريخ الاستئناف** (إن وجد). هذا مفيد للتعامل مع الإجازات، توقف المعدات، أو أي فترة لا ينبغي اعتبار المورد نشطًا خلالها.

## لماذا نستخدم Aspose.Tasks لإدارة تعيينات الموارد؟
- **لا حاجة لـ Microsoft Project** – العمل مباشرةً مع ملفات .mpp.  
- **تحكم كامل في التواريخ** – يمكنك فحص تاريخ الإيقاف، تاريخ الاستئناف، وتعديلهما برمجيًا.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.  
- **واجهة برمجة تطبيقات غنية** – توفر *مثالًا على تعيين الموارد* يمكنك توسيعه للتقارير المخصصة.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

- مجموعة تطوير Java (JDK) مثبتة على نظامك.  
- مكتبة Aspose.Tasks للـ Java تم تنزيلها. يمكنك تنزيلها من [هنا](https://releases.aspose.com/tasks/java/).  
- فهم أساسي لبرمجة Java.  

## استيراد الحزم
أولًا، لنستورد الحزم الضرورية إلى مشروع Java الخاص بنا:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## الخطوة 1: تحميل ملف المشروع
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

هنا نقوم **بقراءة ملف المشروع بصيغة Java** (`.mpp`) وننشئ كائن `Project` يمنحنا الوصول إلى جميع بيانات المشروع، بما في ذلك تعيينات الموارد.

## الخطوة 2: التجول عبر تعيينات الموارد
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

نحدد **تاريخًا أدنى** لتصفية تواريخ الحجز الافتراضية ثم نمر على كل تعيين. هذا هو النمط المعتاد *لمثال تعيين الموارد* المستخدم عندما تحتاج إلى فحص أو تعديل التعيينات.

## الخطوة 3: فحص تواريخ الإيقاف والاستئناف
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

في هذا الجزء ن **نفحص تاريخ الإيقاف** و **ننفحص تاريخ الاستئناف** لكل تعيين. إذا كان التاريخ قبل `minDate`، نتعامل معه كغير محدد (`"NA"`); وإلا نطبع التاريخ الفعلي. هذه المنطقية أساسية لإدارة تعيينات الموارد بشكل صحيح.

## المشكلات الشائعة والحلول
- **تواريخ فارغة** – قد تُعيد `ra.get(Asn.STOP)` القيمة `null`. احرص على إضافة فحص `null` قبل استدعاء `.before(minDate)`.  
- **مسار ملف غير صحيح** – تأكد من أن `dataDir` ينتهي بفاصل مسار (`/` أو `\\`) المناسب لنظام التشغيل الخاص بك.  
- **عدم توافق الإصدارات** – استخدم أحدث نسخة من Aspose.Tasks للـ Java لتجنب فقدان قيم التعداد.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Tasks دون تثبيت Microsoft Project؟
نعم، تتيح لك Aspose.Tasks العمل مع ملفات Microsoft Project دون الحاجة إلى تثبيت البرنامج.

### أين يمكنني العثور على مزيد من الوثائق؟
يمكنك العثور على الوثائق التفصيلية [هنا](https://reference.aspose.com/tasks/java/).

### هل هناك نسخة تجريبية مجانية؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على الدعم إذا واجهت أي مشاكل؟
يمكنك الحصول على الدعم من المجتمع [هنا](https://forum.aspose.com/c/tasks/15).

### هل يمكنني شراء ترخيص مؤقت؟
نعم، يمكنك شراء ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

## الأسئلة الشائعة

**س: كيف يمكنني برمجيًا تعيين تاريخ إيقاف لتعيين؟**  
ج: استخدم `ra.set(Asn.STOP, yourDateObject);` حيث `yourDateObject` هو كائن من نوع `java.util.Date`.

**س: ماذا يحدث إذا كان تاريخ الاستئناف أسبق من تاريخ الإيقاف؟**  
ج: لا تفرض الواجهة ترتيبًا زمنيًا؛ ومع ذلك، سيعامل المجدول التعيين كنشط فقط بعد التاريخ الأحدث بينهما، لذا يجب عليك التحقق من صحة التواريخ بنفسك.

**س: هل يمكنني تصفية التعيينات لتظهر فقط تلك التي لديها تاريخ إيقاف محدد؟**  
ج: نعم، مر عبر `prj.getResourceAssignments()` وتحقق من `ra.get(Asn.STOP) != null`.

**س: هل يمكن إزالة تاريخ الإيقاف بعد تعيينه؟**  
ج: عيّن تاريخ الإيقاف إلى `null` باستخدام `ra.set(Asn.STOP, null);` ثم احفظ المشروع.

**س: هل تدعم Aspose.Tasks حقول تواريخ أخرى مثل البداية، النهاية، أو البداية الفعلية؟**  
ج: بالتأكيد. يوفر تعداد `Asn` ثوابت لجميع حقول التعيين، مثل `Asn.START`, `Asn.FINISH`، وغيرها.

## الخلاصة
باتباعك لهذه الخطوات، أصبحت الآن تعرف **كيفية إيقاف التعيين**، فحص تواريخ الإيقاف/الاستئناف، واستئناف التعيين عند الحاجة. هذه القدرة تتيح لك **إدارة تعيينات الموارد** بدقة أكبر، خاصة في سيناريوهات مثل إجازات الموارد أو توقف المعدات. لا تتردد في توسيع المثال لتحديث التواريخ، إنشاء تقارير، أو دمجه مع منطق الجدولة الخاص بك.

---

**آخر تحديث:** 2026-01-10  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}