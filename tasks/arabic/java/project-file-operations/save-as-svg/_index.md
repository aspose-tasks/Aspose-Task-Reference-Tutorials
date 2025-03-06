---
title: تحويل MS Project إلى SVG في Java
linktitle: احفظه بتنسيق SVG في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية حفظ ملفات Microsoft Project بتنسيق SVG في Java باستخدام مكتبة Aspose.Tasks. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية.
weight: 18
url: /ar/java/project-file-operations/save-as-svg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل MS Project إلى SVG في Java

## مقدمة
Aspose.Tasks for Java هي مكتبة قوية للعمل مع ملفات إدارة المشاريع، مما يسمح للمطورين بمعالجة بيانات المشروع وتنفيذ عمليات متنوعة وإنشاء التقارير بكفاءة. في هذا البرنامج التعليمي، سنستكشف كيفية حفظ مشروع بصيغة SVG باستخدام Aspose.Tasks لـ Java. SVG (Scalable Vector Graphics) هو تنسيق يستخدم على نطاق واسع لعرض الرسومات المتجهة على الويب، مما يوفر قابلية التوسع والعرض عالي الجودة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
### بيئة تطوير جافا
تأكد من تثبيت Java Development Kit (JDK) على نظامك. يمكنك تنزيل JDK وتثبيته من موقع Oracle الإلكتروني.
### Aspose.Tasks لمكتبة جافا
 قم بتنزيل وتثبيت مكتبة Aspose.Tasks لـ Java من موقع الويب. يمكنك العثور على رابط التنزيل في الوثائق المقدمة[هنا](https://releases.aspose.com/tasks/java/).

## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم الضرورية في برنامج Java الخاص بك للعمل مع وظائف Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

لنقم الآن بتقسيم المثال المقدم إلى خطوات متعددة:
## الخطوة 2: تحديد دليل البيانات
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"`مع المسار إلى الدليل حيث يوجد ملف المشروع الخاص بك.
## الخطوة 3: تحميل ملف المشروع
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
تقوم هذه الخطوة بتحميل ملف المشروع المسمى "HomeMovePlan.mpp" من دليل البيانات المحدد.
## الخطوة 4: احفظ بصيغة SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
تقوم هذه الخطوة بحفظ المشروع المحمل بتنسيق SVG بالاسم "project5.svg" في دليل البيانات المحدد.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية حفظ مشروع بصيغة SVG باستخدام Aspose.Tasks لـ Java. باتباع الخطوات المتوفرة، يمكنك تحويل ملفات المشروع بكفاءة إلى تنسيق SVG، مما يتيح التكامل السلس مع التطبيقات المستندة إلى الويب أو أدوات التصور.
## الأسئلة الشائعة
### هل Aspose.Tasks for Java متوافق مع كافة إصدارات ملفات Microsoft Project؟
نعم، يدعم Aspose.Tasks for Java إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك تنسيقات MPP وMPT وXML.
### هل يمكنني تخصيص مظهر مخرجات SVG؟
نعم، يمكنك تخصيص مظهر مخرجات SVG عن طريق ضبط المعلمات مثل الخطوط والألوان وتكوينات التخطيط.
### هل يتطلب Aspose.Tasks for Java ترخيصًا للاستخدام التجاري؟
 نعم، يلزم وجود ترخيص صالح للاستخدام التجاري لـ Aspose.Tasks لـ Java. يمكنك الحصول على ترخيص من الموقع[هنا](https://purchase.aspose.com/temporary-license/).
### هل يمكنني تجربة Aspose.Tasks لـ Java قبل الشراء؟
 نعم، يمكنك طلب نسخة تجريبية مجانية من Aspose.Tasks لـ Java من موقع الويب[هنا](https://purchase.aspose.com/buy) لتقييم مميزاته وقدراته.
### أين يمكنني الحصول على الدعم لـ Aspose.Tasks لـ Java؟
 يمكنك الحصول على دعم Aspose.Tasks لـ Java من خلال زيارة المنتدى[هنا](https://forum.aspose.com/c/tasks/15)حيث يمكنك طرح الأسئلة والتفاعل مع المجتمع.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
