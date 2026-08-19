---
date: 2026-03-03
description: تعلم كيفية إنشاء مهمة مشروع جافا وإدارة ملاحظات المهمة باستخدام Aspose.Tasks
  for Java. اتبع هذا الدليل خطوةً بخطوة لإضافة ملاحظات المهمة بكفاءة.
linktitle: Task Notes Management in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إنشاء مهمة مشروع جافا – ملاحظات المهمة باستخدام Aspose.Tasks
url: /ar/java/task-properties/task-notes/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مهمة مشروع Java – ملاحظات المهمة باستخدام Aspose.Tasks

## المقدمة
توفر Aspose.Tasks for Java حلاً قويًا يتيح لك **create project task java** وإدارة الملاحظات المرتبطة بها. في هذا البرنامج التعليمي، سنستعرض تفاصيل التعامل مع ملاحظات المهمة بفعالية باستخدام Aspose.Tasks for Java. سواء كنت مطورًا متمرسًا أو مبتدئًا، سيوجهك هذا الدليل خطوة بخطوة عبر عملية إضافة واسترجاع ملاحظات المهمة بسلاسة.

## الإجابات السريعة
- **ما الذي يمكنني إدارته باستخدام Aspose.Tasks؟** مهام المشروع، الموارد، الجداول، وملاحظات المهمة.  
- **كيف أقوم بتعيين الملاحظات؟** استخدم الحقل `Tsk.NOTES_RTF` في كائن `Task`.  
- **ما الصيغة المدعومة للملاحظات؟** تنسيق النص الغني (RTF) مدعوم بالكامل.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ يتطلب الإنتاج ترخيصًا تجاريًا.  
- **ما نسخة Java المطلوبة؟** JDK 8 أو أعلى.

## المتطلبات المسبقة
قبل أن نبدأ الدرس، تأكد من توفر المتطلبات التالية:
- مجموعة تطوير Java (JDK) مثبتة على جهازك.
- مكتبة Aspose.Tasks for Java تم تنزيلها وإعدادها. يمكنك تنزيلها [هنا](https://releases.aspose.com/tasks/java/).
- فهم أساسي لبرمجة Java.

## استيراد الحزم
تأكد من استيراد الحزم الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## كيفية إنشاء مهمة مشروع Java
### الخطوة 1: إنشاء مشروع ومهمة
أولاً، تحتاج إلى إنشاء نسخة جديدة من `Project` وإضافة مهمة إلى الجذر الخاص به. هذه هي الخطوة الأساسية عندما تقوم بـ **create project task java**.
```java
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task");
```

## كيفية إضافة ملاحظات المهمة
### الخطوة 2: تعيين الملاحظات بصيغة RTF
الآن بعد أن المهمة موجودة، يمكنك إرفاق ملاحظات. المثال التالي يوضح **how to add task notes** بصيغة النص الغني.
```java
String rtf = "{\\rtf1\\ansi\\ansicpg1252\\deff0\\deflang1033{\\fonttbl{\\f0\\fnil\\fcharset134 SimSun;}{\\f1\\fnil\\fcharset0 Calibri;}}\r\n"
        + "{\\*\\generator Msftedit 5.41.21.2510;}\\viewkind4\\uc1\\pard\\sa200\\sl276\\slmult1\\lang9\\f0\\fs22\\'d4\\'e7\\'c9\\'cf\\'ba\\'c3\\f1\\par\r\n"
        + "}\r\n"
        + "; // 早上好";
task.set(Tsk.NOTES_RTF, rtf);
```

### الخطوة 3: استرجاع وعرض الملاحظات
للتحقق من أن الملاحظات تم حفظها بشكل صحيح، اقرأ الحقل `NOTES_RTF` واطبع قيمته.
```java
System.out.println("Notes RTF: " + task.get(Tsk.NOTES_RTF));
```

## المشكلات الشائعة والحلول
- **الملاحظات تظهر مشوشة:** تأكد من أن سلسلة RTF مُهربة بشكل صحيح وتستخدم ترميز Unicode المناسب.
- **خطأ مؤشر فارغ عند الوصول إلى المهمة:** تحقق من أن المهمة أضيفت إلى هيكل المشروع قبل تعيين الملاحظات.
- **استثناء الترخيص:** استخدم ملف ترخيص صالح أو النسخة التجريبية؛ وإلا قد تُظهر Aspose خطأ ترخيص.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Tasks for Java مجانًا؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الوثائق التفصيلية؟
راجع الوثائق [هنا](https://reference.aspose.com/tasks/java/).

### كيف يمكنني الحصول على الدعم لـ Aspose.Tasks for Java؟
قم بزيارة منتدى الدعم [هنا](https://forum.aspose.com/c/tasks/15).

### هل تتوفر تراخيص مؤقتة؟
نعم، يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني شراء Aspose.Tasks for Java؟
يمكنك شراء المنتج [هنا](https://purchase.aspose.com/buy).

#### أسئلة وإجابات إضافية
**س: هل يمكنني تخزين الملاحظات كنص عادي بدلاً من RTF؟**  
ج: نعم، يمكنك استخدام الحقل `Tsk.NOTES` للملاحظات النصية العادية، لكن RTF يحافظ على التنسيق.

**س: هل من الممكن تحديث الملاحظات بعد حفظ المهمة؟**  
ج: بالتأكيد. استدعِ `task.set(Tsk.NOTES_RTF, newRtf)` ثم احفظ المشروع.

**س: هل تدعم Aspose.Tasks الملاحظات متعددة اللغات؟**  
ج: نعم، طالما أن سلسلة RTF مُشفرة بشكل صحيح (UTF‑8) وتتوفر الخطوط المناسبة.

## الخاتمة
إدارة ملاحظات المهمة في Aspose.Tasks for Java عملية بسيطة بمجرد أن تعرف **how to create project task java** وترفق ملاحظات RTF. الآن لديك مقتطفات الشيفرة الأساسية لإضافة، استرجاع، وحل مشكلات ملاحظات المهمة في تطبيقات Java الخاصة بك.

---

**آخر تحديث:** 2026-03-03  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}