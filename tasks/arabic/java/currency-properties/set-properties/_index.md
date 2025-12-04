---
date: 2025-12-04
description: تعلم كيفية تعيين العملة في مشاريع Aspose.Tasks Java، بما في ذلك كيفية
  تغيير العملة وتغيير رمز العملة في Java. تعامل مع ملفات Microsoft Project بسهولة.
language: ar
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: كيفية تعيين العملة في مشاريع Aspose.Tasks – دليل Java
url: /java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين العملة في مشاريع Aspose.Tasks – دليل Java

## المقدمة
في هذا الدرس ستتعلم **كيفية تعيين العملة** لملف Microsoft Project باستخدام Aspose.Tasks Java API. سواء كنت بحاجة إلى *تغيير العملة* للفرق الدولية أو تعديل *رمز العملة* في Java، فإن الخطوات أدناه ستقودك خلال العملية مع شروحات واضحة وكود جاهز للتنفيذ.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java.  
- **هل يمكنني تغيير رمز العملة؟** نعم – استخدم `CurrencySymbolPositionType` و `Prj.CURRENCY_SYMBOL`.  
- **ما صيغ الملفات المدعومة؟** XML، MPP، والعديد غيرها عبر `SaveFileFormat`.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للاختبار؛ الترخيص مطلوب للإنتاج.  
- **كم يستغرق التنفيذ؟** حوالي 5‑10 دقائق لإعداد أساسي.

## ما هي “العملة” في ملف المشروع؟
تحدد عملة المشروع كيفية عرض قيم التكلفة—الرمز (مثال: `AUD`)، عدد الأرقام العشرية، الرمز (`$`)، وموقع الرمز. ضبط هذه الخصائص يضمن أن كل حقل متعلق بالتكلفة (معدلات الموارد، ميزانيات المهام، إلخ) يعكس الصيغة النقدية الصحيحة لجمهورك.

## لماذا نستخدم Aspose.Tasks لتغيير العملة؟
- **لا حاجة لتثبيت Microsoft Project** – يمكن تعديل الملفات على أي خادم.  
- **تغطية كاملة للـ API** – جميع الحقول المتعلقة بالعملة متاحة عبر ثوابت `Prj`.  
- **متعدد المنصات** – يعمل على Windows، Linux، و macOS مع أي بيئة تطوير Java.  
- **أداء عالي** – يعالج ملفات المشاريع الكبيرة بسرعة وموثوقية.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

1. **مجموعة تطوير Java (JDK)** – الإصدار 8 أو أعلى.  
2. **Aspose.Tasks for Java** – حمّل أحدث JAR من [صفحة تنزيل Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **بيئة تطوير متكاملة (IDE)** – Eclipse، IntelliJ IDEA، أو أي محرر تفضله.  
4. **مجلد قابل للكتابة** – حيث سيتم حفظ ملف المشروع المُنشأ.

## استيراد الحزم
أولاً، استورد الفئات التي توفر الوصول إلى خصائص المشروع ومعالجة الملفات.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## دليل خطوة بخطوة

### الخطوة 1: تعريف دليل البيانات
حدد المجلد الذي يحتوي على ملفات المصدر ومكان كتابة الناتج.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 2: إنشاء كائن مشروع جديد
أنشئ كائن `Project` جديد. هذا الكائن يمثل ملف Microsoft Project في الذاكرة.

```java
Project project = new Project();
```

### الخطوة 3: تعيين خصائص العملة
هنا نوضح **كيفية تعيين العملة** بما يشمل الرمز، عدد الأرقام، الرمز، وموقع الرمز.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **نصيحة احترافية:** إذا كنت بحاجة إلى **تغيير العملة** لمشروع موجود، ما عليك سوى تحميل الملف باستخدام `new Project("file.mpp")` قبل تطبيق الإعدادات أعلاه.

### الخطوة 4: حفظ المشروع المحدث
اكتب المشروع مرة أخرى إلى القرص بالص المطلوبة. في هذا المثال نستخدم صيغة XML، لكن يمكنك أيضًا اختيار `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### الخطوة 5: تأكيد النجاح
اطبع رسالة ودية لتعرف أن العملية انتهت دون أخطاء.

```java
System.out.println("Process completed Successfully");
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **`NullPointerException` عند `project.save`** | `dataDir` ليس مسارًا صالحًا أو يفتقر إلى صلاحية الكتابة. | تأكد من وجود الدليل وأن عملية Java لديها صلاحية الكتابة. |
| **رمز العملة لا يظهر** | تم ضبط موقع الرمز بشكل غير صحيح للمنطقة. | استخدم `CurrencySymbolPositionType.Before` إذا كان الرمز يجب أن يسبق المبلغ. |
| **ملف المشروع لا يفتح في MS Project** | تم حفظه بصيغة قديمة مع إعدادات غير متوافقة. | احفظ باستخدام `SaveFileFormat.MPP` للحصول على توافق كامل مع إصدارات MS Project الحديثة. |

## الأسئلة المتكررة

**س: هل يمكنني تعيين عملات متعددة في مشروع واحد باستخدام Aspose.Tasks؟**  
ج: نعم، يسمح Aspose.Tasks بالتعامل مع عملات متعددة داخل ملف مشروع واحد عبر ضبط خصائص العملة لكل مورد أو مهمة على حدة.

**س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟**  
ج: بالتأكيد. تدعم المكتبة ملفات MPP من Project 2000 حتى أحدث الإصدارات، بالإضافة إلى XML وصيغ أخرى.

**س: هل يوفر Aspose.Tasks دعمًا لتنسيقات عملة مخصصة؟**  
ج: نعم، يمكنك تعريف رموز مخصصة، أرقام عشرية، ومواقع لتلبية أي متطلبات إقليمية.

**س: هل يمكن دمج Aspose.Tasks مع مكتبات أو أطر Java أخرى؟**  
ج: بالطبع. الـ API نقي Java، لذا يعمل بسلاسة مع Spring، Hibernate، Maven، Gradle، وغيرها.

**س: أين يمكنني العثور على دعم إضافي أو مساعدة بخصوص Aspose.Tasks؟**  
ج: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على مساعدة المجتمع، أو راجع الوثائق الرسمية للحصول على مراجع API مفصلة.

## الخاتمة
الآن تعرف **كيفية تعيين العملة**، وكيفية **تغيير قيم العملة**، وكيفية **تغيير رمز العملة في Java** باستخدام Aspose.Tasks for Java. تتيح لك هذه الإمكانيات تخصيص بيانات التكلفة للفرق العالمية، إنشاء تقارير مخصصة حسب المنطقة، والحفاظ على تناسق ملفات المشروع عبر الحدود.

---

**آخر تحديث:** 2025-12-04  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}