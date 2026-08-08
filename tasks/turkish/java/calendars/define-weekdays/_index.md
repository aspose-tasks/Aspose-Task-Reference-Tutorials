---
date: 2026-08-08
description: Aspose.Tasks for Java kullanarak calendar ms project nasıl ayarlanır,
  daily working hours nasıl belirlenir ve weekend working days nasıl eklenir öğrenin.
  Projeyi sadece birkaç satır kodla XML olarak kaydedin.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: calendar ms project nasıl ayarlanır ve weekdays tanımlanır
og_description: Aspose.Tasks for Java kullanarak calendar ms project ayarlayın, weekdays
  tanımlayın ve weekend working days ekleyin. Bu adım adım öğreticiyi izleyin ve XML
  olarak kaydedin.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Aspose.Tasks ile calendar ms project ayarlama – Java rehberi
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: calendar ms project nasıl ayarlanır ve weekdays tanımlanır
url: /tr/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project takvimini ayarlama ve hafta içi günlerini tanımlama

Bu öğreticide programlı olarak **MS Project takvimini ayarlamayı**, hafta içi günlerini tanımlamayı ve Aspose.Tasks Java kütüphanesini kullanarak özel çalışma günlerini yapılandırmayı öğreneceksiniz. İster bir zamanlama motoru oluşturuyor olun, ERP sistemleriyle entegrasyon yapıyor olun ya da Microsoft Project'i açmadan bir proje planı oluşturmanız gerekiyor olsun, aşağıdaki adımlar bir takvim oluşturmayı, günlük çalışma saatlerini ayarlamayı ve birkaç satır kodla hafta sonu çalışma günlerini eklemeyi gösterir.

## Hızlı cevaplar
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java.  
- **Hafta sonu çalışma günleri ekleyebilir miyim?** Evet – sadece Cumartesi ve Pazar'ı çalışma günü olarak işaretleyin.  
- **Projeyi nasıl kaydederim?** `prj.save(..., SaveFileFormat.Xml)` çağırın.  
- **Lisans gerekli mi?** Değerlendirme için ücretsiz deneme çalışır; üretim kullanımı için lisans gerekir.  
- **Hangi Java sürümü destekleniyor?** Java 8 veya üzeri.

## MS Project takvimini ayarlama nedir?
MS Project'te takvimi ayarlamak, hangi günlerin çalışma günü olarak kabul edildiğini, her gün kaç çalışma saati olduğunu ve tatiller veya şirket çapında kapanışlar gibi özel istisnaları belirler. Bu bilgiler görev zamanlamasını, kaynak tahsislerini ve genel proje zaman çizelgelerini yönlendirir ve hesaplamaların kuruluşun gerçek çalışma düzenine uygun olmasını sağlar.

## Takvim manipülasyonu için neden Aspose.Tasks kullanılmalı?
Aspose.Tasks, Microsoft Project kullanıcı arayüzünü başlatmadan takvimler üzerinde programlı kontrol sağlar. Java'yı destekleyen herhangi bir işletim sisteminde çalışır, 50'den fazla giriş ve çıkış formatını destekler ve tüm dosyayı belleğe yüklemeden çok sayfalı projeleri işleyebilir; bu da sunucu tarafı otomasyon için idealdir.

## Önkoşullar
- **Java Development Kit (JDK) 8+** – [Oracle web sitesinden](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) indirin.  
- **Aspose.Tasks for Java** – en son JAR'ı [Aspose.Tasks indirme sayfasından](https://releases.aspose.com/tasks/java/) edinin.  
- Aspose.Tasks JAR'ını sınıf yolunuza eklemek için bir IDE veya yapı aracı (Maven/Gradle).

## Paketleri içe aktar
Projeler, takvimler ve çalışma zamanı nesnelerine erişim sağlayan sınıfları içe aktarın.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Adım adım rehber

### Adım 1: bir proje örneği oluşturun
`Project` nesnesini örnekleyin; bu nesne, manipüle edeceğiniz MS Project dosyasını temsil eder.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Adım 2: yeni bir takvim tanımlayın
`Calendar`, bir proje için çalışma zamanları, istisnalar ve tatiller kümesini temsil eder.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Adım 3: standart çalışma günlerini ekleyin (Pazartesi‑Perşembe)
`WeekDay`, haftanın belirli bir günü için çalışma zamanını tanımlar.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Adım 4: hafta sonu çalışma günlerini ekleyin
Projeniz hafta sonları da çalışıyorsa, Cumartesi ve Pazar'ı normal çalışma günleri olarak ekleyin. Bu, **hafta sonu çalışma günlerini ekleme** gösterir.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Adım 5: özel kısa bir çalışma günü ayarlayın (Cuma)
Cuma gününü sabah vardiyası (09:00‑12:00) ve öğleden sonra vardiyası (13:00‑16:00) ile yapılandırarak **günlük çalışma saatlerini ayarlama** ve özel kısa bir çalışma gününü gösterin.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Adım 6: projeyi XML olarak kaydedin
`SaveFileFormat`, bir projeyi kaydederken desteklenen dosya formatlarını (XML veya MPP gibi) listeler.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Yaygın sorunlar ve çözümler
| Sorun | Çözüm |
|-------|----------|
| **Çalışma zamanları uygulanmadı** | `setDayWorking(true)`'in her özel `WeekDay` üzerinde çağrıldığından emin olun. |
| **Kaydederken dosya bulunamadı** | `dataDir`'in mevcut bir klasöre işaret ettiğini ve uygulamanın yazma iznine sahip olduğunu doğrulayın. |
| **Takvim görevlerde yansımıyor** | Yeni oluşturulan takvimi `task.setCalendar(cal)` kullanarak kaynaklara veya görevlere atayın. |

## Sıkça sorulan sorular

**Q: Aspose.Tasks for Java kullanarak özel çalışmayan günler tanımlayabilir miyim?**  
**A:** Evet. Çalışmayan gün olarak değerlendirmek istediğiniz herhangi bir `WeekDay` için `DayWorking` özelliğini `false` olarak ayarlayın.

**Q: Tatilleri veya şirket çapında istisnaları nasıl ekleyebilirim?**  
**A:** `CalendarException` nesneleri oluşturun, istisna tarihlerini belirleyin ve bunları `cal.getExceptions()`'a ekleyin.

**Q: Kütüphane eski MS Project sürümleriyle uyumlu mu?**  
**A:** Kesinlikle. Aspose.Tasks, çeşitli Project sürümlerinde MPP, MPT ve XML formatlarını destekler.

**Q: İçe aktarılan bir projedeki mevcut takvimi değiştirebilir miyim?**  
**A:** Projeyi `new Project("existing.mpp")` ile yükleyin, istediğiniz takvimi alın, değişiklikleri yapın ve kaydedin.

**Q: Aspose.Tasks yinelemeli görevleri de yönetebiliyor mu?**  
**A:** Evet, `RecurringTask` sınıfını kullanarak yinelemeli görevler oluşturabilir ve düzenleyebilirsiniz.

## Sonuç
Artık **MS Project takvimini ayarlamayı**, hafta içi günlerini tanımlamayı, hafta sonu çalışma günlerini eklemeyi ve kısa bir Cuma programı yapılandırmayı—hepsini Aspose.Tasks for Java ile— biliyorsunuz. Sonucu XML olarak kaydedin ve takvim mantığını herhangi bir Java tabanlı proje yönetim çözümüne entegre edin.

---

**Son Güncelleme:** 2026-08-08  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks for Java ile projeye takvim ekleme](/tasks/java/calendars/create/)
- [Aspose.Tasks ile Çalışma Günlerini ve Çalışma Saatlerini Belirleme](/tasks/java/calendars/working-hours/)
- [Aspose.Tasks ile Takvime Tatil Ekleyip MPP Olarak Kaydetme](/tasks/java/calendars/update-to-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}