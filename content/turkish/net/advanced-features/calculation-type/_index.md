---
title: Aspose.Tasks'ta Hesaplama Türü
linktitle: Aspose.Tasks'ta Hesaplama Türü
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks kütüphanesindeki Hesaplama Türü ile .NET projelerinde değer hesaplamalarını nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 30
url: /tr/net/advanced-features/calculation-type/
---
## giriiş

Bu eğitimde Aspose.Tasks for .NET'teki Hesaplama Türü özelliğini inceleyeceğiz. Aspose.Tasks, .NET geliştiricilerinin sistemlerinde Microsoft Project'in yüklü olmasına gerek kalmadan Microsoft Project dosyalarıyla çalışmasını sağlayan güçlü bir kütüphanedir. Hesaplama Türü, bir proje içindeki görevler ve özet görevler için değerlerin nasıl hesaplanacağını tanımlamamıza olanak tanır.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1. Temel C# ve .NET framework bilgisi.
2. Sisteminizde Visual Studio yüklü.
3.  Aspose.Tasks for .NET kütüphanesi kuruldu. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
4.  Referans amacıyla Aspose.Tasks for .NET belgelerine erişim mevcuttur[Burada](https://reference.aspose.com/tasks/net/).

## Ad Alanlarını İçe Aktar

Örneğe dalmadan önce gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.Tasks;
using System;


```

## 1. Adım: Yeni bir Proje oluşturun

Öncelikle yeni bir proje nesnesi oluşturalım:

```csharp
var project = new Project();
```

## 2. Adım: Görev Ekle

Şimdi projemize bir görev ekleyelim:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Adım 3: Genişletilmiş Bir Nitelik için Hesaplama Türünü Tanımlayın

Hesaplama Türü Formül olarak ayarlandığında genişletilmiş bir öznitelik tanımı oluşturacağız:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Adım 4: Özet Satırlar için Hesaplama Türünü Tanımlayın

Daha sonra, özet görev değerlerinin Ortalama toplama türü kullanılarak hesaplandığı başka bir genişletilmiş öznitelik tanımı oluşturacağız:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'te Hesaplama Türü ile nasıl çalışılacağını araştırdık. Genişletilmiş nitelikler için Hesaplama Türlerini tanımlayarak, bir proje içindeki görevler ve özet görevler için değerlerin nasıl hesaplanacağını özelleştirerek daha fazla esneklik ve kontrol sağlayabiliriz.

## SSS'ler

### S1: Aspose.Tasks'ta Hesaplama Türü Nedir?

A1: Aspose.Tasks'taki Hesaplama Türü, bir proje içindeki görevler ve özet görevler için değerlerin nasıl hesaplanacağını belirler ve Formül ve Toplama gibi seçenekler sunar.

### S2: Genişletilmiş Öznitelik için Hesaplama Türünü nasıl ayarlayabilirim?

Cevap2: Genişletilmiş bir Öznitelik için Hesaplama Türünü, CalculationType özelliğini uygun şekilde tanımlayarak ayarlayabilirsiniz.

### S3: Bir projedeki özet satırları için Hesaplama Türünü özelleştirebilir miyim?

C3: Evet, Aspose.Tasks, özet satırları için Hesaplama Türünü belirtmenize olanak tanıyarak değer hesaplamalarını gereksinimlerinize göre uyarlamanıza olanak tanır.

### S4: Özet görev hesaplamaları için farklı Toplama Türleri mevcut mu?

Cevap4: Evet, Aspose.Tasks, özet görevlerin değerlerini hesaplamak için Ortalama, Toplam ve Sayım gibi çeşitli Toplama Türleri sağlar.

### S5: Aspose.Tasks for .NET'te daha fazla kaynağı nerede bulabilirim?

 Cevap5: Web sitesinde bulunan belgeleri ve topluluk destek forumlarını inceleyebilirsiniz.[.NET için Aspose.Tasks](https://reference.aspose.com/tasks/net/) Kapsamlı rehberlik ve yardım için.