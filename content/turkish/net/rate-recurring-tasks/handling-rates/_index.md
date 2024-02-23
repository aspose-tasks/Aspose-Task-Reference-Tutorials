---
title: Aspose.Tasks for .NET ile MS Project Oranlarını Yönetme
linktitle: Aspose.Tasks'ta İşleme Oranları
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Proje Oranlarını kolaylıkla yönetme konusunda uzmanlaşın. Daha sorunsuz proje iş akışları için görevleri verimli bir şekilde otomatikleştirin.
type: docs
weight: 10
url: /tr/net/rate-recurring-tasks/handling-rates/
---
## giriiş
Aspose.Tasks for .NET'i kullanarak MS Proje Hızlarını yönetme eğitimimize hoş geldiniz! Bu kılavuzda, MS Project belgelerinizdeki oranları verimli bir şekilde yönetebilmenizi sağlamak için süreç boyunca size adım adım yol göstereceğiz. Aspose.Tasks for .NET, MS Project dosyalarını programlı olarak yönetmek için güçlü özellikler sunarak proje yönetimi görevlerinizi zahmetsizce kolaylaştırmanıza olanak tanır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1. Visual Studio Yüklü: Sisteminizde Visual Studio'nun yüklü olduğundan emin olun.
2.  Aspose.Tasks for .NET Kütüphanesi: Aspose.Tasks for .NET kütüphanesini indirin ve yükleyin. İndirme linkini bulabilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
3. Temel C# Anlayışı: C# programlama dilinin temellerine aşina olun.
## Ad Alanlarını İçe Aktar
Öncelikle gerekli ad alanlarını C# projenize aktarmanız gerekir. Bu ad alanları, MS Proje Oranlarını yönetmek için gereken sınıflara ve yöntemlere erişim sağlayacaktır.
## Adım 1: Aspose.Tasks Ad Alanını İçe Aktarın
```csharp
using Aspose.Tasks;
using System;

```
Şimdi verilen örneği birden fazla adıma ayıralım ve her adımı iyice anlayalım.
## Adım 1: Proje Dosyasını Yükleyin
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Bu adımda "Project1.mpp" isimli mevcut bir MS Project dosyasını aşağıdaki komutu kullanarak yüklüyoruz.`Project` Aspose.Tasks tarafından sağlanan sınıf.
## Adım 2: Kaynak Ekleme ve Çalışmayı Ayarlama
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Burada projeye "Resource 1" adında yeni bir kaynak ekliyoruz ve türünü "Work" olarak ayarlıyoruz. Bu kaynağın çalışma süresini de tanımlıyoruz.
## 3. Adım: Standart Oranı Ayarlayın
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
Bu adımda kaynağın standart ücretini saat başına 20$ olarak ayarladık.
## Adım 4: Oran Dönemlerini Tanımlayın
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Burada kaynağa ait oran dönemlerini tanımlıyoruz. Oran1, standart ve fazla mesai ücretlerinin belirtilmesiyle 1 Ocak 2019 ile 11 Kasım 2019 tarihleri arasında belirlenmiştir.
## Adım 5: Başka Bir Fiyat Dönemi Ekleyin
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
Bu son adımda, 12 Kasım 2019'dan 31 Aralık 2019'a kadar farklı bir standart ücret ve kullanım başına maliyet tanımlı başka bir ücret dönemi ekliyoruz.
Tebrikler! Aspose.Tasks for .NET'i kullanarak MS Project Rates'i başarıyla yönettiniz.
## Çözüm
MS Proje Oranlarını programlı bir şekilde yönetmek, proje yönetimi iş akışınızı önemli ölçüde geliştirebilir. Aspose.Tasks for .NET ile hız işleme görevlerini verimli bir şekilde otomatikleştirerek zamandan ve kaynaklardan tasarruf etme gücüne sahip olursunuz.
## SSS'ler
### S: Aspose.Tasks karmaşık proje yapılarını yönetebilir mi?
C: Evet, Aspose.Tasks karmaşık proje yapılarının kolaylıkla üstesinden gelmenizi sağlayacak güçlü özellikler sunar.
### S: Aspose.Tasks, MS Project dosyalarının tüm sürümleriyle uyumlu mudur?
C: Aspose.Tasks, MS Project dosyalarının çeşitli sürümlerini destekleyerek farklı platformlar arasında uyumluluk sağlar.
### S: Aspose.Tasks'ı kullanarak bir MS Project dosyasındaki mevcut oranları değiştirebilir miyim?
C: Kesinlikle! Aspose.Tasks mevcut oranları değiştirmenize, yeni oranlar eklemenize ve bunları dinamik olarak yönetmenize olanak tanır.
### S: Aspose.Tasks özel oran hesaplamaları için destek sunuyor mu?
C: Evet, belirli proje gereksinimlerini karşılamak için Aspose.Tasks'ı kullanarak özel oran hesaplamaları uygulayabilirsiniz.
### S: Aspose.Tasks kullanıcıları için bir topluluk forumu veya destek mevcut mu?
 C: Evet, ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15)yardım istemek ve diğer kullanıcılarla etkileşimde bulunmak için.