---
date: 2026-08-03
description: Aspose.Tasks for Java kullanarak ms project calendar oluşturmayı, calendar'ı
  bir project'e eklemeyi ve project'i XML olarak kaydetmeyi öğrenin.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Aspose.Tasks kullanarak Calendar'ı Project'e ekleyin
og_description: Aspose.Tasks for Java kullanarak programlı bir şekilde ms project
  calendar oluşturun. Calendar'ları ekleyin, schedule'ları özelleştirin ve dakikalar
  içinde XML'e dışa aktarın.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Aspose.Tasks for Java ile ms project calendar oluşturun
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Aspose.Tasks for Java ile ms project calendar oluşturun
url: /tr/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java ile ms proje takvimi oluşturma

## Giriş
Modern proje‑management iş akışlarında, **create ms project calendar** işlevini programlı olarak gerçekleştirme yeteneği, saatlerce süren manuel düzenlemeleri tasarruf ettirebilir. Aspose.Tasks for Java, Microsoft Project dosyalarını masaüstü istemcisini açmadan manipüle etmenizi sağlayan temiz, tip‑güvenli bir API sunar. Bu öğreticide bir takvim eklemeyi, bir MS Project takvimi oluşturmayı ve projeyi XML olarak kaydetmeyi sadece birkaç satır Java kodu ile öğreneceksiniz.

## Hızlı Yanıtlar
- **What does “create ms project calendar” mean?**  
  Bu, bir Microsoft Project dosyasına kod aracılığıyla yeni bir çalışma zamanı tanımı (takvim) eklemek anlamına gelir.  
- **Which library handles this?**  
  Aspose.Tasks for Java, takvimleri yönetmek için `Calendar` sınıfı ve `Project` konteynerini sağlar.  
- **Do I need a license?**  
  Geçici bir değerlendirme lisansı test için çalışır; üretim kullanımı için tam lisans gereklidir.  
- **Can I save the file as XML?**  
  Evet—projeyi XML dosyası olarak dışa aktarmak için `SaveFileFormat.Xml` kullanın.  
- **What are the prerequisites?**  
  Java JDK 8+ ve sınıf yolunuzda Aspose.Tasks for Java JAR'ı.

## create ms project calendar nedir?
MS Project takvimi oluşturmak, bir Project dosyasına programlı olarak yeni bir takvim tanımı eklemek, çalışma günlerini, istisnaları ve günlük çalışma saatlerini belirlemek ve ardından bu takvimi görevler, kaynaklar veya tüm proje için atamak anlamına gelir; böylece takvim hesaplamaları tanımlanan çalışma zamanına göre yapılır.

## Projeye takvim eklemek için neden Aspose.Tasks for Java kullanılmalı?
Aspose.Tasks for Java'ı kullanmalısınız çünkü Microsoft Project yüklü olmadan çalışan tamamen tip‑güvenli bir API sunar, tüm büyük Project sürümlerini (2007‑2021, 5+ sürüm) destekler ve XML, MPP ve **10+** diğer formatlara dışa aktarabilir; bu da herhangi bir sunucuda otomatik toplu takvim oluşturmayı mümkün kılar.

## Önkoşullar
- **Java Development Kit (JDK) 8 veya daha yeni** yüklü ve yapılandırılmış.  
- **Aspose.Tasks for Java** kütüphanesi – [official website](https://releases.aspose.com/tasks/java/) adresinden indirin ve JAR'ı projenizin sınıf yoluna ekleyin.  
- Seçtiğiniz bir IDE veya derleme aracı (Maven/Gradle).

## Adım adım kılavuz

### Adım 1: Gerekli Aspose.Tasks paketini içe aktar
İlk olarak, Aspose.Tasks sınıflarını kapsam içine alın, böylece projeler ve takvimlerle çalışabilirsiniz.

```java
import com.aspose.tasks.*;
```

### Adım 2: veri dizini yolunu ayarla
Oluşturulan proje dosyasının nereye yazılacağını tanımlayın. Yer tutucuyu makinenizdeki mutlak veya göreli bir yol ile değiştirin.

```java
String dataDir = "Your Data Directory";
```

### Adım 3: yeni bir Project örneği oluştur
`Project`, bellek içinde bir Microsoft Project dosyasını temsil eden temel sınıftır.

```java
Project prj = new Project();
```

### Adım 4: eklemek istediğiniz takvimleri tanımlayın
`Calendar`, bir proje için çalışma günleri, istisnalar ve çalışma saatleri içeren bir takvim tanımlar.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Pro tip:** Takvim ekledikten sonra, çalışma günlerini `cal1.getWeekDays().add(...)` ile özelleştirebilir ve günlük çalışma saatlerini `cal1.getBaseCalendar().setWorkingTime(...)` kullanarak ayarlayabilirsiniz.

### Adım 5: projeyi kaydet (projeyi XML olarak kaydet)
`SaveFileFormat.Xml`, Aspose.Tasks'e projeyi XML formatında yazmasını söyler.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Adım 6: tamamlanma mesajını göster
Kullanıcıya işlemin başarıyla tamamlandığını bildirin.

```java
System.out.println("Process completed Successfully");
```

Bu altı özlü adımı izleyerek, **added a calendar to a project** işlemini başarıyla gerçekleştirdiniz ve sonucu bir XML dosyası olarak kaydettiniz.

## Yaygın sorunlar ve çözümler
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `prj.getCalendars()`** | Project nesnesi doğru şekilde başlatılmadı. | `new Project()` çağrısının takvimlere erişmeden önce yapıldığından emin olun. |
| **File not found when saving** | `dataDir`, var olmayan bir klasöre işaret ediyor. | Önce klasörü oluşturun veya mutlak bir yol kullanın. |
| **Calendar name appears as “no info”** | Örnekte yer tutucu adlar kullanıldı. | Takvimi yansıtan anlamlı adlarla değiştirin (ör. “US Holiday Calendar”). |
| **Saved XML cannot be opened in MS Project** | Eski bir Aspose.Tasks sürümü kullanılıyor. | En son Aspose.Tasks for Java sürümüne güncelleyin. |

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks, birden fazla istisna içeren karmaşık takvimleri yönetebilir mi?**  
**A:** Evet – takvim ekledikten sonra `WeekDay` ve `Exception` sınıflarını kullanarak istisnalar, çalışma saatleri ve çalışılmayan günleri tanımlayabilirsiniz.

**Q: Yeni takvimi belirli görevlere atamak mümkün mü?**  
**A:** Kesinlikle. `prj.getRootTask().getChildren().add("Task Name")` ile bir görev alın ve `task.set(Tsk.CALENDAR, cal3);` ile takvimi atayın.

**Q: Kütüphane, MPP gibi diğer formatlarda kaydetmeyi destekliyor mu?**  
**A:** Evet. Gerektiğinde `SaveFileFormat.Xml` yerine `SaveFileFormat.Mpp` veya `SaveFileFormat.P6` kullanın; Aspose.Tasks **12** çıktı formatını destekler.

**Q: Geliştirme sürümleri için lisansa ihtiyacım var mı?**  
**A:** Test için geçici bir değerlendirme lisansı yeterlidir; üretim dağıtımları için tam lisans gereklidir.

**Q: Sorun yaşarsam nereden yardım alabilirim?**  
**A:** Aspose.Tasks topluluk forumu mükemmel bir kaynaktır: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Son Güncelleme:** 2026-08-03  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [MS Project Takvimlerinde Hafta Günlerini Tanımlama – Aspose.Tasks Java](/tasks/java/calendars/)
- [Aspose.Tasks ile Java'da Proje Takvimini Ayarlama](/tasks/java/calendars/properties/)
- [Aspose.Tasks for Java ile Özel Takvim İstisnaları Oluşturma](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}