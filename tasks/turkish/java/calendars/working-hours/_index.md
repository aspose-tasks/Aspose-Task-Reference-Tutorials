---
date: 2026-08-24
description: MS Project takvimlerinden çalışma saatlerini çıkararak tatil takvimini
  eklemeyi, çalışma günlerini belirlemeyi ve görev süresini hesaplamayı Aspose.Tasks
  for Java kullanarak öğrenin.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Tatil takvimini ekleme ve çalışma günlerini belirleme
og_description: MS Project takvimlerinden çalışma saatlerini çıkararak tatil takvimini
  eklemeyi, çalışma günlerini belirlemeyi ve görev süresini hesaplamayı Aspose.Tasks
  for Java kullanarak öğrenin.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Tatil takvimini ekleme ve çalışma günlerini belirleme
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: Tatil takvimini ekleme ve çalışma günlerini belirleme
url: /tr/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tatiller takvimini ekleme ve çalışma günlerini belirleme

Proje takvimlerini yönetmek, başarılı proje planlamasının temel bir parçasıdır. Bu öğreticide **tatiller takvimini ekleyecek**, herhangi bir görev için **çalışma günlerini belirleyecek** ve Aspose.Tasks for Java kullanarak bir MS Project takviminden **çalışma saatlerini çıkaracaksınız**. Kılavuzun sonunda **görev süresini hesaplayabilecek**, çalışma saatlerini özelleştirebilecek ve ihtiyacınız olan verileri almak için **MPP dosyasını güvenilir bir şekilde yükleyebileceksiniz** — Microsoft Project kurmadan.

## Hızlı cevaplar
- **“determine working days” ne anlama geliyor?** Bu, belirli bir görev için takvim tarihlerinin hangi günlerin çalışma günü olarak kabul edildiğini belirlemeyi ifade eder.  
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Tasks for Java, MS Project dosyalarıyla çalışmak için tam özellikli bir API sağlar.  
- **Uygulama ne kadar sürer?** Temel bir çıkarma işlemi için genellikle 10–15 dakika sürer.  
- **Bir lisansa ihtiyacım var mı?** Ücretsiz bir deneme sürümü mevcuttur; üretim kullanımı için ticari bir lisans gereklidir.  
- **Çalışma saatlerini özelleştirebilir miyim?** Evet – takvimleri değiştirebilir, tatiller ekleyebilir ve özel çalışma zaman aralıkları belirleyebilirsiniz.  

## “determine working days” nedir?
**Determine working days**, bir proje takvimini sorgulayarak hangi tarihlerin çalışma günü, hangilerinin çalışma dışı gün (hafta sonları, tatiller veya özel istisnalar) olarak işaretlendiğini bulmak anlamına gelir. Bu bilgi, yalnızca çalışma günlerinin bir görevin geçen süresine katkıda bulunması nedeniyle **calculate task duration** için doğru hesaplamalar yapmak açısından önemlidir.

## Çalışma saatlerini almak için Aspose.Tasks neden kullanılmalı?
Aspose.Tasks, Microsoft Project yüklü olmadan MS Project dosyalarını okumanızı sağlar ve herhangi bir platformda otomasyonu mümkün kılar. Ayrıca yüksek performanslı işleme, geniş format desteği ve ayrıntılı belgeler sunar.

- **Tam takvim desteği** – varsayılan, kaynak ve görev takvimlerine tümüyle erişilebilir.  
- **Yüksek performans** – standart 2.5 GHz CPU’da **10.000+ görevi 2 saniyenin altında** işleyebilir.  
- **Geniş format kapsamı** – **50+ giriş ve çıkış formatını** destekler, MPP, MPX, XML ve Primavera dahil.  
- **Kapsamlı dokümantasyon** – kod örnekleri, API referansı ve topluluk forumları mevcuttur.  

## Önkoşullar
Başlamadan önce şunlara sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK)** – sürüm 8 veya üzeri.  
2. **Aspose.Tasks for Java** – en son JAR dosyasını [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/) adresinden indirin.  
3. Temel Java programlama bilgisi.  

## Paketleri içe aktar
`Project` sınıfı, Aspose.Tasks'ın bellek içinde tek bir MS Project dosyasını temsil eden üst‑seviye nesnesidir. Başlamadan önce gerekli ad alanını içe aktarın:

Paketleri içe aktar

```java
import com.aspose.tasks.*;
```

## Aspose.Tasks ile bir MPP dosyasını nasıl yüklenir?
`Project` sınıfı bir MS Project dosyasını yükler ve verilerine erişim sağlar. Projeyi tek bir kod satırıyla yükleyin; UI veya COM etkileşimi gerekmez. Bu basit adım, takvimlere, görevlere ve kaynaklara tam erişim sağlar.

MPP dosyasını yükleme

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Görev ve takvim bilgilerini al
`Task` bir proje görevini temsil eder ve `Calendar` onun çalışma zamanı kurallarını tanımlar. Analiz etmek istediğiniz görevi seçin ve ilişkili takvimini alın. `Task` nesnesi `getStart()` ve `getFinish()` metodlarını sunarken, `Calendar` nesnesi çalışma zamanı tanımlarını ortaya çıkarır.

Görev ve takvimi alma

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Başlangıç ve bitiş tarihlerini tanımla
`Date` nesneleri takvim analizinin zaman aralığını belirler. **determine working days** için zaman aralığını ayarlayın. Görevin başlangıç ve bitiş tarihlerini kullanmak, yalnızca ilgili dönemi değerlendirmenizi sağlar.

Tarihleri tanımlama

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Tarihler arasında yineleme yap
`for` döngüsü, tarih aralığındaki her günü yineleyebilir. Görevin süresindeki her tarihi döngüye alın. Bu döngü, gerektiğinde **çalışma saatlerini özelleştirmenize** olanak tanır ve toplam çalışma süresini hesaplamanın temelidir.

Tarihleri yineleme

```java
java.util.Calendar tempDate = calStartDate;
```

## Süreyi hesapla
`Duration`, yinelemeden elde edilen toplam çalışma süresini toplar. Yineleme sırasında her günün çalışma günü olup olmadığını kontrol eder, çalışma saatlerini toplar ve sonunda görevin süresini dakika, saat ve gün olarak hesaplar. Bu, programlı olarak **calculate working days** ve **calculate task duration** nasıl yapılır gösterir.

Süreyi hesaplama

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## Çalışma saatlerini ve tatilleri nasıl özelleştirirsiniz
Takvimin çalışma zaman aralıklarını değiştirebilir ve tatiller gibi istisnalar ekleyebilirsiniz. Yeni çalışma periyotları ayarlamak için `taskCalendar.addWorkingTime()` ve bir tatil eklemek için `taskCalendar.addException()` kullanın. Bu, varsayılan 9‑5 programı kuruluşunuzun politikalarıyla uyuşmadığında faydalıdır.

## Yaygın sorunlar ve çözümler
| Sorun | Çözüm |
|-------|----------|
| **Görev takvim için `null` döndürür** | Görevin gerçekten bir takvim atandığından emin olun; aksi takdirde projenin varsayılan takvimini devralır. |
| **Tatiller nedeniyle hatalı süre** | Tatillerin görev takviminde veya projenin temel takviminde tanımlandığını doğrulayın. |
| **Zaman dilimi uyumsuzluğu** | Gerekirse takvimin zaman dilimini sisteminizle eşleştirmek için `java.util.TimeZone` kullanın. |

## Sıkça sorulan sorular
### S: Aspose.Tasks for Java karmaşık proje yapılarını yönetebilir mi?
C: Evet, Aspose.Tasks for Java, görevler, kaynaklar ve takvimler dahil olmak üzere karmaşık proje yapılarını yönetmek için kapsamlı destek sağlar.

### S: Aspose.Tasks for Java farklı MS Project sürümleriyle uyumlu mu?
C: Kesinlikle, Aspose.Tasks for Java çeşitli MS Project sürümlerini destekler ve farklı ortamlar arasında uyumluluğu sağlar.

### S: Proje takvimlerinde çalışma saatlerini ve tatilleri özelleştirebilir miyim?
C: Evet, Aspose.Tasks for Java API'lerini kullanarak proje gereksinimlerinize göre çalışma saatlerini ve tatilleri kolayca özelleştirebilirsiniz.

### S: Aspose.Tasks for Java destek ve dokümantasyon sunuyor mu?
C: Evet, Aspose.Tasks for Java, geliştiricilerin özelliklerini etkili bir şekilde kullanmalarına yardımcı olmak için kapsamlı dokümantasyon ve özel destek forumları sunar.

### S: Aspose.Tasks for Java için bir deneme sürümü mevcut mu?
C: Evet, Aspose.Tasks for Java için ücretsiz bir deneme sürümüne [Aspose releases page](https://releases.aspose.com/) üzerinden erişebilirsiniz.

## Sonuç
Bu kılavuzda, Aspose.Tasks for Java kullanarak bir MS Project takviminden **tatiller takvimini ekleme**, **çalışma günlerini belirleme**, **çalışma saatlerini alma** ve **görev süresini hesaplama** nasıl yapılacağını gösterdik. Yukarıdaki adımları izleyerek takvim analizi otomasyonu yapabilir, takvimleri özelleştirebilir ve proje planlarınızı doğru ve güncel tutabilirsiniz. Artık **MS Project** verilerini **okuma**, **MPP dosyasını yükleme** ve Microsoft Project'e ihtiyaç duymadan kesin süre hesaplamaları yapma araçlarına sahipsiniz.

---

**Son Güncelleme:** 2026-08-24  
**Test Edilen:** Aspose.Tasks for Java 24.12 (yazım anındaki en son sürüm)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks for Java ile projeye takvim ekleme](/tasks/java/calendars/create/)
- [Takvime tatiller ekleyin ve Aspose.Tasks ile MPP olarak kaydedin](/tasks/java/calendars/update-to-mpp/)
- [Aspose.Tasks for Java ile Özel Takvim İstisnaları Oluşturma](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}