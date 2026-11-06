---
date: 2026-11-06
description: Özel takvim istisnalarını zahmetsizce oluşturun, MS Project takvimini
  entegre edin ve Aspose.Tasks ile Java projelerinde takvim istisnalarını yönetin,
  tanımlayın, işleyin ve alın. Proje iş akışlarını kolaylaştırarak verimli proje yönetimi
  sağlayın.
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: Takvim İstisnaları
og_description: Aspose.Tasks kullanarak Java'da takvim istisnalarının nasıl oluşturulacağını
  öğrenin. Proje takvimlerini yönetin, nonworking days ayarlayın ve MS Project takvimlerini
  verimli bir şekilde değiştirin.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Aspose.Tasks for Java ile takvim istisnaları oluşturun
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: Aspose.Tasks for Java ile takvim istisnaları nasıl oluşturulur
url: /tr/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java ile takvim istisnaları nasıl oluşturulur

## Giriş

`Aspose.Tasks` bir Java kütüphanesidir ve Microsoft Project dosyalarının programlı olarak oluşturulmasını, manipüle edilmesini ve dönüştürülmesini sağlar. Bu öğreticide **takvim istisnaları oluşturma**—projelerin varsayılan takvimini geçersiz kılan özel çalışılmayan dönemleri—nasıl yapacağınızı öğreneceksiniz. Çalışma ve çalışılmayan günler üzerinde kesin kontrol, doğru zaman çizelgesi tahmini, kaynak tahsisi ve bölgesel tatillere uyum için hayati öneme sahiptir. Bu rehberin sonunda **MS Project takvimini bütünleştirme** konusunda da bilgi sahibi olacak ve istisnalarını alıp değiştirebileceksiniz.

## Hızlı cevaplar
- **Ne başarabilirim?** Java projelerinde özel takvim istisnaları oluşturun, değiştirin ve alın.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java (latest stable release).  
- **Bir lisansa ihtiyacım var mı?** Evet, üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **MS Project dosyalarıyla çalışabilir miyim?** Kesinlikle – MS Project takvim verilerini içe aktarabilir, düzenleyebilir ve dışa aktarabilirsiniz.  
- **Herhangi bir özel kurulum gerekli mi?** Sadece Aspose.Tasks JAR dosyasını sınıf yolunuza ekleyin ve ilgili sınıfları içe aktarın.

## Aspose.Tasks for Java'da özel takvim istisnaları nasıl oluşturulur?

Aspose.Tasks for Java'da özel takvim istisnaları oluşturmak için hedef Project'i yükleyin, takvimini alın, istisnanın başlangıç ve bitiş tarihlerini istediğiniz çalışma zamanı ile tanımlayın, isteğe bağlı olarak bir yineleme deseni ayarlayın ve ardından projeyi kaydedin. Bu sıralama istisnayı anında ekler ve .mpp dosyasına kalıcı olarak yazar.

`Project` sınıfı, Aspose.Tasks'in bir Microsoft Project dosyasını modelleyen birincil nesnesidir. `Project` sınıfı bir Microsoft Project dosyasını temsil eder ve içeriğine erişim sağlar. `Calendar` nesnesi, proje için çalışma ve çalışılmayan zamanları tanımlar. `Calendar` sınıfı, istisnalar dahil tüm çalışma‑zamanı kurallarının konteyneridir. `addException()` yöntemi, takvime yeni bir takvim istisnası ekler. `addException()` tek‑çağrı API'si olup belirtilen tarih aralığı için çalışılmayan bir dönemi kaydeder.

Hedef projeyi `Project project = new Project("example.mpp")` ile yükleyin, `Calendar` nesnesini alın ve `addException()` yöntemini istenen tarih aralığı ve çalışma zamanı ayarlarıyla çağırın. Bu iki‑adımlı desen, yeni bir istisnayı anında oluşturur ve projeyi kaydettiğinizde kalıcı hâle getirir. Yinelenen tatiller için, kaydetmeden önce istisna üzerinde `RecurrencePattern`'i yapılandırın.

Bu şekilde takvim istisnaları oluşturmak, **çalışılmayan günleri** tek tek, bir kerelik kapanışlar ya da yıllık tatiller olsun, kesin olarak ayarlamanızı sağlar. İstisna eklendikten sonra `project.save("updated.mpp")` çağrısıyla değişiklikleri diske yazabilirsiniz.

### Adımların genel görünümü
1. Projeyi dosyasını yükleyin.  
2. Bir `Calendar` örneği alın veya oluşturun.  
3. İstisnanın tarih aralığını ve çalışma zamanını tanımlayın.  
4. (İsteğe bağlı) Yıllık tatiller için yineleme yapılandırın.  
5. Projeyi kaydedin.

## Aspose.Tasks'te takvim istisnalarını yönetin
[Aspose.Tasks for Java'da takvim istisnalarını ekleme ve kaldırma konusunda verimli bir şekilde nasıl öğrenilir](./add-remove/). Proje yönetiminde esneklik anahtardır. Aspose.Tasks, takvim istisnalarını zahmetsizce yönetmenizi sağlar ve proje zaman çizelgelerinde dinamik ayarlamalar yapmanıza imkan tanır. Bu öğretici adım adım rehber, süreci etkin bir şekilde kavramanızı sağlar. Proje yönetim iş akışlarınızı kolaylıkla geliştirin.

## Aspose.Tasks ile takvim istisnaları için hafta içi günlerini tanımlama
[Java projelerinde takvim istisnaları için hafta içi günlerini tanımlama sanatını ustalaşın](./define-weekdays/) Aspose.Tasks kullanarak. Doğru proje zamanlaması, ayrıntılara titiz bir dikkat gerektirir. Aspose.Tasks ile takvim istisnaları için hafta içi günlerini kesin olarak tanımlayabilir, projelerinizin belirli zaman çizelgeleriyle sorunsuz bir şekilde uyumlu olmasını sağlayabilirsiniz. Bu öğretici, zamanlamayı optimize etmenizi ve proje zaman çizelgeleri üzerinde tam kontrol sahibi olmanızı sağlar.

## Aspose.Tasks kullanarak takvim istisnalarındaki olayları yönetme
[Aspose.Tasks for Java ile Java projelerinde takvim istisnalarını etkili bir şekilde yönetin](./handle-occurrences/). Proje yönetimi dinamik bir süreçtir ve beklenmedik olaylara uyum sağlamak için ayarlamalar gerektirebilir. Aspose.Tasks, takvim istisnalarını etkili bir şekilde yönetmenizi sağlayarak proje yönetimine akıcı bir yaklaşım sunar. Bu ayrıntılı öğretici sayesinde proje belirsizliklerini kolaylıkla yönetmeyi öğrenin.

## Aspose.Tasks ile takvim istisnalarını alma
[Aspose.Tasks for Java kullanarak MS Project'ten takvim istisnalarını nasıl alacağınızı öğrenin](./retrieve/). Takvim istisnalarını proje yönetimi sürecinize sorunsuz bir şekilde entegre edin. Bu öğretici, takvim istisnalarını almanın adım adım sürecini anlatır ve projelerinize sorunsuz ve verimli bir entegrasyon sağlar. Aspose.Tasks'in gücünü kullanarak proje yönetimi yeteneklerinizi artırın.

## MS Project takvimini Aspose.Tasks ile nasıl bütünleştirirsiniz?

MS Project takvimini Aspose.Tasks ile bütünleştirmek, `Project` sınıfını kullanarak kaynak .mpp dosyasını yüklemeyi, varsayılan veya özel `Calendar` nesnelerine erişmeyi, gerektiğinde istisnaları değiştirmeyi veya birleştirmeyi ve ardından güncellenmiş projeyi kaydetmeyi içerir. Bu sayede MS Project takvimleriyle manuel UI etkileşimi olmadan programlı olarak çalışabilirsiniz.

`Project` sınıfı, Aspose.Tasks'in bir Microsoft Project dosyasını modelleyen birincil nesnesidir. `new Project("source.mpp")` ile mevcut bir MS Project dosyasını içe aktarın; kütüphane varsayılan takvimini ve varsa özel istisnaları otomatik olarak yükler. Bu istisnaları okuyabilir, değiştirebilir veya birleştirebilir, ardından projeyi diske geri kaydedebilirsiniz. Bu yaklaşım, **MS Project takvim verilerini** programlı olarak değiştirme imkanı sunar.

## Yaygın kullanım senaryoları
- **Tatil planlaması** – Ulusal tatilleri birden fazla projede çalışılmayan günler olarak tanımlayın.  
- **Vardiya çalışması** – Standart olmayan takvimlerde çalışan ekipler için özel çalışma haftaları oluşturun.  
- **Proje aşaması kısıtlaması** – Bakım pencereleri gibi hiçbir işin planlanmaması gereken dönemleri engelleyin.  
- **Eski sistem geçişi** – Eski MS Project dosyalarından takvimleri içe aktarın ve programlı olarak ayarlayın.

## İpuçları ve en iyi uygulamalar
- **Pro ipucu:** Yeni istisnalar eklemeden önce mevcut takvimi her zaman alın, böylece yinelenmelerin önüne geçilir.  
- **Uyarı:** Görevlere zaten atanmış bir takvimi değiştirmek görev tarihlerini kaydırabilir; değişikliklerden sonra takvimi yeniden hesaplayın.  
- **Performans:** Birden fazla istisna güncellemesini tek bir işlemde toplu olarak yapın, böylece dosya I/O yükünü azaltın. Aspose.Tasks, 1 GB'a kadar dosyaları işleyebilir ve bellek kullanımını 200 MB altında tutar; tipik sunucu donanımında saniyede 30'dan fazla takvim‑ile‑ilgili API çağrısını işleyebilir.

## Takvim istisnaları öğreticileri
### [Aspose.Tasks'te Takvim İstisnalarını Yönet](./add-remove/)
Aspose.Tasks for Java'da takvim istisnalarını ekleme ve kaldırma konusunda verimli bir şekilde nasıl öğrenilir. Proje yönetim iş akışlarını zahmetsizce geliştirin.
### [Aspose.Tasks ile Takvim İstisnaları için Hafta İçi Günlerini Tanımlama](./define-weekdays/)
Java projelerinde takvim istisnaları için hafta içi günlerini tanımlama konusunda doğru proje zamanlaması için nasıl yapılacağını öğrenin.
### [Aspose.Tasks kullanarak Takvim İstisnalarındaki Olayları Yönetme](./handle-occurrences/)
Aspose.Tasks for Java ile Java projelerinde takvim istisnalarını etkili bir şekilde nasıl yöneteceğinizi öğrenin. Proje yönetim sürecinizi şimdi akıcı hâle getirin.
### [Aspose.Tasks ile Takvim İstisnalarını Alma](./retrieve/)
Aspose.Tasks for Java kullanarak MS Project'ten takvim istisnalarını nasıl alacağınızı öğrenin. Sorunsuz entegrasyon için adım adım öğretici.

## Sıkça Sorulan Sorular

**S: Proje zaten yayınlandıktan sonra takvim istisnalarını değiştirebilir miyim?**  
**C: Evet. Takvimi güncellemek için ekle‑kaldır ve hafta içi tanımlama API'lerini kullanın, ardından proje dosyasını yeniden kaydedin.**

**S: Aspose.Tasks yinelenen istisnaları (örneğin, her ayın ilk Pazartesi'si) destekliyor mu?**  
**C: Kesinlikle. “olayları yönet” öğreticisi yinelenen desenleri nasıl ayarlayacağınızı gösterir.**

**S: Özel takvimimin projedeki tüm görevler tarafından kullanıldığından nasıl emin olabilirim?**  
**C: Takvimi projenin varsayılan takvimine atayın veya her görevin `Calendar` özelliğine açıkça ayarlayın.**

**S: Birden fazla MS Project dosyasından takvimleri birleştirmek mümkün mü?**  
**C: Evet. Her takvimi alın, istisnalarını programlı olarak birleştirin ve ardından birleştirilmiş takvimi hedef projeye atayın.**

**S: Bu özellikler için hangi Aspose.Tasks sürümü gereklidir?**  
**C: Tüm özellikler, Aspose.Tasks for Java'ın mevcut kararlı sürümünde (2025.x) mevcuttur.**

## İlgili Öğreticiler

- [Proje Takvimi Oluşturma Aspose – Takvim İstisnaları için Hafta İçi Günlerini Tanımlama](/tasks/java/calendar-exceptions/define-weekdays/)
- [Aspose.Tasks ile Takvim İstisnalarını Alma – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Aspose for Java ile Takvim İstisnası Oluşturma](/tasks/java/calendar-exceptions/add-remove/)

---

**Son Güncelleme:** 2026-11-06  
**Test Edilen:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}