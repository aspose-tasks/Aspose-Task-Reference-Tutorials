---
title: Aspose.Tasks ile MS Project Options Primavera'yı kaydedin
linktitle: Aspose.Tasks için Primavera Kaydetme Seçenekleri
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak Primavera için MS Project seçeneklerini sorunsuz bir şekilde nasıl kaydedeceğinizi keşfedin. Adım adım eğitimimizi takip edin.
type: docs
weight: 14
url: /tr/net/saving-options/primavera-save-options/
---
## giriiş
Aspose.Tasks for .NET, geliştiricilerin .NET uygulamalarında Microsoft Project dosyalarıyla sorunsuz bir şekilde çalışmasına olanak tanıyan güçlü bir kitaplıktır. Sunduğu önemli işlevlerden biri, popüler bir proje yönetimi yazılımı olan Primavera için MS Project seçeneklerini kaydetme yeteneğidir. Bu eğitimde bunu Aspose.Tasks kullanarak nasıl başaracağımızı inceleyeceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- C# ve .NET çerçevesine ilişkin temel anlayış.
-  Aspose.Tasks for .NET, geliştirme ortamınıza kuruludur. Değilse indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
- Deneme amaçlı örnek bir MS Project dosyası.

## Ad Alanlarını İçe Aktar
Öncelikle gerekli ad alanlarını C# kodumuza aktaralım:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Adım 1: MS Proje Dosyasını Yükleyin
Çalışmayı planladığınız MS Project dosyasını C# uygulamanıza yükleyerek başlayın. Bunu kullanarak yapabilirsiniz`Project` Aspose.Tasks tarafından sağlanan sınıf.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Adım 2: Primavera Kaydetme Seçeneklerini Tanımlayın
Daha sonra Primavera kaydetme seçeneklerini oluşturun ve bunları ihtiyaçlarınıza göre özelleştirin. Bu adım, etkinlik kimliği öneki, son eki, artışı ve etkinlik kimliklerinin yeniden numaralandırılıp numaralandırılmayacağı gibi parametrelerin belirtilmesini içerir.
```csharp
var options = new PrimaveraSaveOptions
{
    ActivityIdPrefix = "TEST",
    ActivityIdSuffix = 10000,
    ActivityIdIncrement = 5,
    RenumberActivityIds = true
};
```
## Adım 3: Primavera için MS Proje Seçeneklerini Kaydetme
 Artık proje dosyasını yüklediğinize ve Primavera kaydetme seçeneklerini tanımladığınıza göre, Primavera seçeneklerini kaydetme zamanı geldi. Kullan`Save` tarafından sağlanan yöntem`Project` İstenilen çıktı dosyası yolunu ve Primavera kaydetme seçeneklerini ileten sınıf.
```csharp
project.Save(DataDir + "WorkWithPrimaveraSaveOptions_out.xer", options);
```

## Çözüm
Sonuç olarak, Aspose.Tasks for .NET'ten yararlanmak, geliştiricilerin Primavera kaydetme seçenekleri de dahil olmak üzere MS Project dosyalarını sorunsuz bir şekilde yönetmelerine olanak tanır. Bu öğreticide özetlenen adımları izleyerek bu işlevselliği .NET uygulamalarınızla verimli bir şekilde tümleştirebilirsiniz.
## SSS'ler
### S: Primavera için MS Project seçeneklerini kaydederken etkinlik kimlikleri dışında diğer parametreleri de özelleştirebilir miyim?
C: Evet, Aspose.Tasks, kaynak tahsisi ve görev planlama da dahil olmak üzere çok çeşitli özelleştirme seçenekleri sunuyor.
### S: Aspose.Tasks, Primavera dışında başka proje yönetimi yazılımlarını da destekliyor mu?
C: Evet, Aspose.Tasks, Oracle Primavera, Microsoft Project Server ve daha fazlası gibi popüler proje yönetimi araçlarıyla uyumlu çeşitli formatları destekler.
### S: Aspose.Tasks hem küçük ölçekli hem de kurumsal düzeydeki projeler için uygun mudur?
C: Kesinlikle, Aspose.Tasks, her boyutta proje üzerinde çalışan geliştiricilerin ihtiyaçlarını karşılamak, ölçeklenebilirlik ve sağlam performans sunmak üzere tasarlanmıştır.
### S: Satın almadan önce Aspose.Tasks'ı ücretsiz deneyebilir miyim?
 C: Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/) özelliklerini ve yeteneklerini keşfetmek için.
### S: Aspose.Tasks'ı kullanırken sorunlarla karşılaşırsam veya sorularım olursa nereden destek alabilirim?
C: Aspose.Tasks topluluğundan ve destek ekibinden yardım isteyebilirsiniz.[forum](https://forum.aspose.com/c/tasks/15).