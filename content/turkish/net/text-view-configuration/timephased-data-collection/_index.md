---
title: Aspose.Tasks'ta Zaman Aşamalı Veri Toplama konusunda Uzmanlaşmak
linktitle: Aspose.Tasks'ta Zaman Aşamalı Verilerin Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te zaman aşamalı veri toplamayı keşfedin. Adım adım kılavuz, SSS ve daha fazlası. Proje yönetimi yeteneklerinizi bugün geliştirin!
type: docs
weight: 15
url: /tr/net/text-view-configuration/timephased-data-collection/
---
## giriiş
Aspose.Tasks'ı kullanarak .NET uygulamalarınızda zaman aşamalı verilerin gücünden yararlanmak mı istiyorsunuz? Başka yerde arama! Bu kapsamlı kılavuz, Aspose.Tasks for .NET ile zaman aşamalı veri toplama sürecinde size yol gösterecek ve bu güçlü kütüphaneden en iyi şekilde yararlanmanızı sağlayacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1.  Aspose.Tasks for .NET Library: Kütüphaneyi şuradan indirip yükleyin:[Aspose.Tasks .NET Belgeleri](https://reference.aspose.com/tasks/net/).
2. .NET Geliştirme Ortamı: Çalışan bir .NET geliştirme ortamı kurduğunuzdan emin olun.
3. Belge Dizininiz: Kod parçacıklarındaki "Belge Dizininiz" yer tutucusunu belge dizininizin yolu ile değiştirin.
## Ad Alanlarını İçe Aktar
.NET projenize Aspose.Tasks işlevlerinden yararlanmak için gerekli ad alanlarını içe aktararak başlayın:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Bir Proje ve Kaynak Oluşturun
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Projeye Görevler Ekleyin
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Görev özelliklerini ayarla...
var task2 = project.RootTask.Children.Add("Task 2");
// Görev2 özelliklerini ayarlayın...
```
## 3. Kaynakları Görevlere Atayın
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Atama özelliklerini ayarlayın...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// Atama2 özelliklerini ayarla...
```
## 4. Zaman Aşamalı Verilerle Çalışmak
```csharp
// Konturlu çalışma konturunu ayarlayın
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Zaman aşamalı veri toplamanın salt okunur olup olmadığını kontrol edin
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Oluşturulan zaman aşamalı verileri temizle
assignment.TimephasedData.Clear();
// Zaman aşamalı veriler oluşturma ve ekleme
var td = new TimephasedData
{
    // Zaman aşamalı veri özelliklerini ayarla...
};
assignment.TimephasedData.Add(td);
// Zaman aşamalı verilerin bir listesini ekleyin
var list = new List<TimephasedData>();
// Listeye daha fazla zaman aşamalı veri öğesi ekleyin...
assignment.TimephasedData.AddRange(list);
// Zaman aşamalı verileri türe ve tarih aralığına göre filtreleyin
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Filtrelenmiş zaman aşamalı verileri yazdır...
```
## 5. Zaman Aşamalı Verileri Yönetin
```csharp
//Yanlış bir zaman aşamalı veri öğesi ekleyin ve ardından silin
var td4 = new TimephasedData
{
    // Yanlış zaman aşamalı veri özelliklerini ayarlayın...
};
assignment.TimephasedData.Add(td4);
// Yanlış zaman aşamalı veri öğesini silin
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Tüm zaman aşamalı öğeleri yineleyin
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Zaman aşamalı öğe ayrıntılarını yazdır...
}
```
## 6. Zaman Aşamalı Verileri Başka Bir Atamaya Kopyalayın
```csharp
// Zaman aşamalı verileri başka bir atamaya kopyalama
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Koleksiyonu düz bir listeye dönüştürün
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Zaman aşamalı veri öğelerini tek tek kaldırın
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Çözüm
Sonuç olarak, bu eğitimde Aspose.Tasks for .NET kullanılarak zaman aşamalı veri toplama konusunda ayrıntılı bir kılavuz sunulmaktadır. Bu adımları izleyerek bu işlevselliği projelerinize sorunsuz bir şekilde entegre edebilir, etkili zaman takibi ve kaynak yönetimi sağlayabilirsiniz.
## Sıkça Sorulan Sorular
### Aspose.Tasks for .NET'i diğer proje yönetimi araçlarıyla birlikte kullanabilir miyim?
Evet, Aspose.Tasks for .NET, popüler proje yönetimi araçlarıyla çalışacak şekilde tasarlanmıştır ve çeşitli dosya formatlarını destekler.
### Aspose.Tasks ile yönetebileceğim kaynak ve görev sayısında bir sınırlama var mı?
Aspose.Tasks farklı boyutlardaki projeleri yönetir ve kaynak ve görev sayısında kesin bir sınır yoktur.
### Aspose.Tasks for .NET ile ilgili herhangi bir sorun veya sorgu için nasıl destek alabilirim?
 Destek için şu adresi ziyaret edin:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) toplulukla bağlantı kurmak ve yardım almak için.
### Aspose.Tasks for .NET'i satın almadan önce deneyebilir miyim?
 Evet, Aspose.Tasks for .NET'in özelliklerini şu adrese erişerek keşfedebilirsiniz:[ücretsiz deneme](https://releases.aspose.com/).
### Aspose.Tasks for .NET lisansını nereden satın alabilirim?
 Aspose.Tasks for .NET için bir lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).