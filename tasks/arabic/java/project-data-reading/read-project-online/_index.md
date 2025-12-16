---
date: 2025-12-15
description: تعلم كيفية قراءة بيانات MS Project Online باستخدام Aspose.Tasks Java.
  يوضح هذا الدليل كيفية استرجاع قائمة المشاريع، وقائمة مشاريع SharePoint، والحصول
  على عدد الموارد.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Aspose.Tasks Java - قراءة بيانات MS Project Online بسهولة'
url: /ar/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: قراءة بيانات MS Project Online بسهولة

## المقدمة
في مجال إدارة المشاريع، التعامل مع بيانات Microsoft Project Online بكفاءة أمر حاسم لتسهيل العمليات. **aspose tasks java** توفر واجهة برمجة تطبيقات قوية وسهلة الاستخدام تتيح لك قراءة بيانات Project Online دون الحاجة إلى التعامل مع طلبات HTTP منخفضة المستوى. في هذا الدرس سنستعرض كيفية استرجاع قائمة المشاريع، سرد مشاريع SharePoint، والحصول على عدد الموارد في كل مشروع—كل ذلك ببضع أسطر من كود Java.

## إجابات سريعة
- **ما الذي تفعله aspose tasks java؟** تقوم بقراءة ومعالجة ملفات Microsoft Project وبيانات Project Online برمجياً.  
- **هل أحتاج إلى ترخيص لتجربتها؟** تتوفر نسخة تجريبية مجانية؛ الترخيص مطلوب للاستخدام في بيئة الإنتاج.  
- **ما هي بيانات الاعتماد المطلوبة؟** نطاق SharePoint، اسم المستخدم، وكلمة المرور (أو رمز Azure AD).  
- **هل يمكنني سرد مشاريع SharePoint؟** نعم – استخدم `ProjectServerManager.getProjectList()` لاسترجاعها.  
- **كيف أحصل على عدد الموارد؟** حمّل كل كائن `Project` واستدعِ `project.getResources().size()`.

## ما هو aspose tasks java؟
**aspose tasks java** هي مكتبة موجهة للمطورين تُبسط تعقيدات صيغ ملفات Microsoft Project وواجهات REST الخاصة بـ Project Server. تمكّنك من قراءة وإنشاء وتعديل بيانات المشروع مباشرةً من تطبيقات Java، مما يجعل التكامل مع الأنظمة المؤسسية الحالية سهلًا.

## لماذا تستخدم aspose tasks java لقراءة MS Project Online؟
- **لا حاجة للتعامل اليدوي مع HTTP** – المكتبة تتولى المصادقة واستدعاءات REST.  
- **أمان نوع قوي** – العمل مع `Project` و`ProjectInfo` وغيرها من POJOs بدلاً من JSON الخام.  
- **متعددة المنصات** – تعمل على أي بيئة متوافقة مع JVM.  
- **مجموعة ميزات غنية** – إلى جانب القراءة، يمكنك أيضًا تحديث المهام والموارد والجداول الزمنية.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – تثبيت JDK 8 أو أعلى.  
2. **Aspose.Tasks for Java library** – حمّلها من [here](https://releases.aspose.com/tasks/java/).  
3. **Microsoft Project Online account** – مع صلاحيات قراءة المشاريع.  
4. **SharePoint domain address** – حيث توجد مثيل Project Online الخاص بك.  
5. **Username and password** – أو بيانات اعتماد Azure AD المناسبة للمصادقة.

## استيراد الحزم
أولاً، استورد الفئات الأساسية من Aspose.Tasks التي سنستخدمها طوال الدرس:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## الخطوة 1: تعيين نطاق SharePoint واسم المستخدم وكلمة المرور
عرّف تفاصيل الاتصال ببيئة Project Online الخاصة بك. استبدل القيم النائبة ببيانات الاعتماد الخاصة بك.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## الخطوة 2: المصادقة باستخدام بيانات اعتماد خادم المشروع
أنشئ كائن `ProjectServerCredentials` وابدأ بـ `ProjectServerManager`. سيتولى هذا المدير جميع الاستدعاءات اللاحقة إلى Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## الخطوة 3: استرجاع قائمة المشاريع وعرض المعلومات
استخدم المدير **لاسترجاع قائمة المشاريع** (سرد مشاريع SharePoint) واطبع التفاصيل الأساسية مثل الاسم، تاريخ الإنشاء، وتاريخ الحفظ الأخير.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## الخطوة 4: تحميل المشاريع الفردية وعرض عدد الموارد
لكل مشروع تم إرجاعه في الخطوة السابقة، حمّل كائن `Project` الكامل واعرض **عدد الموارد**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **Authentication failed** | نطاق أو اسم مستخدم أو كلمة مرور غير صحيحة. | تحقق من بيانات الاعتماد وتأكد من أن الحساب يمتلك صلاحيات قراءة Project Online. |
| **SSLHandshakeException** | بيئة Java لا تدعم إصدار TLS المطلوب. | حدّث JDK إلى أحدث إصدار أو فعّل TLS 1.2+. |
| **`reader.getProjectList()` returns empty** | الحساب لا يملك صلاحية الوصول إلى أي مشروع. | راجع صلاحيات Project Online أو استخدم حساب مسؤول. |
| **Large projects cause OutOfMemoryError** | تحميل عدة مشاريع في آن واحد يستهلك الذاكرة. | حمّل المشاريع واحدة تلو الأخرى وأفرغ المراجع بعد الانتهاء. |

## الأسئلة المتكررة
### س: هل يمكنني استخدام aspose tasks java لتعديل بيانات MS Project Online؟
نعم، توفر Aspose.Tasks إمكانيات واسعة لقراءة **وتعديل** بيانات Project Online برمجياً.

### س: هل يدعم Aspose.Tasks صيغ ملفات إدارة المشاريع الأخرى؟
بالطبع. يدعم صيغ MPP، XML، Primavera، والعديد غيرها، مما يضمن التوافق عبر بيئات المشاريع المتنوعة.

### س: هل يتوفر نسخة تجريبية مجانية لـ Aspose.Tasks for Java؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من [here](https://releases.aspose.com/) لاستكشاف ميزات ووظائف Aspose.Tasks.

### س: أين يمكنني العثور على الوثائق الشاملة لـ Aspose.Tasks for Java؟
يمكنك الرجوع إلى الوثائق التفصيلية [here](https://reference.aspose.com/tasks/java/) للحصول على إرشادات شاملة حول استخدام Aspose.Tasks في مشاريع Java الخاصة بك.

### س: ما هي خيارات الدعم المتاحة لـ Aspose.Tasks for Java؟
إذا واجهت أي مشاكل أو كان لديك استفسارات، يمكنك طلب المساعدة من منتدى مجتمع Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**آخر تحديث:** 2025-12-15  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11 (أحدث نسخة وقت كتابة هذا الدليل)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}