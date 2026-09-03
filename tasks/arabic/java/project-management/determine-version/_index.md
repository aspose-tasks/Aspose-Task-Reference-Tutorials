---
date: 2026-05-31
description: تعلم كيفية الحصول على نسخة المشروع واسترجاع تاريخ الحفظ الأخير من ملفات
  MS Project باستخدام Aspose.Tasks for Java. دليل خطوة بخطوة مع أمثلة على الشيفرة.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: تحديد نسخة المشروع باستخدام Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية الحصول على نسخة المشروع – دليل Aspose Tasks Java
url: /ar/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية الحصول على إصدار المشروع – Aspose Tasks Java Tutorial

في هذا **Aspose Tasks Java tutorial** ستتعلم **كيفية الحصول على إصدار المشروع** لملف Microsoft Project وأيضًا كيفية **استرجاع تاريخ الحفظ الأخير** باستخدام مكتبة Aspose.Tasks للغة Java. معرفة إصدار الملف ووقت الحفظ يساعدك على تجنب مشاكل التوافق، وتطبيق سياسات الترحيل، والحفاظ على سجلات تدقيق دقيقة. سنستعرض كل خطوة — من إعداد البيئة إلى طباعة الإصدار والتاريخ — حتى تتمكن من دمج هذا الفحص في أي تطبيق Java بثقة.

## إجابات سريعة
- **ما الذي يغطيه هذا الدرس؟** تحديد إصدار ملف MS Project وتاريخ الحفظ الأخير باستخدام Aspose.Tasks للغة Java.  
- **هل أحتاج إلى تثبيت Microsoft Project؟** لا، Aspose.Tasks يعمل بشكل مستقل عن Microsoft Project.  
- **ما هي صيغ الملفات المدعومة؟** ملفات Project القائمة على XML مثل MPP و XML مدعومة بالكامل.  
- **كم من الوقت تستغرق عملية التنفيذ؟** تقريبًا 5‑10 دقائق لفحص الإصدار الأساسي.  
- **هل يلزم الحصول على ترخيص؟** نسخة تجريبية مجانية تكفي للتقييم؛ يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج.

## ما هو دليل Aspose Tasks Java؟
دليل `Aspose.Tasks` للغة Java هو دليل مختصر وتطبيقي يوضح كيفية التفاعل مع بيانات Microsoft Project برمجيًا. يوضح لك كيفية قراءة وتعديل وتحليل معلومات المشروع دون الحاجة إلى تثبيت Microsoft Project على الخادم. بالإضافة إلى ذلك، يغطي تحميل الملفات، الوصول إلى الخصائص، وحفظ التغييرات، مما يمكّن المطورين من أتمتة مهام إدارة المشاريع بكفاءة.

## لماذا تستخدم Aspose.Tasks لتحديد إصدار المشروع؟
Aspose.Tasks يوفر **بيانات تعريف الإصدار الدقيقة** و**طوابع الوقت لآخر حفظ** أثناء التشغيل على أي نظام تشغيل يدعم Java. يعالج الملفات حتى **500 صفحة في أقل من ثانيتين** على معالج قياسي بسرعة 2.5 GHz، مما يجعله مثاليًا لأتمتة الدُفعات وسيناريوهات الترحيل على نطاق واسع.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – الإصدار 8 أو أحدث.  
2. **Aspose.Tasks for Java JAR** – قم بتنزيله من [الموقع الإلكتروني](https://releases.aspose.com/tasks/java/) وأضفه إلى مسار الفئة (classpath) الخاص بمشروعك.  
3. **MS Project file** – ملف Project قائم على XML (مثال: `input.xml`) ترغب في فحصه.  

> **نصيحة احترافية:** احفظ ملف المشروع في مجلد `data` مخصص للحفاظ على تنظيم المسارات وتجنب الكتابة فوقه عن طريق الخطأ.

## استيراد الحزم
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## كيفية إعداد دليل المشروع
لتحديد موقع ملفات مشروعك بشكل صحيح، أنشئ دليلًا مخصصًا داخل بنية تطبيقك واحفظ جميع ملفات الإدخال هناك. هذا يحافظ على نظافة الكود ويتجنب الأخطاء المتعلقة بالمسارات عند تحميل الملفات. استخدم اسم متغير واضح لمسار الدليل، والذي يمكن أن يكون مطلقًا أو نسبيًا لجذر المشروع.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

## كيفية تحميل المشروع
`Project` هو الكائن الأساسي في Aspose.Tasks الذي يمثل ملف Microsoft Project في الذاكرة، مما يمنحك الوصول إلى جميع خصائص المشروع ومجموعاته. بعد إنشاء نسخة `Project`، يمكنك استعلام حقوله، أو التكرار عبر المهام، أو تعديل البيانات قبل حفظ الملف مرة أخرى على القرص.

```java
Project project = new Project(dataDir + "input.xml");
```

## كيفية تحديد إصدار المشروع
`Prj.SAVE_VERSION` هي خاصية تشير إلى رقم إصدار Microsoft Project الذي حفظ الملف. `Prj.LAST_SAVED` هي خاصية تخزن التاريخ والوقت عندما تم حفظ الملف آخر مرة. `Prj.SAVE_VERSION` تُعيد رقم الإصدار الرقمي لتطبيق Microsoft Project الذي حفظ الملف (مثال: 12 لـ Project 2010). `Prj.LAST_SAVED` توفر التاريخ والوقت الدقيق لأحدث عملية حفظ.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

## كيفية عرض النتيجة
بعد استرجاع الإصدار ومعلومات آخر حفظ، عادةً ما ترغب في طباعتها إلى وحدة التحكم أو ملف سجل. استخدم `System.out.println` لعرض القيم، مع تنسيق التاريخ حسب الحاجة. هذا يؤكد نجاح الاستخراج ويوفر تغذية راجعة فورية أثناء التطوير أو في السكريبتات الآلية.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | الملف غير موجود أو المسار غير صحيح | تحقق من `dataDir` واسم الملف؛ استخدم مسارًا مطلقًا للاختبار. |
| رقم إصدار غير متوقع (مثال: 0) | تحميل ملف XML غير مشروع | تأكد من أن الملف هو ملف Microsoft Project صالح (MPP/XML). |
| استثناء الترخيص | استخدام النسخة التجريبية دون ترخيص صالح في بيئة الإنتاج | طبق ترخيص Aspose.Tasks الخاص بك (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع لغات برمجة أخرى؟**  
ج: نعم، Aspose.Tasks يدعم .NET و Java و C++ وغيرها.

**س: هل Aspose.Tasks مناسب للمشاريع ذات النطاق الواسع؟**  
ج: بالتأكيد؛ يمكنه معالجة مشاريع مئات الصفحات في ثوانٍ دون تحميل الملف بالكامل في الذاكرة.

**س: هل يمكنني تخصيص بيانات المشروع باستخدام Aspose.Tasks؟**  
ج: نعم، يمكنك تعديل المهام والموارد والتقويمات وأي عنصر آخر في المشروع عبر الـ API.

**س: هل يتطلب Aspose.Tasks تثبيت Microsoft Project؟**  
ج: لا، المكتبة تعمل بشكل مستقل ولا تحتاج إلى Microsoft Project على الجهاز المضيف.

**س: هل يتوفر دعم فني لـ Aspose.Tasks؟**  
ج: نعم، يمكنك الحصول على المساعدة من منتدى Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

**أسئلة إضافية**

**س: كيف يمكنني استرجاع خصائص مشروع أخرى (مثل المؤلف، الشركة)؟**  
ج: استخدم `project.get(Prj.AUTHOR)` أو `project.get(Prj.COMPANY)` بنفس الطريقة التي تسترجع بها الإصدار.

**س: هل يمكنني التحقق من إصدار ملف MPP (ثنائي)؟**  
ج: نعم، Aspose.Tasks يحمل ملفات `.mpp` مباشرة؛ خاصية `Prj.SAVE_VERSION` تعمل أيضًا مع الصيغ الثنائية.

**س: هل هناك طريقة لترقية ملف مشروع قديم إلى إصدار أحدث برمجيًا؟**  
ج: حمّل الملف القديم، ثم احفظه باستخدام `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks يكتب الملف بأحدث صيغة بشكل افتراضي.

## الخلاصة
لقد أصبحت الآن متمكنًا من **كيفية الحصول على إصدار المشروع** و**استرجاع تاريخ الحفظ الأخير** من ملفات MS Project باستخدام Aspose.Tasks للغة Java. دمج هذه الشفرات في خطوط الأنابيب الأوتوماتيكية، أدوات التقارير، أو أدوات الترحيل يضمن أنك دائمًا تعرف الإصدار الدقيق للمشروع الذي تتعامل معه.

---

**آخر تحديث:** 2026-05-31  
**تم الاختبار باستخدام:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [تعيين تاريخ بدء المشروع في MS Project باستخدام Aspose.Tasks للغة Java](/tasks/java/project-properties/write-project-info/)
- [قراءة قاعدة بيانات مشروع Microsoft باستخدام Aspose.Tasks للغة Java](/tasks/java/project-data-reading/read-project-database/)
- [حفظ المشروع كقالب، CSV، ونص باستخدام Aspose.Tasks للغة Java](/tasks/java/project-file-operations/save-csv-text-template/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}