---
title: Aspose.Tasks'ta Proje Kaynağı Koleksiyonunu Yönetme
linktitle: Aspose.Tasks'ta Kaynak Toplama Yönetimi
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks API'yi kullanarak .NET'te Microsoft Project kaynak koleksiyonlarını nasıl verimli bir şekilde yöneteceğinizi öğrenin. Üretkenliği ve esnekliği artırın.
type: docs
weight: 13
url: /tr/net/resource-risk-analysis/managing-resource-collection/
---
## giriiş
Bu eğitimde, Aspose.Tasks for .NET'i kullanarak Microsoft Project kaynak koleksiyonlarını etkili bir şekilde nasıl yönetebileceğimizi keşfedeceğiz. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarıyla programlı olarak çalışmasına olanak tanıyan, proje verilerinin sorunsuz entegrasyonuna ve manipülasyonuna olanak tanıyan güçlü bir API'dir.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. C# ve .NET Framework Bilgisi: Bu eğitimde C# programlama dili ve .NET Framework'e aşina olunduğu varsayılmaktadır.
2. Aspose.Tasks for .NET Kurulumu: Aspose.Tasks for .NET'i yüklediğinizden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
3. Geliştirme Ortamı Kurulumu: Geliştirme ortamınızı Visual Studio veya tercih edilen herhangi bir IDE ile kurun.

## Ad Alanlarını İçe Aktar
Başlamadan önce Aspose.Tasks işlevlerine erişmek için gerekli ad alanlarını içe aktarın:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Adım 1: Proje Dosyasını Yükleyin
Öncelikle Microsoft Project dosyasını Aspose.Tasks proje nesnesine yükleyin:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## 2. Adım: Boş Kaynak Ekleme
Daha sonra projeye boş bir kaynak ekleyelim:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## 3. Adım: Adıyla Kaynak Ekleme
Şimdi projeye belirtilen ada sahip bir kaynak ekleyin:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## Adım 4: Başka Bir Kaynağın Öncesine Kaynak Ekleme
Belirtilen ada sahip bir kaynağı, kimliğine göre başka bir kaynağın önüne ekleyin:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## Adım 5: Kaynaklara Kimlik veya UID ile Erişme
Kaynaklara kimlikleri veya UID'leri ile erişebilirsiniz:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## Adım 6: Kaynak Bilgilerini Yazdırma
Proje kaynakları hakkındaki bilgileri yazdırın:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## Adım 7: Kaynakları Silme
Kaynakları projeden silin:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## Çözüm
Aspose.Tasks for .NET'i kullanarak Microsoft Project kaynak koleksiyonlarını yönetmek, geliştiricilere proje kaynaklarını programlı olarak verimli bir şekilde yönetmeleri için güçlü bir araç seti sağlar. Bu eğitimde özetlenen adımları izleyerek projelerinizdeki kaynakları sorunsuz bir şekilde yönetebilir, proje yönetimi görevlerinde üretkenliği ve esnekliği artırabilirsiniz.
## SSS'ler
### S: Aspose.Tasks büyük ölçekli proje dosyalarını yönetebilir mi?

C: Evet, Aspose.Tasks, büyük ölçekli proje dosyalarını verimli bir şekilde yönetecek şekilde tasarlanmış olup yüksek performans ve güvenilirlik sunar.

### S: Aspose.Tasks, Microsoft Project'in farklı sürümleriyle uyumlu mudur?

C: Aspose.Tasks, Microsoft Project'in çeşitli sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.

### S: Aspose.Tasks'ı kullanarak kaynak özelliklerini özelleştirebilir miyim?

C: Kesinlikle Aspose.Tasks, kaynak özelliklerini belirli proje gereksinimlerine göre özelleştirmek için kapsamlı yetenekler sunuyor.

### S: Aspose.Tasks eşzamanlı işlemler için çoklu iş parçacığını destekliyor mu?

C: Evet, Aspose.Tasks çoklu iş parçacığını destekleyerek performansı artırmak için proje verileri üzerinde eş zamanlı işlemler yapılmasına olanak tanır.

### S: Aspose.Tasks kullanıcıları için teknik destek mevcut mu?

 C: Evet, Aspose.Tasks kullanıcıları teknik desteğe forum aracılığıyla erişebilirler[Burada](https://forum.aspose.com/c/tasks/15).