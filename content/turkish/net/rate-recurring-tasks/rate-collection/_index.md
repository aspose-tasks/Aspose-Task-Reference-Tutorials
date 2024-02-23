---
title: Aspose.Tasks ile MS Proje Hızlarında Ustalaşın
linktitle: Aspose.Tasks'ta Oranların Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project dosyalarındaki oranları nasıl yöneteceğinizi öğrenin. Etkili kaynak yönetimi için adım adım eğitim.
type: docs
weight: 11
url: /tr/net/rate-recurring-tasks/rate-collection/
---
## giriiş
Aspose.Tasks for .NET'i kullanarak MS Project'te oranları yönetme eğitimimize hoş geldiniz! Bu kılavuzda, Aspose.Tasks'ı kullanarak MS Project dosyalarınızdaki oranlarla çalışma sürecinde size yol göstereceğiz. İster deneyimli bir geliştirici olun ister .NET geliştirmeye yeni başlıyor olun, bu eğitim size projelerinizdeki oranları etkili bir şekilde yönetmeniz için adım adım talimatlar sağlayacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### 1. Visual Studio Yüklü
Sisteminizde Visual Studio'nun kurulu olduğundan emin olun. Henüz yapmadıysanız web sitesinden indirebilirsiniz.
### 2. .NET için Aspose.Tasks
 Aspose.Tasks for .NET kütüphanesini şu adresten indirip yükleyin:[İnternet sitesi](https://releases.aspose.com/tasks/net/).
### 3. Temel C# ve .NET Bilgisi
Bu eğitimde sağlanan kod örneklerini daha iyi anlamak için C# programlama dili ve .NET framework temelleri hakkında bilgi edinin.
## Ad Alanlarını İçe Aktar
Aspose.Tasks işlevlerini kullanmak için C# projenize gerekli ad alanlarını içe aktarın:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Şimdi her örneği birden fazla adıma ayıralım:
## Adım 1: Bir MS Proje Dosyası Yükleyin
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Burada yeni bir tane oluşturuyoruz`Project` Mevcut bir MS Project dosyasını yükleyerek nesneyi oluşturun.
## 2. Adım: Kaynak Ekleyin ve İşi ve Oranları Ayarlayın
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Projeye yeni bir kaynak ekliyoruz, türünü iş, iş miktarı ve standart oran olarak ayarlıyoruz.
## 3. Adım: Kaynağa Oranları Ekleyin
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Başlangıç ve bitiş tarihlerini, standart ücreti ve ücret biçimini belirterek kaynağa oranlar ekliyoruz.
## Adım 4: Hız Bilgilerini Yazdırın
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
Bu adım, kaynakla ilişkili oranlar hakkındaki bilgileri yazdırır.
## 5. Adım: Oranı Güncelleyin
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Belirli bir fiyatın bitiş tarihini güncelleriz.
## 6. Adım: Oranları Kaldır
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Bu adım, belirli bir türdeki tüm oranları kaldırır.
## Adım 7: Kalan Oranları Yineleyin
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Son olarak, kaldırıldıktan sonra kalan oranları yineliyoruz.
## Çözüm
Sonuç olarak, bu eğitim size Aspose.Tasks for .NET kullanarak MS Project dosyalarındaki oranları yönetme konusunda kapsamlı bir kılavuz sağladı. Bu eğitimde özetlenen adım adım talimatları izleyerek projelerinizdeki oranları verimli bir şekilde yönetebilir ve doğru kaynak yönetimi sağlayabilirsiniz.
## SSS'ler
### S: Aspose.Tasks for .NET'i diğer proje yönetimi yazılımlarıyla birlikte kullanabilir miyim?
C: Evet, Aspose.Tasks for .NET, MS Project, Primavera ve daha fazlasını içeren çeşitli proje yönetimi yazılımlarıyla entegrasyonu destekler.
### S: Aspose.Tasks for .NET, MS Project dosyalarının farklı sürümleriyle uyumlu mudur?
C: Aspose.Tasks for .NET kesinlikle farklı sürümlerdeki MS Project dosyalarıyla çalışmayı destekleyerek esneklik ve uyumluluk sağlar.
### S: Aspose.Tasks for .NET dokümantasyon ve destek sunuyor mu?
 C: Evet, Aspose.Tasks'ta kapsamlı belgeler bulabilir ve destek forumlarına erişim sağlayabilirsiniz.[İnternet sitesi](https://reference.aspose.com/tasks/net/).
### S: Satın almadan önce Aspose.Tasks for .NET'i deneyebilir miyim?
C: Evet, Aspose.Tasks for .NET'in özelliklerini ve gereksinimlerinize uygunluğunu değerlendirmek için ücretsiz deneme sürümünden yararlanabilirsiniz.
### S: Aspose.Tasks for .NET lisansını nasıl satın alabilirim?
 C: Aspose.Tasks for .NET lisansını şu adresten satın alabilirsiniz:[İnternet sitesi](https://purchase.aspose.com/temporary-license/)İhtiyaçlarınıza uyacak esnek lisanslama seçenekleri sunan.