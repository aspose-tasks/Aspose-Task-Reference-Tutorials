---
date: 2025-12-20
description: تعلم كيفية استرجاع رموز المخطط التفصيلي لمشروع MS برمجيًا باستخدام Aspose.Tasks
  للغة Java. عزّز قدراتك في إدارة المشاريع.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: استرجاع رموز المخطط التفصيلي في MS Project باستخدام Aspose.Tasks
url: /ar/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استرجاع رموز المخطط التفصيلي لمشروع MS في Aspose.Tasks

## المقدمة
في هذا البرنامج التعليمي، ستكتشف **كيفية استرجاع ms project outline codes** باستخدام Aspose.Tasks for Java. تُوفر رموز المخطط التفصيلي في MS Project طريقة قوية لتصنيف المهام والموارد والتعيينات، والوصول إليها برمجياً يتيح لك بناء تقارير مخصصة، أتمتة، أو حلول تكامل. سنستعرض مثالًا كاملاً خطوة بخطوة يمكنك نسخه إلى مشروعك الخاص.

## إجابات سريعة
- **ماذا يفعل الكود؟** يقوم بتحميل ملف Project ويطبع كل تعريف لرمز المخطط التفصيلي، الأقنعة الخاصة به، والقيم.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java (أي نسخة حديثة).  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للتطوير؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أعلى.  
- **هل يمكنني تعديل الرموز بعد استرجاعها؟** نعم – نفس الـ API يتيح لك إضافة أو تعديل أو حذف رموز المخطط التفصيلي.

## ما هي رموز المخطط التفصيلي لمشروع ms؟
رموز المخطط التفصيلي هي حقول مخصصة تسمح لمديري المشاريع بتجميع وتصفية المهام بما يتجاوز التسلسل الهرمي الافتراضي. يمكن أن تكون قيمًا رقمية بسيطة، سلاسل نصية، أو حتى رموز مخصصة على مستوى المؤسسة. من خلال قراءة هذه الرموز، يمكنك تشغيل لوحات معلومات، تصدير بيانات، أو فرض قواعد تسمية تلقائيًا.

## لماذا استرجاع رموز المخطط التفصيلي لمشروع ms باستخدام Aspose.Tasks؟
- **الأتمتة:** إنشاء تقارير أو تشغيل سير عمل دون تصدير يدوي.  
- **التكامل:** مزامنة رموز المخطط التفصيلي مع أنظمة ERP أو PPM أو أدوات BI.  
- **التخصيص:** تطبيق قواعد الأعمال بناءً على قيم الرموز (مثال: تخصيص التكاليف).  
- **متعدد المنصات:** يعمل على Windows وLinux وmacOS، مستقل عن واجهة Microsoft Project.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من إعداد المتطلبات التالية:

### 1. بيئة تطوير Java
تأكد من تثبيت مجموعة تطوير Java (JDK) على نظامك. يمكنك تنزيل وتثبيت JDK من موقع Oracle.

### 2. مكتبة Aspose.Tasks
قم بتنزيل وإضافة مكتبة Aspose.Tasks إلى مشروع Java الخاص بك. يمكنك تنزيل المكتبة من [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
أولاً، استورد الحزم الضرورية من Aspose.Tasks في كود Java الخاص بك:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

الآن لنقسم مثال الكود المقدم إلى عدة خطوات:

## الخطوة 1: تحميل المشروع
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
في هذه الخطوة، نقوم بتحميل ملف Microsoft Project إلى كائن `Project` باستخدام اسم الملف المقدم.

## الخطوة 2: استرجاع رموز المخطط التفصيلي
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
نقوم بالتكرار عبر كل تعريف لرمز المخطط التفصيلي في المشروع.

## الخطوة 3: الوصول إلى خصائص رمز المخطط التفصيلي
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
نسترجع ونطبع خصائص مختلفة لتعريف رمز المخطط التفصيلي مثل Alias، Field ID، وField Name.

## الخطوة 4: التحقق من رمز مخصص للمؤسسة
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
نتحقق مما إذا كان رمز المخطط التفصيلي رمزًا مخصصًا للمؤسسة ونطبع النتيجة وفقًا لذلك.

## الخطوة 5: عرض أقنعة رمز المخطط التفصيلي
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
نقوم بالتكرار عبر كل قناع مرتبط برمز المخطط التفصيلي ونطبع مستواه وقيمة القناع.

## الخطوة 6: عرض قيم رمز المخطط التفصيلي
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
نقوم بالتكرار عبر كل قيمة لرمز المخطط التفصيلي ونطبع الوصف، معرف القيمة، القيمة، والنوع.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **لا يوجد إخراج** | مسار ملف المشروع غير صحيح | تحقق من أن `projectName` يشير إلى ملف `.mpp` صالح. |
| **قيم فارغة** | رمز المخطط التفصيلي غير معرف في الملف | تأكد من أن ملف المشروع يحتوي فعليًا على رموز المخطط التفصيلي (تحقق في واجهة MS Project). |
| **LicenseException** | استخدام النسخة التجريبية دون تفعيل صحيح | تطبيق ترخيص مؤقت أو كامل عبر `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java لتعديل رموز المخطط التفصيلي في ملف Project؟**  
ج: نعم، توفر Aspose.Tasks for Java واجهات برمجة تطبيقات لتعديل رموز المخطط التفصيلي برمجياً. يمكنك إضافة أو تعديل أو حذف التعريفات باستخدام نفس كائن `Project`.

**س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks for Java من [Aspose.Tasks website](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على الدعم الفني لـ Aspose.Tasks for Java؟**  
ج: يمكنك الحصول على الدعم الفني بزيارة [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) ونشر استفساراتك هناك.

**س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك شراء ترخيص مؤقت لـ Aspose.Tasks for Java من [purchase page](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني العثور على الوثائق الكاملة لـ Aspose.Tasks for Java؟**  
ج: يمكنك الرجوع إلى [documentation](https://reference.aspose.com/tasks/java/) للحصول على معلومات مفصلة حول استخدام Aspose.Tasks for Java.

## الخلاصة
في هذا البرنامج التعليمي، تعلمنا كيفية استرجاع **ms project outline codes** باستخدام Aspose.Tasks for Java. باتباع الخطوات المقدمة، يمكنك الوصول إلى رموز المخطط التفصيلي ومعالجتها بفعالية في تطبيقات Java الخاصة بك، مما يتيح إمكانيات متقدمة لإدارة المشاريع مثل التقارير المخصصة، الأتمتة، والتكامل مع أنظمة مؤسسية أخرى.

---

**آخر تحديث:** 2025-12-20  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}