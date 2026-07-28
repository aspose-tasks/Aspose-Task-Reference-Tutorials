---
date: 2026-02-05
description: Aspose.Tasks kullanarak Microsoft Project takviminden Java çalışma haftalarını
  nasıl okuyacağınızı öğrenin. Tam kod örnekleriyle adım adım rehberi izleyin.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile Java’da MS Project Takviminden Çalışma Haftalarını Okuma
url: /tr/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project Takviminden Workweeks Java Nasıl Okunur Aspose.Tasks

## Giriiş
Bu öğreticide **Workweeks Java'nın nasıl anlatılacağı** Microsoft Project takviminden Aspose.Tasks kütüphanesini kullanarak dosyalarını kullanır. Raporlama aracı oluşturulur, takvimleri güncellenir ya da proje verisi çıkarımını otomatik olarak yükseltir olun, iş-haftası tanımlarına programlı olarak erişebilmek için sınırsız manuel saat tasarrufu sağlar. Gerekli kurulum adım adım girerseniz, iş-haftası detaylarını almak için tam kodu sunacak ve her adımı açıklayacağız, böylece çözüm kendi projelerinize uyarlayabilirsiniz.

## Hızlı Yanıtlar
- **“readworkweeks java” ne anlama geliyor?**Java kodunu kullanarak bir Proje dosyasından iş‑haftası tanımlarını çıkarma anlamına gelir.
- **Hangi paketi gerekiyor mu?**Aspose.Tasks for Java (ücretsiz deneme mevcut).
- **Geliştirme için lisansa ihtiyacım var mı?**Test için deneme sürümü yeterlidir; üretim için ticari lisans gereklidir.
- **Hangi dosya formatları destekleniyor mu?**Hem *.mpp* hem de Proje XML dosyaları işlenebilir.
- **Uygulama ne kadar sürer?**Kütüphane kurulduktan sonra genellikle 10dakikadan az sürer.

## Workweeks Java'yı Microsoft Proje Takviminden Nasıl Okuyabilirim?
Java’da iş haftalarını okumak, Aspose.Tasks API’sini kullanarak bir Microsoft Project’in içindeki takvim nesnesinin `WorkWeekCollection`a açılması demektir. Her `WorkWeek`, başlangıç/bitiş tarihlerini ve elde edilmesinin planlanmasının günlük çalışma‑zamanı tanımlarını içerir.

## Neden Workweeks Java'yı Microsoft Project takviminden okumalısınız?
- **Otomasyon:** Takvim'in manuel kopyasıyla-yapıştırmaktan kurtulun.
- **Entegrasyon:** İş‑haftası'nın alınması ERP, İK veya özel raporlama sistemlerine besleyin.
- **Tutarlılık:** Tüm alt sistemlerin aynı takvim kurallarına uymasını sağlayın.

## Önkoşullar
Kodlara bölünmeden önce yüklü olduğunuzdan emin olun:

1. **Java Development Kit (JDK)** – sürüm 8 veya üzeri yüklü.
2. **Aspose.Tasks for Java** – resmi siteden en yeni JAR’ı indirin: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).
3. Bilinen bir bilgisayara yerleştirilen bir **örnek Proje dosyası** (`ReadWorkWeeksInformation.mpp`).

## Paketleri İçe Aktar
Takvimler ve iş haftalarıyla etkileşimi için gerekli sınıfları içe aktarın:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Adım 1: Veri Dizininizi Kurun
`.mpp` dosyasını içeren klasörü tanımlayın. Yer tutucuyu makinenizdeki gerçek yol ile değiştirin:

```java
String dataDir = "Your Data Directory";
```

## Adım 2: Bir Proje Örneği Oluşturun ve Takvime Erişin
Bir `Project` nesnesi oluşturun, istediğiniz takvimi (UID ile) seçin ve `WorkWeekCollection`’ını alın:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** Takvim UID’sinden emin değilseniz `project.getCalendars()` üzerinden döngü kurarak her takvimin adını ve UID’sini yazdırabilirsiniz.

## Adım 3: Çalışma Haftaları Üzerinde Yineleme Yapın
Her `WorkWeek` üzerinde döngü kurarak adını, başlangıç/bitiş tarihlerini ve günlük çalışma zamanlarını gösterin:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**What you’ll see:** Konsol, her iş‑haftasının etiketini (örn. “Standard”), geçerli tarih aralığını ve her gün için kesin çalışma saatlerini yazdırır.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden | Çözüm |
|----------|-----------|-----|
| `takvim`e erişirken `NullPointerException` | Yanlış UID veya takvim mevcut değil | UID'yi `project.getCalendars().size()` ile doğrulayın ve önceden kullanılabilir takvimleri listeleyin. |
| İş haftaları için çıktı yok | Seçilen takvimde özel iş haftası yok (varsayılanı kullanıyor) | varsayılan takvim (`project.getDefaultCalendar()`) kullanın veya programlı olarak bir iş haftası oluşturun. |
| Tarih formatı garip görünüyor | `System.out.println` varsayılan `java.util.Date` formatını kullanıyor | Gerektiği gibi bağımsız biçimlendirmek için bir `SimpleDateFormat` eklentisi. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java kullanarak iş haftasını kazanabilir miyim?**
C: Evet. API, `addWorkWeek()`, `removeWorkWeek()` gibi kopyalamalar ve isim, tarih, erişime yönelik dağıtılabilir özellik paketleri sunar.

**S: Aspose.Tasks farklı Microsoft Project dosyasıyla uyumlu mu?**
C: elbette. Project 98’den en yeni sürümlere kadar MPP karakteri ve Project XML sürümüne kadar.

**S: Aspose.Tasks’i diğer Java çerçeveleriyle entegre edebilir miyim?**
C: Evet. Kütüphanede güvenli Java'nız var Spring, Jakarta EE veya başka herhangi bir çerçeveyle birlikte kullanılabilir.

**S: Aspose.Tasks için deneme sürümü var mı?**
C: Evet, resmi siteden ücretsiz 30 günlük deneme indirme indirmeleri: [Aspose.Tasks deneme sürümü](https://releases.aspose.com/).

**S: Aspose.Tasks'ın herhangi bir yerde saklanabilir miyim?**
C: En iyi yer Aspose topluluk forumudur: [Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).

## Çözüm
Artık **Workweeks Java nasıl okunur** konusunda uzmanlaştınız ve Aspose.Tasks’i kullanarak bunu gerçekleştirebiliyorsunuz. Yukarıdaki adımları izleyerek herhangi bir MS Project takviminden programlı olarak iş‑haftası tanımlarını çekebilir, bu verileri uygulamalarınıza entegre edebilir ve takvimle ilgili iş akışlarını otomatikleştirebilirsiniz. İş haftaları oluşturma veya güncelleme deneyleri yapmaktan çekinmeyin—Aspose.Tasks bunu oldukça basit hâle getiriyor.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}