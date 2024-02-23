---
title: Aspose.Tasks for .NET ile Zaman Aşamalı Veri İşleme konusunda uzmanlaşın
linktitle: Aspose.Tasks'ta Zaman Aşamalı Verileri İşleme
second_title: Aspose.Tasks .NET API'si
description: Zaman aşamalı verileri zahmetsizce yönetmek, proje planlamasını geliştirmek ve kaynak yönetimini optimize etmek için Aspose.Tasks for .NET'i keşfedin. #Aspose #Görevler #MS Projesi
type: docs
weight: 14
url: /tr/net/text-view-configuration/timephased-data/
---
## giriiş
Proje yönetimi dünyasında, zaman aşamalı verilerin etkili bir şekilde kullanılması kaynak tahsisi, maliyet tahmini ve genel proje planlaması açısından çok önemlidir. Aspose.Tasks for .NET, özel zaman aşamalı verilerle sorunsuz bir şekilde çalışmak için güçlü bir çözüm sunar. Bu eğitim, Aspose.Tasks'ı kullanarak zaman aşamalı verileri işleme sürecinde size rehberlik edecek ve projelerinizde kaynak yönetimini optimize etmenize olanak tanıyacak.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Proje yönetimi kavramlarının temel anlayışı.
-  .NET için Aspose.Tasks'ı yükledim. İndirebilirsin[Burada](https://releases.aspose.com/tasks/net/).
- Sağlanan örneklerin uygulanması için Visual Studio gibi bir kod düzenleyici.
## Ad Alanlarını İçe Aktar
.NET projenizde Aspose.Tasks işlevlerinden yararlanmak için gerekli ad alanlarını içe aktardığınızdan emin olun. Kod dosyanızın başına aşağıdaki satırları ekleyin:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Şimdi, Aspose.Tasks'ı kullanarak zaman aşamalı verileri yönetme konusunda size rehberlik etmesi için verilen örneği birden fazla adıma ayıralım:
## Adım 1: Projeyi Kurun
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Burada yeni bir proje başlatıyoruz ve hesaplama modunu ayarlıyoruz.
## Adım 2: Kaynakları ve Görevleri Tanımlayın
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Bir proje yapısını simüle etmek için iş ve maliyet kaynaklarının yanı sıra bir görev oluşturun.
## 3. Adım: Kaynakları Göreve Atayın
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Göreve iş ve maliyet kaynaklarını atayın.
## 4. Adım: Özel Zaman Aşamalı Verileri Ekleme
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// CostAssignment için benzer adımlar
costAssignment.TimephasedData.Clear();
```
Hem iş hem de maliyet atamaları için özel zaman aşamalı veriler ekleyin.
## Adım 5: Zaman Aşamalı Verileri Görüntüleyin
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Her zaman aşamalı veri girişiyle ilgili bilgileri görüntüleyin
    }
}
```
Son olarak, her atama için zaman aşamalı verileri görüntüleyin.
#
## Çözüm
Aspose.Tasks'ta zaman aşamalı verilerin etkili bir şekilde işlenmesi, ayrıntılı proje planlaması ve kaynak yönetimi için yeni olanaklar sunar. Bu adım adım kılavuzu izleyerek, projelerinizin belirli ihtiyaçlarını karşılamak için zaman aşamalı verileri nasıl değiştireceğinizi öğrendiniz.
## Sıkça Sorulan Sorular
### Aspose.Tasks for .NET'i diğer proje yönetimi araçlarıyla birlikte kullanabilir miyim?
Aspose.Tasks öncelikle .NET geliştirme için tasarlanmıştır. Ancak işlevleri çeşitli proje yönetimi araçlarını tamamlayabilir.
### Aspose.Tasks for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Tasks for .NET için nasıl destek alabilirim?
 ziyaret edin[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15)topluluk desteği için.
### Geçici lisans nedir ve nasıl edinebilirim?
 Geçici lisanslar hakkında bilgi edinin[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Tasks for .NET belgelerini nerede bulabilirim?
 Kapsamlı bakın[dokümantasyon](https://reference.aspose.com/tasks/net/) detaylı bilgi için.