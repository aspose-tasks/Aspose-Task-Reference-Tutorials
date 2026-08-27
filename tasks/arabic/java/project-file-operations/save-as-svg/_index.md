---
date: 2026-03-27
description: تعلم كيفية تصدير ملفات MPP إلى SVG في جافا باستخدام Aspose.Tasks. دليل
  خطوة بخطوة، أمثلة على الشيفرة ونصائح لحفظ المشروع كملف SVG بسرعة.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية تصدير MPP إلى SVG في Java باستخدام Aspose.Tasks
url: /ar/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تصدير ملف MPP إلى SVG في Java

## تصدير MPP إلى SVG – مقدمة
في هذا الدرس ستتعلم كيفية **تصدير MPP إلى ملفات SVG** باستخدام Aspose.Tasks for Java. تحويل ملف Microsoft Project (MPP) إلى صورة Scalable Vector Graphics (SVG) يتيح لك تضمين مخططات عالية الجودة ومستقلة عن الدقة مباشرةً في صفحات الويب أو التقارير أو لوحات التحكم. سنستعرض الإعدادات المطلوبة، ونظهر لك الشيفرة الدقيقة التي تحتاجها، ونشرح كل خطوة حتى تتمكن من **حفظ المشروع كملف SVG** بثقة في تطبيقاتك الخاصة.

## إجابات سريعة
- **ماذا يعني “تصدير MPP إلى SVG”؟**  
  يحول ملف Microsoft Project (.mpp) إلى صورة SVG يمكن عرضها في أي متصفح دون فقدان الجودة.  
- **أي مكتبة تتولى عملية التحويل؟**  
  Aspose.Tasks for Java توفر طريقة `save` ذات سطر واحد لإجراء التحويل.  
- **هل أحتاج إلى ترخيص؟**  
  يلزم ترخيص مؤقت للاستخدام التجاري؛ يتوفر نسخة تجريبية مجانية.  
- **ما المتطلبات المسبقة؟**  
  Java JDK 8+ وملف JAR الخاص بـ Aspose.Tasks for Java.  
- **كم تستغرق عملية التحويل؟**  
  عادةً أقل من ثانية لملفات المشروع القياسية.

## ما هو “تصدير MPP إلى SVG”؟
يعني تصدير MPP إلى SVG أخذ التمثيل البصري لجدول المشروع — المهام، الجداول الزمنية، والموارد — وكتابته كملف SVG. SVG هو ملف مبني على XML، خفيف الوزن، ويتوسع بشكل مثالي على الشاشات عالية الدقة.

## لماذا تصدر MPP إلى SVG باستخدام Aspose.Tasks؟
- **لا يلزم تثبيت Microsoft Project** – المكتبة تعمل بشكل مستقل.  
- **دقة كاملة** – المخططات، أشرطة جانت، والمعالم تحتفظ بأنماطها.  
- **متعدد المنصات** – تشغيل الشيفرة على Windows أو Linux أو macOS.  
- **واجهة برمجة تطبيقات بسطر واحد** – استدعاء واحد يحفظ المشروع كملف SVG، مما يندمج طبيعياً مع خطوط أنابيب Java الحالية.

## المتطلبات المسبقة
- **مجموعة تطوير جافا (JDK)** – الإصدار 8 أو أحدث. يمكن تحميله من موقع Oracle.  
- **Aspose.Tasks for Java** – احصل على المكتبة من صفحة التحميل الرسمية **[هنا](https://releases.aspose.com/tasks/java/)**.  

## استيراد الحزم
أولاً، استورد الفئات التي ستحتاجها. يبقى كتلة الاستيراد دون تغيير.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## الخطوة 1: تعريف دليل البيانات
حدد مكان وجود ملف MPP المصدر ومكان كتابة ملف SVG.

```java
String dataDir = "Your Data Directory";
```

> **نصيحة احترافية:** استخدم مسارًا مطلقًا أو مسارًا نسبيًا إلى مجلد موارد المشروع لتجنب استثناء `FileNotFoundException`.

## الخطوة 2: تحميل ملف MPP
أنشئ كائن `Project` بتحميل ملف Microsoft Project الموجود.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

هذه السطر يقرأ *HomeMovePlan.mpp* من المجلد الذي حددته مسبقًا.

## الخطوة 3: حفظ المشروع كملف SVG
الآن يمكنك **تصدير MPP إلى SVG** بأمر واحد.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

تكتب الطريقة `project5.svg` إلى نفس الدليل. يمكن فتح ملف SVG الناتج في أي متصفح حديث أو تضمينه مباشرةً في HTML.

## حالات الاستخدام الشائعة
- **لوحات معلومات المشروع** – تضمين مخططات جانت حية في بوابات الويب دون الحاجة لتثبيت Microsoft Project لدى العميل.  
- **التقارير الآلية** – توليد صور SVG عند الطلب لتقارير PDF أو HTML.  
- **التعاون بين الفرق** – مشاركة جدول بصري مع أصحاب المصلحة الذين يحتاجون فقط إلى متصفح لعرضه.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|--------|-------|------|
| **الملف غير موجود** | مسار `dataDir` غير صحيح | تحقق من أن سلسلة الدليل تنتهي بفاصل (`/` أو `\\`). |
| **إخراج SVG فارغ** | تم تحميل المشروع دون عروض | تأكد من أن ملف MPP يحتوي على عرض مخطط جانت قبل الحفظ. |
| **استثناء الترخيص** | لم يتم تطبيق ترخيص صالح | قم بتطبيق ترخيص مؤقت باستخدام `License.setLicense("path/to/license.xml")` قبل استدعاء `save`. |

## الأسئلة المتكررة

**س: هل Aspose.Tasks for Java متوافق مع جميع إصدارات ملفات Microsoft Project؟**  
ج: نعم، يدعم صيغ MPP و MPT و XML من الإصدارات القديمة حتى أحدث إصدارات Project.

**س: هل يمكنني تخصيص مظهر إخراج SVG؟**  
ج: بالطبع. استخدم `SvgOptions` لتحديد الخطوط والألوان وخيارات التخطيط قبل استدعاء `save`.

**س: هل يتطلب Aspose.Tasks for Java ترخيصًا للاستخدام التجاري؟**  
ج: نعم، يلزم وجود ترخيص صالح للإنتاج. يمكنك الحصول على ترخيص مؤقت **[هنا](https://purchase.aspose.com/temporary-license/)**.

**س: هل يمكن تجربة Aspose.Tasks for Java قبل الشراء؟**  
ج: نعم، تتوفر نسخة تجريبية مجانية **[هنا](https://purchase.aspose.com/buy)**.

**س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks for Java؟**  
ج: زر منتدى المجتمع **[هنا](https://forum.aspose.com/c/tasks/15)** لطرح الأسئلة ومشاركة الملاحظات.

## الخلاصة
أنت الآن تعرف كيفية **تصدير MPP إلى SVG** في Java و**حفظ المشروع كملف SVG** بفعالية باستخدام Aspose.Tasks. تتيح لك هذه القدرة دمج تصورات مشروع غنية في بوابات الويب، لوحات التقارير، أو أي مكان تحتاج فيه إلى رسومات قابلة للتوسع. جرّب `SvgOptions` لضبط الإخراج بدقة، وستحصل على أداة قوية في مجموعة أدوات التطوير الخاصة بك.

---

**آخر تحديث:** 2026-03-27  
**تم الاختبار مع:** Aspose.Tasks for Java 24.10  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}