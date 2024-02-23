---
title: Aspose.Tasks .NET'te Adım Adım WBS Kodu Yapılandırması
linktitle: Aspose.Tasks'ta WBS Kod Maskelerini Yapılandırma
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks'ı kullanarak .NET projelerinde adım adım WBS Kod Maskeleri yapılandırmasını keşfedin. Proje yönetimi yeteneklerini zahmetsizce geliştirin.
type: docs
weight: 14
url: /tr/net/view-wbs-code-configuration/wbs-code-masks/
---
## giriiş
Aspose.Tasks for .NET, geliştiricilerin .NET uygulamalarındaki proje yönetimi verilerini verimli bir şekilde yönetmelerine olanak tanıyan güçlü bir kitaplıktır. Bu eğitimde, Aspose.Tasks'ı kullanarak İş Kırılım Yapısı (WBS) Kod Maskelerini yapılandırma sürecini inceleyeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.Tasks for .NET Library: Kütüphaneyi şuradan indirip yükleyin:[.NET Belgeleri için Aspose.Tasks](https://reference.aspose.com/tasks/net/).
- Geliştirme Ortamı: Çalışan bir .NET geliştirme ortamı kurduğunuzdan emin olun.
- Belge Dizini: Proje dosyalarını depolamak için sisteminizde bir dizin seçin.
## Ad Alanlarını İçe Aktar
.NET projenize Aspose.Tasks ile çalışmak için gerekli ad alanlarını ekleyin:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## 1. Adım: Proje Örneği Oluşturun
Yeni bir proje örneği oluşturarak başlayın:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Adım 2: İKY Kodu Tanımını Tanımlayın
Projeniz için İKY Kod Tanımını ayarlayın:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 3. Adım: WBS Kodu Maskelerini Ekleyin
WBS Kod Maskelerini tanımlayın ve projeye ekleyin:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## 4. Adım: Görevler Oluşturun
Projeye görevler ekleyin:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Adım 5: Yeniden Hesapla
İKY kodlarının doğru şekilde uygulandığından emin olmak için projeyi yeniden hesaplayın:
```csharp
project.Recalculate();
```
## Adım 6: WBS Maskesi Bilgilerini Görüntüleyin
WBS maskeleri hakkındaki bilgilerin konsola çıktısı:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Adım 7: Projeyi Kaydet
Projeyi eklenen WBS kodlarıyla kaydedin:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Tebrikler! Aspose.Tasks projenizde WBS Kod Maskelerini başarıyla yapılandırdınız.
## Çözüm
Bu eğitimde, Aspose.Tasks for .NET'i kullanarak WBS Kod Maskelerini yapılandırmanın adım adım sürecini inceledik. Bu güçlü kitaplık, geliştiricilere .NET uygulamaları dahilinde proje yönetimi yeteneklerini geliştirmeleri için kusursuz bir yol sağlar.

## SSS'ler
### Aspose.Tasks'ı ücretsiz kullanabilir miyim?
 Aspose.Tasks, indirebileceğiniz ücretsiz bir deneme sürümü sunuyor[Burada](https://releases.aspose.com/).
### Ek desteği nerede bulabilirim?
 ziyaret edin[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15)topluluk desteği için.
### Geçici lisansı nasıl alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Ayrıntılı belgeler mevcut mu?
 Evet, kapsamlı belgeler mevcut[Burada](https://reference.aspose.com/tasks/net/).
### Aspose.Tasks'ı nereden satın alabilirim?
 Aspose.Tasks'ı satın alın[Burada](https://purchase.aspose.com/buy).