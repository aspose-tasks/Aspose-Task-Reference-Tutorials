---
date: 2026-02-07
description: تعلم كيفية تعيين رمز العملة في جافا في مشاريع Aspose.Tasks، وتغيير رمز
  العملة، وتطبيق تنسيق عملة مخصص لملفات Microsoft Project.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: رمز العملة في جافا – كيفية تعيينه في مشاريع Aspose.Tasks
url: /ar/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين رمز العملة في Aspose.Tasks – دليل Java

## Introduction
في هذا الدرس ستتعلم **كيفية تعيين رمز العملة java** لملف Microsoft Project باستخدام Aspose.Tasks Java API. سواء كنت بحاجة إلى *تغيير العملة* للفرق الدولية، أو تعديل *رمز العملة*، أو تطبيق **تنسيق عملة مخصص**، فإن الخطوات أدناه ستقودك عبر العملية مع شروحات واضحة وكود جاهز للتنفيذ.

## Quick Answers
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java.  
- **هل يمكنني تغيير رمز العملة؟** نعم – استخدم `CurrencySymbolPositionType` و `Prj.CURRENCY_SYMBOL`.  
- **ما صيغ الملفات المدعومة؟** XML، MPP، والعديد غيرها عبر `SaveFileFormat`.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تعمل للاختبار؛ الترخيص مطلوب للإنتاج.  
- **كم يستغرق التنفيذ؟** حوالي 5‑10 دقائق لإعداد أساسي.

## How to Set Currency Code Java in Aspose.Tasks
تحدد عملة المشروع كيفية عرض قيم التكلفة — الرمز (مثال: `AUD`)، عدد الأرقام العشرية، الرمز (`$`)، وموقع الرمز. يضمن ضبط هذه الخصائص أن كل حقل متعلق بالتكلفة (معدلات الموارد، ميزانيات المهام، إلخ) يعكس التنسيق النقدي الصحيح لجمهورك.

## Why Use Aspose.Tasks to Change Currency?
- **لا حاجة لتثبيت Microsoft Project** – معالجة الملفات على أي خادم.  
- **تغطية كاملة للـ API** – جميع الحقول المتعلقة بالعملة مكشوفة عبر ثوابت `Prj`.  
- **متعدد المنصات** – يعمل على Windows وLinux وmacOS مع أي بيئة تطوير متوافقة مع Java.  
- **أداء عالي** – معالجة ملفات المشاريع الكبيرة بسرعة وبشكل موثوق.  
- **يدعم تنسيق عملة مخصص** – يمكنك تعريف الرموز، الأرقام العشرية، والموقع لتطابق المعايير الإقليمية.

## Prerequisites
قبل البدء، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – الإصدار 8 أو أعلى.  
2. **Aspose.Tasks for Java** – حمّل أحدث JAR من [صفحة تنزيل Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **بيئة تطوير متكاملة (IDE)** – Eclipse أو IntelliJ IDEA أو أي محرر تفضله.  
4. **مجلد قابل للكتابة** – حيث سيتم حفظ ملف المشروع المُنشأ.

## Import Packages
أولاً، استورد الفئات التي توفر الوصول إلى خصائص المشروع ومعالجة الملفات.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define the Data Directory
حدد المجلد الذي يحتوي على ملفات المصدر الخاصة بك والمكان الذي سيُكتب فيه الناتج.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Create a New Project Instance
أنشئ كائن `Project` جديد. هذا الكائن يمثل ملف Microsoft Project في الذاكرة.

```java
Project project = new Project();
```

### Step 3: Set Currency Properties
هنا حيث نحدد تفاصيل **كيفية تعيين العملة** مثل الرمز، الأرقام العشرية، الرمز، وموقع الرمز.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **نصيحة احترافية:** إذا كنت بحاجة إلى **تغيير عملة المشروع** لملف موجود، فقط قم بتحميله باستخدام `new Project("file.mpp")` قبل تطبيق الإعدادات أعلاه.

### Step 4: Save the Updated Project
احفظ المشروع مرة أخرى على القرص بالتنسيق المطلوب. في هذا المثال نستخدم تنسيق XML، لكن يمكنك أيضًا اختيار `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 5: Confirm Success
اطبع رسالة ودية لتعرف أن العملية انتهت دون أخطاء.

```java
System.out.println("Process completed Successfully");
```

## Common Issues & Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `project.save`** | `dataDir` ليس مسارًا صالحًا أو يفتقر إلى صلاحية الكتابة. | تأكد من وجود الدليل وأن عملية Java لديك لديها صلاحية كتابة. |
| **Currency symbol not showing** | تم ضبط موقع الرمز بشكل غير صحيح وفقًا للمنطقة الخاصة بك. | استخدم `CurrencySymbolPositionType.Before` إذا كان يجب أن يسبق الرمز المبلغ. |
| **Project file does not open in MS Project** | الحفظ بصيغة قديمة مع إعدادات غير متوافقة. | احفظ باستخدام `SaveFileFormat.MPP` للحصول على توافق كامل مع إصدارات MS Project الحديثة. |

## Frequently Asked Questions

**س: هل يمكنني تعيين عملات متعددة في مشروع واحد باستخدام Aspose.Tasks؟**  
ج: نعم، يتيح لك Aspose.Tasks التعامل مع عملات متعددة داخل ملف مشروع واحد عن طريق ضبط خصائص العملة على أساس كل مورد أو كل مهمة.

**س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟**  
ج: بالتأكيد. تدعم المكتبة ملفات MPP من Project 2000 حتى أحدث الإصدارات، بالإضافة إلى XML وصيغ أخرى.

**س: هل يوفر Aspose.Tasks دعمًا لتنسيقات عملة مخصصة؟**  
ج: نعم، يمكنك تعريف رموز مخصصة، أرقام عشرية، وموقع لتلبية أي متطلبات إقليمية.

**س: هل يمكنني دمج Aspose.Tasks مع مكتبات أو أطر Java أخرى؟**  
ج: بالطبع. الـ API مكتبة Java صافية، لذا تعمل بسلاسة مع Spring وHibernate وMaven وGradle وغيرها من الأنظمة.

**س: أين يمكنني العثور على دعم إضافي أو مساعدة لـ Aspose.Tasks؟**  
ج: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على مساعدة المجتمع، أو راجع الوثائق الرسمية للحصول على مراجع API مفصلة.

## Conclusion
أنت الآن تعرف **كيفية تعيين رمز العملة java**، وكيفية **تغيير قيم العملة**، وكيفية **تغيير رمز العملة** باستخدام Aspose.Tasks for Java. تتيح لك هذه الإمكانيات تخصيص بيانات التكلفة للفرق العالمية، وإنشاء تقارير مخصصة للمنطقة، والحفاظ على تناسق ملفات المشروع عبر الحدود.

---

**آخر تحديث:** 2026-02-07  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}