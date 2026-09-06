---
date: 2026-08-13
description: Takvime tatilleri eklemeyi, takvimi bir projeye atamayı ve Aspose.Tasks
  for Java kullanarak MS Project dosyasını MPP olarak kaydetmeyi öğrenin.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Aspose.Tasks'te takvimi MPP formatına güncelleyin
og_description: Takvime tatilleri ekleyin, takvimi bir projeye atayın ve Aspose.Tasks
  for Java kullanarak takvimi MPP'ye dönüştürün. Adım adım otomasyonu öğrenin.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Takvime tatilleri ekleyin ve Aspose.Tasks ile MPP olarak kaydedin
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Takvime tatilleri ekleyin ve Aspose.Tasks ile MPP olarak kaydedin
url: /tr/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Takvime tatil ekleyin ve Aspose.Tasks ile MPP olarak kaydedin

## Giriş

Modern proje yönetiminde, genellikle **add holidays to calendar** dosyalarına tatil eklemeniz, bir **MS Project calendar** oluşturmanız ve ardından takvimi yerel MPP formatında paylaşmanız gerekir. Birden fazla kaynaktan zaman çizelgelerini birleştiriyor ya da eski verileri taşıyor olun, takvimi programlı olarak oluşturmak manuel hataları ortadan kaldırır ve teslimatı hızlandırır. Bu öğreticide, MS Project içinde bir takvim oluşturma, tatillerle özelleştirme, **assign calendar to project** ve sonunda Aspose.Tasks Java API kullanarak **convert project to MPP** işlemlerinin tüm sürecini adım adım gösteriyoruz.

## Hızlı Yanıtlar
- **Bu öğretici neyi kapsıyor?** Takvime tatil ekleme, onu bir projeye atama ve sonucu Aspose.Tasks for Java ile MPP dosyası olarak kaydetme.  
- **Bir lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gereklidir.  
- **Hangi Java sürümü gereklidir?** Java 8 veya üzeri (JDK 8+).  
- **Takvimi özelleştirebilir miyim?** Evet – çalışma saatleri, istisnalar ve tatiller ekleyebilirsiniz.  
- **Uygulama ne kadar sürer?** Temel bir takvim için yaklaşık 10‑15 dakika.  

## “create calendar MS Project” nedir?

Bir calendar MS Project oluşturmak, bir Microsoft Project dosyasında görev zamanlamasını yönlendiren çalışma günlerini, saatlerini ve istisnalarını tanımlamak anlamına gelir. Aspose.Tasks kullanarak bu takvimi programlı olarak oluşturabilir, tatilleri ayarlayabilir ve MS Project kullanıcı arayüzünü açmadan bir projeye gömebilirsiniz.

## Bu görev için neden Aspose.Tasks kullanılmalı?

Aspose.Tasks'i kullanmalısınız çünkü tam Java uyumluluğu sağlar, Microsoft Office gerektirmez ve koddan doğrudan yerel MPP dosyaları oluşturup kaydetmenize olanak tanır. Kütüphane tüm takvim özelliklerini destekler, herhangi bir sunucu ortamında çalışır ve projeleri 10.000 göreve kadar bir saniyeden kısa sürede işler.

## Önkoşullar

1. **Java Development Kit (JDK) 8+** – `java -version` komutunun 1.8 veya daha yeni bir sürüm gösterdiğinden emin olun.  
2. **Aspose.Tasks for Java** – en yeni JAR dosyasını [Aspose web sitesinden](https://releases.aspose.com/tasks/java/) indirin.  
3. **IDE** – IntelliJ IDEA, Eclipse veya tercih ettiğiniz herhangi bir editör.  
4. **Temel Java bilgisi** – sınıflar, metodlar ve dosya I/O konularına aşina olmak.  

## Takvime tatil ekleme

Tatilleri eklemek için yeni bir `Calendar` nesnesi oluşturur, onun `Exceptions` koleksiyonunu alır ve her tatil tarihi için `DateException` girdileri eklersiniz. `DateException`, takvimde tek bir çalışmayan tarih veya aralığı temsil eder. Aspose.Tasks bu tarihleri çalışmayan günler olarak kabul eder ve görevlerin tanımlı tatillerin etrafında planlanmasını sağlar.

### Adım 1: Gerekli paketleri içe aktar

İlk olarak, Aspose.Tasks sınıflarını ve Java yardımcı programlarını kapsam içine getirin.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Adım 2: Veri dizinini ayarla

Giriş şablonunuzun ve çıktı dosyalarınızın nerede bulunacağını tanımlayın. Yer tutucuyu makinenizdeki gerçek yol ile değiştirin.

```java
String dataDir = "Your Data Directory";
```

### Adım 3: Giriş ve çıkış dosya adlarını tanımla

Mevcut bir MPP dosyasını (veya boş bir projeyi) yükleyecek ve sonucu yeni bir dosyaya yazacağız.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Adım 4: Projeyi yükle ve yeni bir takvim ekle

`Project` sınıfı, bellekte bir MS Project dosyasını temsil eder ve takvimlerine, görevlerine ve kaynaklarına erişim sağlar.

Kaynak dosyadan bir `Project` örneği oluşturun ve **“Calendar 1”** adlı bir takvim ekleyin.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Adım 5: Takvimi özelleştir (isteğe bağlı)

`Calendar` nesnesi, bir proje takvimi için çalışma günlerini, saatlerini ve istisnalarını tanımlar.

Belirli çalışma saatlerine, tatillere veya istisnalara ihtiyacınız varsa, kendi yardımcı metodunuzu çağırın. Örnek, yer tutucu olarak `GetTestCalendar` kullanır.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **İpucu:** Her haftanın günü için çalışma saatlerini ayarlamak üzere `cal1.getWeekDays()`'i doğrudan manipüle edebilir veya `cal1.getExceptions()`'ı kullanarak **add holidays to calendar** yapabilirsiniz.

### Adım 6: Takvimi projeye ata

Projeye, tüm zamanlama hesaplamaları için yeni oluşturulan takvimi kullanmasını söyleyin.

```java
project.set(Prj.CALENDAR, cal1);
```

### Adım 7: Projeyi MPP olarak kaydet

`SaveFileFormat` enum'ı çıktı formatını belirtir; `Mpp` yerel Microsoft Project formatını gösterir.

Şimdi `SaveFileFormat.Mpp` seçeneğiyle kaydederek **convert project to MPP** yapın.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Adım 8: Başarılı tamamlamayı doğrula

Basit bir konsol mesajı, işlemin hatasız tamamlandığını bildirir.

```java
System.out.println("Process completed Successfully");
```

## Yaygın kullanım senaryoları

- **Tekrarlayan projeler için otomatik takvim oluşturma** (ör. haftalık sprintler).  
- **Eski CSV veya Excel takvimlerini** tam özellikli bir MS Project dosyasına taşıma.  
- **Sunucu tarafı raporlama**; bir web servisi talep üzerine MPP dosyası döndürür.  

## Sorun Giderme ve yaygın tuzaklar

| Sorun | Neden | Çözüm |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` points to a non‑existent folder | Dizinin mevcut olduğundan emin olun veya program aracılığıyla oluşturun. |
| Calendar not applied to tasks | Tasks still reference the default calendar | `Prj.CALENDAR` ayarlandıktan sonra, görevlerin `Task.CALENDAR` değerleri daha önce geçersiz kılındıysa onları da güncelleyin. |
| Output file is 0 KB | Missing write permissions | JVM'yi uygun dosya sistemi izinleriyle çalıştırın veya yazılabilir bir yol seçin. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java farklı MS Project sürümleriyle uyumlu mu?**  
A: Evet, Aspose.Tasks Project 2007'den Project 2024'e kadar tüm Microsoft Project dosya formatlarını destekler, 10'dan fazla sürümü kapsar.

**S: Takvimleri belirli proje gereksinimlerine göre özelleştirebilir miyim?**  
A: Kesinlikle. Çalışma günlerini tanımlayabilir, özel çalışma haftaları ayarlayabilir, tatiller ekleyebilir ve tek bir proje dosyasında birden fazla takvim oluşturabilirsiniz.

**S: Aspose.Tasks for Java sorun giderme ve destek sunuyor mu?**  
A: Evet, Aspose.Tasks topluluk forumundan yardım alabilirsiniz [Aspose.Tasks topluluk forumu](https://forum.aspose.com/c/tasks/15).

**S: Aspose.Tasks for Java için ücretsiz deneme sürümü mevcut mu?**  
A: Evet, tam işlevsel bir ücretsiz deneme sürümü mevcuttur [Aspose.Tasks ücretsiz deneme](https://releases.aspose.com/).

**S: Aspose.Tasks for Java için geçici lisans nasıl alabilirim?**  
A: Geçici lisanslar Aspose web sitesi üzerinden talep edilebilir [Aspose geçici lisans talebi](https://purchase.aspose.com/temporary-license/).

---

**Son Güncelleme:** 2026-08-13  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Tasks for Java ile projeye takvim ekleme](/tasks/java/calendars/create/)
- [MS Project Takvimlerinde Hafta Günlerini Tanımlama – Aspose.Tasks Java](/tasks/java/calendars/)
- [Aspose.Tasks for Java ile Özel Takvim İstisnaları Oluşturma](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}