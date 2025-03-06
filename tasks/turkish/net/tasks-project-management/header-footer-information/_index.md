---
title: Aspose.Tasks ile Üstbilgi ve Altbilgi Bilgilerini Çıkarın
linktitle: Aspose.Tasks'ta Üstbilgi ve Altbilgi Bilgileri
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project dosyalarından üstbilgi ve altbilgi bilgilerini çıkarmayı öğrenin. Kolay, verimli ve geliştirici dostu bir çözüm.
weight: 29
url: /tr/net/tasks-project-management/header-footer-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Üstbilgi ve Altbilgi Bilgilerini Çıkarın

## giriiş
Aspose.Tasks for .NET, geliştiricilerin Microsoft Project dosyalarını kolaylıkla yönetmelerine olanak tanıyan güçlü bir kitaplıktır. Bu eğitimde Aspose.Tasks kullanarak MS Project dosyalarından üstbilgi ve altbilgi bilgilerinin nasıl alınacağını öğreneceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Visual Studio: Visual Studio'yu sisteminize yükleyin.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
3. Temel C# Bilgisi: C# programlama diline aşinalık.

## Ad Alanlarını İçe Aktar
Öncelikle gerekli ad alanlarını C# projenize aktarmanız gerekir. Bu, Aspose.Tasks kütüphanesi tarafından sağlanan sınıflara ve yöntemlere erişmenizi sağlayacaktır.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Adım 1: Proje Nesnesini Başlatın
 Başlamak için bir başlatmanız gerekir`Project` Mevcut bir MS Project dosyasını yükleyerek nesneyi oluşturun.
```csharp
// Belgeler dizininin yolu.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Adım 2: Üstbilgi ve Altbilgi Bilgilerini Alın
 Proje dosyasını yükledikten sonra üstbilgi ve altbilgi bilgilerini aşağıdaki komutu kullanarak alabilirsiniz.`PageInfo` mülk.
```csharp
var info = project.DefaultView.PageInfo;
// Başlık Bilgileri
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Altbilgi Bilgileri
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Bu basit adımları izleyerek Aspose.Tasks for .NET'i kullanarak MS Project dosyalarından üstbilgi ve altbilgi bilgilerini kolayca alabilirsiniz.

## Çözüm
Bu eğitimde Aspose.Tasks for .NET kullanarak MS Project dosyalarından üstbilgi ve altbilgi bilgilerinin nasıl çıkarılacağını araştırdık. Bu güçlü kitaplık, C# uygulamalarında Project dosyalarıyla çalışma görevini basitleştirerek geliştiricilere manipülasyon için güçlü araçlar sağlar.
### SSS
### Aspose.Tasks'ı kullanarak üstbilgi ve altbilgi bilgilerini değiştirebilir miyim?
Evet, Aspose.Tasks for .NET'i kullanarak üstbilgi ve altbilgi bilgilerini programlı olarak değiştirebilirsiniz.
### Aspose.Tasks, MS Project'in yanı sıra diğer proje dosya formatlarını da destekliyor mu?
Evet, Aspose.Tasks MPP, XML ve MPX dahil olmak üzere çeşitli proje dosyası formatlarını destekler.
### Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?
 Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Tasks belgelerini nerede bulabilirim?
 Aspose.Tasks belgelerini burada bulabilirsiniz[Burada](https://reference.aspose.com/tasks/net/).
### Aspose.Tasks için nasıl destek alabilirim?
 Aspose.Tasks için destek almak için şu adresi ziyaret edebilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
