---
date: 2026-03-21
description: Aspose.Tasks for .NET ile kaynakların kullanılabilirlik dönemlerini nasıl
  yöneteceğinizi öğrenin ve etkili proje kaynak kullanılabilirliği sağlayın. Bu adım
  adım kılavuz, kullanılabilirlik dönemlerini nasıl ekleyeceğinizi, güncelleyeceğinizi
  ve kaldıracağınızı gösterir.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Proje Kaynak Kullanılabilirliği – Aspose.Tasks'te Kullanılabilirlik Dönemlerini
  Yönetme
url: /tr/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proje Kaynak Kullanılabilirliği: Aspose.Tasks'te Kullanılabilirlik Dönemlerinin Koleksiyonu

**Proje kaynak kullanılabilirliğini** yönetmek, başarılı proje planlamasının temel bir parçasıdır. Bu öğreticide, Aspose.Tasks for .NET API'sini kullanarak kaynakların kullanılabilirliğini adım adım nasıl yöneteceğinizi öğreneceksiniz; bir projeyi yüklemekten kaynaklar arasında dönemleri kopyalamaya kadar.

## Hızlı Yanıtlar
- **Kullanılabilirlik dönemleri için ana sınıf nedir?** `AvailabilityPeriod` sınıfı, `Aspose.Tasks` ad alanında bulunur.  
- **Mevcut dönemleri temizleyebilir miyim?** Evet, `resource.AvailabilityPeriods.Clear()` metodunu çağırın.  
- **Yeni bir dönem nasıl eklenir?** Bir `AvailabilityPeriod` nesnesi oluşturun ve `Add` ya da `Insert` metodunu kullanın.  
- **Dönemleri başka bir kaynağa kopyalamak mümkün mü?** Kesinlikle – `CopyTo` metodunu kullanın ve ardından her öğeyi hedef kaynağa ekleyin.  
- **Üretim ortamında lisansa ihtiyacım var mı?** Evet, deneme dışı dağıtımlar için ticari bir Aspose.Tasks lisansı gereklidir.

## Proje kaynak kullanılabilirliği nedir?
Proje kaynak kullanılabilirliği, bir kaynağın görevlere atanabileceği tarihleri ve birimlerini (kapasite yüzdesi) tanımlar. Bu dönemleri kontrol ederek aşırı tahsisatı önler ve takvim doğruluğunu artırırsınız.

## Kullanılabilirlik dönemlerini yönetmek için Aspose.Tasks neden tercih edilmeli?
- **Tam .NET entegrasyonu** – COM ara yüzüne gerek yok, tamamen yönetilen kod.  
- **İnce ayar kontrolü** – kesin başlangıç/bitiş tarihleri ve kesirli birimler ayarlanabilir.  
- **Kolay kopyalama** – kullanılabilirlik verilerini manuel ayrıştırma yapmadan kaynaklar arasında taşıyabilirsiniz.  
- **Performans odaklı** – büyük MPP dosyalarıyla verimli çalışır.

## Önkoşullar
1. **Visual Studio** – herhangi bir güncel sürüm (2019, 2022 veya daha yenisi).  
2. **Aspose.Tasks for .NET** – [buradan](https://releases.aspose.com/tasks/net/) indirin.  
3. **Temel C# bilgisi** – sınıflar, koleksiyonlar ve LINQ konusunda rahat olmalısınız.

## İsim Alanlarını İçe Aktarma

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

Temel Aspose.Tasks ad alanını, daha sonra ihtiyaç duyacağımız standart .NET koleksiyonlarıyla birlikte içe aktarıyoruz.

## Adım 1: Projeyi ve Kaynağı Başlatma

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Burada mevcut bir MPP dosyasını yüklüyor ve kullanılabilirliğini düzenlemek istediğimiz kaynağı (ID = 1) alıyoruz.

## Adım 2: Mevcut Kullanılabilirlik Dönemlerini Temizleme

```csharp
resource.AvailabilityPeriods.Clear();
```

Temizleme, önceden tanımlanmış tüm dönemleri kaldırır ve temiz bir başlangıç sağlar.

## Adım 3: Kullanılabilirlik Dönemleri Ekleme

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

`AvailabilityPeriod` nesnelerinin bir koleksiyonunu alıyoruz (`GetPeriods` yardımcı metodunun başka bir yerde tanımlandığı varsayılır) ve koleksiyonun yazılabilir olduğundan emin olarak her birini ekliyoruz.

## Adım 4: Yeni Bir Kullanılabilirlik Dönemi Ekleme

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Bu, 2013 yılı için özel bir dönem oluşturur ve zaten mevcut değilse 1. konuma (ikinci slot) ekler.

## Adım 5: Kullanılabilirlik Dönemlerini Görüntüleme

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

Konsola hızlı bir döküm, toplam sayıyı ve her dönemin ayrıntılarını gösterir – hata ayıklama veya doğrulama için kullanışlıdır.

## Adım 6: Kullanılabilirlik Dönemlerini Başka Bir Kaynağa Kopyalama

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

Tüm koleksiyonu bir diziye kopyalıyoruz, hedef kaynağın dönemlerini temizliyoruz ve ardından yeniden dolduruyoruz. Bu, kullanılabilirlik verilerinin kaynaklar arasında nasıl çoğaltılacağını gösterir.

## Adım 7: Kullanılabilirlik Dönemlerini Güncelleme ve Kaldırma

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Burada sondan ikinci dönemin `AvailableUnits` değerini ayarlıyor ve daha önce eklediğimiz 2013 dönemini kaldırıyoruz.

## Yaygın Sorunlar ve Çözümler
- **Yalnızca‑okunur koleksiyon hatası** – Projenin yalnızca‑okunur modda açılmadığından ve yeni öğeler eklemeden önce `resource.AvailabilityPeriods.Clear()` çağrıldığından emin olun.  
- **Çakışan dönemler** – Aspose.Tasks çakışmaları otomatik birleştirmez; tespit ve çözüm için özel mantık yazmanız gerekebilir.  
- **Yanlış tarih formatı** – Her zaman `DateTime` nesneleri kullanın; dize ayrıştırma yerel ayar hatalarına yol açabilir.

## Sıkça Sorulan Sorular

**S: Kullanılabilirlik dönemlerine özel alanlar ekleyebilir miyim?**  
C: Hayır, Aspose.Tasks for .NET'te kullanılabilirlik dönemleri özel alanları desteklemez.

**S: Kullanılabilirlik dönemleri belirli görevlere bağlı mı?**  
C: Hayır, bu dönemler kaynaklarla ilişkilidir ve kaynağın genel olarak görevlere ne zaman uygun olduğunu tanımlar.

**S: Kullanılabilirlik dönemlerini dış kaynaklardan içe aktarabilir miyim?**  
C: Evet, CSV, XML veya bir veritabanından `AvailabilityPeriod` nesneleri oluşturarak koleksiyona ekleyebilirsiniz.

**S: Çakışan kullanılabilirlik dönemlerini nasıl yönetirim?**  
C: Çakışmalar otomatik olarak çözülmez; çakışan dönemleri birleştirmek veya reddetmek için özel doğrulama uygulamanız gerekir.

**S: Bir kaynağın sahip olabileceği kullanılabilirlik dönemi sayısında bir sınırlama var mı?**  
C: Katı bir sınır yoktur, ancak çok büyük koleksiyonlar performansı etkileyebilir; mümkün olduğunca dönemleri birleştirmeyi düşünün.

## Sonuç

Bu rehberde, Aspose.Tasks for .NET ile **proje kaynak kullanılabilirliğini** yönetmek için bilmeniz gereken her şeyi ele aldık—projeyi başlatma ve eski verileri temizlemeden, dönem ekleme, ekleme, kopyalama, güncelleme ve kaldırmaya kadar. Bu adımları ustalaştırmak, kaynak takvimlerinizi doğru tutmanıza ve proje takvimlerinizi gerçekçi hale getirmenize yardımcı olur.

---

**Son Güncelleme:** 2026-03-21  
**Test Edilen Versiyon:** Aspose.Tasks for .NET (en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}