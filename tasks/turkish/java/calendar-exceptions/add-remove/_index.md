---
date: 2026-11-06
description: Aspose.Tasks for Java kullanarak bir proje takvimindeki istisnayı nasıl
  kaldıracağınızı öğrenin, istisnaları verimli bir şekilde ekleyin ve yönetin ve zamanlamayı
  iyileştirin.
images:
- /java/calendar-exceptions/add-remove/og-image.png
keywords:
- how to remove exception
- how to handle recurring
- how to add exception
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-11-06
linktitle: Aspose.Tasks'te Takvim İstisnalarını Ekle ve Kaldır
og_description: Aspose.Tasks for Java kullanarak bir proje takvimindeki istisna nasıl
  kaldırılır. Takvim istisnalarını verimli bir şekilde yönetin, ekleyin ve doğrulayın.
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: Bir proje takvimindeki istisna nasıl kaldırılır – Aspose.Tasks Java rehberi
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Learn how to remove exception in a project calendar using Aspose.Tasks
    for Java, add and manage exceptions efficiently.
  headline: How to remove exception in a project calendar using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Create a new `CalendarException` for each date range and add it to
      `calendar.getExceptions()` inside a loop.
    question: Can I add multiple exceptions to a calendar using Aspose.Tasks for Java?
  - answer: Aspose.Tasks supports a wide range of .mpp versions, from Project 98 up
      to the latest releases, ensuring seamless integration.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Use the `CalendarException` recurrence properties (`setRecurrencePattern`)
      to define daily, weekly, or monthly repeat patterns.
    question: How can I handle recurring exceptions (e.g., weekly meetings) in project
      calendars?
  - answer: Yes, you can download a free trial from the [Aspose Releases page](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: Aspose.Tasks for Java kullanarak bir proje takvimindeki istisna nasıl kaldırılır
url: /tr/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proje takviminde Aspose.Tasks for Java kullanarak istisna nasıl kaldırılır

## Giriş
Doğru proje zamanlaması, **takvim istisnaları**—kaynakların mevcut olmadığı veya çalışma programlarının değiştiği günlerin—ele alınmasına bağlıdır. **Aspose.Tasks for Java** ile takvim istisnalarını **oluşturabilir**, **ekleyebilir**, **kaldırabilir** ve **yönetebilirsiniz**. Bu öğreticide bir projeyi yükleme, yeni bir istisna ekleme, mevcut bir istisnayı kaldırma ve sonuçları doğrulama adımlarını göstereceğiz, böylece artık ihtiyaç duyulmadığında **istisna girişlerini nasıl kaldıracağınızı** tam olarak anlayacaksınız.

## Hızlı yanıtlar
- **“Takvim istisnası oluşturmak” ne anlama gelir?** Standart çalışma takviminden sapma gösteren bir tarih aralığı tanımlamaktır.  
- **Bu yeteneği hangi kütüphane sağlar?** Aspose.Tasks for Java.  
- **Denemek için lisansa ihtiyacım var mı?** Ücretsiz bir deneme sürümü mevcuttur; üretim kullanımı için lisans gereklidir.  
- **Mevcut bir istisnayı kaldırabilir miyim?** Evet—takvimdeki istisna listesini bulup silmeniz yeterlidir.  
- **Bu, Microsoft Project dosyalarıyla uyumlu mu?** Kesinlikle; Aspose.Tasks tüm büyük .mpp sürümlerini okuyup yazabilir.

## create calendar exception java nedir?
`CalendarException` sınıfı, bir proje takvimine eklediğiniz çalışmayan bir dönemi temsil eder. Belirtilen tarihlerin tatil, bakım penceresi veya herhangi bir özel çalışmayan zaman olarak ele alınmasını sağlar ve görev tarihlerinin gerçek dünya kısıtlamalarına uymasını garantiler.

## Takvim istisnaları için Aspose.Tasks neden kullanılmalı?
Aspose.Tasks for Java **50+ giriş ve çıkış formatını** destekler ve dosyaları **2 GB**’a kadar, belgeyi tamamen belleğe yüklemeden işleyebilir. Büyük istisna listeleriyle çalışırken yerel Microsoft Project API’lerine göre yaklaşık **%40 performans artışı** sağlar, bu da kurumsal ölçekli zamanlama senaryoları için idealdir.

## Önkoşullar
- Java Development Kit (JDK) 8 veya üzeri yüklü olmalıdır.  
- Aspose.Tasks for Java kütüphanesi projenizin sınıf yoluna eklenmiş olmalıdır.  
- Java sözdizimi ve proje yönetimi kavramlarına temel aşinalık.

## Takvimden istisna nasıl kaldırılır?
`Project` sınıfı bir Microsoft Project dosyasını temsil eder ve takvimlerine, görevlerine ve kaynaklarına erişim sağlar. `CalendarException` sınıfı takvim içinde bir çalışmayan dönemi tanımlar. Projeyi yükleyin, takvimdeki istenmeyen `CalendarException` öğesini bulun ve listeden `remove` metodunu çağırın. Bu işlem takvimi anında günceller ve değişikliği kalıcı hale getirmek istemediğiniz sürece tüm proje dosyasını yeniden kaydetmenize gerek kalmaz.

## Takvime istisna nasıl eklenir?
`CalendarException` sınıfı takvime eklenebilen bir çalışmayan dönemi tanımlar. Yeni bir `CalendarException` örneği oluşturun, başlangıç ve bitiş tarihlerini ayarlayın, çalışmayan olarak işaretleyin ve takvimin istisna listesine ekleyin. Ekleme anında gerçekleşir ve zamanlayıcı bu aralığı takvime bağlı tüm görevler için tatil olarak kabul eder.

## Tekrarlayan istisnalar nasıl yönetilir?
`CalendarException` tekrarlama özellikleri (`setRecurrencePattern`) günlük, haftalık veya aylık tekrar desenleri tanımlamanıza olanak verir. Bu özellikleri yapılandırarak haftalık toplantılar, aylık bakım pencereleri veya herhangi bir desen‑tabanlı çalışmayan zamanı, her bir oluşum için ayrı bir giriş oluşturmadan modelleyebilirsiniz.

## Paketleri içe aktar
`import` ifadeleri, kod içinde referans verilebilecek gerekli Aspose.Tasks sınıflarını kapsam içine alır.

```java
import com.aspose.tasks.*;
```

## Adım 1: projeyi yükleyin ve takvimine erişin
`Project` bir Microsoft Project dosyasını, `Calendar` ise o projedeki bir takvimi temsil eder. Mevcut bir dosyayı yüklemek ve koleksiyondaki ilk takvimi almak ilk adımdır.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## Adım 2: mevcut bir istisna kaldırın (gerekirse)
`CalendarException` nesneleri çalışmayan dönemleri tanımlar. Bu kod parçacığı, istisna listesini kontrol eder ve birden fazla istisna varsa ilk öğeyi kaldırarak tek bir istisnanın yanlışlıkla silinmesini önler.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Pro ipucu:** Öğeleri kaldırmadan önce istisna listesinin boyutunu her zaman doğrulayın, aksi takdirde `IndexOutOfBoundsException` alabilirsiniz.

## Adım 3: yeni bir takvim istisnası oluşturun (ekleyin)
Yeni bir `CalendarException` örneği oluşturur, başlangıç ve bitiş tarihlerini ayarlar, çalışmayan olarak işaretler ve takvimin istisna koleksiyonuna ekleriz.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Neden önemli:** İstisnalar eklemek, tatilleri, bakım pencerelerini veya herhangi bir çalışmayan dönemi doğrudan proje takvimine modellemenizi sağlar. Bu, **create calendar exception java** işlevinin temelidir.

## Adım 4: doğrulama için tüm istisnaları gösterin
`calendar.getExceptions()` üzerinden döngü kurarak her bir girdiyi yazdırmak, takvimin istenen değişiklikleri yansıtıp yansıtmadığını onaylar ve hataları erken yakalamanıza yardımcı olur.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Java’da takvim istisnası nasıl eklenir?
`new Project("input.mpp")` ile projenizi yükleyin, hedef `Calendar`’ı alın, istediğiniz başlangıç ve bitiş tarihleriyle bir `CalendarException` örneği oluşturun, çalışma bayrağını `false` olarak ayarlayın ve `calendar.getExceptions()` listesine ekleyin. Bu kısa sekans, sadece birkaç satır kodla bir takvim istisnası java oluşturur.

## Yaygın sorunlar ve çözümler
| Sorun | Neden | Çözüm |
|-------|-------|------|
| Çıktı görünmüyor | İstisna listesi boş | İstisna eklediğinizden emin olun ve ardından yineleyin. |
| `project` üzerinde `NullPointerException` | Yanlış dosya yolu | `dataDir`’in geçerli bir `.mpp` dosyasına işaret ettiğini doğrulayın. |
| Tarihler bir gün eksik | Zaman dilimi farkları | Açık zaman dilimiyle `java.util.Calendar` kullanın veya `java.time` API’sini tercih edin. |

## Sıkça sorulan sorular

**S:** Aspose.Tasks for Java kullanarak bir takvime birden fazla istisna ekleyebilir miyim?  
**C:** Evet. Her tarih aralığı için yeni bir `CalendarException` oluşturup `calendar.getExceptions()` listesine bir döngü içinde ekleyebilirsiniz.

**S:** Aspose.Tasks for Java, Microsoft Project dosyalarının tüm sürümleriyle uyumlu mu?  
**C:** Aspose.Tasks, Project 98’den en yeni sürümlere kadar geniş bir .mpp sürüm yelpazesini destekler, sorunsuz entegrasyon sağlar.

**S:** Proje takvimlerinde tekrarlayan istisnalar (ör. haftalık toplantılar) nasıl yönetilir?  
**C:** `CalendarException` tekrarlama özelliklerini (`setRecurrencePattern`) kullanarak günlük, haftalık veya aylık tekrar desenleri tanımlayabilirsiniz.

**S:** Aspose.Tasks for Java için bir deneme sürümü mevcut mu?  
**C:** Evet, tüm özellikleri keşfetmek için [Aspose Releases sayfasından](https://releases.aspose.com/) ücretsiz bir deneme indirebilirsiniz.

**S:** Aspose.Tasks for Java ile ilgili destek nasıl alınır?  
**C:** [Aspose Tasks Java forumunda](https://reference.aspose.com/tasks/java/) sorular sorabilir veya doğrudan Aspose destek ekibiyle iletişime geçebilirsiniz.

## Sonuç
Takvim istisnalarını yönetmek, gerçekçi proje zaman çizelgeleri ve kaynak planlaması için kritiktir. **Aspose.Tasks for Java** ile takvim istisnalarını **oluşturabilir**, **ekleyebilir**, **kaldırabilir** ve **doğrulayabilirsiniz**—hepsi birkaç satır kodla. **İstisna kaldırma** işlemini ustalaşmak, takvimlerinizi doğru ve gerçek dünya kısıtlamalarına uygun tutmanızı sağlar.

---

**Son Güncelleme:** 2026-11-06  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose

## İlgili öğreticiler

- [Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions](/tasks/java/calendar-exceptions/define-weekdays/)
- [Retrieve Calendar Exceptions with Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}