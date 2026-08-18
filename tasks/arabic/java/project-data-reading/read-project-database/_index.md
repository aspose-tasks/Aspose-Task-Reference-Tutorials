---
date: 2026-02-18
description: تعلم كيفية حفظ المشروع كملف PDF وقراءة قاعدة بيانات Microsoft Project
  باستخدام Aspose.Tasks للغة Java، بالإضافة إلى الاتصال بـ Project Server، تحويل المشروع
  إلى HTML، وتصدير المشروع إلى XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: حفظ المشروع كملف PDF وقراءة قاعدة بيانات المشروع باستخدام Aspose.Tasks لجافا
url: /ar/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حفظ المشروع كملف PDF وقراءة قاعدة بيانات Microsoft Project باستخدام Aspose.Tasks للغة Java

## المقدمة
في هذا البرنامج التعليمي ستكتشف كيفية **قراءة قاعدة بيانات Microsoft Project** مباشرةً من خادم Microsoft Project Server ثم **حفظ المشروع كملف PDF** باستخدام Aspose.Tasks Java API. سواء كنت بحاجة إلى إنشاء تقارير، أو ترحيل البيانات، أو دمج معلومات المشروع في تطبيقاتك الخاصة، فإن هذا الدليل يرافقك في كل خطوة — من إعداد اتصال قاعدة البيانات إلى تصدير المشروع إلى PDF أو XML أو HTML. في النهاية، ستحصل على حل قوي جاهز للإنتاج يعمل دون الحاجة لتثبيت Microsoft Project على الجهاز المضيف.

## إجابات سريعة
- **ما الذي يفعله Aspose.Tasks؟** يوفر API نقيًا بلغة Java لقراءة وكتابة ومعالجة ملفات وقواعد بيانات Microsoft Project.  
- **هل أحتاج إلى تثبيت Microsoft Project؟** لا، Aspose.Tasks يعمل بشكل مستقل عن Microsoft Project.  
- **ما نوع قاعدة البيانات المدعومة؟** Microsoft SQL Server (الواجهة الخلفية لـ Project Server).  
- **هل يمكنني التصدير إلى صيغ أخرى؟** نعم، بالإضافة إلى PDF يمكنك الحفظ بصيغة XML أو HTML أو CSV وغيرها.  
- **ما هي المتطلبات الأساسية؟** JDK، مكتبة Aspose.Tasks للغة Java، برنامج تشغيل SQL Server JDBC، وبيانات الاعتماد **للاتصال بـ Project Server**.

## ما هو “قراءة قاعدة بيانات Microsoft Project”؟
قراءة قاعدة بيانات Microsoft Project تعني الاتصال بمستودع SQL Server الخاص بـ Project Server، استخراج بيانات المشروع المخزنة، وتحميلها في كائن `Project` يمكن لـ Aspose.Tasks معالجته. هذا النهج مثالي للتقارير الآلية، ترحيل البيانات، أو التحليلات المخصصة.

## لماذا تستخدم Aspose.Tasks للغة Java؟
- **عدم الاعتماد على Microsoft Project** – تشغيل على أي خادم أو بيئة CI.  
- **نموذج كائن غني** – الوصول إلى المهام والموارد والتعيينات والتقويمات والحقول المخصصة برمجياً.  
- **خيارات تصدير متعددة** – PDF، XML، HTML، PNG، إلخ، باستدعاء API واحد.  
- **أداء عالي** – مُحسّن للمشاريع المؤسسية الكبيرة.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

1. بيئة تطوير Java تعمل (JDK 8 أو أحدث).  
2. مكتبة Aspose.Tasks للغة Java مضافة إلى مسار الفئات (classpath) في مشروعك.  
3. بيانات اعتماد الوصول لقاعدة بيانات SQL الخاصة بـ Project Server (اسم الخادم، المنفذ، اسم قاعدة البيانات، اسم المستخدم، كلمة المرور) **للاتصال بـ Project Server**.  
4. برنامج تشغيل Microsoft JDBC لـ SQL Server (مثال: `sqljdbc4.jar`).  

## استيراد الحزم
أولاً، استورد الفئات التي ستحتاجها. تتضمن القائمة فئات أساسية من Aspose.Tasks ومكتبات Java القياسية.

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
إنشاء اتصال موثوق هو الأساس لقراءة بيانات المشروع. تأكد من أن نسخة SQL Server قابلة للوصول من مضيف Java الخاص بك وأن حساب الدخول الذي تستخدمه يمتلك صلاحيات **SELECT** على مخطط Project Server.

## الخطوة 1: إعداد اتصال قاعدة البيانات
أنشئ كائن `MspDbSettings` يحتوي على سلسلة اتصال JDBC. استبدل القيم النائبة بتفاصيل الخادم الفعلية الخاصة بك.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **نصيحة احترافية:** احفظ سلسلة الاتصال في ملف إعدادات آمن أو متغير بيئي بدلاً من كتابة بيانات الاعتماد مباشرةً في الشيفرة.

## الخطوة 2: إضافة برنامج تشغيل JDBC
حمّل برنامج تشغيل Microsoft SQL Server JDBC في وقت التشغيل حتى يتمكن JVM من التواصل مع قاعدة البيانات.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **تحذير:** تأكد من أن نسخة برنامج التشغيل تتطابق مع نسخة SQL Server الخاصة بك. قد يتسبب استخدام برنامج تشغيل غير متوافق في فشل الاتصال.

## الخطوة 3: قراءة بيانات المشروع
أنشئ كائن `Project` بتمرير `MspDbSettings`. سيقوم Aspose.Tasks بجلب بيانات المشروع من قاعدة البيانات تلقائيًا.

```java
Project project = new Project(settings);
```

في هذه المرحلة يمكنك استكشاف كائن `project` — سرد المهام أو الموارد أو تعديل الحقول حسب الحاجة.

## الخطوة 4: حفظ المشروع كملف PDF
صدّر المشروع المحمَّل إلى الصيغة التي تختارها. المثال أدناه يحفظ المشروع كـ **PDF**، وهو مثالي للتقارير القابلة للطباعة. يمكنك أيضًا **تصدير المشروع إلى XML** أو **تحويل المشروع إلى HTML** بتغيير قيمة تعداد `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

إذا كنت تفضّل XML، استبدل `SaveFileFormat.Pdf` بـ `SaveFileFormat.Xml`. للحصول على مخرجات HTML، استخدم `SaveFileFormat.Html`.

## المشكلات الشائعة والحلول
| المشكلة | السبب الشائع | الحل |
|---------|--------------|------|
| **انتهاء مهلة الاتصال** | خادم/منفذ غير صحيح أو جدار حماية يمنع الاتصال | تحقق من عنوان الخادم، افتح المنفذ 1433، واختبر الاتصال باستخدام برنامج اختبار JDBC بسيط. |
| **خطأ في المصادقة** | اسم مستخدم/كلمة مرور غير صالحة أو عدم تكوين SQL Server للمصادقة عبر SQL | استخدم تسجيل دخول SQL صالح أو فعّل المصادقة المختلطة على الخادم. |
| **لم يتم العثور على برنامج التشغيل** | ملف JAR الخاص بـ JDBC غير موجود في مسار الفئات | تأكد من أن `addJDBCDriver` يشير إلى ملف `.jar` الصحيح وأن المسار يستخدم شرطات مائلة مزدوجة (`\\`). |
| **مشروع فارغ بعد التحميل** | أذونات غير كافية لقراءة جداول Project Server | امنح تسجيل الدخول صلاحيات SELECT على مخطط قاعدة بيانات Project Server. |

## الأسئلة المتكررة

**س: هل يمكن استخدام Aspose.Tasks لقراءة بيانات المشروع من قواعد بيانات أخرى غير Microsoft Project؟**  
ج: نعم، يدعم Aspose.Tasks قراءة بيانات المشروع من مصادر متعددة، بما في ذلك ملفات XML، Primavera، وقواعد بيانات Microsoft Project.

**س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من Microsoft Project؟**  
ج: نعم، صُمم Aspose.Tasks للعمل مع إصدارات متعددة من Microsoft Project، مما يضمن تكاملًا سلسًا.

**س: هل يمكنني تعديل بيانات المشروع قبل حفظها؟**  
ج: بالتأكيد، يوفر Aspose.Tasks API غنيًا لإضافة مهام، وتحديث الموارد، وتعيين خصائص المشروع قبل التصدير.

**س: هل يدعم Aspose.Tasks صيغ إخراج متعددة؟**  
ج: نعم، يمكنك حفظ المشاريع كـ PDF، XML، HTML، CSV، PNG، JPEG، وغيرها.

**س: أين يمكنني العثور على دعم إضافي أو مساعدة بخصوص Aspose.Tasks؟**  
ج: للحصول على مساعدة إضافية، زر منتدى Aspose.Tasks أو استكشف الوثائق المتاحة على الموقع [here](https://forum.aspose.com/c/tasks/15).

## الخلاصة
باتباعك لهذا الدليل خطوة بخطوة، أصبحت الآن تعرف كيفية **قراءة قاعدة بيانات Microsoft Project**، **حفظ المشروع كملف PDF**، وتصديره إلى صيغ أخرى باستخدام Aspose.Tasks للغة Java. يزيل هذا النهج الاعتماد على Microsoft Project، يبسط عملية التقارير الآلية، ويفتح الباب أمام تكاملات مخصصة قوية.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}