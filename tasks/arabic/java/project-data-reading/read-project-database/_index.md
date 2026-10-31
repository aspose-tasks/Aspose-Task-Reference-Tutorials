---
date: 2026-10-31
description: تعرف على كيفية حفظ المشروع كملف PDF وقراءة قاعدة بيانات Microsoft Project
  باستخدام Aspose.Tasks للغة Java، بالإضافة إلى الاتصال بـ Project Server، وتحويل
  المشروع إلى HTML، وتصدير المشروع إلى XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: قراءة بيانات المشروع من قاعدة بيانات Microsoft Project في Aspose.Tasks
og_description: حفظ المشروع كملف PDF وقراءة قاعدة بيانات Microsoft Project باستخدام
  Aspose.Tasks للغة Java. تعرف على كيفية الاتصال بـ Project Server، وتصدير المشروع
  إلى HTML وXML وCSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: حفظ المشروع كملف PDF وقراءة قاعدة بيانات Microsoft Project باستخدام Aspose.Tasks
  للغة Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: حفظ المشروع كملف PDF وقراءة قاعدة بيانات Microsoft Project باستخدام Aspose.Tasks
  للغة Java
url: /ar/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# احفظ المشروع كملف PDF واقرأ قاعدة بيانات Microsoft Project باستخدام Aspose.Tasks للـ Java

## المقدمة
في هذا البرنامج التعليمي ستكتشف كيفية **قراءة قاعدة بيانات Microsoft Project** مباشرةً من خادم Microsoft Project Server ثم **حفظ المشروع كملف PDF** باستخدام Aspose.Tasks Java API. سواء كنت تحتاج إلى إنشاء تقارير قابلة للطباعة، أو ترحيل بيانات قديمة، أو تضمين معلومات المشروع في بوابة مخصصة، فإن هذا الدليل يشرح لك كل خطوة — من تكوين اتصال JDBC إلى تصدير المشروع إلى PDF أو XML أو HTML. في النهاية، ستحصل على حل جاهز للإنتاج يعمل على أي خادم Java دون الحاجة لتثبيت Microsoft Project.

## إجابات سريعة
- **ماذا يفعل Aspose.Tasks؟** يوفر API نقي‑Java لقراءة وكتابة ومعالجة ملفات وقواعد بيانات Microsoft Project.  
- **هل أحتاج إلى تثبيت Microsoft Project؟** لا، Aspose.Tasks يعمل بشكل مستقل عن Microsoft Project.  
- **ما نوع قاعدة البيانات المدعومة؟** Microsoft SQL Server، الخلفية لخادم Project Server.  
- **هل يمكنني التصدير إلى صيغ أخرى؟** نعم—PDF، XML، HTML، CSV، PNG، JPEG، وأكثر.  
- **ما هي المتطلبات الأساسية الرئيسية؟** JDK 8 أو أحدث، مكتبة Aspose.Tasks للـ Java، برنامج تشغيل SQL Server JDBC، واعتمادات صالحة لخادم Project Server.

## ما هو “قراءة قاعدة بيانات Microsoft Project”؟
قراءة قاعدة بيانات Microsoft Project تعني الاتصال بمستودع SQL Server الخاص بـ Project Server، استخراج بيانات المشروع المخزنة، وتحميلها إلى كائن `Project` يمكن لـ Aspose.Tasks معالجته. هذا النهج مثالي للتقارير الآلية، ترحيل البيانات، أو التحليلات المخصصة.

## لماذا تستخدم Aspose.Tasks للـ Java؟
Aspose.Tasks للـ Java يتيح لك العمل مع بيانات Microsoft Project دون الحاجة إلى تطبيق سطح المكتب، مقدمًا حلًا نقيًا‑Java يعمل على أي منصة. يوفر نموذج كائن شامل للمهام والموارد والتقويمات والحقول المخصصة، ويمكنه معالجة مشاريع مؤسسية كبيرة بكفاءة، مما يجعله مثاليًا للتقارير الآلية، والترحيل، وسيناريوهات التكامل.

- **بدون اعتماد على Microsoft Project** — تشغيل على أي خادم أو بيئة CI.  
- **نموذج كائن غني** — الوصول إلى المهام والموارد والتعيينات والتقويمات والحقول المخصصة برمجياً.  
- **خيارات تصدير متعددة** — Aspose.Tasks يدعم التصدير إلى **أكثر من 20 تنسيق ملف**، بما في ذلك PDF، XML، HTML، CSV، PNG، و JPEG، باستدعاء API واحد.  
- **أداء عالي** — المكتبة يمكنها معالجة مشاريع تحتوي على **ما يصل إلى 10,000 مهمة** في أقل من دقيقة، وتقوم ببث البيانات لتجنب تحميل الملف بالكامل في الذاكرة.

## المتطلبات المسبقة
1. بيئة تطوير Java تعمل (JDK 8 أو أحدث).  
2. مكتبة Aspose.Tasks للـ Java مضافة إلى classpath الخاص بالمشروع.  
3. بيانات اعتماد الوصول لقاعدة بيانات SQL الخاصة بـ Project Server (اسم الخادم، المنفذ، اسم قاعدة البيانات، اسم المستخدم، كلمة المرور) للاتصال بـ Project Server.  
4. برنامج تشغيل Microsoft JDBC لـ SQL Server (مثال: `sqljdbc4.jar`).  

## استيراد الحزم
أولاً، استورد الفئات التي ستحتاجها. القائمة تشمل الفئات الأساسية لـ Aspose.Tasks وأدوات Java القياسية.

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## كيفية الاتصال بـ Project Server
إنشاء اتصال موثوق هو الأساس لقراءة بيانات المشروع. تأكد من أن نسخة SQL Server قابلة للوصول من مضيف Java الخاص بك وأن تسجيل الدخول الذي تستخدمه يمتلك صلاحيات **SELECT** على مخطط Project Server. يجب أيضًا التحقق من زمن استجابة الشبكة وتكوين أي إعدادات SSL مطلوبة لضمان اتصال آمن.

## الخطوة 1: إعداد اتصال قاعدة البيانات
فئة `MspDbSettings` تغلف تفاصيل اتصال JDBC المطلوبة للوصول إلى قاعدة بيانات Microsoft Project Server. أنشئ مثيلًا من `MspDbSettings` يحمل سلسلة اتصال JDBC. استبدل القيم النائبة بتفاصيل الخادم الفعلية الخاصة بك.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **نصيحة احترافية:** احفظ سلسلة الاتصال في ملف تكوين آمن أو متغير بيئي بدلاً من كتابة الاعتمادات مباشرةً في الشيفرة.

## الخطوة 2: إضافة برنامج تشغيل JDBC
حمّل برنامج تشغيل Microsoft SQL Server JDBC في وقت التشغيل حتى يتمكن JVM من التواصل مع قاعدة البيانات.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **تحذير:** تأكد من أن إصدار برنامج التشغيل يتطابق مع إصدار SQL Server الخاص بك. قد يتسبب استخدام برنامج تشغيل غير متوافق في فشل الاتصال.

## الخطوة 3: قراءة بيانات المشروع
فئة `Project` تمثل ملف Microsoft Project محملاً في الذاكرة، مكشوفةً للمهام والموارد والتعيينات. أنشئ كائن `Project` بتمرير `MspDbSettings`. سيقوم Aspose.Tasks بجلب بيانات المشروع من قاعدة البيانات تلقائيًا.

```java
Project project = new Project(settings);
```

في هذه المرحلة يمكنك استكشاف كائن `project` — سرد المهام، الموارد، أو تعديل الحقول حسب الحاجة.

## الخطوة 4: حفظ المشروع كملف PDF
تحدد تعداد `SaveFileFormat` صيغة الإخراج لطريقة `Project.save`، مثل PDF أو XML أو HTML. صدّر المشروع المحمّل إلى صيغة الملف التي تختارها. المثال أدناه يحفظ المشروع كـ **PDF**، وهو مثالي للتقارير القابلة للطباعة. يمكنك أيضًا **تصدير المشروع إلى XML** أو **تحويل المشروع إلى HTML** بتغيير تعداد `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

إذا كنت تفضّل XML، استبدل ببساطة `SaveFileFormat.Pdf` بـ `SaveFileFormat.Xml`. للحصول على إخراج HTML، استخدم `SaveFileFormat.Html`.

## المشكلات الشائعة والحلول
| المشكلة | السبب الشائع | الحل |
|-------|---------------|-----|
| **انتهاء مهلة الاتصال** | عنوان خادم/منفذ غير صحيح أو جدار ناري يمنع الاتصال | تحقق من عنوان الخادم، افتح المنفذ 1433، واختبر الاتصال ببرنامج اختبار JDBC بسيط. |
| **خطأ في المصادقة** | اسم مستخدم/كلمة مرور غير صالحة أو عدم تكوين SQL Server للمصادقة عبر SQL | استخدم تسجيل دخول SQL صالح أو فعّل المصادقة المختلطة على الخادم. |
| **لم يتم العثور على برنامج التشغيل** | ملف jar الخاص بـ JDBC غير موجود في classpath | تأكد من أن `addJDBCDriver` يشير إلى ملف `.jar` الصحيح وأن المسار يستخدم الشرطتين المائلتين (`\\`). |
| **مشروع فارغ بعد التحميل** | صلاحيات غير كافية لقراءة جداول Project Server | امنح تسجيل الدخول صلاحيات SELECT على مخطط قاعدة بيانات Project Server. |

## الأسئلة المتكررة

**س: هل يمكن استخدام Aspose.Tasks لقراءة بيانات المشروع من قواعد بيانات أخرى غير Microsoft Project؟**  
ج: نعم، يدعم Aspose.Tasks قراءة بيانات المشروع من ملفات XML، قواعد بيانات Primavera، وغيرها من صيغ المشاريع القياسية.

**س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من Microsoft Project؟**  
ج: نعم، المكتبة تعمل مع Microsoft Project 2007 حتى أحدث إصدارات 2024، مما يضمن تكاملًا سلسًا عبر الإصدارات.

**س: هل يمكنني تعديل بيانات المشروع قبل حفظه؟**  
ج: بالتأكيد، يمكنك إضافة أو تحديث أو حذف المهام والموارد والحقول المخصصة باستخدام API الغني قبل التصدير.

**س: هل يدعم Aspose.Tasks صيغ إخراج متعددة؟**  
ج: نعم، يمكنك حفظ المشاريع كـ PDF، XML، HTML، CSV، PNG، JPEG، وأكثر — أكثر من 20 صيغة إجمالاً.

**س: أين يمكنني العثور على دعم إضافي أو مساعدة بخصوص Aspose.Tasks؟**  
ج: للحصول على مساعدة إضافية، زر منتدى Aspose.Tasks أو استكشف الوثائق المتاحة على الموقع [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## الخلاصة
باتباعك لهذا الدليل خطوة بخطوة، أصبحت الآن تعرف كيفية **قراءة قاعدة بيانات Microsoft Project**، **حفظ المشروع كملف PDF**، وتصديرها إلى صيغ أخرى باستخدام Aspose.Tasks للـ Java. يزيل هذا النهج الاعتماد على Microsoft Project، يبسط التقارير الآلية، ويفتح الباب أمام تكاملات مخصصة قوية.

---

**آخر تحديث:** 2026-10-31  
**تم الاختبار مع:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [كيفية حفظ المشروع كملف PDF باستخدام Aspose.Tasks – دليل التصدير](/tasks/java/project-file-operations/save-as-pdf/)
- [حفظ المشروع كملف PDF – عرض ورقة المهام باستخدام Aspose.Tasks للـ Java](/tasks/java/task-properties/render-task-sheet/)
- [تصدير المشروع إلى PDF وتقليل الفجوة بين قائمة المهام والتذييل في Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}