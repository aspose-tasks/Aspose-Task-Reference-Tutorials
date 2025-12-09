---
date: 2025-12-03
description: Aspose.Tasks kullanarak bir Microsoft Project takviminden iş haftalarını
  Java ile nasıl okuyacağınızı öğrenin. Tam kod örnekleriyle adım adım kılavuzu izleyin.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MS Project Takviminden Aspose.Tasks ile Java’da Çalışma Haftalarını Okuma
url: /tr/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Read Work Weeks Java from MS Project Calendar Aspose.Tasks

## Introduction
Bu öğreticide **read work weeks Java** ifadesini Aspose.Tasks kütüphanesini kullanarak bir Microsoft Project takviminden nasıl okuyacağınızı göstereceğiz. Raporlama aracı oluşturuyor, takvimleri senkronize ediyor ya da proje verilerini otomatik olarak çıkartıyorsanız, çalışma‑haftası tanımlarına programlı olarak erişebilmek sayısız manuel saati tasarruf ettirir. Gerekli kurulumu adım adım gösterecek, çalışma‑haftası detaylarını almanız için tam kodu sunacak ve her adımı açıklayarak çözümü kendi projelerinize uyarlamanızı sağlayacağız.

## Quick Answers
- **“read work weeks java” ne anlama geliyor?** Java kodu kullanarak bir Project dosyasından çalışma‑haftası tanımlarını çıkarmak anlamına gelir.  
- **Hangi kütüphane gerekiyor?** Aspose.Tasks for Java (ücretsiz deneme sürümü mevcut).  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için deneme sürümü yeterlidir; üretim ortamı için ticari lisans gerekir.  
- **Hangi dosya formatları destekleniyor?** Hem *.mpp* hem de Project XML dosyaları işlenebilir.  
- **Uygulama ne kadar sürer?** Kütüphane kurulduktan sonra genellikle 10 dakikadan az sürer.

## What is “read work weeks java”?
Java’da çalışma haftalarını okumak, Aspose.Tasks API’sini kullanarak bir Microsoft Project dosyası içindeki takvim nesnesinin `WorkWeekCollection`’ına erişmek demektir. Her `WorkWeek` başlangıç/bitiş tarihlerini ve kaynakların planlanmasını belirleyen günlük çalışma‑saat tanımlarını içerir.

## Why read work weeks java from a Microsoft Project calendar?
- **Otomasyon:** Takvim verilerini manuel kopyala‑yapıştır yapmaktan kurtulun.  
- **Entegrasyon:** Çalışma‑haftası bilgilerini ERP, İK veya özel raporlama sistemlerine besleyin.  
- **Tutarlılık:** Tüm downstream araçların Project dosyasında tanımlı aynı takvim kurallarını kullanmasını sağlayın.

## Prerequisites
Kodlamaya başlamadan önce şunların kurulu olduğundan emin olun:

1. **Java Development Kit (JDK)** – sürüm 8 veya üzeri yüklü.  
2. **Aspose.Tasks for Java** – resmi siteden en yeni JAR dosyasını indirin: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Bilinen bir klasöre yerleştirilmiş bir **örnek Project dosyası** (`ReadWorkWeeksInformation.mpp`).

## Import Packages
İlk olarak takvim ve çalışma haftalarıyla etkileşim kurmak için gerekli sınıfları içe aktarın:

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
`.mpp` dosyasının bulunduğu klasörü tanımlayın. Yer tutucuyu makinenizdeki gerçek yol ile değiştirin:

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

> **Pro ipucu:** Takvim UID’sinden emin değilseniz `project.getCalendars()` üzerinden döngü kurarak her takvimin adını ve UID’sini yazdırabilirsiniz.

## Step 3: Iterate Through Work Weeks
Her `WorkWeek` üzerinde döngü kurarak adını, başlangıç/bitiş tarihlerini ve günlük çalışma saatlerini gösterin:

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

**Gördükleriniz:** Konsol, her çalışma‑haftasının etiketini (ör. “Standard”), geçerli tarih aralığını ve gün bazında tam çalışma saatlerini yazdırır.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` when accessing `calendar` | Yanlış UID veya takvim mevcut değil | `project.getCalendars().size()` ile UID’yi doğrulayın ve önce mevcut takvimleri listeleyin. |
| No output for work weeks | Seçilen takvimde özel çalışma haftası yok (varsayılan kullanılıyor) | Varsayılan takvimi (`project.getDefaultCalendar()`) kullanın veya programlı olarak bir çalışma haftası oluşturun. |
| Date format looks odd | `System.out.println` varsayılan `java.util.Date` formatını kullanıyor | İstediğiniz biçimde tarihleri göstermek için bir `SimpleDateFormat` uygulayın. |

## Frequently Asked Questions

**Q: Can I modify the work weeks information using Aspose.Tasks for Java?**  
A: Yes. The API provides methods such as `addWorkWeek()`, `removeWorkWeek()`, and property setters to change names, dates, and working times.

**Q: Is Aspose.Tasks compatible with different versions of Microsoft Project files?**  
A: Absolutely. It supports MPP files from Project 98 up to the latest versions, as well as Project XML files.

**Q: Can I integrate Aspose.Tasks with other Java frameworks?**  
A: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta EE, or any other framework.

**Q: Is there a trial version available for Aspose.Tasks?**  
A: Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Where can I find support for Aspose.Tasks?**  
A: The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
Artık Aspose.Tasks kullanarak **read work weeks java** konusunu kavradınız. Yukarıdaki adımları izleyerek herhangi bir MS Project takviminden programlı olarak çalışma‑haftası tanımlarını çekebilir, bu verileri uygulamalarınıza entegre edebilir ve takvim‑ile‑ilgili iş akışlarını otomatikleştirebilirsiniz. Çalışma haftaları oluşturma veya güncelleme konularında denemeler yapmaktan çekinmeyin—Aspose.Tasks bunu oldukça basit bir şekilde sağlar.

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}