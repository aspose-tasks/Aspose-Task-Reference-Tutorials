---
date: 2026-02-10
description: تعلم كيفية استخراج رموز العملات من ملفات MS Project باستخدام Aspose.Tasks
  للغة Java – الطريقة السريعة للحصول على رمز العملة الذي يحتاجه مطورو Java.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية استرجاع العملة من MS Project باستخدام Aspose.Tasks
url: /ar/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استرجاع العملة من MS Project باستخدام Aspise.Tasks

## مقدمة
مرحبًا! في هذا الدرس ستكتشف **how to retrieve currency** من ملفات MS Project باستخدام Aspose.Tasks Java API. سواءً كنت تُنشئ تقارير مالية متعددة العملات، أو تجمع مشاريع من مناطق مختلفة، أو تحتاج ببساطة إلى الرموز النقدية الصحيحة للمعالجة اللاحقة، فإن هذا الدليل يرافقك في كل خطوة — من إعداد بيئتك إلى استخراج رمز العملة برمجيًا. في النهاية، ستكون قادرًا على قراءة ملفات MS Project واستخدام استدعاء **get currency code java** للحصول على معرف العملة وفق معيار ISO.

## إجابات سريعة
- **What does the API do?** يقرأ ملفات MS Project ويكشف عن خصائص مثل رمز العملة.  
- **Which language is used?** Java، عبر مكتبة Aspose.Tasks for Java.  
- **Do I need a license?** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم الحصول على رخصة تجارية للإنتاج.  
- **Can I retrieve the code in one line?** نعم—`prj.get(Prj.CURRENCY_CODE)` تُعيد سلسلة رمز العملة.  
- **Is it compatible with all Project versions?** Aspose.Tasks يدعم كل من الصيغ القديمة (MPP) والحديثة (XML, XER).

## ما هو **read ms project file**؟
قراءة ملف MS Project تعني فتح مستند مشروع (*.mpp* أو أي صيغة مدعومة) برمجيًا والوصول إلى هياكله البيانات—المهام، الموارد، التقويمات، وإعدادات المالية—دون الحاجة إلى التفاعل اليدوي مع Microsoft Project نفسه.

## لماذا نستخدم Aspose.Tasks ل**read msproject** الملفات؟
- **Full format support** – يدعم الملفات من Project 98 حتى أحدث إصدارات Office.  
- **No COM or Office installation needed** – Java نقي، مثالي لأتمتة الخوادم.  
- **Rich API** – يتيح الوصول المباشر إلى خصائص مثل `Prj.CURRENCY_CODE`، مما يسمح لك بـ **how to retrieve currency** فورًا.  
- **Performance** – تحليل خفيف الوزن، مثالي لمعالجة دفعات متعددة من المشاريع.

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من توفر ما يلي:

### Java Development Kit (JDK) مثبت
تأكد من وجود JDK حديث على جهازك. يمكنك تنزيل وتثبيت أحدث نسخة من JDK من [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### مكتبة Aspose.Tasks for Java
حمّل وأعدد مكتبة Aspose.Tasks for Java. الوثائق التفصيلية والملفات الثنائية الأحدث متوفرة [here](https://reference.aspose.com/tasks/java/).

## استيراد الحزم
لبدء العمل، دعنا نستورد الحزم الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد دليل البيانات
حدد المجلد الذي يحتوي على ملف *.mpp* الخاص بك. عدّل المسار ليتوافق مع بيئتك.
```java
String dataDir = "Your Data Directory";
```

### الخطوة 2: تحميل ملف المشروع
أنشئ كائن `Project` بتحميل ملف MS Project. هذه هي النقطة التي تقوم فيها بـ **read msproject** البيانات إلى الذاكرة.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### الخطوة 3: استرجاع رمز العملة
الآن بعد تحميل المشروع، يمكنك الحصول على معلومات **how to retrieve currency** باستدعاء واحد. هذا يوضح استخدام **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
سيكون الناتج هو رمز العملة ISO المكوّن من ثلاثة أحرف (مثال: `USD`، `EUR`، `GBP`) الذي تم تكوين المشروع لاستخدامه.

### الخطوة 4: كيفية استرجاع رمز العملة في Java (سياق إضافي)
إذا كنت بحاجة لتخزين القيمة لاستخدام لاحق، ما عليك سوى تعيينها إلى متغيّر:
*لا يلزم أي كتلة شيفرة إضافية* – فقط احتفظ بالسلسلة التي تُعيدها `prj.get(Prj.CURRENCY_CODE)` ومرّرها إلى أي خدمة مالية، محرك تقارير، أو مكوّن واجهة مستخدم.

### الخطوة 5: (اختياري) استخدام رمز العملة
قد ترغب في تطبيق الرمز المسترجع في أماكن أخرى — مثل تنسيق قيم التكلفة في تقرير مخصص أو تمريره إلى واجهة برمجة تطبيقات مالية. تشمل السيناريوهات الشائعة:
- **Report generation** – أضف الرمز قبل أعمدة التكلفة (`USD 1,200`).  
- **API integration** – أرسل رمز ISO إلى بوابات الدفع التي تتطلب معرف عملة.  
- **Data consolidation** – اجمع عدة مشاريع حسب العملة لتحليل المحفظة.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **Null output** | ملف المشروع لا يحدد عملة (القيمة الافتراضية فارغة). | حدد العملة في Microsoft Project أو عيّنها عبر `prj.set(Prj.CURRENCY_CODE, "USD");` قبل القراءة. |
| **File not found** | مسار `dataDir` غير صحيح. | تحقق من المسار وتأكد من أن اسم الملف مطابق تمامًا، بما في ذلك حساسية الأحرف. |
| **Unsupported file version** | ملف *.mpp* قديم جدًا أو تالف. | استخدم أحدث نسخة من Aspose.Tasks أو حوّل الملف إلى صيغة أحدث في Microsoft Project أولاً. |

## الأسئلة المتكررة

**Q: Can Aspose.Tasks handle complex project structures?**  
A: نعم، يمكن للـ API قراءة ومعالجة هياكل المهام متعددة المستويات، مجموعات الموارد، والحقول المخصصة دون أي مشكلة.

**Q: Is Aspose.Tasks compatible with different versions of MS Project files?**  
A: بالتأكيد. يدعم صيغ MPP، XML، XER، وغيرها عبر إصدارات متعددة من Microsoft Project.

**Q: Does Aspose.Tasks provide documentation and support?**  
A: وثائق شاملة، أمثلة على الشيفرة، ودعم مخصص متوفران على موقع Aspose.

**Q: Can I try Aspose.Tasks before purchasing?**  
A: تتوفر نسخة تجريبية مجانية لتقييم جميع الميزات، بما في ذلك قراءة رموز العملة.

**Q: Where can I get temporary licenses for Aspose.Tasks?**  
A: يمكن الحصول على تراخيص مؤقتة من [website](https://purchase.aspose.com/temporary-license/) للتقييم قصير الأمد.

**آخر تحديث:** 2026-02-10  
**تم الاختبار مع:** Aspose.Tasks for Java (latest version)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}