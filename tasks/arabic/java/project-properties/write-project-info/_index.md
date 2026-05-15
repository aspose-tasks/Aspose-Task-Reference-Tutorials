---
date: 2026-05-15
description: تعرف على كيفية تعيين تاريخ بدء المشروع، كتابة معلومات المشروع، وحفظ المشروع
  كملف XML باستخدام Aspose.Tasks للـ Java.
keywords:
- set project start date
- save project as xml
- Aspose.Tasks Java
linktitle: كتابة معلومات المشروع في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  headline: Set Project Start Date in MS Project using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  name: Set Project Start Date in MS Project using Aspose.Tasks for Java
  steps:
  - name: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
    text: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
  - name: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
  - name: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
    text: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java provides robust functionalities for both reading
      and writing MS Project files.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, Aspose.Tasks for Java supports various MS Project versions,
      ensuring seamless handling of MPP, XML, and Primavera formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial version allows full feature exploration but inserts a watermark
      on generated files and limits the number of project entities you can create.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: تعيين تاريخ بدء المشروع في MS Project باستخدام Aspose.Tasks للـ Java
url: /ar/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحديد تاريخ بدء المشروع في MS Project باستخدام Aspose.Tasks for Java

## مقدمة
في هذا الدرس، ستكتشف كيفية **تحديد تاريخ بدء المشروع** وكتابة معلومات إضافية عن MS Project باستخدام Aspose.Tasks for Java. سواءً كنت تقوم بأتمتة جداول المشاريع، أو إنشاء تقارير، أو دمج بيانات المشروع في نظام أكبر، فإن التحكم في تاريخ البدء برمجياً يمنحك تحكمًا دقيقًا في الجداول الزمنية. سنستعرض كل خطوة — من إعداد البيئة إلى حفظ المشروع المحدث كملف XML — حتى تتمكن من تطبيق هذه التقنيات فورًا.

## إجابات سريعة
- **ما هي الفئة الأساسية للتعامل مع مشروع؟** `Project` من مكتبة Aspose.Tasks.  
  فئة `Project` تمثل ملف MS Project في الذاكرة.  
- **كيف يمكنني تحديد تاريخ بدء المشروع؟** استخدم `project.set(Prj.START_DATE, <date>)`.  
  `Prj.START_DATE` هو مفتاح الخاصية المستخدم لتعيين تاريخ بدء المشروع.  
- **هل يمكنني أيضًا تحديد تاريخ الحالة؟** نعم، باستخدام `project.set(Prj.STATUS_DATE, <date>)`.  
  `Prj.STATUS_DATE` يحدد التاريخ الذي يعكس الحالة الحالية للمشروع.  
- **أي صيغة يجب أن أستخدمها لتصدير المشروع؟** احفظ كملف XML باستخدام `SaveFileFormat.Xml`.  
  `SaveFileFormat.Xml` يشير إلى أن المشروع سيُحفظ بصيغة XML.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يتطلب تشغيل كامل الوظائف ترخيص صالح لـ Aspose.Tasks.  
- **ما البيئات التي يدعمها Aspose.Tasks؟** Windows وLinux وmacOS مع Java 8+.

## ما هو تحديد تاريخ بدء المشروع؟
تحديد تاريخ بدء المشروع يحدد اليوم التقويمي الذي يبدأ فيه الجدول الزمني، مما يضع الأساس لجميع حسابات المهام، والاعتماديات، وتحليل المسار الحرج. من خلال تعريف هذا التاريخ برمجياً، تضمن أن كل ملف مشروع يتم إنشاؤه يبدأ من نفس النقطة، مما يلغي أخطاء الإدخال اليدوي ويضمن نتائج قابلة للتكرار عبر عمليات البناء.

## لماذا نستخدم Aspose.Tasks for Java لكتابة معلومات المشروع؟
توفر Aspose.Tasks for Java **أكثر من 150 خاصية قابلة للتكوين** وتدعم **أكثر من 30 صيغة ملف**، مما يتيح لك قراءة وتعديل وكتابة بيانات MS Project دون الحاجة إلى تثبيت Microsoft Project. تعمل المكتبة على Windows وLinux وmacOS، وتُعالج ملفات مئات الصفحات في وضع كفء للذاكرة، ويمكن دمجها في خطوط CI/CD، أو خدمات المعالجة الدفعية، أو الخلفيات السحابية. تجعل هذه القدرات المكمَّنة منها الخيار الأكثر موثوقية لأتمتة المشاريع على نطاق المؤسسات.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – أي نسخة حديثة (يوصى بـ 8+).  
2. **Aspose.Tasks for Java library** – قم بتنزيلها من [هنا](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA أو Eclipse أو أي محرر Java تفضله.  

## استيراد الحزم
أولاً، استورد الحزم الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## الخطوة 1: إعداد دليل البيانات
حدد الدليل الذي سيتم تخزين بيانات مشروعك فيه.
```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: إنشاء كائن Project
فئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف MS Project واحد في الذاكرة. إن إنشاؤها ينتج جدولًا زمنيًا فارغًا يمكنك البدء في ملئه فورًا.
```java
Project project = new Project();
```

## الخطوة 3: تعيين خصائص معلومات المشروع
هنا نقوم بتعيين **تاريخ بدء المشروع**، وعلامة الجدول من البداية، وتاريخ الحالة — لتغطية الكلمات المفتاحية الأساسية والثانوية *كتابة معلومات المشروع* و*كيفية تعيين الحالة*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## الخطوة 4: حفظ المشروع كملف XML
أخيرًا، احفظ ملف المشروع المحدث. حفظه كملف XML يضمن أقصى توافق مع الأدوات اللاحقة ويقلل حجم الملف.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **تاريخ بدء غير صحيح** | شهر التقويم في Java يبدأ من الصفر. | استخدم `Calendar.JULY` (أو أضف 1 إلى فهرس الشهر) كما هو موضح. |
| **الملف غير محفوظ** | `dataDir` غير موجود أو لا يملك صلاحية كتابة. | أنشئ الدليل مسبقًا أو اختر مسارًا قابلًا للكتابة. |
| **تحذير الترخيص** | التشغيل بدون ترخيص يضيف علامة مائية. | طبّق ترخيص Aspose.Tasks صالح قبل إنشاء كائن `Project`. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java لقراءة ملفات MS Project؟**  
ج: نعم، توفر Aspose.Tasks for Java وظائف قوية للقراءة والكتابة لملفات MS Project.

**س: هل Aspose.Tasks for Java متوافق مع إصدارات مختلفة من MS Project؟**  
ج: بالتأكيد، يدعم Aspose.Tasks for Java إصدارات متعددة من MS Project، مما يضمن معالجة سلسة لملفات MPP وXML وPrimavera.

**س: هل هناك أي قيود على نسخة التجربة من Aspose.Tasks for Java؟**  
ج: نسخة التجربة تسمح باستكشاف جميع الميزات لكنها تُضيف علامة مائية على الملفات المُنشأة وتحد من عدد كيانات المشروع التي يمكنك إنشاؤها.

**س: كيف يمكنني الحصول على دعم لـ Aspose.Tasks for Java؟**  
ج: يمكنك طلب المساعدة من منتدى مجتمع Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

**س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks for Java؟**  
ج: نعم، تتوفر تراخيص مؤقتة للاستخدام قصير الأمد. يمكنك الحصول عليها من [هنا](https://purchase.aspose.com/temporary-license/).

## الخلاصة
لقد تعلمت الآن كيفية **تحديد تاريخ بدء المشروع**، وكتابة معلومات المشروع الأساسية، و**حفظ المشروع كملف XML** باستخدام Aspose.Tasks for Java. تُعد هذه اللبنات الأساسية تمكينًا لك لأتمتة سير عمل إدارة المشاريع، وإنشاء جداول زمنية متسقة، ودمج بيانات MS Project في تطبيقات Java الخاصة بك. بعد ذلك، استكشف كيفية إضافة مهام، وموارد، وحقول مخصصة لإثراء جداولك الزمنية المؤتمتة أكثر.

---

**آخر تحديث:** 2026-05-15  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية تعيين تقويم المشروع باستخدام Aspose.Tasks for Java](/tasks/java/calendars/properties/)
- [كيفية قراءة معلومات المشروع من Microsoft Project باستخدام Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [تحميل ملف MPP في Java - إدارة خصائص المشروع باستخدام Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}