---
title: Aspose.Tasks'ta Baseline Collection ile Çalışmak
linktitle: Aspose.Tasks'ta Baseline Collection ile Çalışmak
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te temel çizgileri verimli bir şekilde nasıl yöneteceğinizi öğrenin. Adım adım rehberlik için kapsamlı eğitimimizi takip edin.
type: docs
weight: 20
url: /tr/net/advanced-features/working-with-baseline-collection/
---
## giriiş

Aspose.Tasks for .NET, geliştiricilerin .NET uygulamalarında Microsoft Project dosyalarıyla sorunsuz bir şekilde çalışmasına olanak tanıyan güçlü bir kitaplıktır. Pek çok özelliğinin yanı sıra, projeler içindeki temel çizgilerin yönetilmesi için güçlü bir destek sağlar. Temel çizgiler, orijinal proje planını mevcut durumla karşılaştırmanıza izin vererek proje ilerlemesinin daha iyi izlenmesine ve analiz edilmesine olanak tanıdığından proje yönetimi için çok önemlidir.

## Önkoşullar

Aspose.Tasks'ta temel koleksiyonlarla çalışmaya başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. Visual Studio: Sisteminize Visual Studio IDE'yi yükleyin.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini aşağıdaki adresten indirip yükleyin:[İndirme: {link](https://releases.aspose.com/tasks/net/).
3. Temel C# anlayışı: C# programlama diline aşina olun.
4. Microsoft Project dosyası: Test amacıyla bir Microsoft Project dosyasını (.mpp) hazır bulundurun.

## Ad Alanlarını İçe Aktar

Aspose.Tasks'ta temel koleksiyonlarla çalışmaya başlamak için aşağıdaki ad alanlarını içe aktarmanız gerekir:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Şimdi her örneği birden fazla adıma ayıralım:

## Adım 1: Proje Dosyasını Yükleyin

İlk olarak Aspose.Tasks'ı kullanarak Microsoft Project dosyasını yükleyin:

```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## 2. Adım: Kaynak Alın

Daha sonra projeden istenen kaynağı alın:

```csharp
var resource = project.Resources.GetByUid(1);
```

## Adım 3: Temel Bilgiyi Görüntüleyin

Şimdi kaynakla ilişkili taban çizgileri hakkındaki bilgileri görüntüleyin:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Adım 4: Temel Çizgiler Üzerinden Yineleme Yapın

Kaynakla ilişkili her bir temel çizgiyi yineleyin ve ilgili bilgileri yazdırın:

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Adım 5: Taban Çizgilerini Kaldır

Kaynakla ilişkili tüm temel çizgileri silin:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'te temel koleksiyonlarla nasıl çalışılacağını araştırdık. Adım adım kılavuzu takip ederek, .NET uygulamalarınızdaki temel çizgileri kolayca yönetebilir ve etkili proje takibi ve analizine olanak tanıyabilirsiniz.

## SSS'ler

### S1: Aspose.Tasks büyük proje dosyalarını yönetebilir mi?

Cevap1: Evet, Aspose.Tasks büyük proje dosyalarını verimli bir şekilde yönetecek ve sorunsuz performans sağlayacak şekilde optimize edilmiştir.

### S2: Aspose.Tasks, Microsoft Project'in tüm sürümleriyle uyumlu mudur?

Cevap2: Aspose.Tasks, Microsoft Project'in çeşitli sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.

### S3: Aspose.Tasks'ta taban çizgilerini özelleştirebilir miyim?

C3: Evet, Aspose.Tasks for .NET'i kullanarak temelleri proje gereksinimlerinize göre özelleştirebilirsiniz.

### S4: Aspose.Tasks bulut platformları için destek sunuyor mu?

Cevap4: Evet, Aspose.Tasks, popüler bulut platformlarıyla entegrasyon desteği sağlayarak dağıtımda esneklik sunar.

### S5: Aspose.Tasks kullanıcılarının yardım isteyebileceği ve bilgi paylaşabileceği bir topluluk forumu var mı?

 A5: Evet, ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) toplulukla etkileşime geçmek ve uzmanlardan yardım almak.