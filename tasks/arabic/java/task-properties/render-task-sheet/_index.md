---
title: تقديم ورقة المهام في Aspose.Tasks
linktitle: تقديم ورقة المهام في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: أطلق العنان لإدارة المشاريع الفعالة باستخدام Aspose.Tasks لـ Java. تقديم أوراق المهام بسلاسة. اكتشف الدليل الشامل الآن!
weight: 27
url: /ar/java/task-properties/render-task-sheet/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تقديم ورقة المهام في Aspose.Tasks

## مقدمة
مرحبًا بك في عالم Aspose.Tasks for Java، وهي مكتبة قوية تمكّن مطوري Java من إمكانات إدارة المشاريع بسلاسة. سواء كنت مطورًا متمرسًا أو مبتدئًا يتطلع إلى تحسين مهارات إدارة المشروعات لديك، فسيرشدك هذا الدليل خلال عرض أوراق المهام باستخدام Aspose.Tasks.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): قم بتثبيت أحدث إصدار من JDK لتنفيذ برامج Java.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل المكتبة وإعدادها. يمكن ان تجدها[هنا](https://releases.aspose.com/tasks/java/).
## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية في مشروع Java الخاص بك. هذه الخطوة ضرورية للوصول إلى وظائف Aspose.Tasks في التعليمات البرمجية الخاصة بك.
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```
## الخطوة 1: قم بتعيين دليل المستندات الخاص بك
ابدأ بتحديد المسار إلى دليل المستند الخاص بك في كود Java. هذا هو المكان الذي سيتم فيه حفظ ملف مشروعك وورقة المهام المقدمة.
```java
String dataDir = "Your Document Directory";
```
## الخطوة 2: تحميل ملف المشروع
قم بتحميل ملف مشروعك باستخدام مكتبة Aspose.Tasks. في هذا المثال، نفترض أن ملف المشروع يسمى "NewProductDev.mpp."
```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```
## الخطوة 3: تكوين خيارات الحفظ
قم بتكوين خيارات الحفظ، مع تحديد تنسيق العرض التقديمي المطلوب. في هذه الحالة، نريد إنشاء ورقة مهام بتنسيق PDF.
```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```
## الخطوة 4: احفظ المشروع كورقة مهام
احفظ المشروع بالخيارات المحددة لإنشاء ورقة المهام بتنسيق PDF.
```java
project.save(dataDir + "taskSheet.pdf", options);
```
## الخطوة 5: مراجعة النتيجة
قم بمراجعة ورقة المهام التي تم إنشاؤها والمرفقة في الدليل المحدد. يتم الآن عرض ورقة المهام الخاصة بمشروعك بكفاءة باستخدام Aspose.Tasks لـ Java.
## خاتمة
يعمل Aspose.Tasks for Java على تبسيط إدارة المشروع من خلال توفير ميزات قوية لعرض أوراق المهام. باتباع هذا الدليل المفصّل خطوة بخطوة، تكون قد استفدت من قوة Aspose.Tasks لتعزيز قدرات إدارة مشروعك.

## الأسئلة الشائعة
### هل Aspose.Tasks متوافق مع جميع إصدارات Java؟
 نعم، Aspose.Tasks متوافق مع مجموعة واسعة من إصدارات Java. الرجوع إلى[توثيق](https://reference.aspose.com/tasks/java/) للحصول على تفاصيل محددة.
### هل يمكنني تجربة Aspose.Tasks قبل الشراء؟
 قطعاً! اكتشف النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم لـ Aspose.Tasks؟
 انضم إلى مجتمع Aspose.Tasks على[المنتدى](https://forum.aspose.com/c/tasks/15) للدعم والمناقشات.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟
 احصل على ترخيصك المؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني شراء Aspose.Tasks لـ Java؟
 شراء Aspose.Tasks لجافا[هنا](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
