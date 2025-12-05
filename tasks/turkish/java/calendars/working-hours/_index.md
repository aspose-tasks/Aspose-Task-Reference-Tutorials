---
date: 2025-12-05
description: Aspose.Tasks for Java kullanarak MS Project takvimlerinden çalışma saatlerini
  çıkararak çalışma günlerini belirlemeyi ve görev süresini hesaplamayı öğrenin.
language: tr
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile Çalışma Günlerini ve Çalışma Saatlerini Belirleyin
url: /java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Çalışma Günlerini ve Çalışma Saatlerini Belirleme

## Giriş
Proje takvimlerini yönetmek, başarılı proje planlamasının temel bir parçasıdır. Bu öğreticide **herhangi bir görev için çalışma günlerini** belirleyecek ve Aspose.Tasks for Java kullanarak bir MS Project takviminden **çalışma saatlerini** çıkaracaksınız. Rehberin sonunda **görev süresini hesaplayabilecek**, çalışma saatlerini özelleştirebilecek ve ihtiyacınız olan verileri almak için bir MPP dosyasını **güvenilir bir şekilde yükleyebileceksiniz**.

## Hızlı Yanıtlar
- **“Çalışma günlerini belirleme” ne anlama geliyor?** Bu, belirli bir görev için takvim tarihlerinin hangi günlerin çalışma günü olarak kabul edildiğini belirlemeyi ifade eder.  
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Tasks for Java, MS Project dosyalarıyla çalışmak için tam özellikli bir API sunar.  
- **Uygulama ne kadar sürer?** Temel bir çıkarım için genellikle 10–15 dakika yeterlidir.  
- **Lisans gerekir mi?** Ücretsiz bir deneme sürümü mevcuttur; üretim kullanımı için ticari lisans gereklidir.  
- **Çalışma saatlerini özelleştirebilir miyim?** Evet – takvimleri değiştirebilir, tatilleri ekleyebilir ve özel çalışma zamanı aralıkları belirleyebilirsiniz.

## “Çalışma günlerini belirleme” nedir?
Bir görev planlandığında, proje takvimi hangi günlerin çalışma günü, hangi günlerin ise (hafta sonları, tatiller) çalışma günü olmadığını tanımlar. Çalışma günlerini belirlemek, takvimi sorgulayarak işin ne zaman gerçekleşebileceğini kesin olarak bilmek anlamına gelir; bu da doğru **görev süresi hesaplamaları** için kritiktir.

## Çalışma saatlerini almak için neden Aspose.Tasks kullanılmalı?
- **Microsoft Project gerekmez** – .MPP dosyalarıyla herhangi bir platformda çalışabilirsiniz.  
- **Tam takvim desteği** – varsayılan, kaynak ve görev takvimlerini içerir.  
- **Yüksek performans** – büyük projeleri hızlı bir şekilde işleyebilir.  
- **Kapsamlı dokümantasyon** – örnekler ve API referansı kolayca bulunur.

## Önkoşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

1. **Java Development Kit (JDK)** – sürüm 8 veya üzeri.  
2. **Aspose.Tasks for Java** – en yeni JAR dosyasını [burada](https://releases.aspose.com/tasks/java/) indirebilirsiniz.  
3. Temel Java programlama bilgisi.  

## Paketleri İçe Aktarma
İlk olarak, Aspose.Tasks çekirdek paketini içe aktarın:

```java
import com.aspose.tasks.*;
```

## Adım 1: MPP dosyasını yükleme
Takvimleriyle çalışabilmek için proje dosyanızı (**load mpp file** adımı) yükleyin:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Adım 2: Görev ve Takvim Bilgilerini Almak
Analiz etmek istediğiniz görevi seçin ve ilişkili takvimini alın. Bu adımda görev için **çalışma saatlerini** elde edeceğiz:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Adım 3: Başlangıç ve Bitiş Tarihlerini Tanımlama
**Çalışma günlerini belirlemek** istediğiniz zaman aralığını ayarlayın:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Adım 4: Tarihler Üzerinde Döngü
Görevin süresi boyunca her bir tarihi döngüye alın. Bu döngü, gerektiğinde **çalışma saatlerini özelleştirmemize** olanak tanır:

```java
java.util.Calendar tempDate = calStartDate;
```

## Adım 5: Süreyi Hesaplama
Döngü sırasında her günün çalışma günü olup olmadığını kontrol eder, çalışma saatlerini toplar ve sonunda görevin süresini dakika, saat ve gün olarak hesaplarız:

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

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Görev takvimi `null` döndürüyor** | Görevin gerçekten bir takvim atandığından emin olun; aksi takdirde projenin varsayılan takvimini devralır. |
| **Tatiller nedeniyle yanlış süre** | Tatillerin görev takviminde veya projenin temel takviminde tanımlandığını doğrulayın. |
| **Zaman dilimi uyumsuzluğu** | Gerekirse takvimin zaman dilimini sisteminizle eşleştirmek için `java.util.TimeZone` kullanın. |

## Sıkça Sorulan Sorular
### Q: Aspose.Tasks for Java karmaşık proje yapılarıyla başa çıkabilir mi?
A: Evet, Aspose.Tasks for Java görevler, kaynaklar ve takvimler dahil olmak üzere karmaşık proje yapılarını yönetmek için kapsamlı destek sağlar.

### Q: Aspose.Tasks for Java farklı MS Project sürümleriyle uyumlu mu?
A: Kesinlikle, Aspose.Tasks for Java çeşitli MS Project sürümlerini destekler ve farklı ortamlar arasında uyumluluk sağlar.

### Q: Proje takvimlerinde çalışma saatlerini ve tatilleri özelleştirebilir miyim?
A: Evet, Aspose.Tasks for Java API'lerini kullanarak proje gereksinimlerinize göre çalışma saatlerini ve tatilleri kolayca özelleştirebilirsiniz.

### Q: Aspose.Tasks for Java destek ve dokümantasyon sunuyor mu?
A: Evet, Aspose.Tasks for Java kapsamlı dokümantasyon ve geliştiricilere özelliklerini etkili bir şekilde kullanmaları için yardımcı olmak amacıyla özel destek forumları sağlar.

### Q: Aspose.Tasks for Java için bir deneme sürümü mevcut mu?
A: Evet, Aspose.Tasks for Java için ücretsiz bir deneme sürümüne [burada](https://releases.aspose.com/) ulaşabilirsiniz.

## Sonuç
Bu rehberde Aspose.Tasks for Java kullanarak bir MS Project takviminden **çalışma günlerini belirleme**, **çalışma saatlerini alma** ve **görev süresini hesaplama** işlemlerini gösterdik. Yukarıdaki adımları izleyerek takvim analizi otomatikleştirebilir, takvimleri özelleştirebilir ve proje planlarınızı doğru ve güncel tutabilirsiniz.

---

**Son Güncelleme:** 2025-12-05  
**Test Edilen:** Aspose.Tasks for Java 24.12 (yazım zamanındaki en yeni sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}