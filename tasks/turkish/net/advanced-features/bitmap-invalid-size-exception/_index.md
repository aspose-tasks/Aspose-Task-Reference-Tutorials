---
date: 2026-03-21
description: Aspose.Tasks for .NET'te bir projeyi resim olarak kaydederken görüntüyü
  dışa aktarmayı ve BitmapInvalidSizeException hatasını nasıl ele alacağınızı öğrenin.
  Projeyi resim olarak kaydetme ve PNG olarak dışa aktarma adımlarını içerir.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Görseli Nasıl Dışa Aktarır ve Geçersiz Boyut İstisnasını Ele Alırsınız
url: /tr/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Export Image – Handling Invalid Size Exception for Bitmap in Aspose.Tasks

Bu öğreticide **bir Microsoft Project dosyasından görüntü dışa aktarmayı** Aspose.Tasks for .NET kullanarak öğrenecek ve daha da önemlisi, süreç sırasında oluşabilecek `BitmapInvalidSizeException` hatasını nasıl yakalayacağınızı göreceksiniz. Bir projeyi görüntü olarak dışa aktarmak, raporlama panoları, dokümantasyon veya sadece bir takvimin görsel anlık görüntüsünü paylaşmak için yaygın bir gereksinimdir. Bu kılavuzun sonunda **projeyi görüntü olarak kaydetmeyi** güvenilir bir şekilde yapabilecek ve hatta **projeyi PNG formatında dışa aktarabileceksiniz**.

## Quick Answers
- **What exception can occur when exporting an image?** `BitmapInvalidSizeException`  
- **Which format is used in the example?** PNG (`SaveFileFormat.Png`)  
- **Do I need a special license?** Üretim ortamı için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **Can I change the timescale?** Evet – zaman ölçeği birimini (dakika, saat, gün vb.) ayarlayabilirsiniz.  
- **Is the code compatible with .NET Core?** Kesinlikle – aynı API .NET Framework ve .NET Core üzerinde çalışır.

## What is the BitmapInvalidSizeException?
`BitmapInvalidSizeException`, görüntü için hesaplanan bitmap boyutları desteklenen aralığın dışına çıktığında (ör. genişlik ya da yükseklik sıfır veya iç limitleri aştığında) fırlatılır. Bu genellikle zaman ölçeği veya görünüm ayarları çok büyük ya da çok küçük bir görüntü oluşturduğunda meydana gelir.

## Why export a project as an image?
- **Visual reporting** – Gantt şemasını PDF, Word belgeleri veya web sayfalarına gömebilirsiniz.  
- **Cross‑platform sharing** – PNG dosyaları, Microsoft Project gerektirmeden herhangi bir cihazda görüntülenebilir.  
- **Performance** – Görüntüler, tam proje dosyalarına göre hızlı ön izlemeler için daha hafiftir.

## Prerequisites
1. C# ve .NET geliştirme konusunda temel bilgi.  
2. Aspose.Tasks for .NET yüklü (NuGet paketi `Aspose.Tasks`).  
3. Örnek bir Microsoft Project dosyası (ör. `Blank2010.mpp`).  

## Import Namespaces
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Step‑by‑Step Guide

### Step 1: Initialize the Project and Choose a View
İlk olarak bir `Project` örneği oluşturun ve renderlamak istediğiniz görünümü seçin (burada ilk Gantt şeması görünümünü kullanıyoruz).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Step 2: Configure Image Save Options (Export Project to PNG)
İstenen görüntü formatını ayarlayın ve Aspose.Tasks'in görünümde tanımlı zaman ölçeğini kullanmasını söyleyin.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Step 3: Adjust the Timescale Unit (Control Image Size)
Zaman ölçeğini değiştirmek bitmap boyutlarını etkiler. Bu örnekte **dakika** birimini kullanarak görüntü boyutunu yönetilebilir tutuyoruz.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Step 4: Attempt to Save the Project as an Image
Bu satır, **projeyi görüntü olarak kaydet** işlemini gerçekleştirir.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Step 5: Catch and Handle the BitmapInvalidSizeException
Kaydetme çağrısını bir `try / catch` bloğuna sarın; böylece bitmap boyutu geçersiz olduğunda uygulamanız sorunsuz bir şekilde yanıt verebilir.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Common Issues and Solutions
| Issue | Cause | Solution |
|-------|-------|----------|
| Hala zaman ölçeği ayarlandıktan sonra istisna atılıyor | Zaman ölçeği hâlâ çok büyük bir bitmap oluşturuyor | `view.MiddleTimescaleTier.Count` değerini azaltın veya daha kaba bir `TimescaleUnit` (ör. Saat) seçin. |
| Çıktı dosyası boş | Yanlış dosya yolu veya yazma izni eksikliği | `DataDir`'in yazılabilir bir klasöre işaret ettiğini ve formatı değiştirirseniz dosya adının `.png` ile bittiğini doğrulayın. |
| Görüntü kalitesi düşük | Varsayılan DPI düşük olabilir | `options.DpiX` ve `options.DpiY` değerlerini daha yüksek bir değere (ör. 300) ayarlayın. |

## Frequently Asked Questions

**Q: What causes the BitmapInvalidSizeException in Aspose.Tasks?**  
A: Hesaplanan bitmap boyutları geçersiz olduğunda ortaya çıkar—genellikle zaman ölçeği çok büyük bir görüntü oluşturduğunda ya da genişlik/yükseklik sıfır olduğunda.

**Q: Can I customize the timescale when exporting an image?**  
A: Evet. `view.MiddleTimescaleTier.Unit` ve `Count` değerlerini ihtiyacınıza göre değiştirebilirsiniz; öğreticide gösterildiği gibi.

**Q: Does Aspose.Tasks support other image formats besides PNG?**  
A: Kesinlikle. `SaveFileFormat` ayrıca JPEG, BMP, GIF ve TIFF gibi formatları da içerir. `ImageSaveOptions` içindeki enum değerini değiştirmeniz yeterlidir.

**Q: Is a license required for exporting images in a production environment?**  
A: Evet. Kütüphane değerlendirme modunda çalışsa da, ticari bir lisans değerlendirme kısıtlamalarını kaldırır ve tam destek sağlar.

**Q: How can I improve the quality of the exported PNG?**  
A: DPI ayarlarını (`options.DpiX` ve `options.DpiY`) artırın veya daha büyük bir bitmap üretmek için görünümün zaman ölçeğini ayarlayın.

## Conclusion
Yukarıdaki adımları izleyerek artık **bir Project dosyasından görüntü dışa aktarmayı**, **projeyi görüntü olarak kaydetmeyi** ve `BitmapInvalidSizeException` hatasını zarif bir şekilde ele almayı biliyorsunuz. Bu teknikler, raporlama süreçlerinizi daha sağlam hâle getirir ve görsel dışa aktarmaların farklı proje boyutları ve zaman ölçekleriyle sorunsuz çalışmasını sağlar.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

---