---
title: Aspose.Tasks'ta CSS Argümanlarını Kaydetme
linktitle: Aspose.Tasks'ta CSS Argümanlarını Kaydetme
second_title: Aspose.Tasks .NET API'si
description: HTML çıktısını özelleştirmek için Aspose.Tasks for .NET'te CSS argümanlarını nasıl kaydedeceğinizi öğrenin. Özel CSS ayarlarıyla sunumu geliştirin.
type: docs
weight: 20
url: /tr/net/calendar-scheduling/css-saving-arguments/
---
## giriiş

Bu eğitimde Aspose.Tasks for .NET'i kullanarak CSS argümanlarını kaydetme sürecini ayrıntılı olarak ele alacağız. Basamaklı Stil Sayfaları (CSS), HTML öğelerinin sunumunu tanımlamak için çok önemlidir. Aspose.Tasks, bu CSS niteliklerini verimli bir şekilde değiştirmemize ve kaydetmemize olanak tanır.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Kurulum: Aspose.Tasks for .NET'i kurduğunuzdan emin olun. adresinden indirebilirsiniz.[İnternet sitesi](https://releases.aspose.com/tasks/net/).

2. Temel Bilgi: C# ve .NET geliştirme ortamına aşinalık önerilir.

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## Adım 1: CSS Kaydedilen Geri Aramaları Tanımlayın

İlk olarak, CSS dosyalarının kaydedilmesini sağlamak için CSS kaydetme geri çağırma yöntemlerini tanımlıyoruz:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // CSS kaydetme mantığınızı buraya uygulayın
    }
}
```

## Adım 2: Yazı Tipi ve Resim Kaydederek Geri Aramaları Uygulayın

Daha sonra, yazı tipi ve resim tasarrufu sağlayan geri çağırma yöntemlerini benzer şekilde uygulayın:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Yazı tipi kaydetme mantığınızı burada uygulayın
}

public void ImageSaving(ImageSavingArgs args)
{
    // Görüntü kaydetme mantığınızı burada uygulayın
}
```

## 3. Adım: Kaydetme Seçeneklerini Yapılandırın

Şimdi, uygulanan geri aramaları kullanmak için HTML kaydetme seçeneklerini yapılandırın:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //HTML kaydetme seçeneklerini yapılandırma
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Adım 4: Projeyi Özelleştirilmiş CSS ile Kaydetme

Son olarak projenizi özelleştirilmiş CSS ayarlarıyla kaydedin:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Çözüm

Bu eğitimde Aspose.Tasks for .NET kullanarak CSS argümanlarının nasıl kaydedileceğini araştırdık. CSS kaydetme geri aramalarını tanımlayarak ve HTML kaydetme seçeneklerini yapılandırarak, CSS niteliklerini gereksinimlerimize göre verimli bir şekilde değiştirebiliriz.

## SSS

### S1: Aspose.Tasks for .NET nedir?

Cevap1: Aspose.Tasks for .NET, geliştiricilerin Microsoft Project dosyalarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir .NET API'sidir.

### S2: HTML dosyalarını Aspose.Tasks ile kaydederken CSS niteliklerini özelleştirebilir miyim?

Cevap2: Evet, CSS niteliklerini ihtiyaçlarınıza göre özelleştirmek için CSS kaydetme geri aramalarını tanımlayabilirsiniz.

### S3: Aspose.Tasks for .NET, Microsoft Project dosyalarının tüm sürümleriyle uyumlu mudur?

Cevap3: Aspose.Tasks for .NET, Microsoft Project dosyalarının çeşitli sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.

### S4: Aspose.Tasks for .NET'in kapsamlı belgelerini nerede bulabilirim?

A4: başvurabilirsiniz[dokümantasyon](https://reference.aspose.com/tasks/net/) detaylı bilgi ve örnekler için.

### S5: Aspose.Tasks for .NET geliştiricilere destek sunuyor mu?

 Cevap5: Evet, Aspose.Tasks topluluğundan destek alabilirsiniz.[forum](https://forum.aspose.com/c/tasks/15).