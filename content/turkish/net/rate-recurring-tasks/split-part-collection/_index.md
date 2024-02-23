---
title: Aspose.Tasks'ta Bölünmüş Parçaların MS Projesini Toplayın
linktitle: Aspose.Tasks'ta Parçalı Parçaların Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project'te bölünmüş parçaları nasıl toplayacağınızı öğrenin. Bu kapsamlı eğitim, süreç boyunca size adım adım rehberlik eder.
type: docs
weight: 19
url: /tr/net/rate-recurring-tasks/split-part-collection/
---
## giriiş
Bu eğitimde, Aspose.Tasks for .NET kullanarak MS Project'te bölünmüş parçaların nasıl toplanacağını açıklayacağız. Görevleri parçalara bölmek proje yönetiminin çok önemli bir yönü olabilir ve Aspose.Tasks bunu verimli bir şekilde ele almak için uygun yöntemler sağlar.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Aspose.Tasks for .NET Kurulumu: Aspose.Tasks for .NET'i yüklediğinizden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
2. Temel C# Bilgisi: C# programlama diline aşina olmak, C#'ta kod parçacıkları yazacağımız için faydalı olacaktır.

## Ad Alanlarını İçe Aktar
C# projenize gerekli ad alanlarını ekleyin:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## 1. Adım: Projenizi Kurun
Öncelikle tercih ettiğiniz IDE'de yeni bir proje oluşturun ve Aspose.Tasks for .NET'e doğru şekilde başvurulduğundan emin olun.
## Adım 2: Proje Nesnesini Başlatın
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
MS Project dosyanızın yolunu içeren yeni bir Project nesnesi başlatın.
## Adım 3: Görevi Alın ve Bölünmüş Parçalar Üzerinde Yineleyin
```csharp
var task = project.RootTask.Children.GetById(1);
// Bölünmüş parçalar üzerinde yineleme
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Görevi projeden alın ve bölünmüş parçaları üzerinde yineleyerek başlangıç ve bitiş tarihlerini yazdırın.
## Adım 4: Dizine Göre Bölünmüş Parçayı Alın
```csharp
// Parçayı dizine göre al
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Belirli bir bölünmüş parçayı dizine göre alın ve başlangıç tarihini yazdırın.

## Çözüm
MS Project dosyalarındaki bölünmüş parçaları yönetmek, proje yönetimi verimliliğini önemli ölçüde artırabilir. Aspose.Tasks for .NET, bölünmüş görevlerin sorunsuz bir şekilde yönetilmesi için sezgisel API'ler sağlayarak bu süreci basitleştirir.
## SSS'ler
### S: Çalışma zamanı sırasında görevleri dinamik olarak bölebilir miyim?
C: Evet, Aspose.Tasks for .NET'i kullanarak görevleri programlı olarak bölebilirsiniz.
### S: Aspose.Tasks, MS Project dosyalarının tüm sürümlerini destekliyor mu?
C: Aspose.Tasks, MS Project dosyalarının çeşitli sürümlerini destekleyerek farklı platformlar arasında uyumluluk sağlar.
### S: Test amaçlı bir deneme sürümü mevcut mu?
 C: Evet, adresinden ücretsiz deneme sürümünü edinebilirsiniz.[Burada](https://releases.aspose.com/) Evrim için.
### S: Projelerim için nasıl geçici lisans alabilirim?
 C: Geçici lisanslar şuradan alınabilir:[Burada](https://purchase.aspose.com/temporary-license/) kısa süreli kullanım için.
### S: Aspose.Tasks ile ilgili nereden yardım veya destek alabilirim?
 C: Aspose.Tasks forumunu ziyaret edebilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15) topluluktan veya Aspose destek ekibinden yardım istemek için.