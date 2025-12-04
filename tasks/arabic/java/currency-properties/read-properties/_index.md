---
date: 2025-12-04
description: تعلم كيفية قراءة خصائص العملة في جافا من ملفات MS Project باستخدام Aspose.Tasks
  for Java. اتبع هذا الدليل خطوةً بخطوة لاستخراج رمز العملة، والرمز، وعدد الأرقام
  العشرية، وموقعه برمجيًا.
language: ar
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: قراءة خصائص العملة في جافا باستخدام مشاريع Aspose.Tasks
url: /java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة خصائص العملة Java باستخدام مشاريع Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي ستقوم **بقراءة خصائص العملة Java** من ملفات Microsoft Project باستخدام Aspose.Tasks for Java API. يتيح لك Aspose.Tasks العمل مع ملفات .mpp دون الحاجة إلى تثبيت Microsoft Project، مما يجعله مثالياً للتقارير الآلية، ترحيل البيانات، أو التكامل مع تطبيقات المؤسسة المبنية على Java. بنهاية هذا الدليل، ستكون قادرًا على استخراج رمز العملة، الرمز، عدد الأرقام العشرية، وموقع الرمز مباشرةً من ملف المشروع.

## إجابات سريعة
- **ماذا يعني “read currency properties java”؟** يشير إلى استرجاع البيانات الوصفية المتعلقة بالعملة (الرمز، الرمز، الأرقام، الموقع) من ملف MS Project باستخدام كود Java.  
- **هل أحتاج إلى ترخيص لتجربة هذا؟** يتوفر نسخة تجريبية مجانية من Aspose.Tasks؛ يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج.  
- **ما نسخة JDK المطلوبة؟** Java 8 أو أعلى.  
- **هل يمكنني تعديل إعدادات العملة بعد قراءتها؟** نعم، يتيح Aspose.Tasks عمليات القراءة والكتابة على خصائص العملة.  
- **هل هذا متوافق مع جميع إصدارات .mpp؟** يدعم الـ API الملفات التي تم إنشاؤها باستخدام Microsoft Project 2003‑2021.

## ما هو قراءة خصائص العملة Java؟
قراءة خصائص العملة في Java تعني الوصول إلى إعدادات مستوى المشروع التي تحدد كيفية عرض القيم المالية في ملف Microsoft Project. تشمل هذه الإعدادات رمز العملة ISO (مثال: **USD**)، الرمز (**$**)، عدد الأرقام العشرية، وما إذا كان الرمز يظهر قبل أو بعد المبلغ.

## لماذا قراءة خصائص العملة Java باستخدام Aspose.Tasks؟
- **لا حاجة لتثبيت Microsoft Project** – يعمل الـ API على أي منصة تدعم Java.  
- **استخراج سريع داخل العملية** – مثالي لمعالجة دفعات كبيرة من ملفات المشروع.  
- **تحكم كامل** – يمكنك دمج القيم المستخرجة مع تقارير مخصصة أو دمجها في أنظمة ERP.  
- **دعم متعدد الإصدارات** – يعمل مع ملفات .mpp من Project 2003 حتى أحدث إصدار 2021.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – Java 8 أو أحدث مثبت ومُعد في `PATH`.  
2. **Aspose.Tasks for Java JAR** – قم بتنزيل أحدث مكتبة من [هنا](https://releases.aspose.com/tasks/java/) وأضفها إلى مسار الفئة (classpath) الخاص بمشروعك.  

## استيراد الحزم
ابدأ باستيراد مساحة الاسم Aspose.Tasks المطلوبة للتعامل مع المشروع:

```java
import com.aspose.tasks.*;
```

## الخطوة 1: إعداد دليل المشروع الخاص بك
حدد المجلد الذي يحتوي على ملف `.mpp` الذي تريد تحليله. يجعل حفظ المسار في متغير الكود قابلًا لإعادة الاستخدام:

```java
String dataDir = "Your Data Directory";
```

*استبدل `"Your Data Directory"` بالمسار المطلق أو النسبي للمجلد الذي يحتوي على `project.mpp`.*

## الخطوة 2: إنشاء مثيل قارئ المشروع
حمّل ملف Microsoft Project في كائن `Project`. يمنحك هذا الكائن الوصول إلى جميع خصائص المشروع، بما في ذلك إعدادات العملة:

```java
Project project = new Project(dataDir + "project.mpp");
```

*إذا كان اسم ملفك مختلفًا، غيّر `"project.mpp"` وفقًا لذلك.*

## الخطوة 3: عرض خصائص العملة
الآن استرجع كل سمة من سمات العملة باستخدام تعداد `Prj` واطبع النتائج على وحدة التحكم. يُعيد الـ API كائنات يمكنك تحويلها إلى سلاسل للعرض:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**ما ستراه:**  
- **Currency Code** – رمز ISO‑4217 مثل `USD`، `EUR`، `JPY`.  
- **Currency Digits** – عادةً `2` لمعظم العملات، `0` للين الياباني.  
- **Currency Symbol** – الحرف الظاهر في التقارير (`$`، `€`، `¥`).  
- **Currency Symbol Position** – `0` للظهور **قبل** المبلغ، `1` للظهور **بعد** المبلغ.

## الخطوة 4: إكمال العملية
أظهر أن الاستخراج انتهى بنجاح. هذه الرسالة البسيطة مفيدة عندما يُشغل الكود كجزء من مهمة دفعة أكبر:

```java
System.out.println("Process completed Successfully");
```

## المشكلات الشائعة والحلول
| المشكلة | لماذا يحدث | الحل |
|-------|----------------|-----|
| **FileNotFoundException** | مسار `dataDir` غير صحيح أو اسم الملف مكتوب بخطأ. | تحقق من سلسلة الدليل وتأكد من وجود ملف `.mpp` في الموقع المحدد. |
| **NullPointerException on `project.get(...)`** | ملف المشروع لا يحتوي على معلومات العملة (نادر) أو مفتاح الخاصية غير صحيح. | استخدم `project.contains(Prj.CURRENCY_CODE)` للتحقق من وجوده قبل القراءة. |
| **LicenseException** | تشغيل بدون ترخيص Aspose.Tasks صالح في بيئة الإنتاج. | طبّق ملف الترخيص باستخدام `License license = new License(); license.setLicense("Aspose.Tasks.lic");` قبل إنشاء كائن `Project`. |

## الأسئلة المتكررة

**س: هل Aspose.Tasks متوافق مع جميع إصدارات Microsoft Project؟**  
ج: يدعم Aspose.Tasks ملفات .mpp التي تم إنشاؤها بواسطة Microsoft Project 2003‑2021، بما يغطي الإصدارات القديمة والحديثة.

**س: هل يمكنني تعديل خصائص العملة باستخدام Aspose.Tasks؟**  
ج: نعم، يمكنك قراءة وكتابة إعدادات العملة. استخدم `project.set(Prj.CURRENCY_CODE, "EUR");` ثم احفظ المشروع.

**س: هل Aspose.Tasks مناسب للاستخدام التجاري؟**  
ج: بالتأكيد. إنها مكتبة تجارية؛ يمكنك شراء ترخيص [هنا](https://purchase.aspose.com/buy).

**س: هل يقدم Aspose.Tasks نسخة تجريبية مجانية؟**  
ج: نعم، تتوفر نسخة تجريبية كاملة الوظائف [هنا](https://releases.aspose.com/).

**س: أين يمكنني الحصول على المساعدة أو الدعم لـ Aspose.Tasks؟**  
ج: أفضل مكان للحصول على المساعدة هو منتدى Aspose.Tasks الرسمي – زرّه [هنا](https://forum.aspose.com/c/tasks/15).

## الخاتمة
لقد تعلمت الآن كيفية **قراءة خصائص العملة Java** من ملف MS Project باستخدام Aspose.Tasks for Java. تتيح لك هذه القدرة دمج بيانات وصف العملة في تقارير مخصصة، تحليلات مالية، أو خطوط تكامل دون الاعتماد على Microsoft Project نفسه. لا تتردد في تجربة تعديل الخصائص أو دمج هذه البيانات مع سمات مشروع أخرى لبناء حلول أكثر غنى.

---

**آخر تحديث:** 2025-12-04  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}