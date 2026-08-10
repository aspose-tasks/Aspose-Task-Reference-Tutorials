---
date: 2026-04-03
description: Aspose.Tasks for .NET kullanarak proje yönetimi görev zamanlamasını öğrenin
  ve yinelenen görev eklemeyi, projeyi MPP olarak kaydetmeyi de dahil olmak üzere.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Aspose.Tasks'te Yıl Günü Tekrarlama
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Yıllık Gün Tekrarı ile Proje Yönetimi Görev Zamanlaması
url: /tr/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Yıl Günü Tekrarlaması İçeren Proje Yönetimi Görev Zamanlaması

## Giriş

Etkili **project management task scheduling** herhangi bir başarılı projenin temelidir. Görevler yıllık olarak tekrar ettiğinde—örneğin yıllık denetimler, bakım pencereleri veya mevsimsel incelemeler—bu tekrarları manuel olarak yönetmek hata yapmaya ve zaman kaybetmeye neden olabilir. Aspose.Tasks for .NET, yıl‑günü desenlerini programlı olarak tanımlamanıza olanak tanıyarak bunu basitleştirir, böylece en önemli şeye odaklanabilirsiniz: değer sunmak. Bu öğreticide, yılın belirli bir gününe dayalı **yinelenen görev ekleme** mantığını öğrenecek ve Microsoft Project ile sorunsuz entegrasyon için **projeyi MPP olarak kaydetmenin** tam olarak nasıl yapılacağını göreceksiniz.

## Hızlı Yanıtlar
- **“year day repetition” ne anlama gelir?** Her yıl belirli bir ayın belirli bir gününde bir görevi zamanlar.  
- **Hangi API sınıfı tekrarı oluşturur?** `YearlyRecurrencePattern` ve `ByYearDayRepetition` birleştirilir.  
- **Başlangıç ve bitiş tarihi ayarlayabilir miyim?** Evet, `EndByRecurrenceRange` kullanarak.  
- **Hangi dosya formatı üretilir?** Proje bir MPP dosyası olarak kaydedilir (`SaveFileFormat.Mpp`).  
- **Üretim için lisansa ihtiyacım var mı?** Değerlendirme dışı kullanım için ticari bir lisans gereklidir.

## Ön Koşullar

Before diving into the tutorial, ensure that you have the following prerequisites in place:

1. Aspose.Tasks for .NET Kütüphanesi: Aspose.Tasks for .NET kütüphanesini [web sitesi](https://releases.aspose.com/tasks/net/) üzerinden indirin ve kurun.  
2. Geliştirme Ortamı: Visual Studio ya da .NET geliştirme için tercih ettiğiniz diğer IDE'lerden birini kullanarak uygun bir geliştirme ortamı kurun.  
3. C# Temel Bilgisi: Kod örneklerini takip edebilmek için C# programlama dilinin temellerine aşina olun.  
4. Proje Yönetimi Kavramları: Proje yönetimi kavramları ve görev zamanlaması konusundaki anlayış, öğreticinin kavramlarını etkili bir şekilde kavramanıza yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Before we begin coding, let's import the necessary namespaces to facilitate our task manipulation using Aspose.Tasks for .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Şimdi, verilen örneği birden fazla adıma ayıralım ve her adımı ayrıntılı olarak açıklayalım.

## Yıl Günü Deseniyle Yinelenen Görev Nasıl Eklenir

### Adım 1: Proje Dosyasını Yükle

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Burada, yeni bir `Project` nesnesi başlatıyor ve **Project1.mpp** adlı mevcut bir proje dosyasını yüklüyoruz.

### Adım 2: Yinelenen Görev Parametrelerini Tanımla

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

Bu adımda, yinelenen görevimiz için parametreleri tanımlıyoruz. Görev adını, süresini ve tekrar desenini belirtiyoruz. Yıllık tekrar için `YearlyRecurrencePattern` kullanıyor ve `ByYearDayRepetition` ile **Temmuz ayının 1. günü** gerçekleşecek şekilde tekrarı ayarlıyoruz. Ayrıca, tekrar aralığını 1 Temmuz 2018'den 1 Temmuz 2019'a kadar tanımlıyoruz.

### Adım 3: Görevi Projeye Ekle

```csharp
project.RootTask.Children.Add(parameters);
```

Burada, tanımlanan yinelenen görev parametrelerini projenin kök görevine ekliyoruz.

### Adım 4: Projeyi MPP Olarak Kaydet

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Son olarak, **projeyi bir MPP dosyası olarak kaydediyoruz**, böylece Microsoft Project ya da uyumlu herhangi bir görüntüleyicide açılmaya hazır hale geliyor.

## Neden Önemlidir

- **Otomasyon** – Yıllık görevlerin manuel girişini ortadan kaldırır, insan hatasını azaltır.  
- **Tutarlılık** – Aynı gün‑ay deseninin birden fazla yılda uygulanmasını garanti eder.  
- **Entegrasyon** – Oluşan MPP dosyası, Microsoft Project'e güvenen paydaşlarla paylaşılabilir.

## Yaygın Tuzaklar ve İpuçları

- **DateTime hassasiyeti** – Başlangıç zamanının proje takviminizle uyumlu olduğundan emin olun; aksi takdirde görev kaymış görünebilir.  
- **Saat dilimleri** – API `DateTime` nesneleriyle çalışır; uygulamanız birden fazla bölgeyi kapsıyorsa UTC dönüşümünü düşünün.  
- **Lisans uygulaması** – Değerlendirme modunda kaydedilen MPP bir filigran içerebilir; üretim için geçerli bir lisans kullanın.

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks karmaşık tekrar desenlerini yönetebilir mi?**  
**A:** Evet, Aspose.Tasks yıllık, aylık, haftalık ve günlük tekrarlar dahil olmak üzere çeşitli tekrar desenleri için kapsamlı destek sağlar.

**Q: Aspose.Tasks farklı proje dosya formatlarıyla uyumlu mu?**  
**A:** Kesinlikle, Aspose.Tasks MPP, XML ve CSV gibi popüler proje dosya formatlarını destekler, farklı proje yönetim araçları arasında uyumluluğu sağlar.

**Q: Aspose.Tasks geliştiriciler için dokümantasyon ve destek sunuyor mu?**  
**A:** Evet, geliştiriciler kapsamlı dokümantasyona erişebilir ve karşılaştıkları sorular veya sorunlar için Aspose.Tasks topluluk forumlarından yardım alabilir.

**Q: Aspose.Tasks kullanarak görev özelliklerini (örneğin süre ve başlangıç tarihi) özelleştirebilir miyim?**  
**A:** Elbette, Aspose.Tasks görev özelliklerini dinamik olarak manipüle etmek için güçlü API'ler sunar; geliştiriciler süreleri, başlangıç tarihlerini, bağımlılıkları ve daha fazlasını özelleştirebilir.

**Q: Aspose.Tasks küçük ölçekli ve kurumsal düzeydeki projeler için uygun mu?**  
**A:** Evet, Aspose.Tasks, bireysel görevlerden büyük ölçekli kurumsal projelere kadar tüm ölçeklerdeki projeler üzerinde çalışan geliştiricilerin ihtiyaçlarını karşılayacak şekilde tasarlanmıştır.

---

**Son Güncelleme:** 2026-04-03  
**Test Edilen:** Aspose.Tasks 24.12 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}