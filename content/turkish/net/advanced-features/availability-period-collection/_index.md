---
title: Aspose.Tasks'ta Kullanılabilirlik Dönemlerinin Toplanması
linktitle: Aspose.Tasks'ta Kullanılabilirlik Dönemlerinin Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te kaynakların kullanılabilirlik sürelerini nasıl yöneteceğinizi öğrenin. Bu adım adım öğretici, kullanılabilirlik dönemlerini ekleme, güncelleme ve kaldırma konusunda size yol göstererek etkili proje kaynak planlaması sağlar.
type: docs
weight: 18
url: /tr/net/advanced-features/availability-period-collection/
---
## giriiş

Bu eğitimde Aspose.Tasks for .NET'te bir kaynağın kullanılabilirlik dönemi koleksiyonuyla nasıl çalışılacağını keşfedeceğiz. Kullanılabilirlik dönemlerini yönetmek, proje yönetimi için çok önemlidir ve bir proje içindeki görevler için kaynakların ne zaman kullanılabilir olduğunu tanımlamamıza olanak tanır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Visual Studio: Sisteminizde Visual Studio'nun kurulu olduğundan emin olun.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
3. Temel Anlama: C# ve .NET çerçevesine aşinalık.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını projemize aktarmamız gerekiyor:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Örnek kodu birden çok adıma ayıralım ve her bir bölümü anlayalım:

## Adım 1: Projeyi ve Kaynağı Başlatın

```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Burada bir proje dosyası yüklüyoruz ve kimliğine göre belirli bir kaynağı elde ediyoruz.

## 2. Adım: Mevcut Kullanılabilirlik Dönemlerini Temizleyin

```csharp
resource.AvailabilityPeriods.Clear();
```

Kaynakla ilişkili mevcut kullanılabilirlik dönemlerini temizliyoruz.

## 3. Adım: Kullanılabilirlik Dönemlerini Ekleyin

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Kullanılabilirlik dönemleri koleksiyonunu yineliyoruz ve bunları kaynağa ekliyoruz.

## 4. Adım: Yeni Bir Kullanılabilirlik Dönemi Ekleme

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

2013 yılı için yeni bir stok dönemi oluşturup koleksiyona ekliyoruz.

## Adım 5: Kullanılabilirlik Dönemlerini Görüntüleyin

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Kaynakla ilişkili her kullanılabilirlik döneminin sayısını ve ayrıntılarını yazdırırız.

## 6. Adım: Kullanılabilirlik Dönemlerini Başka Bir Kaynağa Kopyalayın

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Kullanılabilirlik dönemlerini bir kaynaktan diğerine kopyalarız.

## 7. Adım: Kullanılabilirlik Dönemlerini Güncelleyin ve Kaldırın

```csharp
// Belirli bir dönem için mevcut birimleri güncelleme
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Belirli bir dönemi kaldır
otherResource.AvailabilityPeriods.Remove(period2013);
```

Belirli bir döneme ait mevcut birimleri güncelliyoruz ve belirli dönemleri koleksiyondan kaldırıyoruz.

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'te kullanılabilirlik dönemi koleksiyonlarıyla nasıl çalışılacağını öğrendik. Kaynak kullanılabilirliğini yönetmek, etkili proje planlama ve yürütme için çok önemlidir.

## SSS'ler

### S1: Kullanılabilirlik dönemlerine özel alanlar ekleyebilir miyim?

Cevap1: Hayır, Aspose.Tasks for .NET'teki kullanılabilirlik dönemleri özel alanları desteklemez.

### S2: Kullanılabilirlik dönemleri belirli görevlerle bağlantılı mı?

C2: Hayır, kullanılabilirlik dönemleri kaynaklarla ilişkilidir ve genel olarak görevler için ne zaman kullanılabilir olduklarını tanımlar.

### S3: Kullanılabilirlik dönemlerini harici kaynaklardan alabilir miyim?

Cevap3: Evet, Aspose.Tasks for .NET API'lerini kullanarak çeşitli veri kaynaklarından kullanılabilirlik dönemlerini içe aktarabilirsiniz.

### S4: Çakışan kullanılabilirlik dönemlerini nasıl halledebilirim?

Cevap4: Aspose.Tasks for .NET, çakışan dönemleri yönetecek yerleşik mekanizmalar sağlamaz. Bu tür senaryoları yönetmek için özel mantık uygulamanız gerekebilir.

### S5: Bir kaynağın sahip olabileceği kullanılabilirlik dönemi sayısında bir sınır var mı?

Y5: Bir kaynağın sahip olabileceği kullanılabilirlik dönemlerinin sayısına ilişkin önceden tanımlanmış bir sınır yoktur, ancak performans çok sayıda dönemle birlikte düşebilir.