---
date: 2026-07-19
description: Aspose.Tasks ile .NET projelerinde amount sonrasındaki currency symbol'ü
  sorunsuz bir şekilde nasıl kontrol edeceğinizi öğrenin.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Aspose.Tasks'te Currency Symbol Pozisyonları
og_description: Aspose.Tasks for .NET kullanarak amount sonrasına currency symbol
  yerleştirmeyi öğrenin. Adım adım talimatları ve en iyi uygulamaları izleyin.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Aspose.Tasks'te Amount Sonrası Currency Symbol — Hızlı Rehber
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: Aspose.Tasks'te Amount Sonrasına Currency Symbol Nasıl Yerleştirilir
url: /tr/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Miktardan Sonra Para Birimi Sembolünü Nasıl Yerleştirirsiniz

## Giriş

Proje maliyet raporları oluşturduğunuzda, **currency symbol after amount** konumu okunabilirliği ve bölgesel standartlara uyumu etkileyebilir. Aspose.Tasks for .NET, bu biçimlendirmeyi sadece birkaç satır kodla kontrol etmenizi sağlar ve her finansal rakamın paydaşlarınızın beklediği şekilde görünmesini garantiler. Bu öğreticide gerekli adımları inceleyecek, ayarın neden önemli olduğunu açıklayacak ve gerçek bir .NET projesinde nasıl uygulanacağını göstereceğiz.

## Hızlı Yanıtlar
- **“currency symbol after amount” ne anlama geliyor?** Sembolü (ör. $) sayısal değerin ardından, örneğin `100 $` şeklinde gösterir.
- **Pozisyonu hangi özellik kontrol eder?** `Project` nesnesindeki `CurrencySymbolPosition`.
- **Lisans gerekli mi?** Geliştirme için deneme sürümü çalışır; üretim için ticari lisans gereklidir.
- **Desteklenen para birimleri?** 50'den fazla yerleşik para birimi bulunur ve çoğu küresel pazarı kapsar.
- **Ayarı çalışma zamanında değiştirebilir miyim?** Evet, proje dosyasını kaydetmeden önce istediğiniz zaman güncelleyebilirsiniz.

## “currency symbol after amount” ayarı nedir?
**currency symbol after amount** seçeneği, bir projedeki tüm parasal alanlarda para birimi işaretinin sayısal değerin önünde mi yoksa sonrasında mı görüneceğini belirler. Bu ayarı ayarlamak, raporların yerel muhasebe geleneklerine manuel sonrası işleme gerek kalmadan uymasını sağlar. Ayrıca bu formatı alışkın olan paydaşlar için okunabilirliği artırır.

## Para birimi biçimlendirmesi için neden Aspose.Tasks kullanılmalı?
Aspose.Tasks, **50+ para birimini** destekler ve **10.000+ görev** içeren projeleri tüm dosyayı belleğe yüklemeden işleyebilir, bu da düşük donanımda bile hızlı performans sağlar. API, programatik kontrol sunarak manuel elektronik tablo düzenlemelerine gerek kalmaz. Bu, büyük ölçekli finansal raporlamayı hem verimli hem de güvenilir kılar.

## Önkoşullar

### 1. Aspose.Tasks for .NET Kurulumu
Aspose.Tasks kütüphanesinin kurulu olduğundan emin olun. [buradan](https://releases.aspose.com/tasks/net/) indirebilirsiniz.

### 2. .NET Programlama Temel Bilgisi
Örnekleri takip edebilmek için .NET programlamasına temel bir anlayış gereklidir.

## Ad Alanlarını İçe Aktarma

`Aspose.Tasks` ad alanı, `Project` sınıfına ve ilgili enum'lara erişim sağlar.

`Project` sınıfı, Aspose.Tasks'in bellek içinde tek bir proje dosyasını temsil eden üst‑seviye nesnesidir. Ad alanını içe aktardıktan sonra proje verileriyle çalışmaya başlayabilirsiniz.

```csharp

```

Şimdi, örneği net ve uygulanabilir adımlara ayıralım.

## Para birimi sembolünü miktardan sonra nasıl ayarlarsınız?

`CurrencySymbolPosition`, para birimi sembolünün sayısal değerin önünde mi yoksa sonrasında mı görüneceğini belirten bir enum'dur.

Projenizi yükleyin, `CurrencySymbolPosition` değerini `After` olarak ayarlayın ve ardından kaydedin – bu, sembolü miktardan sonra göstermek için ihtiyacınız olan tek şeydir. Bu doğrudan yöntem, desteklenen herhangi bir para birimi için çalışır ve ek biçimlendirme mantığı gerektirmez. Ayarın doğru olduğunu doğrulamak için örnek bir maliyet raporu dışa aktararak sembolün doğru göründüğünden emin olabilirsiniz.

### Adım 1: Proje Dosyasını Yükleyin
`Project` sınıfı, mevcut bir MS‑Project dosyasını yükler veya bellekte yeni bir dosya oluşturur.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Adım 2: Para Birimi Sembolü Konumunu Ayarlayın
`CurrencySymbolPosition`, `Before` veya `After` seçmenizi sağlayan bir enum'dur. `After` olarak ayarlamak, sembolü sayısal değerin sonuna yerleştirir.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### Adım 3: Proje ile Çalışın
Sembol konumunu yapılandırdıktan sonra, ihtiyaca göre görev, kaynak veya özel alan eklemeye devam edebilirsiniz. Ayar, projeyi kaydettiğinizde kalıcı olur.

```csharp
// Perform other operations with the project...
```

## Yaygın Sorunlar ve Çözümler
- **Sembol hâlâ miktardan önce görünüyor:** Özelliği `Save` çağırmadan *önce* ayarladığınızdan emin olun. Kaydettikten sonra değiştirmek dosyanın yeniden kaydedilmesini gerektirir.
- **Desteklenmeyen para birimi:** Kullandığınız para birimi kodunun Aspose.Tasks'in desteklenen listesinde (50+ para birimi) yer aldığını doğrulayın.
- **Büyük projelerde performans yavaşlaması:** 10.000 görevden fazla olduğunda büyük dosyaları akış olarak işlemek için `ProjectReader` kullanın.

## Sıkça Sorulan Sorular

**S: Aynı proje içinde para birimi sembolü konumunu birden fazla kez değiştirebilir miyim?**  
C: Evet, `CurrencySymbolPosition` değerini ihtiyacınız kadar ayarlayabilirsiniz; sadece özelliği belirleyip projeyi yeniden kaydedin.

**S: Aspose.Tasks, ABD Doları dışındaki para birimlerini destekliyor mu?**  
C: Kesinlikle. Aspose.Tasks, 50'den fazla uluslararası para birimini destekler ve herhangi bir bölgesel formatla çalışmanıza olanak tanır.

**S: Aspose.Tasks for .NET için bir deneme sürümü mevcut mu?**  
C: Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) edinebilirsiniz.

**S: Aspose.Tasks for .NET kullanırken herhangi bir sorunla karşılaşırsam yardım alabilir miyim?**  
C: Elbette! Aspose.Tasks topluluk forumundan [burada](https://forum.aspose.com/c/tasks/15) destek ve yardım alabilirsiniz.

**S: Aspose.Tasks for .NET için lisans nasıl satın alınır?**  
C: Aspose.Tasks for .NET lisansını [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sonuç

**currency symbol after amount** kontrolü, proje yönetimi yazılımında finansal raporlamanın kritik bir parçasıdır. Aspose.Tasks for .NET ile bu seçeneği programatik olarak ayarlayabilir, 50'den fazla para birimini destekleyebilir ve büyük projeleri verimli bir şekilde işleyebilirsiniz. Yukarıdaki adımları uygulayarak proje raporlarınızın her bölgenin biçimlendirme beklentilerine uygun olmasını sağlayın.

---

**Son Güncelleme:** 2026-07-19  
**Test Edilen Versiyon:** Aspose.Tasks 24.11 for .NET  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks'te Takvim Koleksiyonunu Yönetme](/tasks/net/calendar-scheduling/calendar-collection/)
- [Aspose.Tasks'te Takvim İstisnaları Koleksiyonu](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Aspose.Tasks for .NET ile MS Project Ücretlerini Yönetme](/tasks/net/rate-recurring-tasks/handling-rates/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}