---
date: 2026-03-16
description: Aspose.Tasks for .NET'te sayfa kaydetme geri çağrısını nasıl uygulayacağınızı
  öğrenin ve çok sayfalı belge çıktı akışlarını özelleştirilmiş şekilde yönetmenizi
  sağlayın.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te sayfa kaydetme geri çağrısını uygulayın
url: /tr/net/advanced-concepts/page-saving-callback/
weight: 12
---

quote > **Pro tip:** translation.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Sayfa Kaydetme Geri Çağrısını Uygulama

## Giriş

Bu öğreticide, .NET için Aspose.Tasks'te **sayfa kaydetme geri çağrısını uygulamayı** öğreneceksiniz. Bu güçlü özellik, çok sayfalı bir belgenin her sayfasını istediğiniz bir akıma yönlendirmenizi sağlar; böylece çıktının nasıl depolanacağı veya daha ileri işleneceği üzerinde tam kontrol elde edersiniz.

## Hızlı Yanıtlar
- **Sayfa kaydetme geri çağrısı ne işe yarar?** Her render edilen sayfayı ayrı bir akıma yakalar, böylece onları bireysel olarak işleyebilirsiniz.  
- **Hangi formatlara dışa aktarabilirim?** `ImageSaveOptions` tarafından desteklenen herhangi bir format, ör. PNG, JPEG, PDF.  
- **Lisans gerekli mi?** Üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **Bunu .NET Core ile kullanabilir miyim?** Evet, Aspose.Tasks .NET Core ve .NET 5/6+ ile tam uyumludur.  
- **Geri çağrı iş parçacığı‑güvenli mi?** Geri çağrı, render işlemini yapan aynı iş parçacığında çalışır; bu yüzden normal iş parçacığı‑güvenliği kuralları geçerlidir.

## **implement page saving callback** nedir?
**implement page saving callback** deseni, Aspose.Tasks'in kaydetme işlem hattına özel mantık eklemenizi sağlar. Doğrudan bir dosyaya yazmak yerine, her sayfa için bir `Stream` nesnesi alırsınız; bu sayede akışı bellekte tutabilir, bulut depolamaya yükleyebilir veya ek işlem uygulayabilirsiniz.

## Neden bir geri çağrı ile projeyi PNG olarak dışa aktaralım?
Projeyi PNG olarak dışa aktarmak, her Gantt şeması sayfasının raster bir görüntüsünü verir; bu da raporlar, e‑postalar veya web sayfalarına gömme için idealdir. Bir geri çağrı kullanmak, her sayfayı geçici dosyalar oluşturmadan ayrı bir `MemoryStream` içinde tutmanızı sağlar.

## Önkoşullar

1. **C# bilgisi** – sınıflar, arayüzler ve akışlar hakkında temel bilgi.  
2. **Aspose.Tasks for .NET** – [buradan](https://releases.aspose.com/tasks/net/) indirip kurun.  
3. **IDE** – Visual Studio, Rider veya herhangi bir .NET‑uyumlu editör.

## Ad Alanlarını İçe Aktarın

Başlamak için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Adım 1: Bir Project Nesnesi Oluşturun

Mevcut bir MPP dosyasını bir `Project` örneğine yükleyin:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Adım 2: Image Save Options'ı Yapılandırın

PNG çıktısı için `ImageSaveOptions` ayarlayın ve özel geri çağrıyı ekleyin:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **İpucu:** `RenderToSinglePage = false` ayarı, her Gantt şeması sayfasının ayrı ayrı render edilmesini sağlar; bu, geri çağrının farklı akışlar alması için gereklidir.

## Adım 3: Projeyi Geri Çağrı ile Kaydedin

Gerçek akışlar geri çağrı tarafından sağlandığı için `Stream.Null` geçirerek `Save` metodunu çağırın:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Adım 4: Kaydedilen Sayfa Akışlarını İşleyin

Kaydetme işlemi tamamlandıktan sonra, geri çağrı bir `MemoryStream` koleksiyonu tutar—sayfa başına bir tane. Artık bunlar üzerinde döngü kurabilirsiniz:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Adım 5: Özel Sayfa Kaydetme Geri Çağrısını Uygulayın

`IPageSavingCallback` arayüzünü uygulayan mühürlenmiş bir sınıf oluşturun. Bu sınıf, her sayfanın akışını yakalar ve daha sonra kullanılmak üzere bir listede saklar.

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
        // Perform any cleanup or finalization
    }
}
```

## Yaygın Tuzaklar ve Sorun Giderme

| Sorun | Sebep | Çözüm |
|-------|--------|----------|
| **Hiç sayfa dönmüyor** | `RenderToSinglePage` `true` olarak bırakılmış. | Ayrı sayfalar üretmek için `RenderToSinglePage = false` ayarlayın. |
| **Akışlar boş** | `KeepStreamOpen` `true` olarak ayarlanmış ve daha sonra kapatılmamış. | Varsayılan `false` bırakın ve geri çağrının akışları otomatik kapatmasına izin verin. |
| **Bellek dışı hatalar** | Çok büyük projeler yüksek çözünürlüklü PNG'ler üretir. | Akışları tek tek işleyin veya VM bellek limitlerini artırın. |

## Sık Sorulan Sorular

**S1: Aspose.Tasks'te sayfa kaydetme geri çağrısı nedir?**  
C: Sayfa kaydetme geri çağrısı, çok sayfalı bir belgenin her sayfası için kaydetme sürecini yakalamanızı sağlar ve o sayfa için özel bir `Stream` sunar.

**S2: Bu geri çağrıyı kullanarak sayfaları farklı formatlarda kaydedebilir miyim?**  
C: Evet. `SaveFileFormat` değerini değiştirerek PNG, JPEG, PDF, SVG vb. formatlara dışa aktarabilirsiniz.

**S3: Aspose.Tasks .NET Core ile uyumlu mu?**  
C: Kesinlikle. Aspose.Tasks .NET Core, .NET 5 ve .NET 6'yı destekler.

**S4: Sayfa kaydetme sırasında hataları nasıl yönetebilirim?**  
C: Geri çağrı mantığını try/catch bloklarıyla sarın ve istisnaları kaydedin. `OnFinish` metodu, son temizlik işlemleri için iyi bir yerdir.

**S5: Aspose.Tasks için daha fazla kaynak ve destek nereden bulunur?**  
C: Yardım için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilir, belgeleri [buradan](https://reference.aspose.com/tasks/net/) inceleyebilir veya ek özellikler ve lisans seçenekleri için [Aspose.Tasks web sitesine](https://purchase.aspose.com/buy) göz atabilirsiniz.

---

**Son Güncelleme:** 2026-03-16  
**Test Edilen Sürüm:** Aspose.Tasks 24.12 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}