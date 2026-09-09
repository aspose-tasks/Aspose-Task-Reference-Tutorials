---
date: 2026-09-09
description: تعلم كيفية تغيير رمز العملة في مشاريع Aspose.Tasks باستخدام Java، ضبط
  رموز العملات، تعديل الرموز، وتطبيق تنسيقات مخصصة لملفات Microsoft Project.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: تعيين خصائص العملة في مشاريع Aspose.Tasks
og_description: كيفية تغيير رمز العملة في Aspose.Tasks باستخدام Java. اكتشف تعليمات
  خطوة بخطوة، المتطلبات، ونصائح لتخصيص تنسيق تكلفة المشروع.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: كيفية تغيير رمز العملة في Aspose.Tasks – دليل Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: كيفية تغيير رمز العملة في مشاريع Aspose.Tasks – دليل Java
url: /ar/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تغيير رمز العملة في Aspose.Tasks – دليل Java

## مقدمة
في هذا البرنامج التعليمي ستتعلم **كيفية تغيير رمز العملة** لملف Microsoft Project باستخدام Aspose.Tasks Java API. سواء كنت تُعد تقارير لعميل خارجي، أو تُدمج الميزانيات عبر مناطق متعددة، أو تحتاج ببساطة إلى مطابقة معايير المحاسبة في شركتك، فإن تعديل رمز العملة يضمن أن كل حقل متعلق بالتكلفة يعرض العلامة النقدية الصحيحة. يشرح الدليل كل خطوة، من إعداد بيئة التطوير إلى حفظ التغييرات في ملف مشروع جديد أو موجود.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java.  
- **هل يمكنني تغيير رمز العملة؟** نعم – عيّن `Prj.CURRENCY_SYMBOL` واختر `CurrencySymbolPositionType`.  
- **ما صيغ الملفات المدعومة؟** XML، MPP، والعديد غيرها عبر `SaveFileFormat`.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للاختبار؛ الترخيص مطلوب للإنتاج.  
- **كم يستغرق تنفيذ ذلك؟** حوالي 5‑10 دقائق لإعداد أساسي.

## كيفية تغيير رمز العملة في Aspose.Tasks باستخدام Java؟
حمّل المشروع المستهدف (أو أنشئ مشروعًا جديدًا)، عيّن خصائص العملة المطلوبة، واحفظ الملف. العملية بالكامل تتكون من ثلاث استدعاءات API: إنشاء أو تحميل كائن `Project`، تعيين رمز العملة، الرمز، والموضع، ثم استدعاء `project.save`. هذا النهج يعمل لكل من المشاريع الجديدة والملفات الموجودة دون الحاجة إلى تثبيت Microsoft Project.

## لماذا تستخدم Aspose.Tasks لتغيير العملة؟
توفر Aspose.Tasks **تغطية كاملة للـ API لأكثر من 30 خاصية متعلقة بالعملة**، مما يتيح لك تعريف الكود، الرمز، عدد الأرقام العشرية، والموضع في مكان واحد. تعالج المكتبة ملفات Project التي تتجاوز مئات الصفحات في أقل من ثانية على خوادم عادية، وتعمل على Windows، Linux، و macOS دون أي تبعيات إضافية.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK) 8 أو أعلى** – يتطلب الـ API على الأقل JDK 8.  
2. **Aspose.Tasks for Java** – حمّل أحدث JAR من [صفحة تحميل Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **بيئة تطوير متكاملة (IDE)** – Eclipse، IntelliJ IDEA، أو أي محرر يدعم Java.  
4. **مجلد قابل للكتابة** – حيث سيتم حفظ ملف المشروع المُنشأ.

## استيراد الحزم
الفئات التالية تمنحك الوصول إلى خصائص المشروع، معالجة الملفات، وإعدادات العملة.  

`Project` – يمثل ملف Microsoft Project في الذاكرة.  
`Prj` – يحتوي على ثوابت لجميع خصائص مستوى المشروع، بما في ذلك حقول العملة.  
`CurrencySymbolPositionType` – يعدد المواضع الممكنة لرمز العملة (قبل أو بعد المبلغ).  

هذه الاستيرادات مطلوبة قبل أن يتمكن أي كود من تعديل مشروع.

## دليل خطوة بخطوة

### الخطوة 1: تعريف دليل البيانات
اختر مجلدًا يحتوي على ملفات المصدر الخاصة بك وحيث سيتم كتابة المخرجات. تأكد من وجود الدليل وأن عملية Java لديك تملك صلاحية الكتابة.

### الخطوة 2: إنشاء نسخة مشروع جديدة
فئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف Project واحد في الذاكرة. إنشاء نسخة منها يولد مشروعًا فارغًا جاهزًا للتكوين.

### الخطوة 3: تعيين خصائص العملة
هنا تقوم بتكوين رمز العملة، عدد الأرقام العشرية، الرمز نفسه، وموضع الرمز.  

- **رمز العملة** – رمز ISO 4217 المكوّن من ثلاثة أحرف مثل `AUD` أو `USD`.  
- **الأرقام العشرية** – عادةً 2 لمعظم العملات.  
- **رمز العملة** – الحرف أو السلسلة التي تُعرض مع القيم، مثل `$` أو `€`.  
- **موضع الرمز** – `CurrencySymbolPositionType.Before` يضع الرمز قبل الرقم؛ `After` يضعه بعده.

هذه الإعدادات تؤثر على كل الحقول المتعلقة بالتكلفة (أسعار الموارد، ميزانيات المهام، إلخ) في المشروع.

> **نصيحة احترافية:** إذا كنت بحاجة لتغيير العملة لملف موجود، حمّله باستخدام `new Project("file.mpp")` قبل تطبيق الإعدادات أعلاه.

### الخطوة 4: حفظ المشروع المحدث
اكتب المشروع مرة أخرى إلى القرص باستخدام الصيغة المطلوبة. صيغة XML قابلة للقراءة البشرية، بينما `SaveFileFormat.MPP` تحافظ على التوافق الكامل مع Microsoft Project.

### الخطوة 5: تأكيد النجاح
اطبع رسالة قصيرة أو سجل إدخالًا لتعرف أن العملية انتهت دون أخطاء. هذا مفيد خصوصًا في خطوط الأنابيب الآلية.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **`NullPointerException` على `project.save`** | `dataDir` ليس مسارًا صالحًا أو يفتقر إلى صلاحية الكتابة. | تأكد من وجود الدليل وأن عملية Java لديك تملك صلاحية الكتابة. |
| **رمز العملة لا يظهر** | تم تعيين موضع الرمز بشكل غير صحيح للمنطقة المحلية. | استخدم `CurrencySymbolPositionType.Before` إذا كان الرمز يجب أن يسبق المبلغ. |
| **ملف المشروع لا يفتح في MS Project** | تم حفظه بصيغة قديمة بإعدادات غير متوافقة. | احفظ باستخدام `SaveFileFormat.MPP` للحصول على توافق كامل مع إصدارات MS Project الحديثة. |

## الأسئلة المتكررة

**س: هل يمكنني تعيين عملات متعددة في مشروع واحد باستخدام Aspose.Tasks؟**  
ج: نعم، يمكنك تعيين إعدادات عملة مختلفة للموارد أو المهام الفردية بعد تعريف عملة المشروع على المستوى العام.

**س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟**  
ج: بالتأكيد. تدعم المكتبة ملفات MPP من Project 2000 حتى أحدث الإصدارات، بالإضافة إلى XML وصيغ التبادل الأخرى.

**س: هل توفر Aspose.Tasks دعمًا لتنسيقات عملة مخصصة؟**  
ج: نعم، يمكنك تعريف رموز مخصصة، أعداد أرقام عشرية، ومواضع لتلبية أي متطلبات إقليمية، وتُحفظ هذه الإعدادات في الملف.

**س: هل يمكنني دمج Aspose.Tasks مع أطر عمل Java أخرى؟**  
ج: بالطبع. الـ API نقي Java، لذا يعمل بسلاسة مع Spring، Hibernate، Maven، Gradle، وغيرها.

**س: أين يمكنني العثور على مساعدة إضافية أو أمثلة؟**  
ج: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على مساعدة المجتمع، أو راجع الوثائق الرسمية للمراجع التفصيلية للـ API.

## الخلاصة
أنت الآن تعرف **كيفية تغيير رمز العملة** في مشاريع Aspose.Tasks باستخدام Java، وكيفية تعيين رمز العملة، تعديل الأرقام العشرية، وتطبيق رمز مخصص. هذه الإمكانيات تتيح لك توليد تقارير تكلفة مخصصة للمنطقة، مواءمة ميزانيات المشروع مع معايير المحاسبة الإقليمية، والحفاظ على ملفات Microsoft Project متسقة عبر الفرق العالمية.

---

**آخر تحديث:** 2026-09-09  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## دروس ذات صلة

- [java project properties – Extract currency symbol from MPP using Aspose.Tasks for Java](/tasks/java/currency/currency-symbols/)
- [Read Currency Properties Java with Aspose.Tasks Projects](/tasks/java/currency-properties/read-properties/)
- [Manage Currency Codes Java with Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}