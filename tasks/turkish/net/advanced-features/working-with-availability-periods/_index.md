---
date: 2026-04-06
description: Aspose.Tasks for .NET kullanarak projeye kaynak eklemeyi ve kaynak kullanılabilirlik
  dönemlerini ayarlamayı öğrenin. Kaynak takvimlerini yönetmek için adım adım rehber.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Aspose.Tasks'te Kullanılabilirlik Dönemleriyle Çalışma
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Projeye Kaynak Ekle ve Kullanılabilirliği Ayarla
url: /tr/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeye Kaynak Ekleme ve Aspose.Tasks'te Kullanılabilirliği Ayarlama

## Giriş

Bu öğreticide **projeye kaynak eklemeyi** öğrenecek ve ardından Aspose.Tasks .NET kütüphanesini kullanarak kaynak kullanılabilirlik dönemlerini tanımlayacaksınız. Kaynak takvimlerini yönetmek, gerçekçi proje takvimleri için gereklidir ve aşağıdaki adımlar sizi sürecin tamamından geçirir—bir proje örneği oluşturmaktan her dönemin ayrıntılarını yazdırmaya kadar.

## Hızlı Yanıtlar
- **Ana hedef nedir?** Bir projeye kaynak eklemek ve onun kullanılabilirlik dönemlerini yapılandırmak.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for .NET.  
- **Üretim için lisansa ihtiyacım var mı?** Evet, ticari bir lisans gereklidir.  
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Uygulama süresi?** Temel senaryolar için genellikle 15 dakikadan az.

## “Projeye kaynak ekleme” nedir?

Projeye bir kaynak eklemek, görevlere atanabilecek bir kişi, ekipman veya malzeme için bir yer tutucu oluşturur. Kaynak oluşturulduktan sonra, **kaynak kullanılabilirliğini ayarlayabilir**, çalışma takvimini tanımlayabilir ve zamanlayıcının bu kısıtlamalara uymasını sağlayabilirsiniz.

## Neden çalışma takvimini ve kullanılabilirlik dönemlerini yapılandırmalıyız?

- **Doğru planlama:** Görevler, kaynak gerçekten serbest olduğunda planlanır.  
- **Maliyet kontrolü:** Kullanılabilirlik birimleri yarı zamanlı çabayı yansıtır, böylece işçilik maliyetlerini doğru hesaplamanıza yardımcı olur.  
- **Kaynak dengeleme:** Motor, her kaynağın takvimini bildiğinde aşırı tahsisleri otomatik olarak dengeleyebilir.

## Önkoşullar

1. Visual Studio (veya herhangi bir .NET uyumlu IDE).  
2. Aspose.Tasks for .NET – [buradan](https://releases.aspose.com/tasks/net/) indirin.  
3. Temel C# bilgisi.

## Ad Alanlarını İçe Aktar

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Projeye kaynak nasıl eklenir?

### Adım 1: Yeni bir `Project` örneği oluşturun

```csharp
var project = new Project();
```

Bu nesne, bütün proje dosyasını bellekte temsil eder.

### Adım 2: Projeye bir kaynak ekleyin

```csharp
var resource = project.Resources.Add("Work Resource");
```

Bu çağrı, daha sonra görevlere ekleyebileceğiniz *Work Resource* adlı bir **kaynak** oluşturur.

### Adım 3: Kullanılabilirlik dönemlerini tanımlayın

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` gösterilmeyen bir uygulama ile bir yardımcı metottur ve `AvailabilityPeriod` nesnelerinin bir koleksiyonunu döndürür. Her dönem, bir başlangıç tarihi, bir bitiş tarihi ve kaynağın mevcut olduğu birimler (tam zamanlı çabanın yüzdesi) belirtir.

### Adım 4: Dönemleri kaynağa ekleyin

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Burada, koleksiyonu döngüyle dolaşarak ve her dönemi kaynağın takvimine ekleyerek **kaynak kullanılabilirliğini ayarlar**.

### Adım 5: Kullanılabilirlik detaylarını gösterin

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Konsol çıktısı, dönemlerin doğru bir şekilde depolandığını doğrulamanızı sağlar.

## Yaygın Tuzaklar ve İpuçları

- **Tarih hassasiyeti:** `AvailableFrom` ve `AvailableTo` `DateTime` değerleridir; tam gün dönemleri istiyorsanız saat 00:00'da ayarlandıklarından emin olun.  
- **Birim aralığı:** Geçerli değerler 0‑100 % arasındadır; bu aralığın dışındaki değerler bir istisna fırlatır.  
- **Çakışan dönemler:** Çakışan dönemler otomatik olarak birleştirilir, ancak ayrı tutmak daha açıktır.

## Sıkça Sorulan Sorular

### S1: Aspose.Tasks for .NET'i ticari projelerde kullanabilir miyim?
C1: Evet, Aspose.Tasks for .NET ticari projelerde kullanılabilir. Bir lisans satın alabilirsiniz [buradan](https://purchase.aspose.com/buy).

### S2: Aspose.Tasks for .NET için ücretsiz deneme mevcut mu?
C2: Evet, Aspose.Tasks for .NET'in ücretsiz denemesini [buradan](https://releases.aspose.com/) edinebilirsiniz.

### S3: Aspose.Tasks for .NET belgelerini nerede bulabilirim?
C3: Belgeleri [buradan](https://reference.aspose.com/tasks/net/) bulabilirsiniz.

### S4: Aspose.Tasks for .NET için destek nasıl alabilirim?
C4: Topluluk forumundan [buradan](https://forum.aspose.com/c/tasks/15) destek alabilirsiniz.

### S5: Aspose.Tasks for .NET için geçici lisanslar sunuyor musunuz?
C5: Evet, geçici lisanslar [buradan](https://purchase.aspose.com/temporary-license/) temin edilebilir.

---

**Son Güncelleme:** 2026-04-06  
**Test Edilen:** Aspose.Tasks for .NET (en son kararlı sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}