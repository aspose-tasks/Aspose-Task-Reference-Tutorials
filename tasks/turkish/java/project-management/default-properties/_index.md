---
date: 2026-05-31
description: Java'da bir MPP dosyasını nasıl yükleyeceğinizi ve Aspose.Tasks ile proje
  özelliklerini nasıl yöneteceğinizi öğrenin; varsayılan özelliklerin ayarlanması
  ve formatların dönüştürülmesi dahil.
keywords:
- manage project properties
- set default properties
- aspose tasks java
- change task start date
- convert mpp to pdf
linktitle: Aspose.Tasks'te Varsayılan Proje Özelliklerini Yönetme
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to load an MPP file in Java and manage project properties
    with Aspose.Tasks, including setting default properties and converting formats.
  headline: Load MPP File Java – Manage Project Properties with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks is also available for .NET, Python, and other platforms.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely! It scales from small personal projects to large‑scale enterprise
      portfolios.
    question: Is Aspose.Tasks suitable for both personal and enterprise use?
  - answer: Yes, you can find assistance and community support on the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks offer customer support?
  - answer: Of course! You can avail of a free trial from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can get a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Java'da MPP Dosyası Yükleme – Aspose.Tasks ile Proje Özelliklerini Yönetme
url: /tr/java/project-management/default-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP Dosyasını Java’da Yükle – Aspose.Tasks ile Proje Özelliklerini Yönet

## Giriş
Java’da **MPP dosyası yükleme** projelerine ihtiyacınız varsa ve varsayılan proje özelliklerini programlı olarak yönetmek istiyorsanız, Aspose.Tasks for Java bunu zahmetsiz hâle getirir. Bu öğreticide, mevcut bir Microsoft Project dosyasını yüklemekten varsayılan görev ve kaynak ayarlarını özelleştirmeye ve sonunda güncellenmiş projeyi kaydetmeye kadar tüm süreci adım adım göstereceğiz. Sonunda, herhangi bir Java tabanlı proje yönetimi çözümüne ekleyebileceğiniz net, yeniden kullanılabilir bir desen elde edeceksiniz.

## Hızlı Yanıtlar
- **“load MPP file Java” ne anlama geliyor?** Java kodu ile Aspose.Tasks aracılığıyla bir Microsoft Project (.mpp) dosyasını okumak anlamına gelir.  
- **Hangi kütüphane bunu yönetir?** Aspose.Tasks for Java, proje manipülasyonu için tam özellikli bir API sağlar.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim kullanımı için ticari bir lisans gerekir.  
- **Varsayılan görev başlangıç tarihlerini değiştirebilir miyim?** Evet—varsayılanları ayarlamak için `Prj.DEFAULT_START_TIME` ve ilgili özellikleri kullanın.  
- **Hangi çıktı formatları destekleniyor?** Yerel MPP dışında XML, PDF, HTML ve 20'den fazla başka formata kaydedebilirsiniz.

## “load MPP file Java” nedir?
Java’da bir MPP dosyasını yüklemek, ikili Microsoft Project formatını ayrıştırmak için bir kütüphane kullanmak ve nesnelerini (görevler, kaynaklar, takvimler) Java sınıfları olarak ortaya çıkarmak anlamına gelir. Bu sayede Microsoft Project’i hiç açmadan proje verilerini okuyabilir, değiştirebilir ve kaydedebilirsiniz.

## Neden Aspose.Tasks for Java kullanmalı?
Aspose.Tasks, Microsoft Project kurulumu olmadan proje özelliklerini yönetmenizi sağlar, **50+ giriş ve çıkış formatını** destekler ve **10.000'e kadar görev** içeren projeleri bellek kullanımını 200 MB'nin altında tutarak işleyebilir. JDK’yı destekleyen herhangi bir işletim sisteminde çalışır, bu da sunucu‑tarafı otomasyon için idealdir.

## Önkoşullar

### 1. Java Development Kit (JDK)
- JDK 11 veya daha yenisini kurun.  
- İndirmek için [buraya](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) tıklayın.

### 2. Aspose.Tasks for Java Kütüphanesi
- En son Aspose.Tasks JAR dosyasını indirin ve projenizin sınıf yoluna ekleyin.  
- Almak için [web sitesine](https://releases.aspose.com/tasks/java/) gidin.

## Paketleri İçe Aktarma
İçe aktarma ifadeleri, temel Aspose.Tasks sınıflarını Java kaynak dosyanıza getirir.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Java’da MPP dosyasını nasıl yükler ve varsayılan özellikleri ayarlarsınız?
`Project` sınıfı bir Microsoft Project dosyasını temsil eder ve görevlerine, kaynaklarına ve ayarlarına erişim sağlar. Projeyi yükleyin, varsayılanlarını inceleyin, değiştirin ve sonucu kaydedin—hepsi birkaç basit satırda. Bu yaklaşım, takvim varsayılanları, takvim ayarları ve maliyet birikim kuralları üzerinde tam kontrol sağlar ve oluşturulan tüm dosyalarda tutarlı proje standartlarını uygulamanıza olanak tanır.

### Adım 1: Proje Dosyasını Yükle
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Adım 2: Varsayılan Özellikleri Görüntüle
```java
// Display default properties
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```

### Adım 3: Varsayılan Özellikleri Ayarla
```java
// Set default properties
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```

### Adım 4: Projeyi XML Formatında Kaydet
```java
// Save the project to XML format
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```

### Adım 5: Sonucu Görüntüle
```java
// Display result of conversion.
System.out.println("Process completed Successfully");
```

Bu adımları izleyerek **Java’da bir MPP dosyasını başarıyla yüklemiş**, varsayılan ayarlarını incelemiş, özelleştirmiş ve güncellenmiş projeyi kaydetmiş olursunuz.

## Yaygın Sorunlar ve İpuçları
- **Dosya bulunamadı** – `dataDir`'in bir yol ayırıcı (`/` veya `\\`) ile bittiğini doğrulayın.  
- **Lisans uygulanmadı** – Deneme filigranı görürseniz, projeyi yüklemeden önce lisans dosyanızı ekleyin: `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Tarih işleme** – `java.util.Calendar` veya daha yeni `java.time` API'sini kullanın (atanmadan önce `java.util.Date`'e dönüştürün).

## Sıkça Sorulan Sorular

**S: Aspose.Tasks'i diğer programlama dilleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks .NET, Python ve diğer platformlar için de mevcuttur.

**S: Aspose.Tasks kişisel ve kurumsal kullanım için uygun mu?**  
C: Kesinlikle! Küçük kişisel projelerden büyük ölçekli kurumsal portföylere kadar ölçeklenebilir.

**S: Aspose.Tasks müşteri desteği sağlıyor mu?**  
C: Evet, [Aspose.Tasks forumunda](https://forum.aspose.com/c/tasks/15) yardım ve topluluk desteği bulabilirsiniz.

**S: Aspose.Tasks'i satın almadan deneyebilir miyim?**  
C: Tabii ki! [Web sitesinden](https://releases.aspose.com/) ücretsiz deneme alabilirsiniz.

**S: Aspose.Tasks için geçici bir lisans nasıl alabilirim?**  
C: Test ve değerlendirme amaçları için [satın alma sayfasından](https://purchase.aspose.com/temporary-license/) geçici bir lisans edinebilirsiniz.

## Sonuç
Bu öğreticide **Java’da MPP dosyası yükleme** projelerini nasıl yapacağınızı, varsayılan özelliklerini okuyup değiştirdiğinizi ve değişiklikleri Aspose.Tasks for Java kullanarak kaydettiğinizi ele aldık. Bu teknikleri uygulamalarınıza entegre etmek, proje yönetimi görevlerini otomatikleştirmenize, tutarlı varsayılanları uygulamanıza ve manuel çabayı azaltmanıza yardımcı olacaktır.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
- [How to Set Project Calendar with Aspose.Tasks for Java](/tasks/java/calendars/properties/)
- [How to Create MPP File – Create & Save Empty Project in MPP Format with Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}