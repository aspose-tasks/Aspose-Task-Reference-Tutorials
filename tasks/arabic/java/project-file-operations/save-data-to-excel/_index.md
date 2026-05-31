---
date: 2026-05-31
description: تعلم كيفية تصدير MPP إلى Excel وتحويل ملف المشروع إلى Excel باستخدام
  Aspose.Tasks for Java. خطوات بسيطة لمطوري Java.
keywords:
- export mpp to excel
- convert mpp to xlsx
- write excel workbook java
- project file to spreadsheet
- export project schedule excel
linktitle: حفظ البيانات إلى Excel في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to export MPP to Excel and convert project file to Excel
    using Aspose.Tasks for Java. Simple steps for Java developers.
  headline: How to Export MPP to Excel with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to export MPP to Excel and convert project file to Excel
    using Aspose.Tasks for Java. Simple steps for Java developers.
  name: How to Export MPP to Excel with Aspose.Tasks for Java
  steps:
  - name: Define the Data Directory Path
    text: Set the folder where your `.mpp` file resides. Replace the placeholder with
      your actual path. The `dataDir` string tells the API where to locate the source
      file and where to write the resulting Excel workbook. java String dataDir =
      "Your Data Directory";
  - name: Load the Project File
    text: Create a `Project` instance by loading the `.mpp` file you want to convert.
      The `Project` class represents a Microsoft Project file in memory, allowing
      further manipulation or direct export. java Project project = new Project(dataDir
      + "project5.mpp");
  - name: Save the Project as XLSX
    text: 'Finally, export the loaded project to an Excel workbook. The `SaveFileFormat`
      enum specifies the output file format; `SaveFileFormat.Xlsx` tells Aspose.Tasks
      to generate a modern `.xlsx` file, effectively **convert MPP file to XLSX**.
      You can also specify `SaveOptions` to fine‑tune column widths or '
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java provides extensive APIs to read, write, and
      modify project files, including tasks, resources, calendars, and custom fields.
    question: Can I use Aspose.Tasks for Java to manipulate project data programmatically?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: The official documentation is available [here](https://reference.aspose.com/tasks/java/).
    question: Where can I find documentation for Aspose.Tasks for Java?
  - answer: Support is provided through the Aspose.Tasks forum, reachable [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for issues or queries related to Aspose.Tasks
      for Java?
  - answer: Yes, a temporary license can be obtained from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية تصدير MPP إلى Excel باستخدام Aspose.Tasks for Java
url: /ar/java/project-file-operations/save-data-to-excel/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تصدير MPP إلى Excel باستخدام Aspose.Tasks for Java

## مقدمة
Aspose.Tasks for Java هي مكتبة قوية تتيح لك **تصدير MPP إلى Excel** بسرعة وبشكل موثوق. في هذا الدرس سنرشدك عبر الخطوات الدقيقة المطلوبة لتحويل ملف Microsoft Project (.mpp) إلى مصنف Excel (.xlsx). في النهاية ستفهم كيف **تحويل ملف المشروع إلى Excel**، ولماذا هذه التحويلة مفيدة، وكيفية دمج العملية في أي تطبيق Java.

## إجابات سريعة
- **ما الذي تفعله API؟** تقرأ ملفات Project وتحفظها مباشرةً كمصنفات XLSX.  
- **ما هو التنسيق الناتج؟** ملف Excel باستخدام خيار `SaveFileFormat.Xlsx`.  
- **هل أحتاج إلى ترخيص؟** الإصدار التجريبي يعمل للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **ما هي المتطلبات المسبقة؟** JDK مثبت ومكتبة Aspose.Tasks for Java مضافة إلى مشروعك.  
- **كم من الوقت تستغرق عملية التنفيذ؟** عادةً أقل من 10 دقائق لتصدير أساسي.  

## ما هو “كيفية تصدير MPP إلى Excel”؟
تصدير MPP إلى Excel يعني أخذ الجدول الزمني والموارد وبيانات المهام المخزنة في ملف Microsoft Project وكتابتها في جدول بيانات Excel منظم. هذا يجعل من السهل مشاركة بيانات المشروع مع أصحاب المصلحة الذين قد لا يكون لديهم برنامج Project مثبت.

## لماذا تحويل ملف MPP إلى XLSX؟
تصدير MPP إلى Excel يتيح لك مشاركة معلومات المشروع بصيغة متاحة عالميًا. **الإجابة المباشرة:** تحويل MPP إلى XLSX يمنح كل مستخدم تجاري القدرة على فتح وتحرير وتحليل بيانات المشروع باستخدام أدوات Excel الأصلية — الجداول المحورية، المخططات، والصيغ — دون الحاجة إلى تثبيت Microsoft Project. هذا يعزز إمكانية الوصول، يسرّع إعداد التقارير، ويمكن من خطوط الأتمتة التي تستهلك ملفات Excel العادية.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. **Java Development Kit (JDK)** – مثبت ومضاف إلى PATH نظامك.  
2. **Aspose.Tasks for Java library** – قم بتنزيله من [download link](https://releases.aspose.com/tasks/java/) وأضف ملف JAR إلى classpath الخاص بمشروعك.

## استيراد الحزم
`com.aspose.tasks` توفر API الأساسية لمعالجة ملفات Project، بينما `java.io` توفر أدوات نظام الملفات.  
فئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف Microsoft Project واحد في الذاكرة. فئة `Project` تمثل ملف Microsoft Project محملاً في الذاكرة. استورد المساحات الاسمية المطلوبة قبل البدء في العمل مع API.

```text
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
```

## دليل خطوة بخطوة

### كيف يمكنني تصدير MPP إلى Excel باستخدام Aspose.Tasks؟
حمّل ملف `.mpp` الخاص بك باستخدام `new Project("yourfile.mpp")` ثم استدعِ فورًا `project.save("output.xlsx", SaveFileFormat.Xlsx)`. هذا النمط المكوّن من سطرين يقوم بتحويل كامل، مع الحفاظ على المهام والموارد والحقول المخصصة. العملية تستغرق أقل من ثانية لمشاريع تقريبًا 100 مهمة على جهاز تطوير عادي.

#### الخطوة 1: تحديد مسار دليل البيانات
حدد المجلد الذي يوجد فيه ملف `.mpp` الخاص بك. استبدل العنصر النائب بالمسار الفعلي الخاص بك. سلسلة `dataDir` تخبر API بمكان العثور على ملف المصدر وأين كتابة مصنف Excel الناتج.

```text
```java
String dataDir = "Your Data Directory";
```
```

#### الخطوة 2: تحميل ملف المشروع
أنشئ كائن `Project` بتحميل ملف `.mpp` الذي تريد تحويله. فئة `Project` تمثل ملف Microsoft Project في الذاكرة، مما يسمح بمزيد من التلاعب أو التصدير المباشر.

```text
```java
Project project = new Project(dataDir + "project5.mpp");
```
```

#### الخطوة 3: حفظ المشروع كملف XLSX
أخيرًا، صدّر المشروع المحمّل إلى مصنف Excel. يحدد تعداد `SaveFileFormat` تنسيق ملف الإخراج؛ `SaveFileFormat.Xlsx` يخبر Aspose.Tasks بإنشاء ملف `.xlsx` حديث، وبالتالي **تحويل ملف MPP إلى XLSX**. يمكنك أيضًا تحديد `SaveOptions` لضبط عرض الأعمدة بدقة أو تضمين جداول مختارة فقط.

```text
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
```

## حالات الاستخدام الشائعة
- **تقارير تنفيذية:** توفير لمحات سريعة عن المشروع في Excel للإدارة العليا.  
- **تحليل البيانات:** إمداد بيانات المهام والموارد إلى Power Query في Excel للحصول على رؤى أعمق.  
- **تكامل:** تمرير ملف Excel المصدر إلى الأنظمة اللاحقة التي تقبل فقط مدخلات CSV/Excel.  

## نصائح إضافية وأفضل الممارسات
- **نصيحة أداء:** للمشاريع التي تتجاوز 500 مهمة، فعّل `project.setReadWriteMode(ReadWriteMode.MemoryOptimized)` لتقليل استهلاك الذاكرة. `ReadWriteMode.MemoryOptimized` يقلل من استخدام RAM عند معالجة المشاريع الكبيرة.  
- **نصيحة تنسيق:** استخدم `project.save("output.xlsx", SaveFileFormat.Xlsx, new XlsxSaveOptions { ExportAllFields = true })` لتضمين الحقول المخصصة في التصدير. `XlsxSaveOptions` يتيح لك تخصيص تصدير Excel، مثل تصدير جميع الحقول.  
- **معالجة الأخطاء:** احطّ استدعاءات التحميل والحفظ بكتلة try‑catch لالتقاط `FileNotFoundException` أو `LicenseException` وتقديم ملاحظات واضحة للمستخدم.  

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java للتعامل مع بيانات المشروع برمجيًا؟**  
نعم، Aspose.Tasks for Java توفر واجهات برمجة تطبيقات واسعة لقراءة وكتابة وتعديل ملفات المشروع، بما في ذلك المهام والموارد والتقويمات والحقول المخصصة.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks for Java؟**  
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks for Java من [here](https://releases.aspose.com/).

**س: أين يمكنني العثور على وثائق Aspose.Tasks for Java؟**  
الوثائق الرسمية متاحة [here](https://reference.aspose.com/tasks/java/).

**س: كيف يمكنني الحصول على دعم للمشكلات أو الاستفسارات المتعلقة بـ Aspose.Tasks for Java؟**  
الدعم متوفر عبر منتدى Aspose.Tasks، ويمكن الوصول إليه [here](https://forum.aspose.com/c/tasks/15).

**س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks for Java؟**  
نعم، يمكن الحصول على ترخيص مؤقت من [here](https://purchase.aspose.com/temporary-license/).

## الخلاصة
في هذا الدليل أظهرنا **كيفية تصدير MPP إلى Excel** باستخدام Aspose.Tasks for Java. باتباع الخطوات الثلاث البسيطة — تحديد دليل البيانات، تحميل ملف Project، وحفظه كملف XLSX — يمكنك بسهولة **تصدير بيانات المشروع إلى Excel** وتمكين فريقك من تقارير مرنة قابلة للمشاركة. قدرة المكتبة على **كتابة كود Java لإنشاء مصنف Excel** تجعل التكامل سلسًا لأي سير عمل يعتمد على Java.

---

**آخر تحديث:** 2026-05-31  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء ملف MPP – إنشاء وحفظ مشروع فارغ بصيغة MPP باستخدام Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [حفظ المشروع كقالب، CSV، ونص باستخدام Aspose.Tasks for Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [تعيين تاريخ بدء المشروع في MS Project باستخدام Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}