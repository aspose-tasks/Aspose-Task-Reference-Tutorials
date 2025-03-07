---
title: Aspose.Tasks'ta Görüntü Kaydetmeyi Yönetme
linktitle: Aspose.Tasks'ta Görüntü Kaydetmeyi Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te görüntü kaydetme işlemini adım adım yönergelerle nasıl yapacağınızı öğrenin. Görüntü kaydetme işlevini .NET uygulamalarınıza sorunsuz bir şekilde entegre edin.
weight: 10
url: /tr/net/advanced-concepts/image-saving/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Görüntü Kaydetmeyi Yönetme

## giriiş

Bu eğitimde Aspose.Tasks for .NET'te görüntü kaydetme işlemini ele alacağız. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarını programlı olarak değiştirmesine olanak tanıyan güçlü bir API'dir. Proje dosyalarıyla çalışırken sık karşılaşılan görevlerden biri, çizelgeler, grafikler veya diğer görsel öğeleri içerebilen görüntüleri kaydetme ihtiyacıdır. Süreci adım adım inceleyerek, baştan sona netlik ve anlayış sağlayacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1. Visual Studio: Sisteminizde Visual Studio'nun kurulu olduğundan emin olun.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET'i şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
3. Temel C# Anlayışı: C# programlama dilinin temellerine aşina olun.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli namespace’leri projemize aktaralım:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Adım 1: Proje Nesnesi Oluşturun

Microsoft Project dosyanızdan bir Project nesnesi oluşturarak başlayın:

```csharp
var project = new Project("Project1.mpp");
```

## 2. Adım: Kaydetme Seçeneklerini Tanımlayın

Sayfaları ve diğer ayarları belirterek projeniz için kaydetme seçeneklerini tanımlayın:

```csharp
var options = GetSaveOptions(1);
```

## Adım 3: Projeyi HTML olarak kaydedin

Projeyi belirtilen seçeneklerle HTML olarak kaydedin:

```csharp
project.Save("document_out.html", options);
```

## Adım 4: Görüntü Kaydederek Geri Aramayı Uygulayın

Görüntü kaydetme işlemini gerçekleştirmek için ImageSavingCallback arayüzünü uygulayın:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Görüntü kaydetme mantığı buraya gelir
    }
}
```

## Adım 5: Görüntüleri Belirtilen Dizine Kaydetme

ImageSaving yönteminde, görüntüleri istenen dizine kaydetme mantığını belirtin:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Yuvalanmış kaynakları kaydet
}
else
{
    // Düzenli kaynaklardan tasarruf edin
}
```

## Adım 6: Kaydetme Seçeneklerini Belirleyin

CSS, yazı tipleri ve resimler için geri aramalar da dahil olmak üzere kaydetme seçeneklerini belirtin:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Kaydetme seçeneklerini burada belirtin
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Çözüm

Sonuç olarak, Aspose.Tasks for .NET'te görüntü kaydetme işlemi, kaydetme seçeneklerini tanımlamayı ve kaydetme sürecini etkili bir şekilde yönetmek için geri aramaları uygulamayı içerir. Bu öğreticide özetlenen adımları izleyerek görüntü kaydetme işlevini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.

## SSS'ler

### S1: Aspose.Tasks'ı HTML'nin yanı sıra diğer formatlardaki proje dosyalarını değiştirmek için kullanabilir miyim?

Cevap1: Evet, Aspose.Tasks PDF, XLSX ve MPP gibi çeşitli formatları destekler.

### S2: Aspose.Tasks bulut depolama entegrasyonu için destek sağlıyor mu?

Cevap2: Evet, Aspose.Tasks, Amazon S3 ve Google Drive gibi popüler bulut depolama hizmetleriyle çalışmak için API'ler sunuyor.

### S3: Aspose.Tasks .NET Core ile uyumlu mu?

Cevap3: Evet, Aspose.Tasks, .NET Core ile uyumludur ve platformlar arası uygulamalar geliştirmenize olanak tanır.

### S4: Kaydedilen görsellerin görünümünü özelleştirebilir miyim?

Cevap4: Evet, geri çağırma yöntemlerinde görüntü kaydetme mantığını değiştirerek kaydedilen görüntülerin görünümünü özelleştirebilirsiniz.

### S5: Aspose.Tasks değerlendirme amaçlı deneme sürümleri sunuyor mu?

 Cevap5: Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[Burada](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
