---
title: Aspose.Tasks'ta MS Project Kaynak Kullanımı Görünümlerini Yapılandırma
linktitle: Aspose.Tasks'ta Kaynak Kullanımı Görünümlerini Yapılandırma
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project kaynak kullanım görünümlerini nasıl yapılandıracağınızı öğrenin. Kod örneklerinin yer aldığı adım adım kılavuz.
type: docs
weight: 15
url: /tr/net/resource-risk-analysis/resource-usage-views/
---
## giriiş
Microsoft Project (MS Project), kullanıcıların projelerini verimli bir şekilde planlamasına, yürütmesine ve izlemesine olanak tanıyan güçlü bir proje yönetimi aracıdır. Aspose.Tasks for .NET, MS Project dosyalarıyla kusursuz entegrasyon sağlayarak geliştiricilerin proje verilerini programlı olarak değiştirmesine olanak tanır. Bu eğitimde, Aspose.Tasks for .NET'i kullanarak MS Project kaynak kullanım görünümlerini nasıl yapılandıracağımızı keşfedeceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini aşağıdaki adresten indirip yükleyin:[İndirme: {link](https://releases.aspose.com/tasks/net/).
2. Microsoft Project Dosyası: Bir Microsoft Project dosyasına sahip olun (`.mpp`) çalışmak istediğiniz proje verilerini içerir.

## Ad Alanlarını İçe Aktar
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Adım 1: Proje Dosyasını Yükleyin
İlk olarak Aspose.Tasks'ı kullanarak MS Project dosyasını yükleyin:
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ResourceUsageView.mpp");
```
## 2. Adım: Kaydetme Seçeneklerini Tanımlayın
Gerekli zaman ölçeği ayarlarını ve sunum biçimini belirterek kaydetme seçeneklerini tanımlayın:
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.ResourceUsage
};
```
## Adım 3: Projeyi Kaynak Kullanımı Görünümleriyle Kaydetme
Yapılandırılmış kaynak kullanımı görünümleriyle projeyi bir PDF dosyasına kaydedin:
```csharp
project.Save(DataDir + "ResourceUsage_days_out.pdf", options);
```

## Çözüm
Bu eğitimde Aspose.Tasks for .NET'i kullanarak MS Project kaynak kullanım görünümlerini nasıl yapılandıracağımızı öğrendik. Geliştiriciler, verilen adımları izleyerek Aspose.Tasks'ı .NET uygulamalarına sorunsuz bir şekilde entegre ederek proje verilerini verimli bir şekilde yönetebilirler.

## SSS'ler
### S: Aspose.Tasks, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mudur?
C: Evet, Aspose.Tasks, .mpp, .mpt, .xml ve .mpx dahil olmak üzere Microsoft Project dosyalarının çeşitli sürümlerini destekler.
### S: Zaman ölçeği ayarlarını ve sunum biçimini daha da özelleştirebilir miyim?
C: Kesinlikle, Aspose.Tasks, zaman ölçeği ayarlarını ve sunum formatlarını gereksinimlerinize göre özelleştirme esnekliği sağlar.
### S: Aspose.Tasks, PDF'nin yanı sıra diğer çıktı formatlarını da destekliyor mu?
C: Evet, Aspose.Tasks, XLSX, MPP, XML, HTML ve daha fazlasını içeren çeşitli çıktı formatlarını destekler.
### S: Aspose.Tasks desteği için bir topluluk veya forum var mı?
 C: Evet, ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) Sorularınız, tartışmalarınız veya destek ihtiyaçlarınız için.
### S: Satın almadan önce Aspose.Tasks'ı deneyebilir miyim?
 C: Elbette Aspose.Tasks'ı ücretsiz deneme sürümüyle keşfedebilirsiniz.[Burada](https://releases.aspose.com/).