---
title: Aspose.Tasks'ta Ödevlerle Çalışmak
linktitle: Aspose.Tasks'ta Ödevlerle Çalışmak
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks'ı kullanarak .NET'te proje atamalarını nasıl yöneteceğinizi öğrenin. Kaynak planlaması için farklı konturları keşfedin.
type: docs
weight: 13
url: /tr/net/advanced-features/working-with-assignment/
---
## giriiş

Bu eğitimde Aspose.Tasks for .NET'te ödevlerle nasıl çalışılacağını inceleyeceğiz. Atamalar, kaynakları görevlere tahsis ettiğinden, planlamaya ve ilerlemeyi izlemeye yardımcı olduğundan proje yönetiminde çok önemlidir. Aspose.Tasks'ı kullanarak çeşitli hatlara sahip kaynak atama zaman aşamalı verileri oluşturmaya odaklanacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1.  Aspose.Tasks for .NET Kurulumu: Aspose.Tasks for .NET kütüphanesini aşağıdaki adresten indirip yükleyin:[İndirme: {link](https://releases.aspose.com/tasks/net/).
2. C# ve .NET Framework'ün Temel Anlaşılması: Takip etmek için C# programlama dili ve .NET framework kavramlarına aşinalık gereklidir.

## Ad Alanlarını İçe Aktar

Gerekli ad alanlarını C# projenize aktardığınızdan emin olun:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Adım 1: Proje ve Görev Oluşturun

Yeni bir proje oluşturup ona bir görev ekleyerek başlayalım. Görevin başlangıç tarihini, süresini ve bitiş tarihini ayarlayın:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## 2. Adım: Kaynak Ekleme ve Göreve Atama

Daha sonra projeye bir kaynak ekleyin ve onu önceden oluşturulan göreve atayın:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Adım 3: Farklı Konturlara Sahip Zaman Aşamalı Veriler Oluşturun

Şimdi kaynak ataması için farklı konturlara sahip zaman aşamalı veriler oluşturalım:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Adım 4: Konturları Değiştirin ve Veri Oluşturun

Kontur tipini değiştirebilir ve buna göre zaman aşamalı veriler üretebiliriz. İşte bazı örnekler:

```csharp
// Konturu değiştir
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Zaman aşamalı veriler oluşturun ve yazdırın
// Diğer kontur türleri için bu adımı tekrarlayın
```

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'te ödevlerle nasıl çalışılacağını öğrendik. Çeşitli konturlara sahip kaynak atama zaman aşamalı verilerinin oluşturulmasını araştırdık. Bu bilgi proje yönetimi senaryolarında son derece yararlı olabilir.

## SSS'ler

### S1: .NET uygulamamda görevleri planlamak için Aspose.Tasks'ı kullanabilir miyim?

Cevap1: Evet, Aspose.Tasks, .NET uygulamalarında görev planlama ve yönetim için kapsamlı API'ler sağlar.

### S2: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?

 C2: Evet, şu adresten ücretsiz denemeden yararlanabilirsiniz:[Burada](https://releases.aspose.com/).

### S3: Aspose.Tasks'ta görev veya kaynak sayısında herhangi bir sınırlama var mı?

Cevap3: Aspose.Tasks, projelerinizde yönetebileceğiniz görev veya kaynak sayısına herhangi bir sınırlama getirmez.

### S4: Aspose.Tasks'ta kaynak atamalarının konturlarını özelleştirebilir miyim?

C4: Evet, bu eğitimde gösterildiği gibi proje gereksinimlerinize göre kaplumbağa, çan, zirve vb. çeşitli konturları ayarlayabilirsiniz.

### S5: Aspose.Tasks ile ilgili sorgular için desteği nerede bulabilirim?

Cevap 5: Şu adreste destek bulabilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) uzmanların ve topluluk üyelerinin aktif olarak tartışmalara katıldığı yer.