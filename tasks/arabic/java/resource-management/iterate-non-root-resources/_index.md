---
date: 2026-01-13
description: تعلم كيفية تكرار الموارد غير الجذرية في ملفات Microsoft Project باستخدام
  Aspose.Tasks للغة Java.
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: تكرار الموارد غير الجذرية باستخدام Aspose.Tasks لجافا
url: /ar/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تكرار الموارد غير الجذرية باستخدام Aspose.Tasks للغة Java

## المقدمة
Aspose.Tasks for Java هي مكتبة قوية تمنح المطورين طريقة نظيفة وموجهة للكائنات للعمل مع ملفات Microsoft Project. في هذا البرنامج التعليمي ستتعلم **كيفية تكرار الموارد غير الجذرية** حتى تتمكن من قراءة أو تعديل أو تحليل بيانات الموارد دون التعامل مع العنصر الجذري. سواءً كنت تبني أداة تقارير أو برنامج ترحيل أو جدولة مخصصة، فإن إتقان هذه التقنية سيجعل الكود أكثر دقة وكفاءة.

## إجابات سريعة
- **ما معنى “المورد غير الجذري”؟** مورد ليس العنصر النائب الافتراضي “Project” (العقدة الجذرية).  
- **لماذا يتم تصفية المورد الجذري؟** العنصر الجذري لا يحتوي على بيانات جدولة مفيدة ويمكن أن يملأ التقارير.  
- **أي فئة في Aspose.Tasks توفر مجموعة الموارد؟** `Project.getResources()`.  
- **هل أحتاج إلى ترخيص لهذا الكود؟** الإصدار التجريبي المجاني يعمل للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكنني استخدام ذلك مع Java 17؟** نعم – يدعم Aspose.Tasks Java 8 وما فوق.

## المتطلبات المسبقة
قبل الغوص في الكود، تأكد من أن لديك:

1. **Java Development Kit (JDK)** – قم بتثبيت أحدث JDK من [موقع Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **مكتبة Aspose.Tasks للغة Java** – احصل على أحدث ملف JAR من [صفحة التحميل](https://releases.aspose.com/tasks/java/).  

## استيراد الحزم
في مشروع Java الخاص بك، استورد الفئات الضرورية من Aspose.Tasks:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## الخطوة 1: إعداد دليل البيانات
```java
String dataDir = "Your Data Directory";
```
استبدل `"Your Data Directory"` بالمسار المطلق حيث توجد ملفات `.mpp` الخاصة بك.

## الخطوة 2: تحميل ملف المشروع
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
هذا ينشئ كائن `Project` بتحميل **ResourceCosts.mpp** من المجلد الذي حددته.

## الخطوة 3: تكرار الموارد غير الجذرية
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
تقوم الحلقة بالتجول عبر كل كائن `Resource` في المشروع. يتحقق `isRoot()` ويتخطى المورد الجذري المدمج، وتقوم جملة `System.out.println` بطباعة اسم كل **مورد غير جذري**.

## كيفية تكرار الموارد غير الجذرية
المقتطف أعلاه يوضح النمط الأساسي:

1. استرجع المجموعة الكاملة باستخدام `prj.getResources()`.  
2. استخدم `isRoot()` لتصفية العنصر النائب.  
3. وصول إلى أي حقل من حقول المورد (مثل `Rsc.NAME`، `Rsc.COST`) حسب الحاجة.

يمكنك توسيع هذا النمط لتجميع التكاليف، أو تصديره إلى CSV، أو تطبيق قواعد عمل مخصصة.

## المشكلات الشائعة والنصائح
- **فحوصات null** – قد تحتوي بعض الموارد على حقول اختيارية؛ احرص دائمًا على الحماية من `null` عند استدعاء `get()`.  
- **الأداء** – للمشاريع الكبيرة جدًا، فكر في التكرار باستخدام حلقة تعتمد على الفهرس لتجنب إنشاء مجموعات وسيطة.  
- **الترخيص** – تشغيل الكود بدون ترخيص صالح سيضيف علامة مائية إلى الملفات المصدرة؛ تأكد من تفعيل الترخيص مبكرًا في التطبيق.

## الخلاصة
باتباع هذه الخطوات، أنت الآن تعرف **كيفية تكرار الموارد غير الجذرية** باستخدام Aspose.Tasks للغة Java. تساعدك هذه التقنية على التركيز على موارد المشروع الفعلية، وتنظيف استخراج البيانات، وبناء حلول إدارة مشاريع أكثر موثوقية.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Tasks للغة Java لإنشاء ملفات مشروع جديدة؟
نعم، توفر Aspose.Tasks إمكانيات CRUD كاملة (إنشاء، قراءة، تحديث، حذف) لتنسيقات المشاريع MPP و MPT و XML.

### هل يدعم Aspose.Tasks جميع إصدارات ملفات Microsoft Project؟
بالطبع. يتعامل مع ملفات Project من 2003 إلى 2019، بما في ذلك أحدث مواصفات MPP.

### هل Aspose.Tasks متوافق مع أطر Java مثل Spring؟
نعم، يمكنك حقن المكتبة في Spring beans أو استخدامها في أي تطبيق Java قياسي.

### هل يمكنني تخصيص حقول بيانات المشروع باستخدام Aspose.Tasks؟
بالتأكيد. تسمح لك الـ API بإضافة أو تعديل أو حذف الحقول المخصصة للمهام والموارد والتعيينات.

### هل توفر Aspose.Tasks الدعم والوثائق للمطورين؟
يتضمن المنتج وثائق API شاملة، عينات كود، ومنتدى دعم مخصص للحصول على مساعدة سريعة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-01-13  
**تم الاختبار باستخدام:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

---