---
title: Aspose.Tasks'ta Bitmap için Geçersiz Boyut İstisnasını İşleme
linktitle: Aspose.Tasks'ta Bitmap için Geçersiz Boyut İstisnasını İşleme
second_title: Aspose.Tasks .NET API'si
description: Projeleri görüntü olarak kaydederken Aspose.Tasks for .NET'te BitmapInvalidSizeException'ın nasıl işleneceğini öğrenin. Adım adım rehberlik içeren kapsamlı eğitim.
type: docs
weight: 22
url: /tr/net/advanced-features/bitmap-invalid-size-exception/
---
## giriiş

 Bu eğitimde, aşağıdaki işlemleri ele alacağız:`BitmapInvalidSizeException` Aspose.Tasks for .NET ile çalışırken. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarını programlı olarak yönetmelerine olanak tanıyan, projeleri görüntü olarak kaydetme gibi görevleri mümkün kılan güçlü bir kütüphanedir. Ancak bazen bir projeyi resim olarak kaydetmeye çalışırken bir hatayla karşılaşabiliriz.`Invalid Size Exception`Bitmap ile ilgili. Bu eğitimin amacı, bu istisnayı etkili bir şekilde yakalama ve işleme süreci boyunca size rehberlik etmektir.

## Önkoşullar

Bu eğitime devam etmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1. C# programlama dilinin temel anlayışı.
2. .NET için Aspose.Tasks'ı yükledim.
3. Microsoft Project dosyalarıyla çalışmaya aşinalık.

## Ad Alanlarını İçe Aktar

Başlamadan önce gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Adım 1: Projeyi Başlatın ve Görünümü Tanımlayın

 İlk olarak, bir başlat`Project` nesneyi seçin ve bir görünüm tanımlayın, örneğin`GanttChartView`.

```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

## 2. Adım: Görüntü Kaydetme Seçeneklerini Belirleyin

Ardından, format ve zaman ölçeği de dahil olmak üzere görüntüyü kaydetme seçeneklerini belirtin.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

## 3. Adım: Zaman Ölçeği Birimini ve Sayımı Ayarlayın

Zaman ölçeği birimini ayarlayın ve gereksinimlerinize göre sayın. Bu örnekte zaman ölçeğini dakika olarak ayarladık.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

## Adım 4: Projeyi Resim Olarak Kaydet

Belirtilen seçenekleri kullanarak projeyi resim olarak kaydetmeyi deneyin.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

## Adım 5: İstisnayı Yakala ve İşle

 Yakalamak için istisna işlemeyi uygulayın`BitmapInvalidSizeException` görüntü kaydetme işlemi sırasında meydana gelirse.

```csharp
try
{
    // Projeyi resim olarak kaydetmeyi deneyin
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // İstisnayı ele alın
    Console.WriteLine(ex.Message);
}
```

## Çözüm

 Sonuç olarak, işleme`BitmapInvalidSizeException` Aspose.Tasks for .NET'te projeleri görüntü olarak kaydederken uygulamalarınızın sorunsuz yürütülmesi açısından çok önemlidir. Bu eğitimde özetlenen adımları izleyerek bu istisnayı etkili bir şekilde yakalayıp yönetebilir, böylece proje yönetimi çözümlerinizin sağlamlığını artırabilirsiniz.

## SSS'ler

### S1: Aspose.Tasks'ta BitmapInvalidSizeException'ın nedeni nedir?

Y1: Bu özel durum, bir projeyi geçersiz bit eşlem boyutu parametreleriyle görüntü olarak kaydetmeye çalışırken ortaya çıkar.

### S2: Bir projeyi görüntü olarak kaydederken zaman ölçeğini özelleştirebilir miyim?

C2: Evet, eğitimde gösterildiği gibi zaman ölçeği birimini ve sayımı gereksinimlerinize göre ayarlayabilirsiniz.

### S3: Aspose.Tasks for .NET ile çalışmak için daha fazla kaynağı nerede bulabilirim?

Cevap3: Kapsamlı rehberlik ve yardım için Aspose.Tasks tarafından sağlanan belgeleri ve destek forumlarını inceleyebilirsiniz.

### S4: Aspose.Tasks, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mudur?

Cevap4: Evet, Aspose.Tasks, Microsoft Project dosyalarının çeşitli sürümlerini destekleyerek kusursuz bir birlikte çalışabilirlik sağlar.

### S5: Aspose.Tasks için nasıl geçici lisans alabilirim?

Cevap5: Makalede verilen bağlantıdan değerlendirme amaçlı geçici lisans alabilirsiniz.