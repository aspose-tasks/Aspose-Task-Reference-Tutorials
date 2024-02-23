---
title: Aspose.Tasks'ta Kaynak Atamalarının Toplanması
linktitle: Aspose.Tasks'ta Kaynak Atamalarının Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak Microsoft Project'te kaynak atamalarını nasıl yöneteceğinizi öğrenin. Kod örnekleriyle adım adım eğitim.
type: docs
weight: 12
url: /tr/net/resource-risk-analysis/resource-assignment-collection/
---
## giriiş
Aspose.Tasks for .NET'i kullanarak Microsoft Project'te kaynak atamalarını yönetmeye ilişkin bu kapsamlı eğitime hoş geldiniz. Bu öğreticide, kaynak atamalarını verimli bir şekilde nasıl yöneteceğiniz konusunda sağlam bir anlayışa sahip olmanızı sağlamak için süreci adım adım inceleyeceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz bilmeniz gereken her şeyde size yol gösterecektir.
## Önkoşullar
Koda dalmadan önce aşağıdaki ayarlara sahip olduğunuzdan emin olun:
1. Aspose.Tasks for .NET Kurulu: Geliştirme ortamınızda Aspose.Tasks for .NET'in kurulu olduğundan emin olun. Değilse, adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/tasks/net/).
2. Temel C# Bilgisi: Bu eğitimde, C# programlama dili hakkında temel bilgiye sahip olduğunuz varsayılmaktadır.
3. Microsoft Project Dosyası: Test amaçlı bir Microsoft Project dosyasını hazır bulundurun. Eğer elinizde yoksa örnek bir dosya oluşturabilirsiniz.

## Ad Alanlarını İçe Aktar
Öncelikle gerekli ad alanlarını içe aktaralım:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Adım 1: Proje Dosyasını Yükleyin
Microsoft Project dosyasını yükleyerek başlayın:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## 2. Adım: Görev ve Kaynak Ekleme
Şimdi projeye bir görev ve kaynak ekleyelim:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## 3. Adım: Kaynağı Göreve Atayın
Daha sonra kaynağı göreve atayacağız:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Adım 4: Farklı Ödev Türleriyle Çalışmak
Ayrıca birimleri veya maliyetleri içeren ödevlerle de çalışabilirsiniz:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Birim ve maliyet içeren atamaların özelliklerini 3. Adımda gösterildiği gibi ayarlayın
```
## Adım 5: Ödevleri Yazdırın
Proje için ödevleri yazdırın:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Atama ayrıntılarını yazdır
}
```
## Adım 6: Ödevi UID ile Alın
Atamaları UID'ye göre alabilirsiniz:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Adım 7: Salt Okunur Durumunu Kontrol Edin
Kaynak atama koleksiyonunun salt okunur olup olmadığını doğrulayın:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Adım 8: Koleksiyonu Listeye Dönüştürün ve Yineleyin
Koleksiyonu bir listeye dönüştürün ve üzerinde yineleyin:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Çözüm
Tebrikler! Aspose.Tasks for .NET'i kullanarak Microsoft Project'te kaynak atamalarını nasıl yöneteceğinizi öğrendiniz. Bu adımları izleyerek görevleri ve kaynakları verimli bir şekilde yönetebilir, proje yönetimini kolaylaştırabilirsiniz.
## SSS'ler
### S: Aspose.Tasks for .NET'i Microsoft Project dosyalarının farklı sürümleriyle kullanabilir miyim?
C: Evet, Aspose.Tasks for .NET, MPP, MPT ve XML formatları da dahil olmak üzere Microsoft Project dosyalarının çeşitli sürümlerini destekler.
### S: Aspose.Tasks for .NET'i satın almadan önce deneme sürümü mevcut mu?
 C: Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for .NET'i kullanırken herhangi bir sorunla karşılaşırsam nasıl destek alabilirim?
 C: Aspose.Tasks forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15).
### S: Aspose.Tasks for .NET için geçici lisanslar kullanabilir miyim?
 C: Evet, değerlendirme amaçlı olarak geçici lisanslar mevcuttur. Şuradan bir tane alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Tasks for .NET'in tam lisansını nereden satın alabilirim?
 C: Aspose çevrimiçi mağazasından tam lisans satın alabilirsiniz.[Burada](https://purchase.aspose.com/buy).