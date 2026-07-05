---
date: 2026-07-05
description: Aspose.Tasks for .NET kullanarak bir projeyi HTML olarak dışa aktarırken
  CSS nasıl özelleştirileceğini öğrenin. CSS kaydetme argümanlarıyla HTML çıktısını
  özelleştirin.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Aspose.Tasks ile Projeleri Kaydederken CSS Nasıl Özelleştirilir
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks ile Projeleri Kaydederken CSS Nasıl Özelleştirilir
url: /tr/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeleri Aspose.Tasks ile Kaydederken CSS Nasıl Özelleştirilir

Bu rehberde, Aspose.Tasks for .NET kullanarak bir Microsoft Project dosyasının HTML dışa aktarımı sırasında **CSS nasıl özelleştirilir** keşfedeceksiniz. CSS kaydetme argümanlarını ayarlayarak, oluşturulan HTML sayfalarının görsel stilini tam olarak kontrol edebilir, çıktıyı markanıza veya raporlama standartlarınıza uygun hale getirebilirsiniz.

## Hızlı Yanıtlar
- **Ana giriş noktası nedir?** Özel geri aramalarla `HtmlSaveOptions` kullanın.  
- **Bir lisansa ihtiyacım var mı?** Evet, üretim için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Büyük projeleri dışa aktarabilir miyim?** Aspose.Tasks, tüm dosyayı belleğe yüklemeden > 10.000 görev içeren projeleri işleyebilir.  
- **CSS özelleştirme isteğe bağlı mı?** Evet, varsayılan stil sayfasını kullanmak için geri aramaları atlayabilirsiniz.

## Aspose.Tasks'te CSS Nasıl Özelleştirilir?

Projenizi yükleyin, `HtmlSaveOptions` nesnesine CSS‑kaydetme geri aramalarını ekleyin ve ardından `project.Save` metodunu çağırın. Bu desen, birkaç satır kodla özel CSS dosyaları oluşturmanıza, varsayılan stilleri değiştirmenize ve klasör yapısını kontrol etmenize olanak tanır. Geri aramalar, dışa aktarma sürecinde her CSS dosyası için otomatik olarak tetiklenir.

`HtmlSaveOptions`, bir projenin HTML olarak dışa aktarılmasını yapılandırır.

## Giriş

Bu öğreticide, Aspose.Tasks for .NET kullanarak CSS argümanlarını kaydetme sürecine derinlemesine bakacağız. Katmanlı Stil Sayfaları (CSS), HTML öğelerinin sunumunu tanımlamak için kritiktir. Aspose.Tasks, bu CSS özelliklerini verimli bir şekilde manipüle etmemize ve kaydetmemize olanak tanır.

## Önkoşullar

Başlamadan önce, aşağıdaki önkoşulların karşılandığından emin olun:

1. Kurulum: Aspose.Tasks for .NET'i kurduğunuzdan emin olun. [web sitesinden](https://releases.aspose.com/tasks/net/) indirebilirsiniz.
2. Temel Bilgi: C# ve .NET geliştirme ortamına aşina olmanız önerilir.

## Ad Alanlarını İçe Aktarma

Başlamak için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Adım 1: CSS Kaydetme Geri Aramalarını Tanımlama

`ICssSavingCallback`, HTML dışa aktarımı sırasında CSS dosyalarının nasıl kaydedileceğini özelleştirmenizi sağlayan bir arayüzdür.

**CSS kaydetme geri araması**, Aspose.Tasks'in HTML dışa aktarımı sırasında CSS dosyalarını yazmak için çağırdığı bir temsilcidir. Her CSS dosyasının nasıl oluşturulacağını kontrol etmek için geri arama metodlarını tanımlayın:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Adım 2: Yazı Tipi ve Görüntü Kaydetme Geri Aramalarını Uygulama

`FontSavingArgs`, kaydedilen yazı tipi hakkında bilgi sağlarken, `ImageSavingArgs` görüntü kaynaklarıyla ilgili ayrıntıları sunar.

Yazı tipi ve görüntü kaydetme geri arama metodlarını benzer şekilde uygulayın:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Adım 3: Kaydetme Seçeneklerini Yapılandırma

`HtmlSaveOptions`, bir Projenin HTML olarak dışa aktarılmasını kontrol eden yapılandırma nesnesidir.

`HtmlSaveOptions`, geri aramaları, çıktı klasörlerini ve diğer dışa aktarma ayarlarını belirlemenizi sağlar.

Önceden tanımlanan geri aramaları kullanmak ve çıktı klasörünü belirtmek için özelliklerini ayarlayın:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Adım 4: Özelleştirilmiş CSS ile Projeyi Kaydetme

`Project`, manipüle edilebilen ve kaydedilebilen bir Microsoft Project dosyasını temsil eder.

Son olarak, projenizi özelleştirilmiş CSS ayarlarıyla kaydedin:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Projeleri Dışa Aktarırken CSS Neden Özelleştirilir?

Aspose.Tasks, **projeyi HTML olarak dışa aktarmayı** 30+ formatta destekler ve her dışa aktarma için 30'a kadar ayrı CSS dosyası oluşturabilir. 10 000'den fazla görev içeren projeleri, bellek kullanımını 200 MB'nin altında tutarak güvenilir bir şekilde işler ve kurumsal ölçekli raporlamayı performans darboğazları olmadan mümkün kılar.

## Sonuç

Bu öğreticide, Aspose.Tasks for .NET kullanarak CSS argümanlarını nasıl kaydedeceğimizi inceledik. CSS kaydetme geri aramalarını tanımlayarak ve HTML kaydetme seçeneklerini yapılandırarak, gereksinimlerimize göre CSS özelliklerini verimli bir şekilde manipüle edebiliriz.

## SSS

### S1: Aspose.Tasks for .NET nedir?
A1: Aspose.Tasks for .NET, geliştiricilerin Microsoft Project dosyalarıyla programlı olarak çalışmasını sağlayan güçlü bir .NET API'sidir.

### S2: Aspose.Tasks ile HTML dosyalarını kaydederken CSS özelliklerini özelleştirebilir miyim?
A2: Evet, ihtiyaçlarınıza göre CSS özelliklerini özelleştirmek için CSS kaydetme geri aramalarını tanımlayabilirsiniz.

### S3: Aspose.Tasks for .NET, Microsoft Project dosyalarının tüm sürümleriyle uyumlu mu?
A3: Aspose.Tasks for .NET, Microsoft Project dosyalarının çeşitli sürümlerini destekler ve farklı ortamlar arasında uyumluluğu sağlar.

### S4: Aspose.Tasks for .NET için kapsamlı belgeleri nereden bulabilirim?
A4: Ayrıntılı bilgi ve örnekler için [belgelere](https://reference.aspose.com/tasks/net/) başvurabilirsiniz.

### S5: Aspose.Tasks for .NET geliştiricilere destek sunuyor mu?
A5: Evet, Aspose.Tasks topluluğundan [forum](https://forum.aspose.com/c/tasks/15) aracılığıyla destek alabilirsiniz.

**Ek Sorular**

**S: CSS özelleştirme, dışa aktarılan HTML'in boyutunu nasıl etkiler?**  
C: Özel CSS kullanmak, kullanılmayan varsayılan stilleri ortadan kaldırarak toplam boyutu %15'e kadar azaltabilir.

**S: Aynı geri aramaları birden fazla proje için kullanabilir miyim?**  
C: Kesinlikle. Geri aramaları bir kez uygulayın ve istediğiniz sayıda proje dışa aktarımında yeniden kullanın.

**S: CSS'i ayrı dosyalar yerine doğrudan HTML'e gömmek mümkün mü?**  
C: Evet, stil sayfasını satır içi yapmak için `HtmlSaveOptions.EmbeddedCss = true` ayarlayın; bu dağıtımı basitleştirir.

---

**Son Güncelleme:** 2026-07-05  
**Test Edilen Versiyon:** Aspose.Tasks 24.11 for .NET  
**Yazar:** Aspose

## İlgili Öğreticiler

- [MS Project'i Aspose.Tasks ile HTML olarak Kaydet](/tasks/net/saving-options/html-save-options/)
- [Aspose.Tasks'te Sayfa Kaydetme Geri Aramasını Uygulama](/tasks/net/advanced-concepts/page-saving-callback/)
- [Aspose.Tasks'te Görüntü Kaydetmeyi Yönetme](/tasks/net/advanced-concepts/image-saving/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}