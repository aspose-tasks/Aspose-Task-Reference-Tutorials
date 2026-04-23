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

## Introduction
Bu öğreticide **Workweeks Java nasıl okunur** konusunu Microsoft Project takviminden Aspose.Tasks kütüphanesini kullanarak öğreneceksiniz. Raporlama aracı oluşturuyor, takvimleri senkronize ediyor ya da proje verisi çıkarımını otomatikleştiriyor olun, iş‑haftası tanımlarına programlı olarak erişebilmek sayısız manuel saati tasarruf ettirir. Gerekli kurulumu adım adım gösterecek, iş‑haftası detaylarını almak için tam kodu sunacak ve her adımı açıklayacağız, böylece çözümü kendi projelerinize uyarlayabilirsiniz.

## Quick Answers
- **“read workweeks java” ne anlama geliyor?** Java kodu kullanarak bir Project dosyasından iş‑haftası tanımlarını çıkarmak anlamına gelir.  
- **Hangi kütüphane gerekiyor?** Aspose.Tasks for Java (ücretsiz deneme mevcut).  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için deneme sürümü yeterlidir; üretim için ticari lisans gereklidir.  
- **Hangi dosya formatları destekleniyor?** Hem *.mpp* hem de Project XML dosyaları işlenebilir.  
- **Uygulama ne kadar sürer?** Kütüphane kurulduktan sonra genellikle 10 dakikadan az sürer.

## How to Read Workweeks Java from a Microsoft Project Calendar
Java’da iş haftalarını okumak, Aspose.Tasks API’sini kullanarak bir Microsoft Project dosyası içindeki takvim nesnesinin `WorkWeekCollection`’ına erişmek demektir. Her `WorkWeek`, başlangıç/bitiş tarihlerini ve kaynakların planlanmasını belirleyen günlük çalışma‑zamanı tanımlarını içerir.

## Why read workweeks Java from a Microsoft Project calendar?
- **Automation:** Takvim verilerini manuel kopyala‑yapıştırdan kurtulun.  
- **Integration:** İş‑haftası bilgilerini ERP, İK veya özel raporlama sistemlerine besleyin.  
- **Consistency:** Tüm alt sistemlerin aynı takvim kurallarına uymasını sağlayın.

## Prerequisites
Kodlara geçmeden önce şunların yüklü olduğundan emin olun:

1. **Java Development Kit (JDK)** – sürüm 8 veya üzeri yüklü.  
2. **Aspose.Tasks for Java** – resmi siteden en yeni JAR’ı indirin: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Bilinen bir klasöre yerleştirilmiş bir **örnek Project dosyası** (`ReadWorkWeeksInformation.mpp`).

## Import Packages
Takvimler ve iş haftalarıyla etkileşim kurmak için gerekli sınıfları içe aktarın:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Step 1: Set Up Your Data Directory
`.mpp` dosyasını içeren klasörü tanımlayın. Yer tutucuyu makinenizdeki gerçek yol ile değiştirin:

```java
String dataDir = "Your Data Directory";
```

## Step 2: Create a Project Instance and Access the Calendar
Bir `Project` nesnesi oluşturun, istediğiniz takvimi (UID ile) seçin ve `WorkWeekCollection`’ını alın:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** Takvim UID’sinden emin değilseniz `project.getCalendars()` üzerinden döngü kurarak her takvimin adını ve UID’sini yazdırabilirsiniz.

## Step 3: Iterate Through Work Weeks
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

## Common Issues and Solutions
| Sorun | Neden | Çözüm |
|-------|--------|-----|
| `calendar` erişirken `NullPointerException` | Yanlış UID veya takvim mevcut değil | UID'yi `project.getCalendars().size()` ile doğrulayın ve önce kullanılabilir takvimleri listeleyin. |
| İş haftaları için çıktı yok | Seçilen takvimde özel iş haftası yok (varsayılanı kullanıyor) | Varsayılan takvimi (`project.getDefaultCalendar()`) kullanın veya programlı olarak bir iş haftası oluşturun. |
| Tarih formatı garip görünüyor | `System.out.println` varsayılan `java.util.Date` formatını kullanıyor | Gerektiği gibi tarihleri biçimlendirmek için bir `SimpleDateFormat` uygulayın. |

## Frequently Asked Questions

**S: Aspose.Tasks for Java kullanarak iş haftası bilgilerini değiştirebilir miyim?**  
C: Evet. API, `addWorkWeek()`, `removeWorkWeek()` gibi yöntemler ve isim, tarih, çalışma saatlerini değiştiren özellik setleri sunar.

**S: Aspose.Tasks farklı Microsoft Project dosya sürümleriyle uyumlu mu?**  
C: Kesinlikle. Project 98’den en yeni sürümlere kadar MPP dosyalarını ve Project XML dosyalarını destekler.

**S: Aspose.Tasks’i diğer Java çerçeveleriyle entegre edebilir miyim?**  
C: Evet. Kütüphane saf Java olduğundan Spring, Jakarta EE veya başka herhangi bir çerçeveyle birlikte kullanılabilir.

**S: Aspose.Tasks için deneme sürümü var mı?**  
C: Evet, resmi siteden ücretsiz 30‑günlük deneme sürümünü indirebilirsiniz: [Aspose.Tasks trial](https://releases.aspose.com/).

**S: Aspose.Tasks desteğini nereden bulabilirim?**  
C: En iyi yer Aspose topluluk forumudur: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
Artık **Workweeks Java nasıl okunur** konusunda uzmanlaştınız ve Aspose.Tasks’i kullanarak bunu gerçekleştirebiliyorsunuz. Yukarıdaki adımları izleyerek herhangi bir MS Project takviminden programlı olarak iş‑haftası tanımlarını çekebilir, bu verileri uygulamalarınıza entegre edebilir ve takvimle ilgili iş akışlarını otomatikleştirebilirsiniz. İş haftaları oluşturma veya güncelleme deneyleri yapmaktan çekinmeyin—Aspose.Tasks bunu oldukça basit hâle getiriyor.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}