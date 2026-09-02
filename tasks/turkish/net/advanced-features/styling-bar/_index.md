---
date: 2026-04-06
description: Aspose.Tasks for .NET'te çubuk stilini değiştirmeyi ve çubuk renklerini
  özelleştirmeyi öğrenerek proje görselleştirmesini geliştirin.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Aspose.Tasks'te Stil Çubuğu
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Çubuk Stili Nasıl Değiştirilir
url: /tr/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Çubuk Stilini Değiştirme

## Giriş

If you need to **how to change bar** appearance in a Microsoft Project file, Aspose.Tasks for .NET gives you full control over bar colors, shapes, and text styles. By customizing bar colors and other visual attributes you can make project plans far easier to read and more aligned with your organization’s branding. In this tutorial we’ll walk through a complete, step‑by‑step example that shows you how to change bar styling, from loading a project to exporting it with the new visual rules applied.

## Hızlı Yanıtlar
- **Ne stil verebilirim?** Bars, milestones, and task text in Gantt charts.  
- **Hangi format stil verilen çubukları destekler?** PDF, XLSX, HTML and native MPP when saved with `PdfSaveOptions`.  
- **Lisans gerekir mi?** A commercial license is required for production use; a free trial works for testing.  
- **Birden fazla stil uygulayabilir miyim?** Yes – add as many `BarStyle` objects as you need.  
- **.NET Core ile uyumlu mu?** Absolutely – works with .NET Framework and .NET Core/5/6+.

## Aspose.Tasks'te Çubuk Stili Nedir?

Bar styling lets you define visual rules that the Aspose.Tasks engine applies when rendering Gantt charts. Each rule (a **BarStyle**) targets a specific item type—tasks, milestones, or summary tasks—and lets you set colors, shapes, and even custom text.

## Neden çubuk renklerini özelleştirirsiniz?

Customizing bar colors helps stakeholders instantly identify critical paths, delayed tasks, or milestones. It also lets you match corporate color schemes, making reports look professional and on‑brand.

## Önkoşullar

Before we begin, make sure you have:

1. **Aspose.Tasks for .NET** – download it from the [download page](https://releases.aspose.com/tasks/net/).  
2. A development environment that supports .NET (Framework 4.6+, .NET Core 3.1+, or later).  
3. Basic familiarity with C# – the examples use simple, self‑contained code.

## Ad Alanlarını İçe Aktarın

First, import the namespaces that contain the classes we’ll use:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Adım 1: Projeyi Yükleyin

Load an existing MPP file (or create a new one) so you have a project object to work with:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Adım 2: Kaydetme Seçeneklerini Yapılandırın

Create a `PdfSaveOptions` instance and initialise the `BarStyles` collection where we’ll store our custom styles:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Adım 3: Çubuk Stilini Tanımlayın

Now we build a `BarStyle` object and set the properties that control how the bar looks. This is where we **customize bar colors** and shapes:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Adım 4: Metin Dönüştürücüyü Özelleştirin (İsteğe Bağlı)

If you want to tweak the text that appears on the bar, you can assign a custom converter. The example prefixes task names that don’t already start with “T”:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Adım 5: Çubuk Stilini Seçeneklere Ekleyin

Add the fully configured style to the `BarStyles` collection of the save options:

```csharp
options.BarStyles.Add(style);
```

## Adım 6: Projeyi Kaydedin

Finally, export the project. The PDF (or other format) will render the Gantt chart using the bar style we defined:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Yaygın Sorunlar ve Çözümler

| Sorun | Sebep | Düzeltme |
|-------|--------|-----|
| **Bar stili uygulanmadı** | `BarStyles` koleksiyonu boştu veya kaydetme seçeneklerine eklenmemişti. | `Save` çağrılmadan önce `BarStyle`'ı `options.BarStyles` koleksiyonuna eklediğinizden emin olun. |
| **PDF'de renkler farklı görünüyor** | PDF render'ı farklı bir renk profili kullanabilir. | Standart `System.Drawing.Color` değerlerini kullanın veya özel ARGB renkleri tanımlayın. |
| **Metin dönüştürücü null referans hatası veriyor** | Bazı görevlerde `Tsk.Name` özelliği null. | `task.Get(Tsk.Name)` erişmeden önce null kontrolü ekleyin. |

## SSS

### Q1: Tek bir projeye birden fazla çubuk stili uygulayabilir miyim?

A1: Evet, aynı proje içinde farklı görev tiplerine birden fazla çubuk stili tanımlayıp uygulayabilirsiniz.

### Q2: Çalışma zamanında çubuk stillerini dinamik olarak değiştirmek mümkün mü?

A2: Evet, uygulamanız içinde belirli koşullara veya kullanıcı tercihine göre çubuk stillerini dinamik olarak değiştirebilirsiniz.

### Q3: Aspose.Tasks, stil verilen çubuklarla projeleri farklı dosya formatlarına dışa aktarmayı destekliyor mu?

A3: Evet, Aspose.Tasks stil verilen çubuklarla projeleri PDF, XLSX ve HTML gibi çeşitli formatlara dışa aktarmayı destekler.

### Q4: Aspose.Tasks'te önceden tanımlı çubuk stilleri var mı?

A4: Aspose.Tasks varsayılan çubuk stilleri sunsa da, geliştiriciler proje gereksinimlerine göre özelleştirilmiş çubuk stilleri de oluşturabilir.

### Q5: API kullanarak bir projedeki mevcut çubuk stillerini alıp değiştirebilir miyim?

A5: Evet, Aspose.Tasks for .NET API'si ile mevcut çubuk stillerini programlı olarak alıp değiştirebilirsiniz.

## Sık Sorulan Sorular

**S: Normal görevler için çubuk rengini nasıl değiştiririm, kilometre taşları yerine?**  
C: `style.ItemType = BarItemType.Task;` ve `style.BarColor`'ı istediğiniz `Color` değerine atayın.

**S: HTML'ye dışa aktarırken çubukları stil vermek için bu yaklaşımı kullanabilir miyim?**  
C: Evet. `HtmlSaveOptions` kullanın ve `BarStyles` koleksiyonunu aynı şekilde doldurun.

**S: Tanımlayabileceğim çubuk stili sayısında bir sınırlama var mı?**  
C: Pratikte yok; ihtiyacınız kadar ekleyebilirsiniz, ancak çok büyük koleksiyonlarda performansı göz önünde bulundurun.

**S: Stilleri değiştirdikten sonra `project.Calculate()` çağırmam gerekiyor mu?**  
C: Hayır, stiller kaydetme işlemi sırasında uygulanır; yeniden hesaplama yalnızca zaman çizelgesi değişiklikleri için gerekir.

---

**Son Güncelleme:** 2026-04-06  
**Test Edilen Versiyon:** Aspose.Tasks 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}