---
title: قراءة بيانات مشروع MS عبر الإنترنت بسهولة باستخدام Aspose.Tasks
linktitle: قراءة بيانات المشروع عبر الإنترنت في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية قراءة بيانات Microsoft Project Online بسهولة باستخدام Aspose.Tasks لـ Java. تعزيز قدرات إدارة المشروع الخاص بك.
type: docs
weight: 13
url: /ar/java/project-data-reading/read-project-online/
---
## مقدمة
في مجال إدارة المشاريع، يعد التعامل مع بيانات Microsoft Project Online بكفاءة أمرًا بالغ الأهمية لتبسيط العمليات. يوفر Aspose.Tasks for Java حلاً قويًا لقراءة مثل هذه البيانات دون عناء. يتعمق هذا البرنامج التعليمي في الاستفادة من Aspose.Tasks للوصول إلى بيانات MS Project Online ومعالجتها بسلاسة.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
1. Java Development Kit (JDK): قم بتثبيت JDK لتجميع برامج Java وتشغيلها.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل مكتبة Aspose.Tasks وتضمينها في مشروع Java الخاص بك. يمكنك الحصول عليه من[هنا](https://releases.aspose.com/tasks/java/).
3. حساب Microsoft Project Online: احصل على بيانات اعتماد صالحة للوصول إلى بيانات MS Project Online.
4. عنوان مجال SharePoint: عنوان مجال SharePoint حيث توجد بيانات MS Project Online الخاصة بك.
5. اسم المستخدم وكلمة المرور: بيانات الاعتماد لمصادقة الوصول إلى MS Project Online.
## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد حزم Aspose.Tasks اللازمة للتكامل السلس:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## الخطوة 1: قم بتعيين عنوان مجال SharePoint واسم المستخدم وكلمة المرور
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 يستبدل`"https://contoso.sharepoint.com"` باستخدام عنوان مجال SharePoint الخاص بك،`"admin@contoso.onmicrosoft.com"` مع اسم المستخدم الخاص بك، و`"MyPassword"` مع كلمة المرور الخاصة بك.
## الخطوة 2: المصادقة باستخدام بيانات اعتماد خادم Project
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 يخلق`ProjectServerCredentials` الكائن باستخدام عنوان مجال SharePoint واسم المستخدم وكلمة المرور. ثم التهيئة`ProjectServerManager` مع أوراق الاعتماد هذه.
## الخطوة 3: استرداد قائمة المشروع وعرض المعلومات
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 قم بالتكرار من خلال قائمة المشاريع التي تم الحصول عليها من`reader.getProjectList()` وعرض تفاصيل المشروع مثل الاسم وتاريخ الإنشاء وتاريخ آخر حفظ.
## الخطوة 4: تحميل المشاريع الفردية وعدد موارد المخرجات
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 لكل مشروع، قم بتحميله باستخدام`reader.getProject(p.getId())` وإخراج اسم المشروع مع عدد الموارد المرتبطة به.

## خاتمة
يعمل Aspose.Tasks for Java على تبسيط عملية قراءة بيانات MS Project Online، مما يوفر للمطورين مجموعة أدوات قوية لتبسيط مهام إدارة المشروع. باتباع هذا البرنامج التعليمي، يمكنك دمج Aspose.Tasks بكفاءة في تطبيقات Java الخاصة بك للوصول إلى بيانات المشروع ومعالجتها بسهولة.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ Java لتعديل بيانات MS Project Online؟
ج: نعم، يوفر Aspose.Tasks إمكانيات واسعة ليس فقط للقراءة ولكن أيضًا لتعديل بيانات MS Project Online برمجيًا.
### س: هل يدعم Aspose.Tasks تنسيقات ملفات إدارة المشاريع الأخرى؟
ج: بالتأكيد، يدعم Aspose.Tasks تنسيقات ملفات متنوعة بما في ذلك MPP وXML والمزيد، مما يضمن التوافق مع أنظمة إدارة المشاريع المتنوعة.
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من[هنا](https://releases.aspose.com/) لاستكشاف ميزات ووظائف Aspose.Tasks.
### س: أين يمكنني العثور على وثائق شاملة لـ Aspose.Tasks لـ Java؟
 ج: يمكنك الرجوع إلى الوثائق التفصيلية[هنا](https://reference.aspose.com/tasks/java/)للحصول على إرشادات شاملة حول استخدام Aspose.Tasks في مشاريع Java الخاصة بك.
### س: ما هي خيارات الدعم المتاحة لـ Aspose.Tasks لـ Java؟
 ج: إذا واجهت أية مشكلات أو كانت لديك استفسارات، يمكنك طلب المساعدة من منتدى مجتمع Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).