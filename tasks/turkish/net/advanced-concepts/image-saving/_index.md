---
date: 2026-03-05
description: Aspose.Tasks for .NET kullanarak resimleri kaydetmeyi, resimli HTML oluşturmayı
  ve resim dışa aktarmayı özelleştirmeyi öğrenin. Projeyi HTML olarak kaydetmek için
  adım adım rehber.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks for .NET ile Görselleri Nasıl Kaydedilir
url: /tr/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET ile Görüntüleri Kaydetme

## Giriş

Bu öğreticide, Microsoft Project dosyalarından **görüntüleri nasıl kaydedeceğinizi** Aspose.Tasks API for .NET kullanarak keşfedeceksiniz. Raporlara grafik eklemeniz, proje görselleri içeren HTML sayfaları oluşturmanız ya da sadece diyagram kaynaklarını dışa aktarmanız gerektiğinde, aşağıdaki adımlar proje nesnesinin oluşturulmasından görüntü‑dışa aktarma geri çağrılarının özelleştirilmesine kadar tüm süreci size rehberlik edecektir.

## Hızlı Yanıtlar
- **Aspose.Tasks içinde “görüntüleri nasıl kaydederim” ne anlama geliyor?**  
  Görsel kaynakların diske nerede ve nasıl yazılacağını kontrol etmek için `IImageSavingCallback` arayüzünün kullanılmasını ifade eder.
- **Gömülü görüntülerle bir projeyi HTML olarak kaydedebilir miyim?**  
  Evet, `HtmlSaveOptions` ile görüntü‑kaydetme geri çağrıları birlikte kullanılarak **projeyi HTML olarak kaydedebilir** ve tüm oluşturulan görüntüleri dahil edebilirsiniz.
- **Görüntü dışa aktarımı için lisansa ihtiyacım var mı?**  
  Geçici bir değerlendirme lisansı test için yeterlidir; üretim kullanımı için tam lisans gereklidir.
- **Hangi .NET sürümleri destekleniyor?**  
  Aspose.Tasks for .NET, .NET Framework 4.5+, .NET Core 3.1+, ve .NET 5/6+ sürümlerini destekler.
- **Görüntü dışa aktarımını (format, klasör, adlandırma) özelleştirmek mümkün mü?**  
  Kesinlikle – geri çağrı, dosya adı, format ve hedef konum üzerinde tam kontrol sağlar.

## Aspose.Tasks bağlamında “görüntüleri nasıl kaydederim” ne demektir?
Görüntüleri kaydetmek, bir Project dosyasından görsel öğeleri (grafikler, Gantt çubukları, kaynak görselleri) çıkarıp bunları görüntü dosyaları (PNG, JPEG vb.) olarak diske yazmak anlamına gelir. Aspose.Tasks, tam konum, adlandırma kuralı ve hatta görüntü formatını belirlemenizi sağlayan esnek bir geri çağrı mekanizması sunar.

## Aspose.Tasks ile görüntüleri kaydetmenin avantajları
- **Tam programatik kontrol** – manuel UI etkileşimi gerekmez.  
- **Çapraz‑platform** – .NET Core sayesinde Windows, Linux ve macOS’ta çalışır.  
- **Yüksek doğruluklu render** – görüntüler, orijinal Project görünümünün kalitesini korur.  
- **Kolay HTML üretimi** – `HtmlSaveOptions` ile görüntü geri çağrılarını birleştirerek **otomatik olarak görüntülü HTML** oluşturabilirsiniz.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Geliştirme makinenizde Visual Studio yüklü.  
2. Aspose.Tasks for .NET **[buradan](https://releases.aspose.com/tasks/net/)** indirildi.  
3. C# ve .NET proje yapısına temel aşinalık.

## Ad Alanlarını İçe Aktarma

Gerekli ad alanlarını kaynak dosyanıza ekleyin:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Adım 1: Project Nesnesi Oluşturma

Çalışmak istediğiniz Microsoft Project dosyasını yükleyin:

```csharp
var project = new Project("Project1.mpp");
```

## Adım 2: Kaydetme Seçeneklerini Tanımlama

Görüntü‑kaydetme geri çağrılarımızı da tutacak HTML kaydetme seçeneklerini oluşturun:

```csharp
var options = GetSaveOptions(1);
```

## Adım 3: Projeyi HTML Olarak Kaydetme (save project as html)

Projeyi bir HTML dosyasına dışa aktarın. HTML içinde referans verilen görüntüler, bir sonraki adımda tanımlayacağımız geri çağrı tarafından üretilecektir:

```csharp
project.Save("document_out.html", options);
```

## Adım 4: Görüntü Kaydetme Geri Çağrısını Uygulama (customize image export)

`IImageSavingCallback` arayüzünü uygulayın. Burada **görüntü dışa aktarımını özelleştirme** davranışını tanımlarsınız:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## Adım 5: Görüntüleri Belirtilen Dizin'e Kaydetme

`ImageSaving` metodunda, her bir görüntünün nereye kaydedileceğine karar verin. Aşağıdaki örnek, PNG kaynaklarını diğer formatlardan ayırmaktadır:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## Adım 6: Kaydetme Seçeneklerini Belirtme (geri çağrılar dahil)

Yazı tipleri, CSS ve görüntüler için geri çağrıları bağlayın. Bu, her görsel öğenin tutarlı bir şekilde işlenmesini sağlar:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|------|
| Oluşturulan HTML’de görüntüler görünmüyor | Geri çağrı geçerli bir dosya yolu atamıyor | `args.Path`'in yazılabilir bir klasöre işaret ettiğinden ve `args.ImageStream`'in doğru ayarlandığından emin olun. |
| PNG dosyaları yanlış uzantıyla kaydediliyor | Koşul sadece “png” soneki kontrol ediyor | Uzantıyı güvenli bir şekilde kontrol etmek için `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` kullanın. |
| HTML referansları dosyalar taşındıktan sonra kırılıyor | Çıktı klasörü taşındığında göreli yollar değişiyor | HTML ve görüntü klasörlerini birlikte tutun ya da `options.ImageFolder`'ı buna göre güncelleyin. |

## Sonuç

Bu adımları izleyerek **bir Project dosyasından görüntüleri nasıl kaydedeceğinizi**, **projeyi HTML olarak nasıl kaydedeceğinizi** ve **görüntü dışa aktarımını uygulamanızın klasör yapısına göre nasıl özelleştireceğinizi** öğrenmiş oldunuz. Bu yaklaşım, raporlar, dokümantasyon portalları veya web panoları içinde sorunsuz bir şekilde **görüntülü HTML** oluşturmanıza olanak tanır.

## Sık Sorulan Sorular

**S1: Aspose.Tasks’i HTML dışındaki formatlarda proje dosyalarını işlemek için kullanabilir miyim?**  
C1: Evet, Aspose.Tasks PDF, XLSX ve MPP gibi çeşitli formatları destekler.

**S2: Aspose.Tasks bulut depolama entegrasyonu sağlıyor mu?**  
C2: Evet, Aspose.Tasks Amazon S3 ve Google Drive gibi popüler bulut depolama hizmetleriyle çalışmak için API’ler sunar.

**S3: Aspose.Tasks .NET Core ile uyumlu mu?**  
C3: Evet, Aspose.Tasks .NET Core ile uyumludur ve çapraz‑platform uygulamalar geliştirmenize imkan tanır.

**S4: Kaydedilen görüntülerin görünümünü özelleştirebilir miyim?**  
C4: Evet, geri çağrı metodları içinde görüntü kaydetme mantığını değiştirerek görüntülerin görünümünü özelleştirebilirsiniz.

**S5: Aspose.Tasks değerlendirme amaçlı deneme sürümü sunuyor mu?**  
C5: Evet, **[buradan](https://releases.aspose.com/)** ücretsiz bir deneme sürümü alabilirsiniz.

---

**Son Güncelleme:** 2026-03-05  
**Test Edilen Versiyon:** Aspose.Tasks 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}