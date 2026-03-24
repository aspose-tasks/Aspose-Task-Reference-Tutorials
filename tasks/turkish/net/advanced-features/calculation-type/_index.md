---
date: 2026-03-24
description: Aspose.Tasks for .NET'te hesaplamayı nasıl ayarlayacağınızı öğrenin;
  özet değerleri hesaplamak, hesaplama formülünü tanımlamak ve toplama özetini yapılandırmak
  için örneklerle.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Hesaplama Türünü Nasıl Ayarlarsınız
url: /tr/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Hesaplama Türünü Nasıl Ayarlarsınız

## Giriş

Eğer bir Microsoft Project dosyasında görevler ve özet satırlar için **hesaplamayı nasıl ayarlayacağınızı** belirten kurallara ihtiyacınız varsa, bu öğretici Aspose.Tasks for .NET kullanarak tam olarak bunu gösterir. Tam bir **hesaplama türü örneği** üzerinden geçecek, **özet değerleri hesaplamak** nasıl yapılır gösterecek ve **hesaplama formülünü tanımlamak** ile **rollup özetini yapılandırmak** için genişletilmiş özniteliklerin nasıl ayarlanacağını açıklayacağız. Sonunda, bir görevi projeye ekleyebilecek, özel hesaplama mantığını ayarlayabilecek ve roll‑up davranışını güvenle kontrol edebileceksiniz.

## Hızlı Yanıtlar
- **Ana amaç nedir?** Bir Project dosyasında görev ve özet değerlerinin nasıl hesaplandığını kontrol etmek için.  
- **Hangi API sınıfı kullanılıyor?** `ExtendedAttributeDefinition` birlikte `CalculationType` ve `SummaryRowsCalculationType`.  
- **Formül kullanabilir miyim?** Evet – `CalculationType = CalculationType.Formula` ayarlayın ve bir formül dizesi sağlayın.  
- **Özet değerleri nasıl roll‑up yapılır?** `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` kullanın ve `Average` gibi bir `RollupType` belirtin.  
- **Bir lisansa ihtiyacım var mı?** Üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir.

## Hesaplama Türü Nedir ve Hesaplama Nasıl Ayarlanır?

`CalculationType` Aspose.Tasks'e genişletilmiş bir özniteliğin değerini nasıl hesaplayacağını söyler. Statik bir değer, bir formül seçebilir veya kütüphanenin alt görevlerden değerleri roll‑up yapmasına izin verebilirsiniz. Hesaplamayı doğru ayarlamak, projenin manuel güncellemeler olmadan özel iş kurallarını yansıtmasını istediğinizde çok önemlidir.

## Özet değerleri hesaplamak için neden hesaplama türü kullanılmalı?

Bir proje özet görevler içerdiğinde, genellikle özet satırların toplu verileri (ör. toplam maliyet, ortalama süre) göstermesi gerekir. `SummaryRowsCalculationType` ve `RollupType` aracılığıyla **özet değerleri hesaplamak** yapılandırılarak, bireysel görevleri değiştirdiğinizde bu toplamların otomatik olarak senkronize kalması sağlanır.

## Ön Koşullar

Başlamadan önce şunlara sahip olduğunuzdan emin olun:

1. C# ve .NET çerçevesi hakkında temel bilgi.  
2. Makinenizde Visual Studio (herhangi bir yeni sürüm) yüklü.  
3. Aspose.Tasks for .NET kütüphanesi yüklü – bunu [buradan](https://releases.aspose.com/tasks/net/) indirebilirsiniz.  
4. Referans için resmi Aspose.Tasks for .NET dokümantasyonuna erişim, mevcut [burada](https://reference.aspose.com/tasks/net/).

## Ad Alanlarını İçe Aktarın

Örneğe geçmeden önce gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.Tasks;
using System;
```

## Adım 1: Yeni Bir Proje Oluşturun

İlk olarak, görevlerimizi ve özel özniteliklerimizi tutacak boş bir `Project` nesnesi oluştururuz.

```csharp
var project = new Project();
```

## Adım 2: Projeye Bir Görev Ekleyin

Şimdi **görev projesi ekleyin** verilerini, basit bir görev oluşturarak, başlangıç tarihini ayarlayarak ve bir günlük bir süre vererek ekliyoruz.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Adım 3: Genişletilmiş Bir Öznitelik İçin Hesaplama Türünü Tanımlayın (Formül Örneği)

Burada, değeri bir formülden hesaplanan bir genişletilmiş öznitelik tanımı oluşturuyoruz. Bu, bir **hesaplama türü örneği** gösterir ve **hesaplama formülünü tanımlamak** nasıl yapılır gösterir.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Adım 4: Özet Satırlar İçin Hesaplama Türünü Tanımlayın (Rollup Özeti Yapılandırma)

Sonra, Aspose.Tasks'in *Average* roll‑up türünü kullanarak **rollup özetini yapılandır**masını söyleyen başka bir genişletilmiş öznitelik tanımı oluşturuyoruz. Bu, maliyet, iş ya da özel alanlar için **özet değerleri hesaplamak** tipik yoludur.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Yaygın Sorunlar ve Sorun Giderme

| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|------|
| Formül `null` döndürüyor | Formülde hatalı alan referansı | Parantez içindeki alan adını doğrulayın (örneğin `[Start]` yerine `[stARt]` değil). |
| Özet satırlar 0 gösteriyor | `SummaryRowsCalculationType` ayarlanmamış veya yanlış `RollupType` | `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` olduğundan emin olun ve uygun bir `RollupType` seçin. |
| Öznitelikler eklendikten sonra proje yüklenemiyor | Öznitelik tanımı ile görev kullanımı arasında uyumsuzluk | Öznitelik tanımını **herhangi bir göreve atamadan önce** ekleyin. |

## Sonuç

Bu öğreticide, .NET için Aspose.Tasks'te **hesaplamayı nasıl ayarlayacağınızı** kapsadık; basit bir görev oluşturmaktan formül‑tabanlı ve roll‑up‑tabanlı hesaplama türlerini tanımlamaya kadar. Bu ayarları ustalaştırarak **özet değerleri hesaplamak** üzerinde ince ayar kontrolü elde eder, manuel elektronik tablo çalışması olmadan daha zengin proje analizleri yapabilirsiniz.

## SSS

### Q1: Aspose.Tasks'te Hesaplama Türü Nedir?

A1: Aspose.Tasks'te Hesaplama Türü, bir projedeki görevler ve özet görevler için değerlerin nasıl hesaplandığını belirler ve Formül ve Rollup gibi seçenekler sunar.

### Q2: Genişletilmiş Bir Öznitelik İçin Hesaplama Türü Nasıl Ayarlanır?

A2: Genişletilmiş bir öznitelik için Hesaplama Türünü, ilgili CalculationType özelliğini uygun şekilde tanımlayarak ayarlayabilirsiniz.

### Q3: Projedeki özet satırlar için Hesaplama Türünü Özelleştirebilir miyim?

A3: Evet, Aspose.Tasks özet satırlar için Hesaplama Türünü belirlemenize izin verir ve böylece değer hesaplamalarını gereksinimlerinize göre özelleştirebilirsiniz.

### Q4: Özet görev hesaplamaları için farklı Rollup Türleri mevcut mu?

A4: Evet, Aspose.Tasks, özet görevlerin değerlerini hesaplamak için Ortalama, Toplam ve Sayım gibi çeşitli Rollup Türleri sunar.

### Q5: Aspose.Tasks for .NET hakkında daha fazla kaynağı nerede bulabilirim?

A5: Kapsamlı rehberlik ve destek için [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) üzerindeki dokümantasyon ve topluluk destek forumlarını inceleyebilirsiniz.

---

**Son Güncelleme:** 2026-03-24  
**Test Edilen:** Aspose.Tasks for .NET (latest release)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}