---
date: 2025-12-21
description: تعلم كيفية إنشاء SVG من ملفات MPP في Java وحفظ المشروع كـ SVG باستخدام
  مكتبة Aspose.Tasks. دليل خطوة بخطوة مع أمثلة على الشيفرة.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية إنشاء SVG من ملف MPP في جافا باستخدام Aspose.Tasks
url: /ar/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء SVG من MPP في Java

## المقدمة
في هذا البرنامج التعليمي ستتعلم كيفية **إنشاء SVG من MPP** باستخدام Aspose.Tasks for Java. تحويل ملف Microsoft Project (MPP) إلى رسومات متجهة قابلة للتوسع (SVG) يتيح لك تضمين مخططات عالية الجودة ومستقلة عن الدقة مباشرةً في صفحات الويب أو التقارير أو لوحات التحكم. سنستعرض الإعداد المطلوب، ونظهر الشيفرة الدقيقة التي تحتاجها، ونشرح كل خطوة حتى تتمكن بثقة من **حفظ المشروع كـ SVG** في تطبيقاتك الخاصة.

## إجابات سريعة
- **ماذا يعني “إنشاء SVG من MPP”?**  
  يقوم بتحويل ملف Microsoft Project (.mpp) إلى صورة SVG يمكن عرضها في أي متصفح دون فقدان الجودة.  
- **أي مكتبة تتعامل مع التحويل؟**  
  توفر Aspose.Tasks for Java طريقة `save` ذات سطر واحد لإجراء التحويل.  
- **هل أحتاج إلى ترخيص؟**  
  يلزم ترخيص مؤقت للاستخدام التجاري؛ يتوفر إصدار تجريبي مجاني.  
- **ما هي المتطلبات المسبقة؟**  
  Java JDK 8+ وملف JAR الخاص بـ Aspose.Tasks for Java.  
- **كم يستغرق التحويل من الوقت؟**  
  عادةً أقل من ثانية لملفات المشاريع القياسية.

## ما هو “إنشاء SVG من MPP”؟
إنشاء SVG من ملف MPP يعني تصدير التمثيل البصري لجدول المشروع — المهام، الجداول الزمنية، والموارد — إلى تنسيق الرسومات المتجهة القابلة للتوسع (Scalable Vector Graphics). SVG يعتمد على XML، خفيف الوزن، ويتوسع بشكل مثالي على الشاشات عالية الدقة.

## لماذا تستخدم Aspose.Tasks لحفظ المشروع كـ SVG؟
- **لا يلزم تثبيت Microsoft Project** – المكتبة تعمل بشكل مستقل.  
- **دقة كاملة** – الرسوم البيانية، أشرطة جانت، والمعالم تحتفظ بأنماطها.  
- **متعدد المنصات** – تشغيل الشيفرة على Windows أو Linux أو macOS.  
- **تكامل سهل** – استدعاء API بسطر واحد يندمج طبيعياً في خطوط أنابيب Java الحالية.

## المتطلبات المسبقة
- **مجموعة تطوير Java (JDK)** – الإصدار 8 أو أحدث. قم بتنزيله من موقع Oracle.  
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
حدد موقع ملف MPP المصدر ومكان كتابة ملف SVG.

```java
String dataDir = "Your Data Directory";
```

> **نصيحة احترافية:** استخدم مسارًا مطلقًا أو مسارًا نسبيًا إلى مجلد موارد مشروعك لتجنب `FileNotFoundException`.

## الخطوة 2: تحميل ملف MPP
أنشئ كائن `Project` بتحميل ملف Microsoft Project الموجود.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

تقرأ هذه السطر ملف *HomeMovePlan.mpp* من المجلد الذي حددته سابقًا.

## الخطوة 3: حفظ المشروع كـ SVG
الآن يمكنك **حفظ المشروع كـ SVG** بأمر واحد.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

تكتب الطريقة `project5.svg` إلى نفس الدليل. يمكن فتح ملف SVG الناتج في أي متصفح حديث أو تضمينه مباشرةً في HTML.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **الملف غير موجود** | مسار `dataDir` غير صحيح | تحقق من أن سلسلة الدليل تنتهي بفاصل (`/` أو `\\`). |
| **إخراج SVG فارغ** | تم تحميل المشروع بدون عروض | تأكد من أن ملف MPP يحتوي على عرض مخطط جانت قبل الحفظ. |
| **استثناء الترخيص** | لم يتم تطبيق ترخيص صالح | قم بتطبيق ترخيص مؤقت باستخدام `License.setLicense("path/to/license.xml")` قبل استدعاء `save`. |

## الأسئلة المتكررة

**س: هل Aspose.Tasks for Java متوافق مع جميع إصدارات ملفات Microsoft Project؟**  
ج: نعم، يدعم صيغ MPP و MPT و XML من الإصدارات القديمة إلى أحدث إصدارات Project.

**س: هل يمكنني تخصيص مظهر مخرجات SVG؟**  
ج: بالتأكيد. استخدم `SvgOptions` لتعيين الخطوط والألوان وخيارات التخطيط قبل استدعاء `save`.

**س: هل يتطلب Aspose.Tasks for Java ترخيصًا للاستخدام التجاري؟**  
ج: نعم، يلزم وجود ترخيص صالح للإنتاج. يمكنك الحصول على ترخيص مؤقت **[هنا](https://purchase.aspose.com/temporary-license/)**.

**س: هل يمكنني تجربة Aspose.Tasks for Java قبل الشراء؟**  
ج: نعم، يتوفر إصدار تجريبي مجاني **[هنا](https://purchase.aspose.com/buy)**.

**س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks for Java؟**  
ج: زر منتدى المجتمع **[هنا](https://forum.aspose.com/c/tasks/15)** لطرح الأسئلة ومشاركة الملاحظات.

## الخاتمة
أنت الآن تعرف كيفية **إنشاء SVG من ملفات MPP** في Java و**حفظ المشروع كـ SVG** بفعالية باستخدام Aspose.Tasks. تتيح لك هذه القدرة دمج تصورات المشاريع الغنية في بوابات الويب، لوحات تقارير، أو أي مكان يحتاج إلى رسومات قابلة للتوسع. جرب `SvgOptions` لضبط المخرجات بدقة، وستحصل على أداة قوية في مجموعة أدوات التطوير الخاصة بك.

---

**آخر تحديث:** 2025-12-21  
**تم الاختبار مع:** Aspose.Tasks for Java 24.10  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}