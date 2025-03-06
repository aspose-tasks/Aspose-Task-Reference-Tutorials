---
title: Aspose.Tasks'taki Kaynak Türleri
linktitle: Aspose.Tasks'taki Kaynak Türleri
second_title: Aspose.Tasks .NET API'si
description: Adım adım eğitim aracılığıyla Aspose.Tasks for .NET'te iş, malzeme ve maliyet kaynakları da dahil olmak üzere farklı türdeki kaynaklarla nasıl çalışılacağını öğrenin.
type: docs
weight: 14
url: /tr/net/resource-risk-analysis/resource-types/
---
## giriiş
Aspose.Tasks for .NET, geliştiricilerin Microsoft Project dosyalarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir kütüphanedir. İster görevleri, kaynakları veya programları yönetiyor olun, Aspose.Tasks kapsamlı bir API seti sağlayarak süreci basitleştirir. Bu eğitimde Aspose.Tasks for .NET kullanarak projelerinizde kullanabileceğiniz farklı kaynak türlerini inceleyeceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Visual Studio: .NET geliştirme için güçlü bir entegre geliştirme ortamı (IDE) olan Visual Studio'yu yükleyin.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
3. Temel C# Bilgisi: .NET geliştirme için kullanılan programlama dili olan C#'a aşina olun.

## Ad Alanlarını İçe Aktar
Öncelikle Aspose.Tasks for .NET'in işlevlerine erişmek için gerekli ad alanlarını içe aktaralım:
```csharp
    
```

## 1. Adım: Yeni bir Proje örneği oluşturun
```csharp
var project = new Project();
```
Bu satır, projeyle ilgili tüm veriler ve işlemler için kapsayıcı görevi gören yeni bir Project nesnesini başlatır.
## 2. Adım: Çalışma Kaynağı Ekleme
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Burada "Work Resources" isminde yeni bir çalışma kaynağı oluşturup türünü ResourceType.Work olarak belirtiyoruz.
## 3. Adım: Maddi Kaynak Ekleme
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
Bu adım, türü ResourceType.Material olarak ayarlanan "Malzeme kaynağı" adlı bir malzeme kaynağı ekler. Ayrıca ölçü birimini belirtmek için malzeme etiketini "kg" olarak belirtiyoruz.
## 4. Adım: Maliyet Kaynağı Ekleme
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Son olarak “Maliyet kaynağı” adında bir maliyet kaynağı ekliyoruz ve türünü ResourceType.Cost olarak ayarlıyoruz. Ek olarak maliyet değerini de bu kaynakla ilişkili parasal değeri temsil eden 59,99 olarak ayarladık.

## Çözüm
Bu eğitimde Aspose.Tasks for .NET'te iş, malzeme ve maliyet kaynakları da dahil olmak üzere farklı türde kaynaklarla nasıl çalışılacağını araştırdık. Adım adım kılavuzu takip ederek projelerinizdeki kaynakları programlı olarak etkili bir şekilde yönetebilirsiniz.
## SSS'ler
### S: Aspose.Tasks for .NET'i diğer proje yönetimi yazılımı formatlarıyla birlikte kullanabilir miyim?
C: Evet, Aspose.Tasks, Microsoft Project (MPP), Primavera P6 ve daha fazlası dahil olmak üzere çeşitli formatları destekler.
### S: Aspose.Tasks for .NET'in ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for .NET için nasıl teknik destek alabilirim?
 C: Aspose.Tasks forumunu ziyaret edebilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15) teknik yardım için.
### S: Aspose.Tasks for .NET için geçici bir lisans satın alabilir miyim?
 C: Evet, geçici lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Tasks for .NET referans amaçlı belgeler sağlıyor mu?
 C: Evet, belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/tasks/net/).