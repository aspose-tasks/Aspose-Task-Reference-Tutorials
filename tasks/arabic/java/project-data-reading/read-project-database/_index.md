---
title: قراءة بيانات المشروع من قاعدة بيانات MS Project في Aspose.Tasks
linktitle: قراءة بيانات المشروع من قاعدة بيانات Microsoft Project في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية قراءة بيانات المشروع من قاعدة بيانات Microsoft Project باستخدام Aspose.Tasks لـ Java. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية.
weight: 12
url: /ar/java/project-data-reading/read-project-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة بيانات المشروع من قاعدة بيانات MS Project في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية قراءة بيانات المشروع من قاعدة بيانات Microsoft Project باستخدام Aspose.Tasks لـ Java. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات Java قوية تسمح للمطورين بمعالجة مستندات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project. باتباع الخطوات الموضحة في هذا الدليل، ستتعلم كيفية استخراج بيانات المشروع بكفاءة من قاعدة البيانات وحفظها بالتنسيق المطلوب.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. المعرفة الأساسية ببرمجة جافا.
2. تم تثبيت Java Development Kit (JDK) على نظامك.
3. تم تنزيل Aspose.Tasks لمكتبة Java وتكوينها في مشروعك.

## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية:
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
أولاً، تحتاج إلى إعداد الاتصال بقاعدة بيانات Microsoft Project. يتضمن ذلك تحديد عنوان URL لقاعدة البيانات واسم الخادم ورقم المنفذ واسم قاعدة البيانات واسم المستخدم وكلمة المرور.
```java
String url = "jdbc:sqlserver://"؛
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## الخطوة 2: إضافة برنامج تشغيل JDBC
بعد ذلك، تحتاج إلى إضافة برنامج تشغيل JDBC إلى مشروعك. يسهل برنامج التشغيل هذا الاتصال بين تطبيقات Java وقاعدة بيانات Microsoft SQL Server.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## الخطوة 3: قراءة بيانات المشروع
 الآن، قم بإنشاء`Project` الكائن وتحميل بيانات المشروع من قاعدة البيانات باستخدام الإعدادات المحددة مسبقًا.
```java
Project project = new Project(settings);
```
## الخطوة 4: حفظ بيانات المشروع
وأخيراً، احفظ بيانات المشروع بالتنسيق المطلوب. في هذا المثال، نقوم بحفظه كملف XML.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
تهانينا! لقد نجحت في قراءة بيانات المشروع من قاعدة بيانات Microsoft Project باستخدام Aspose.Tasks لـ Java.

## خاتمة
في هذا البرنامج التعليمي، قمنا بتغطية عملية قراءة بيانات المشروع من قاعدة بيانات Microsoft Project باستخدام Aspose.Tasks لـ Java. باتباع الخطوات الموضحة، يمكنك استخراج معلومات المشروع بسهولة ومعالجتها وفقًا لمتطلباتك. يعمل Aspose.Tasks على تبسيط التعامل مع مستندات Microsoft Project، مما يتيح استخراج البيانات ومعالجتها بكفاءة.
## الأسئلة الشائعة
### س: هل يمكن استخدام Aspose.Tasks لقراءة بيانات المشروع من قواعد بيانات أخرى إلى جانب Microsoft Project؟
ج: نعم، يدعم Aspose.Tasks قراءة بيانات المشروع من مصادر مختلفة، بما في ذلك ملفات XML وPrimavera وقواعد بيانات Microsoft Project.
### س: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من Microsoft Project؟
ج: نعم، تم تصميم Aspose.Tasks للعمل مع إصدارات مختلفة من Microsoft Project، مما يضمن التوافق والتكامل السلس.
### س: هل يمكنني معالجة بيانات المشروع قبل حفظها؟
ج: بالتأكيد، يوفر Aspose.Tasks نطاقًا واسعًا من الميزات لمعالجة بيانات المشروع، مثل إضافة المهام وتحديث الموارد وتعيين خصائص المشروع.
### س: هل يدعم Aspose.Tasks تنسيقات الإخراج المتعددة؟
ج: نعم، يدعم Aspose.Tasks تنسيقات الإخراج المختلفة، بما في ذلك XML وPDF وHTML وتنسيقات الصور مثل PNG وJPEG.
### س: أين يمكنني العثور على مزيد من الدعم أو المساعدة فيما يتعلق بـ Aspose.Tasks؟
 ج: للحصول على دعم أو مساعدة إضافية، يمكنك زيارة منتدى Aspose.Tasks أو استكشاف الوثائق المتوفرة على موقع الويب[هنا](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
