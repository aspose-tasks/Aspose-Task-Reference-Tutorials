---
date: 2026-03-24
description: Bellek dışı işleme ve Aspose.Tasks Layout Builder kullanarak .NET'te
  proje görüntüsünü nasıl kaydedeceğinizi öğrenin. Adım adım kod örnekleriyle rehber.
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks Layout Builder (C#) ile Bellek Yetersizliği Yönetimi
url: /tr/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Layout Builder ile Bellek Dışı İşleme

## Giriş

Bellek dışı işleme, büyük proje dosyalarıyla çalışan güvenilir .NET uygulamaları oluşturmanın kritik bir parçasıdır. Aspose.Tasks Layout Builder ile görselleştirmeler oluşturduğunuzda, özellikle karmaşık Gantt grafiklerinde bellekle ilgili istisnalara hızlıca takılabilirsiniz. Bu öğreticide **handle memory exceptions**, **customize Gantt view** ve **save project image** işlemlerini güvenli bir şekilde nasıl yapacağınızı adım adım göstereceğiz, böylece uygulamanız büyük takvimlerde bile yanıt vermeye devam eder.

## Hızlı Cevaplar
- **Bellek dışı işleme nedir?** Büyük verileri işlerken bellek kullanımını yönetmek ve `OutOfMemoryException`‑tipi hataları yakalamak.
- **Hangi API yardımcı olur?** Aspose.Tasks Layout Builder for .NET.
- **Tipik senaryo?** Yüksek çözünürlüklü bir Gantt grafiğini PNG olarak oluşturma.
- **Temel ön koşul?** Aspose.Tasks yüklü .NET (Framework 4.5+ veya .NET 6).
- **Hataları nasıl yakalarsınız?** `ApsLayoutBuilderOutOfMemoryException` ve ilgili istisnalar için `try…catch` blokları kullanın.

## Ön Koşullar

Koda başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. **C# temelleri** – standart C# sözdizimiyle rahat olmalısınız.
2. **Aspose.Tasks for .NET** yüklü. Henüz eklemediyseniz, [buradan](https://releases.aspose.com/tasks/net/) indirin.
3. **Bir IDE** – örneğin Visual Studio (veya C# uzantılı VS Code) – örnek kodu derlemek ve çalıştırmak için.

## Ad Alanlarını İçe Aktarma

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Adım Adım Kılavuz

### Adım 1: Projeyi Yükle

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

Bu satır **Blank2010.mpp** dosyasını bir `Project` örneğine yükler ve görselleştirme için hazırlar.

### Adım 2: Gantt Grafik Görünümünü Özelleştir

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

Burada orta ve alt zaman ölçeği katmanlarını ayarlayarak **customize Gantt view** yapıyoruz. Bu katmanları değiştirmek, aynı anda işlenen veri miktarını azaltır ve bellek baskısını hafifletebilir.

### Adım 3: Görüntü Kaydetme Seçeneklerini Yapılandır

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions`, Aspose.Tasks'e grafiği nasıl oluşturacağını söyler. Çıktı formatı olarak PNG seçiyoruz ve zaman ölçeğini az önce özelleştirdiğimiz görünüme bağlıyoruz.

### Adım 4: Projeyi Görüntü Olarak Kaydet

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

`Save` çağrısı, yukarıda tanımlanan seçenekleri kullanarak **saves the project image** yapar. Proje çok büyükse, bellek dışı durumun ortaya çıkma ihtimalinin en yüksek olduğu nokta budur.

### Adım 5: İstisnaları Ele Al

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

`ApsLayoutBuilderOutOfMemoryException` yakalayarak **handle memory exception** sorunsuz bir şekilde ele alırsınız, uygulamanın çökmesi yerine net bir mesaj sağlarsınız. İkinci catch, büyük grafikler oluşturulurken ortaya çıkabilecek bitmap boyutu sorunlarıyla ilgilenir.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|------|
| **OutOfMemoryException** | Çok yüksek çözünürlüklü bir görüntüyü oluşturmak, işlemin tahsis edebileceğinden daha fazla RAM tüketir. | Görüntü boyutlarını küçültün, zaman ölçeği katmanlarını basitleştirin veya grafiği birden fazla görüntüye bölün. |
| **BitmapInvalidSizeException** | İstenen bitmap boyutu platformun maksimumunu aşıyor. | `ImageSaveOptions` içinde genişlik/yüksekliği sınırlayın veya segmentler halinde render edin. |
| **Slow performance** | Büyük proje dosyaları çok fazla işlem gerektirir. | Render etmeden önce `project.Set(Prj.SaveToCache, true)` etkinleştirin veya bir arka plan iş parçacığı kullanın. |

## SSS

### Q1: Aspose.Tasks for .NET nedir?

A1: Aspose.Tasks for .NET, geliştiricilerin .NET uygulamalarında Microsoft Project dosyalarını programlı olarak manipüle etmelerini sağlayan güçlü bir API'dir.

### Q2: Aspose.Tasks için geçici bir lisans nasıl alınır?

A2: Aspose.Tasks için geçici bir lisansı, [bu linki](https://purchase.aspose.com/temporary-license/) ziyaret ederek alabilirsiniz.

### Q3: Aspose.Tasks büyük proje dosyalarını işlemek için uygun mu?

A3: Evet, Aspose.Tasks büyük proje dosyalarını verimli bir şekilde işlemek için özellikler ve optimizasyonlar sunar, ancak geliştiricilerin hâlâ bellek yönetimi stratejilerini göz önünde bulundurmaları gerekir.

### Q4: Aspose.Tasks kullanarak Gantt grafiklerinin görünümünü özelleştirebilir miyim?

A4: Kesinlikle! Aspose.Tasks, Gantt grafiklerinin görünümünü ve düzenini gereksinimlerinize göre özelleştirmek için kapsamlı yetenekler sunar.

### Q5: Aspose.Tasks için daha fazla yardım ve destek nereden bulunur?

A5: Daha fazla yardım ve destek bulabilir, ayrıca toplulukla etkileşime geçebilirsiniz, [Aspose.Tasks forumunda](https://forum.aspose.com/c/tasks/15).

## Sık Sorulan Sorular

**S:** Proje görüntüsü kaydederken bellek kullanımını nasıl azaltabilirim?  
**C:** Görüntü çözünürlüğünü düşürün, zaman ölçeği aralığını sınırlayın veya grafiği birden fazla daha küçük segmente kaydedin.

**S:** Görüntüyü doğrudan bir web yanıtına akıtmak mümkün mü?  
**C:** Evet, `project.Save(stream, options)` kullanabilir ve akışı HTTP yanıtına yazabilirsiniz.

**S:** Aspose.Tasks .NET Core ve .NET 5/6'yı destekliyor mu?  
**C:** Kütüphane .NET Core, .NET 5 ve .NET 6 ile tam uyumludur.

**S:** Optimizasyondan sonra hâlâ bellek dışı hatası alıyorsam ne yapmalıyım?  
**C:** Projeyi daha fazla RAM'e sahip bir makinede işlemeyi veya render işlemini bir arka plan servisine yüklemeyi düşünün.

**S:** Gantt grafiğini PNG dışındaki formatlara dışa aktarabilir miyim?  
**C:** Evet, `ImageSaveOptions` PNG'ye ek olarak JPEG, BMP ve TIFF formatlarını da destekler.

---

**Son Güncelleme:** 2026-03-24  
**Test Edilen Versiyon:** Aspose.Tasks 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}