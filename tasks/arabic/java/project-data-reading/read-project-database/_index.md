---
date: 2025-12-13
description: تعلم كيفية قراءة قاعدة بيانات Microsoft Project باستخدام Aspose.Tasks
  للغة Java. دليل خطوة بخطوة مع أمثلة على الشيفرة وأفضل الممارسات.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: قراءة قاعدة بيانات Microsoft Project باستخدام Aspose.Tasks للغة Java
url: /ar/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة قاعدة بيانات Microsoft Project باستخدام Aspose.Tasks for Java

## المقدمة
في هذا البرنامج التعليمي ستكتشف كيفية **قراءة قاعدة بيانات Microsoft Project** مباشرةً من خادم Microsoft Project باستخدام واجهة برمجة تطبيقات Aspose.Tasks Java. سواء كنت بحاجة إلى إنشاء تقارير، أو ترحيل البيانات، أو دمج معلومات المشروع في تطبيقاتك الخاصة، فإن هذا الدليل يرافقك في كل خطوة — من إعداد اتصال قاعدة البيانات إلى تصدير المشروع إلى XML. في النهاية، ستحصل على حل جاهز للإنتاج يعمل دون الحاجة لتثبيت Microsoft Project على الجهاز المضيف.

## إجابات سريعة
- **ماذا يفعل Aspose.Tasks؟** يوفر واجهة برمجة تطبيقات Java صافية لقراءة وكتابة ومعالجة ملفات وقواعد بيانات Microsoft Project.  
- **هل أحتاج إلى تثبيت Microsoft Project؟** لا، يعمل Aspose.Tasks بشكل مستقل عن Microsoft Project.  
- **ما نوع قاعدة البيانات المدعومة؟** Microsoft SQL Server (الواجهة الخلفية لـ Project Server).  
- **هل يمكنني التصدير إلى صيغ أخرى** نعم، إلى جانب XML يمكنك الحفظ إلى PDF، HTML، CSV، وأكثر.  
- **ما هي المتطلبات الأساسية؟** JDK، مكتبة Aspose.Tasks for Java، وسائق JDBC لـ SQL Server.

## ما معنى “قراءة قاعدة بيانات Microsoft Project”؟
قراءة قاعدة بيانات Microsoft Project تعني الاتصال بمستودع SQL Server الخاص بـ Project Server، استخراج بيانات المشروع المخزنة، وتحميلها في كائن `Project` يمكن لـ Aspose.Tasks معالجته. هذا النهج مثالي للتقارير الآلية، ترحيل البيانات، أو التحليلات المخصصة.

## لماذا نستخدم Aspose.Tasks for Java؟
- **بدون اعتماد على Microsoft Project** – يمكن تشغيله على أي خادم أو بيئة CI.  
- **نموذج كائنات غني** – الوصول إلى المهام، الموارد، التعيينات، التقويمات، والحقول المخصصة برمجياً.  
- **خيارات تصدير متعددة** – XML، PDF، HTML، PNG، إلخ، باستدعاء API واحد.  
- **أداء عالي** – مُحسّن للمشاريع المؤسسية الكبيرة.

## المتطلبات الأساسية
قبل أن تبدأ، تأكد من وجود ما يلي:

1. بيئة تطوير Java تعمل (JDK 8 أو أحدث).  
2. مكتبة Aspose.Tasks for Java مضافة إلى مسار الفئة (classpath) في مشروعك.  
3. بيانات اعتماد الوصول لقاعدة بيانات Project Server SQL (اسم الخادم، المنفذ، اسم القاعدة، اسم المستخدم، كلمة المرور).  
4. سائق Microsoft JDBC لـ SQL Server (مثال: `sqljdbc4.jar`).  

## استيراد الحزم
أولاً، استورد الفئات التي ستحتاجها. القائمة تشمل فئات Aspose.Tasks الأساسية ومرافق Java القياسية.

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

## الخطوة 1: إعداد اتصال قاعدة البيانات
أنشئ مثيلًا من `MspDbSettings` يحتوي على سلسلة اتصال JDBC. استبدل القيم النائبة ببيانات الخادم الفعلية الخاصة بك.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **نصيحة احترافية:** احفظ سلسلة الاتصال في ملف إعدادات آمن أو متغير بيئي بدلاً من كتابة بيانات الاعتماد مباشرة في الشيفرة.

## الخطوة 2: إضافة سائق JDBC
حمّل سائق Microsoft SQL Server JDBC في وقت التشغيل حتى يتمكن JVM من التواصل مع قاعدة البيانات.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **تحذير:** تأكد من أن إصدار السائق يتطابق مع إصدار SQL Server الخاص بك. قد يؤدي استخدام سائق غير متوافق إلى فشل الاتصال.

## الخطوة 3: قراءة بيانات المشروع
أنشئ كائن `Project` بتمرير `MspDbSettings`. سيقوم Aspose.Tasks بجلب بيانات المشروع من قاعدة البيانات تلقائيًا.

```java
Project project = new Project(settings);
```

في هذه المرحلة يمكنك استكشاف كائن `project` — سرد المهام، الموارد، أو تعديل الحقول حسب الحاجة.

## الخطوة 4: حفظ بيانات المشروع
صدّر المشروع المحمّل إلى صيغة الملف التي تختارها. المثال أدناه يحفظ المشروع كملف XML، والذي يمكنيراده لاحقًا إلى Microsoft Project أو معالجته بصورة إضافية.

```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```

يمكنك استبدال `SaveFileFormat.Xml` بـ `Pdf` أو `Html` أو `Csv`، حسب احتياجاتك في إعداد التقارير.

## المشكلات الشائعة والحلول
| المشكلة | السبب الشائع | الحل |
|-------|---------------|-----|
| **انتهاء مهلة الاتصال** | خادم/منفذ غير صحيح أو جدار حماية يمنع | تحقق من عنوان الخادم، افتح المنفذ 1433، واختبر الاتصال ببرنامج اختبار JDBC بسيط. |
| **خطأ في المصادقة** | اسم مستخدم/كلمة مرور غير صالحة أو عدم إعداد SQL Server للمصادقة عبر SQL | استخدم حساب SQL صالح أو فعّل وضع المصادقة المختلط على الخادم. |
| **السائق غير موجود** | ملف jar الخاص بـ JDBC غير موجود في مسار الفئة | تأكد من أن `addJDBCDriver` يشير إلى ملف `.jar` الصحيح وأن المسار يستخدم الشرطتين المائلتين (`\\`). |
| **مشروع فارغ بعد التحميل** | أذونات غير كافية لقراءة جداول Project Server | امنح حساب الدخول صلاحيات SELECT على مخطط قاعدة بيانات Project Server. |

## الأسئلة المتكررة

**س: هل يمكن استخدام Aspose.Tasks لقراءة بيانات المشروع من قواعد بيانات أخرى غير Microsoft Project؟**  
ج: نعم، يدعم Aspose.Tasks قراءة بيانات المشروع من مصادر مختلفة، بما في ذلك ملفات XML، Primavera، وقواعد بيانات Microsoft Project.

**س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من Microsoft Project؟**  
ج: نعم، صُمم Aspose.Tasks للعمل مع إصدارات متعددة من Microsoft Project، مما يضمن تكاملًا سلسًا.

**س: هل يمكنني تعديل بيانات المشروع قبل حفظها؟**  
ج: بالطبع، يوفر Aspose.Tasks واجهة برمجة تطبيقات غنية لإضافة مهام، تحديث موارد، وتعيين خصائص المشروع قبل التصدير.

**س: هل يدعم Aspose.Tasks صيغ إخراج متعددة؟**  
ج: نعم، يمكنك حفظ المشاريع كـ XML، PDF، HTML، CSV، PNG، JPEG، وأكثر.

**س: أين يمكنني العثور على دعم إضافي أو مساعدة بخصوص Aspose.Tasks؟**  
ج: للحصول على مساعدة إضافية، زر منتدى Aspose.Tasks أو استكشف الوثائق المتاحة على الموقع [هنا](https://forum.aspose.com/c/tasks/15).

## الخاتمة
باتباعك هذا الدليل خطوة بخطوة، أصبحت الآن تعرف كيفية **قراءة قاعدة بيانات Microsoft Project** باستخدام Aspose.Tasks for Java، تعديل البيانات برمجيًا، وتصديرها إلى الصيغة التي تحتاجها. يزيل هذا النهج الاعتماد على Microsoft Project، يبسط إعداد التقارير الآلية، ويفتح الباب أمام تكاملات مخصصة قوية.

---

**آخر تحديث:** 2025-12-13  
**تم الاختبار مع:** Aspose.Tasks for Java 24.5 (أحدث نسخة وقت كتابة هذا الدليل)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
