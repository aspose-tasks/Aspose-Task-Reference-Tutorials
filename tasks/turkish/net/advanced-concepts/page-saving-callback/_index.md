---
title: Aspose.Tasks'ta Sayfa Kaydederek Geri Aramayı Uygulama
linktitle: Aspose.Tasks'ta Sayfa Kaydederek Geri Aramayı Uygulama
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te, çok sayfalı belge çıktı akışlarının özelleştirilmiş şekilde işlenmesini sağlayan, sayfa tasarrufu sağlayan bir geri aramanın nasıl uygulanacağını öğrenin.
weight: 12
url: /tr/net/advanced-concepts/page-saving-callback/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Sayfa Kaydederek Geri Aramayı Uygulama

## giriiş

Bu eğitimde Aspose.Tasks for .NET'te sayfa tasarrufu geri çağırma işleminin nasıl uygulanacağını inceleyeceğiz. Bu özellik, çok sayfalı bir belgeyi kullanıcı tarafından sağlanan akışlara kaydetmemize olanak tanıyarak çıktıların işlenmesinde esneklik ve özelleştirme sunar.

## Önkoşullar:

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. C# programlama dili bilgisi: C# sözdizimi ve kavramları hakkında temel bir anlayışa sahip olmalısınız.
   
2.  Aspose.Tasks for .NET Kurulumu: Aspose.Tasks kütüphanesini geliştirme ortamınıza yüklediğinizden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).

3. Geliştirme Ortamı Kurulumu: .NET geliştirme için tercih ettiğiniz IDE'yi (örneğin, Visual Studio) ayarlayın.

## Ad Alanlarını İçe Aktar:

Başlamak için gerekli ad alanlarını C# kodunuza aktarmanız gerekir:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;

```

## Adım 1: Proje Nesnesi Oluşturun

 Bir örnek oluştur`Project` Mevcut bir proje dosyasını yükleyerek nesne:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## 2. Adım: Görüntü Kaydetme Seçeneklerini Yapılandırın

 Tanımlamak`ImageSaveOptions`ayarlayarak sayfa kaydetme davranışını özelleştirin.`PageSavingCallback` mülk:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

## 3. Adım: Projeyi Geri Aramayla Kaydetme

Yapılandırılmış görüntü kaydetme seçeneklerini kullanarak projeyi kaydedin:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## 4. Adım: Kaydedilen Sayfa Akışlarını İşleyin

Her sayfayı ayrı ayrı işlemek için geri arama tarafından sağlanan sayfa akışlarını yineleyin:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Her sayfa akışını işleyin
}
```

## Adım 5: Özel Sayfa Kaydederek Geri Aramayı Uygulayın

 uygulayan bir sınıf oluşturun.`IPageSavingCallback` sayfa kaydetme işlemini gerçekleştirecek arayüz:

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Herhangi bir temizleme veya sonlandırma işlemini gerçekleştirin
    }
}
```

## Çözüm:

Bu eğitimde, Aspose.Tasks for .NET'te, çok sayfalı belgeleri ayrı akışlara kaydetmemize olanak tanıyan, sayfa tasarrufu geri çağırma işlemini nasıl uygulayacağımızı öğrendik. Bu adımları izleyerek uygulamanızın işlevselliğini geliştirebilir ve özelleştirilmiş çıktı yönetimi elde edebilirsiniz.

## SSS'ler

### S1: Aspose.Tasks'ta sayfa kaydetme geri araması nedir?

Cevap1: Sayfa tasarrufu sağlayan geri arama, Aspose.Tasks'te, kullanıcıların her sayfa için ayrı ayrı akışlar sağlayarak çok sayfalı belgelerin kaydetme sürecini özelleştirmesine olanak tanıyan bir özelliktir.

### S2: Bu geri aramayı kullanarak sayfaları kaydetmek için farklı formatlar kullanabilir miyim?

Cevap2: Evet, sayfaları geri çağırmayla kaydetmek için Aspose.Tasks tarafından desteklenen PNG, JPEG, PDF vb. gibi çeşitli dosya formatlarını kullanabilirsiniz.

### S3: Aspose.Tasks .NET Core ile uyumlu mu?

C3: Evet, Aspose.Tasks, .NET Core'u destekleyerek geliştiricilerin özelliklerini platformlar arası uygulamalarda kullanmalarına olanak tanıyor.

### S4: Sayfa kaydetme işlemi sırasındaki hataları nasıl halledebilirim?

Cevap4: İstisnaları yönetmek ve uygulamanızda sağlamlık sağlamak için geri çağırma yöntemleri dahilinde hata işleme mekanizmalarını uygulayabilirsiniz.

### S5: Aspose.Tasks için daha fazla kaynağı ve desteği nerede bulabilirim?

 A5: ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) yardım için belgelere erişin[Burada](https://reference.aspose.com/tasks/net/) veya ek özellikleri ve lisanslama seçeneklerini keşfedin[Aspose.Tasks web sitesi](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
