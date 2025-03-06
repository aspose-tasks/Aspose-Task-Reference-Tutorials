---
title: Aspose.Tasks'ta Styling Bar
linktitle: Aspose.Tasks'ta Styling Bar
second_title: Aspose.Tasks .NET API'si
description: Proje görselleştirmesini geliştirmek için Aspose.Tasks for .NET'te çubuklara nasıl stil uygulayacağınızı öğrenin.
weight: 19
url: /tr/net/advanced-features/styling-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Styling Bar

## giriiş

Aspose.Tasks'taki çubukların şekillendirilmesi, görsel olarak çekici proje planları oluşturmanın önemli bir unsurudur. Aspose.Tasks API'nin sunduğu esneklik sayesinde geliştiriciler, proje görselleştirmesini geliştirmek için çubukların renk, şekil ve metin stili gibi çeşitli yönlerini özelleştirebilir. Bu derste Aspose.Tasks for .NET kullanarak çubuklara nasıl stil uygulanacağını inceleyeceğiz ve her örneği yönetilebilir adımlara ayıracağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Aspose.Tasks for .NET Kütüphanesi: Aspose.Tasks for .NET kütüphanesini aşağıdaki adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/tasks/net/).
2. Geliştirme Ortamı: .NET framework desteğiyle bir geliştirme ortamı kurun.
3. Temel C# Anlayışı: C# programlama diline aşina olmak faydalı olacaktır.

## Ad Alanlarını İçe Aktar

Öncelikle Aspose.Tasks sınıflarına ve yöntemlerine erişmek için gerekli ad alanlarını içe aktaralım:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Adım 1: Projeyi Yükleyin

Başlamak için proje dosyasını Aspose.Tasks API'sini kullanarak yükleyin:

```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## 2. Adım: Kaydetme Seçeneklerini Yapılandırın

Uygulanacak çubuk stillerini belirterek kaydetme seçeneklerini tanımlayın:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Adım 3: Bar Stilini Tanımlayın

Yeni bir çubuk stili oluşturun ve özelliklerini özelleştirin:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Çubuk öğesi türünü ayarla
style.BarColor = Color.Green; // Çubuk rengini ayarla
style.BarShape = BarShape.HalfHeight; // Çubuk şeklini ayarla
style.StartShape = Shape.LeftBracket; // Şekli çubuğun başlangıcında ayarla
style.StartShapeColor = Color.Aqua; // Başlangıç şeklinin rengini ayarlama
style.EndShape = Shape.RightBracket; // Çubuğun sonundaki şekli ayarla
style.EndShapeColor = Color.Aquamarine; // Son şeklin rengini ayarlayın
style.TextStyle = new TextStyle(); // Metin stilini ayarla
style.TextStyle.BackgroundColor = Color.Black; // Metin için arka plan rengini ayarlama
```

## Adım 4: Metin Dönüştürücüyü Özelleştirin

İsteğe bağlı olarak, metin oluşturmayı değiştirmek için metin dönüştürücüyü özelleştirin:

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

## Adım 5: Seçeneklere Çubuk Stili Ekleme

Yapılandırılmış çubuk stilini kaydetme seçeneklerine ekleyin:

```csharp
options.BarStyles.Add(style);
```

## Adım 6: Projeyi Kaydet

Son olarak projeyi uygulanan çubuk stilleriyle kaydedin:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Çözüm

Aspose.Tasks for .NET'te çubuk stillerini özelleştirmek, geliştiricilere görsel olarak çekici proje planları oluşturma yeteneği sağlar. Bu öğreticide özetlenen adımları izleyerek, belirli proje görselleştirme gereksinimlerini karşılamak için çubuklara etkili bir şekilde stil verebilirsiniz.

## SSS'ler

### S1: Tek bir projeye birden fazla çubuk stili uygulayabilir miyim?

Cevap1: Evet, aynı proje içindeki farklı görev türlerine birden fazla çubuk stili tanımlayabilir ve uygulayabilirsiniz.
   
### S2: Çalışma zamanı sırasında çubuk stillerini dinamik olarak değiştirmek mümkün müdür?

C2: Evet, uygulamanızdaki belirli koşullara veya kullanıcı tercihlerine göre çubuk stillerini dinamik olarak değiştirebilirsiniz.
   
### S3: Aspose.Tasks, stillendirilmiş çubuklara sahip projelerin farklı dosya formatlarına aktarılmasını destekliyor mu?

Cevap3: Evet, Aspose.Tasks, stillendirilmiş çubuklara sahip projelerin PDF, XLSX ve HTML gibi çeşitli formatlara aktarılmasını destekler.
   
### S4: Aspose.Tasks'ta önceden tanımlanmış çubuk stilleri mevcut mu?

Cevap4: Aspose.Tasks varsayılan çubuk stilleri sağlarken, geliştiriciler de proje gereksinimlerine göre uyarlanmış özel çubuk stilleri oluşturabilirler.
   
### S5: API'yi kullanarak bir proje içindeki mevcut çubuk stillerini alıp değiştirebilir miyim?

Cevap5: Evet, Aspose.Tasks for .NET API'yi kullanarak mevcut çubuk stillerini programlı olarak alabilir ve değiştirebilirsiniz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
