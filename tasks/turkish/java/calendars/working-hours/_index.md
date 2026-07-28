---
date: 2026-02-05
description: Aspose.Tasks for Java kullanarak MS Project takvimlerinden çalışma saatlerini
  çıkararak çalışma günlerini belirlemeyi ve görev süresini hesaplamayı öğrenin.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile Çalışma Günlerini ve Çalışma Saatlerini Belirleyin
url: /tr/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Çalışma Günlerini ve Çalışma Saatlerini Belirleme

## Giriş
Proje takvimlerini yönetmek, başarılı proje planlamasının temel bir parçasıdır. Bu öğreticide, Aspose.Tasks for Java kullanarak herhangi bir görev için **çalışma günlerini belirleyecek** ve bir MS Project takviminden **çalışma saatlerini çıkaracaksınız**. Kılavuzun sonunda **görev süresini hesaplayabilecek**, çalışma saatlerini özelleştirebilecek ve ihtiyacınız olan verileri almak için **bir MPP dosyasını güvenilir bir şekilde yükleyebileceksiniz**. Ayrıca **Microsoft Project** yüklü olmadan **MS Project** dosyalarını **okuyabileceğinizi** göreceksiniz, bu da otomasyonu herhangi bir platformda mümkün kılar.

## Hızlı Yanıtlar
- **“determine working days” ne anlama geliyor?** Bu, belirli bir görev için takvim tarihlerinin hangi günlerin çalışma günü olarak kabul edildiğini belirlemeyi ifade eder.  
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Tasks for Java, MS Project dosyalarıyla çalışmak için tam özellikli bir API sağlar.  
- **Uygulama ne kadar sürer?** Temel bir çıkarma için genellikle 10–15 dakika.  
- **Lisans gerekli mi?** Ücretsiz bir deneme sürümü mevcuttur; üretim kullanımı için ticari bir lisans gereklidir.  
- **Çalışma saatlerini özelleştirebilir miyim?** Evet – takvimleri değiştirebilir, tatilleri ekleyebilir ve özel çalışma zamanı aralıkları belirleyebilirsiniz.  

## “determine working days” nedir?
Bir görev planlandığında, proje takvimi hangi günlerin çalışma günü, hangilerinin (hafta sonları, tatiller) çalışma günü olmadığını tanımlar. Çalışma günlerini belirlemek, bu takvime sorgu yaparak çalışmanın tam olarak ne zaman gerçekleşebileceğini bilmek anlamına gelir; bu, doğru **görev süresini hesaplama** hesaplamaları için gereklidir.

## Çalışma saatlerini almak için neden Aspose.Tasks kullanılmalı?
- **Microsoft Project gerekmez** – MS Project dosyalarını doğrudan Java kodundan okuyabilirsiniz.  
- **Tam takvim desteği** – varsayılan, kaynak ve görev takvimlerini içerir.  
- **Yüksek performans** – büyük projeleri hızlı bir şekilde işleyin.  
- **Kapsamlı dokümantasyon** – örnekler ve API referansı kolayca bulunur.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK)** – sürüm 8 veya üzeri.  
2. **Aspose.Tasks for Java** – en son JAR dosyasını [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. Temel Java programlama bilgisi.  

## Paketleri İçe Aktarma
İlk olarak, temel Aspose.Tasks ad alanını içe aktarın:

```java
import com.aspose.tasks.*;
```

## Aspose.Tasks ile bir MPP dosyası nasıl yüklenir?
Proje dosyasını yüklemek, herhangi bir takvim analizine yönelik ilk adımdır. API, **bir MPP dosyasını** tek bir kod satırıyla, MS Project kullanıcı arayüzüne ihtiyaç duymadan yüklemenizi sağlar.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Görev ve Takvim Bilgilerini Almak
Analiz etmek istediğiniz görevi seçin ve ilişkili takvimini alın. Burada görev için **çalışma saatlerini alıyoruz**:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Başlangıç ve Bitiş Tarihlerini Tanımlama
**Çalışma günlerini belirlemek** istediğiniz zaman aralığını ayarlayın. Görevin başlangıç ve bitiş tarihlerini kullanmak, yalnızca ilgili dönemi değerlendirmenizi sağlar.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Tarihleri Döngüyle İşleme
Görevin süresindeki her tarihi döngüyle işleyin. Bu döngü, gerekirse **çalışma saatlerini özelleştirmemize** yardımcı olacaktır:

```java
java.util.Calendar tempDate = calStartDate;
```

## Süreyi Hesaplama
İterasyon sırasında her günün çalışma günü olup olmadığını kontrol eder, çalışma saatlerini toplar ve sonunda görevin süresini dakika, saat ve gün cinsinden hesaplarız. Bu adım, programlı olarak **çalışma günlerini hesaplamayı** ve **görev süresini hesaplamayı** gösterir.

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
Aspose.Tasks, takvimin çalışma zamanı aralıklarını değiştirmenize ve tatil gibi istisnalar eklemenize olanak tanır. Takvimi kuruluşunuzun politikalarına göre uyarlamak için `taskCalendar.addWorkingTime()` veya `taskCalendar.addException()` çağırabilirsiniz. Varsayılan 9‑5 programı gerçeklikle uyuşmadığında bu faydalıdır.

## Yaygın Sorunlar ve Çözümleri
| Sorun | Çözüm |
|-------|----------|
| **Görev takvim için `null` döndürüyor** | Görevin gerçekten bir takvim atandığından emin olun; aksi takdirde projenin varsayılan takvimini devralır. |
| **Tatiller nedeniyle yanlış süre** | Tatillerin görev takviminde veya projenin temel takviminde tanımlandığını doğrulayın. |
| **Saat dilimi uyumsuzluğu** | Gerekirse takvimin saat dilimini sisteminizle eşleştirmek için `java.util.TimeZone` kullanın. |

## Sıkça Sorulan Sorular
### Q: Aspose.Tasks for Java karmaşık proje yapılarıyla başa çıkabilir mi?
A: Evet, Aspose.Tasks for Java, görevler, kaynaklar ve takvimler dahil olmak üzere karmaşık proje yapılarıyla başa çıkmak için kapsamlı destek sağlar.

### Q: Aspose.Tasks for Java farklı MS Project sürümleriyle uyumlu mu?
A: Kesinlikle, Aspose.Tasks for Java, farklı MS Project sürümlerini destekler ve çeşitli ortamlar arasında uyumluluğu sağlar.

### Q: Proje takvimlerinde çalışma saatlerini ve tatilleri özelleştirebilir miyim?
A: Evet, Aspose.Tasks for Java API'lerini kullanarak proje gereksinimlerinize göre çalışma saatlerini ve tatilleri kolayca özelleştirebilirsiniz.

### Q: Aspose.Tasks for Java destek ve dokümantasyon sunuyor mu?
A: Evet, Aspose.Tasks for Java, özelliklerini etkili bir şekilde kullanmalarına yardımcı olmak için kapsamlı dokümantasyon ve özel destek forumları sunar.

### Q: Aspose.Tasks for Java için bir deneme sürümü mevcut mu?
A: Evet, Aspose.Tasks for Java'ın ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

## Sonuç
Bu rehberde, Aspose.Tasks for Java kullanarak bir MS Project takviminden **çalışma günlerini belirleme**, **çalışma saatlerini alma** ve **görev süresini hesaplama** nasıl yapılır gösterdik. Yukarıdaki adımları izleyerek takvim analizini otomatikleştirebilir, takvimleri özelleştirebilir ve proje planlarınızı doğru ve güncel tutabilirsiniz. Artık **MS Project** verilerini **okuma**, **MPP dosyası yükleme** ve Microsoft Project'e ihtiyaç duymadan kesin süre hesaplamaları yapma araçlarına sahipsiniz.

---

**Son Güncelleme:** 2026-02-05  
**Test Edilen:** Aspose.Tasks for Java 24.12 (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}