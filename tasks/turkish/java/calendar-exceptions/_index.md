---
date: 2026-08-18
description: Aspose.Tasks ile Java projelerinde özel takvim istisnalarını zahmetsizce
  oluşturun, MS Project takvimini entegre edin ve takvim istisnalarını yönetin, tanımlayın,
  işleyin ve alın. Proje iş akışlarını kolaylaştırarak verimli proje yönetimi sağlayın.
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
lastmod: 2026-08-18
linktitle: Takvim İstisnaları
og_description: Aspose.Tasks kullanarak Java'da takvim istisnalarını oluşturmayı,
  proje takvimini yönetmeyi ve çalışılmayan günleri ayarlamayı öğrenin. Geliştiriciler
  için hızlı bir rehber.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Aspose.Tasks for Java ile takvim istisnaları nasıl oluşturulur
schemas:
- author: Aspose
  dateModified: '2026-08-18'
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

# Java için Aspose.Tasks ile takvim istisnaları nasıl oluşturulur

## Giriş

`Aspose.Tasks` bir Java kütüphanesidir ve Microsoft Project dosyalarının programlı olarak oluşturulmasını, manipüle edilmesini ve dönüştürülmesini sağlar. Bu öğreticide **takvim istisnaları oluşturmayı** öğreneceksiniz—projelerin varsayılan takvimini geçersiz kılan özel çalışılmayan dönemler. Çalışma ve çalışılmayan günler üzerinde kesin kontrol, doğru takvim tahmini, kaynak tahsisi ve bölgesel tatillere uyum için gereklidir. Kılavuzun sonunda **MS Project takvimini** Java uygulamanıza entegre etmeyi ve istisnalarını alıp değiştirmeyi de öğreneceksiniz.

## Hızlı cevaplar
- **Ne elde edebilirim?** Java projelerinde özel takvim istisnalarını oluşturma, değiştirme ve alma.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java (en son kararlı sürüm).  
- **Lisans gerekir mi?** Evet, üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **MS Project dosyalarıyla çalışabilir miyim?** Kesinlikle – MS Project takvim verilerini içe aktarabilir, düzenleyebilir ve dışa aktarabilirsiniz.  
- **Herhangi bir özel kurulum gerekli mi?** Sadece Aspose.Tasks JAR dosyasını sınıf yolunuza ekleyin ve ilgili sınıfları içe aktarın.

## Aspose.Tasks for Java’da özel takvim istisnaları nasıl oluşturulur?

`Project` sınıfı bir Microsoft Project dosyasını temsil eder ve içeriğine erişim sağlar. `Calendar` nesnesi projenin çalışma ve çalışılmayan zamanlarını tanımlar. `addException()` yöntemi takvime yeni bir takvim istisnası ekler.

Hedef projeyi `Project project = new Project("example.mpp")` ile yükleyin, `Calendar` nesnesini alın ve istenen tarih aralığı ve çalışma zamanı ayarlarıyla `addException()` çağırın. Bu iki adımlı desen, yeni bir istisnayı anında oluşturur ve projeyi kaydettiğinizde kalıcı hâle getirir. Yinelenen tatiller için, kaydetmeden önce istisna üzerinde `RecurrencePattern` yapılandırın.

Bu şekilde takvim istisnaları oluşturmak, **çalışılmayan günleri** tek tek, tek seferlik kapanışlar ya da yıllık tatiller olsun, kesin olarak ayarlamanızı sağlar. İstisna eklendikten sonra `project.save("updated.mpp")` çağırarak değişiklikleri diske yazabilirsiniz.

### Adımların genel görünümü
1. Proje dosyasını yükleyin.  
2. `Calendar` örneğini alın veya oluşturun.  
3. İstisnanın tarih aralığını ve çalışma zamanını tanımlayın.  
4. (İsteğe bağlı) Yıllık tatiller için yinelenmeyi yapılandırın.  
5. Projeyi kaydedin.

## Aspose.Tasks’te takvim istisnalarını yönetin

[Java için Aspose.Tasks’te takvim istisnalarını ekleme ve kaldırma konusunda verimli bir şekilde nasıl öğrenilir](./add-remove/). Proje yönetiminde esneklik anahtardır. Aspose.Tasks, takvim istisnalarını zahmetsizce yönetmenizi sağlar ve proje zaman çizelgelerinde dinamik ayarlamalara imkan tanır. Bu öğretici, süreci verimli bir şekilde kavramanız için adım adım bir rehber sunar. Proje yönetimi iş akışlarınızı kolayca nasıl geliştirebileceğinizi keşfedin.

## Aspose.Tasks ile takvim istisnaları için hafta içi günlerini tanımlayın

[Java projelerinde takvim istisnaları için hafta içi günlerini tanımlama sanatını Aspose.Tasks kullanarak öğrenin](./define-weekdays/). Doğru proje zamanlaması, ayrıntılara titiz bir dikkat gerektirir. Aspose.Tasks ile takvim istisnaları için hafta içi günlerini kesin olarak tanımlayabilir, projelerinizin belirli zaman çizelgeleriyle sorunsuz uyum sağlamasını garantileyebilirsiniz. Bu öğretici, zamanlamayı optimize etmeniz için gerekli bilgileri sunar ve proje zaman çizelgeleri üzerinde kontrol sağlar.

## Aspose.Tasks kullanarak takvim istisnalarındaki oluşumları yönetin

[Java projelerinde takvim istisnalarını etkili bir şekilde yönetin](./handle-occurrences/) Aspose.Tasks for Java ile. Proje yönetimi dinamik bir süreçtir ve genellikle beklenmeyen olaylara uyum sağlamak için ayarlamalar gerektirir. Aspose.Tasks, takvim istisnalarını etkili bir şekilde yönetmenizi sağlar ve proje yönetimine akıcı bir yaklaşım sunar. Bu detaylı öğreticide proje belirsizliklerini kolaylıkla yönetme sanatını öğrenin.

## Aspose.Tasks ile takvim istisnalarını alın

[Java için Aspose.Tasks kullanarak MS Project’ten takvim istisnalarını nasıl alacağınızı öğrenin](./retrieve/). Takvim istisnalarını proje yönetimi sürecinize sorunsuz bir şekilde entegre edin. Bu öğretici, takvim istisnalarını almanın adım adım sürecini size gösterir ve projelerinizde sorunsuz ve verimli bir entegrasyon sağlar. Aspose.Tasks’in gücünü kullanarak proje yönetimi yeteneklerinizi artırın.

## MS Project takvimini Aspose.Tasks ile nasıl entegre ederim?

`Project` sınıfı bir Microsoft Project dosyasını yükler ve takvimlerini ve diğer proje verilerini ortaya çıkarır. Mevcut bir MS Project dosyasını `new Project("source.mpp")` ile içe aktarın; kütüphane varsayılan takvimini ve tüm özel istisnaları otomatik olarak yükler. Daha sonra bu istisnaları okuyabilir, değiştirebilir veya birleştirebilir ve projeyi diske kaydetmeden önce kaydedebilirsiniz. Bu yaklaşım, **MS Project takvimini** manuel olarak MS Project arayüzünde düzenlemeden programlı olarak değiştirmenizi sağlar.

## Yaygın kullanım senaryoları
- **Tatil planlaması** – Ulusal tatilleri birden fazla projede çalışılmayan günler olarak tanımlayın.  
- **Vardiya çalışması** – Standart dışı programlarda çalışan ekipler için özel çalışma haftaları oluşturun.  
- **Proje aşaması kısıtlaması** – Bakım pencereleri gibi hiçbir işin planlanmaması gereken dönemleri engelleyin.  
- **Eski sistem geçişi** – Eski MS Project dosyalarından takvimleri içe aktarın ve programlı olarak ayarlayın.

## İpuçları ve en iyi uygulamalar
- **Pro ipucu:** Çift kayıtları önlemek için yeni istisnalar eklemeden önce mevcut takvimi her zaman alın.  
- **Uyarı:** Görevlerle zaten ilişkilendirilmiş bir takvimi değiştirmek görev tarihlerini kaydırabilir; değişikliklerden sonra takvimi yeniden hesaplayın.  
- **Performans:** Dosya I/O yükünü azaltmak için bir işlemde birden fazla istisna güncellemesini toplu olarak yapın. Aspose.Tasks, tüm belgeyi belleğe yüklemeden 500 MB’a kadar dosyaları işler ve tipik sunucu donanımında saniyede 50+ takvim‑ile ilgili API çağrısı gerçekleştirir.

## Takvim istisnaları öğreticileri
### [Aspose.Tasks’te Takvim İstisnalarını Yönetin](./add-remove/)
Java için Aspose.Tasks’te takvim istisnalarını ekleme ve kaldırma konusunda verimli bir şekilde nasıl yapılacağını öğrenin. Proje yönetimi iş akışlarını zahmetsizce geliştirin.
### [Aspose.Tasks ile Takvim İstisnaları için Hafta İçi Günlerini Tanımlayın](./define-weekdays/)
Aspose.Tasks kullanarak Java projelerinde takvim istisnaları için hafta içi günlerini nasıl tanımlayacağınızı öğrenin ve doğru proje zamanlaması sağlayın.
### [Aspose.Tasks kullanarak Takvim İstisnalarındaki Oluşumları Yönetin](./handle-occurrences/)
Java projelerinde takvim istisnalarını etkili bir şekilde nasıl yöneteceğinizi Aspose.Tasks for Java ile öğrenin. Proje yönetimi sürecinizi şimdi akıcı hâle getirin.
### [Aspose.Tasks ile Takvim İstisnalarını Alın](./retrieve/)
Aspose.Tasks for Java kullanarak MS Project’ten takvim istisnalarını nasıl alacağınızı öğrenin. Sorunsuz entegrasyon için adım adım öğretici.

## Sıkça Sorulan Sorular

**Q:** Proje zaten yayınlandıktan sonra takvim istisnalarını değiştirebilir miyim?  
**A:** Evet. Takvimi güncellemek için ekle‑kaldır ve hafta‑içi‑günleri API’lerini kullanın, ardından proje dosyasını yeniden kaydedin.

**Q:** Aspose.Tasks yinelenen istisnaları (ör. her ayın ilk Pazartesi’si) destekliyor mu?  
**A:** Kesinlikle. “Oluşumları yönet” öğreticisi, yinelenen desenlerin nasıl ayarlanacağını kapsar.

**Q:** Özel takvimimin projedeki tüm görevler tarafından kullanılmasını nasıl sağlarım?  
**A:** Takvimi projenin varsayılan takvimine atayın veya her görevin `Calendar` özelliğine açıkça ayarlayın.

**Q:** Birden fazla MS Project dosyasından takvimleri birleştirmek mümkün mü?  
**A:** Evet. Her takvimi alın, istisnalarını programlı olarak birleştirin ve ardından birleştirilmiş takvimi hedef projeye atayın.

**Q:** Bu özellikler için hangi Aspose.Tasks sürümü gereklidir?  
**A:** Tüm özellikler, Aspose.Tasks for Java’ın mevcut kararlı sürümünde (2025.x) mevcuttur.

---

**Son Güncelleme:** 2026-08-18  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Projeler İçin Takvim Oluşturma Aspose – Takvim İstisnaları için Hafta İçi Günlerini Tanımlama](/tasks/java/calendar-exceptions/define-weekdays/)
- [Aspose.Tasks ile Takvim İstisnalarını Alın – asp tasks java öğreticisi](/tasks/java/calendar-exceptions/retrieve/)
- [Java için Takvim İstisnası Oluşturma Aspose](/tasks/java/calendar-exceptions/add-remove/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}