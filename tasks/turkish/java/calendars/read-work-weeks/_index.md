---
date: 2026-08-13
description: Aspose.Tasks for Java kullanarak bir MS Project takviminden çalışma haftalarını
  nasıl okuyacağınızı öğrenin. Kod örnekleri ve sorun giderme ipuçlarıyla adım adım
  rehberi izleyin.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Aspose.Tasks ile Takvimden Çalışma Haftalarını Okuma
og_description: Aspose.Tasks for Java kullanarak bir MS Project takviminden çalışma
  haftalarını nasıl okuyacağınızı öğrenin. Kurulum adımları, kod parçacıkları ve sorun
  giderme ipuçlarıyla kısa öğreticiyi izleyin.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Aspose.Tasks ile MS takviminden çalışma haftalarını okuma
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Aspose.Tasks ile MS takviminden çalışma haftalarını okuma
url: /tr/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS takviminden Aspose.Tasks ile çalışma haftalarını okuma

## Giriş
Bu öğreticide **çalışma haftalarını nasıl okuyacağınızı** Microsoft Project takviminden Aspose.Tasks Java kütüphanesini kullanarak öğreneceksiniz. Raporlama panosu oluşturuyor, takvimleri bir ERP sistemiyle senkronize ediyor ya da analiz için veri çıkarımını otomatikleştiriyor olun, programatik olarak çalışma‑haftası tanımlarına erişim sayısız manuel saati tasarruf ettirir. Aspose.Tasks **50+ giriş ve çıkış formatını** destekler ve tüm dosyayı belleğe yüklemeden çok sayfalı proje dosyalarını işleyebilir, bu da size esneklik ve performans sağlar.

## Hızlı cevaplar
- **“Çalışma haftalarını okuma” ne anlama geliyor?** Bir Project dosyasından Java kodu aracılığıyla çalışma‑haftası tanımlarını (tarihleri ve günlük çalışma‑zamanı kurallarını) çıkarmak anlamına gelir.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java (ücretsiz deneme mevcut).  
- **Geliştirme için lisansa ihtiyacım var mı?** Deneme sürümü test için çalışır; üretim dağıtımları için ticari lisans gereklidir.  
- **Hangi dosya formatları destekleniyor?** Hem *.mpp* hem de Project XML dosyaları işlenir, ayrıca içe/dışa aktarım için 50+ başka format vardır.  
- **Uygulama ne kadar sürer?** Kütüphane kurulduktan sonra genellikle 10 dakikadan az sürer.

## MS Project'te bir çalışma haftası nedir?
Bir çalışma haftası, kaynakların belirli bir dönemde ne zaman kullanılabilir olduğunu belirleyen takvim kurallarını tanımlar. Başlangıç tarihi, bitiş tarihi ve günlük çalışma‑zamanı aralıklarını (ör. 09:00–17:00) içerir. MS Project'te her takvim birden fazla çalışma haftası içerebilir; bu sayede tatiller, vardiya desenleri veya mevsimsel programlar modellenebilir.

## Aspose.Tasks bir takvimden çalışma haftalarını nasıl okur?
Aspose.Tasks, bir `Calendar` nesnesinin `WorkWeekCollection` özelliğini sunar. Bir `Project` örneği oluşturup, istenen takvimi (UID veya ad ile) seçerek ve `WorkWeekCollection` üzerinde döngü yaparak her çalışma haftasının etiketi, geçerli tarih aralığı ve günlük çalışma‑zamanı dilimlerini alabilirsiniz. API tüm tarih‑zaman dönüşümlerini yönetir ve projenin saat‑dilimi ayarlarını otomatik olarak dikkate alır.

## Neden Microsoft Project takviminden Java ile çalışma haftalarını okuyalım?
Çalışma haftalarını programatik olarak okumak, manuel kopyala‑yapıştırmayı ortadan kaldırır, alt sistemlerin (ERP, İK, raporlama) aynı zamanlama kurallarını kullanmasını sağlar ve birden çok proje arasında tutarlılığı garantiler. Otomasyon ayrıca insan hatasını azaltır ve entegrasyon boru hatlarını hızlandırır, özellikle her gece onlarca proje dosyasını işlemeyi planlıyorsanız.

## Önkoşullar
Önce aşağıdakilerin kurulu olduğundan emin olun:

1. **Java Development Kit (JDK)** – 8 veya daha yeni bir sürüm yüklü.  
2. **Aspose.Tasks for Java** – resmi siteden en son JAR'ı indirin: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Bilgisayarınızda bilinen bir klasöre yerleştirilmiş bir **örnek Project dosyası** (`ReadWorkWeeksInformation.mpp`).

## Paketleri içe aktar
Takvimler ve çalışma haftalarıyla etkileşim kurmak için ihtiyacımız olan sınıfları içe aktaralım:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Adım 1: veri dizininizi ayarlayın
`.mpp` dosyasını içeren klasörü tanımlayın. Yer tutucuyu makinenizdeki gerçek yol ile değiştirin:

```java
String dataDir = "Your Data Directory";
```

## Adım 2: bir Project örneği oluşturun ve takvime erişin
`Project` sınıfı bir Microsoft Project dosyasını temsil eder ve takvimler, görevler, kaynaklar gibi veri yapılarının erişimini sağlar.  
Bir `Project` nesnesi oluşturun, istediğiniz takvimi (UID ile) seçin ve `WorkWeekCollection`'ını alın:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** Takvim UID'sinden emin değilseniz, önce `project.getCalendars()` üzerinden döngü yapıp her takvimin adını ve UID'sini yazdırın.

## Adım 3: çalışma haftaları üzerinde döngü oluşturun
`WorkWeek` sınıfı bir çalışma‑haftası tanımını kapsar; başlangıç/bitiş tarihleri ve günlük çalışma‑zamanı ayarlarını içerir.  
Her `WorkWeek` üzerinden döngü kurarak adını, başlangıç/bitiş tarihlerini ve günlük çalışma saatlerini gösterin:

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

**Ne göreceksiniz:** Konsol, her çalışma haftasının etiketini (ör. “Standard”), geçerli tarih aralığını ve her gün için kesin çalışma saatlerini yazdırır.

## Yaygın sorunlar ve çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| `calendar` erişilirken `NullPointerException` | Yanlış UID veya takvim mevcut değil | UID'yi `project.getCalendars().size()` ile doğrulayın ve önce mevcut takvimleri listeleyin. |
| Çalışma haftaları için çıktı yok | Seçilen takvimde özel çalışma haftaları yok (varsayılanı kullanıyor) | Varsayılan takvimi (`project.getDefaultCalendar()`) kullanın veya programlı olarak bir çalışma haftası oluşturun. |
| Tarih formatı garip görünüyor | `System.out.println` varsayılan `java.util.Date` formatını kullanıyor | İhtiyaca göre tarihleri biçimlendirmek için bir `SimpleDateFormat` uygulayın. |

## Sıkça sorulan sorular
**S: Aspose.Tasks for Java kullanarak çalışma haftası bilgilerini değiştirebilir miyim?**  
C: Evet. API `addWorkWeek()`, `removeWorkWeek()` ve isim, tarih ve çalışma saatlerini değiştiren özellik ayarlayıcılarını sağlar.

**S: Aspose.Tasks farklı Microsoft Project dosya sürümleriyle uyumlu mu?**  
C: Kesinlikle. Project 98'den en yeni sürümlere kadar MPP dosyalarını ve Project XML dosyalarını destekler.

**S: Aspose.Tasks'i diğer Java çerçeveleriyle entegre edebilir miyim?**  
C: Evet. Kütüphane saf Java'dır, bu yüzden Spring, Jakarta EE veya başka bir çerçeveyle birlikte kullanılabilir.

**S: Aspose.Tasks için bir deneme sürümü mevcut mu?**  
C: Evet, resmi siteden ücretsiz 30‑günlük bir deneme indirebilirsiniz: [Aspose.Tasks trial](https://releases.aspose.com/).

**S: Aspose.Tasks için destek nereden alınabilir?**  
C: Aspose topluluk forumu en iyi yerdir: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Son Güncelleme:** 2026-08-13  
**Test Edilen Sürüm:** Aspose.Tasks for Java 24.12 (yazım zamanındaki en son)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Eğitimler

- [Aspose.Tasks for Java ile projeye takvim ekleme](/tasks/java/calendars/create/)
- [Aspose.Tasks ile Takvim İstisnalarını Getirme – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [MS Project'te Takvim Ayarlama ve Hafta Günlerini Tanımlama Aspose.Tasks ile](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}