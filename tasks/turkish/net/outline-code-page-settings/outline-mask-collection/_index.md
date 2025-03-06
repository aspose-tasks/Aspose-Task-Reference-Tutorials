---
title: Aspose.Tasks ile MS Project Outline Maskelerinde Ustalaşın
linktitle: Aspose.Tasks'ta Anahat Maskelerinin Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project koleksiyonu anahat maskelerini nasıl değiştireceğinizi öğrenin. Bu kapsamlı eğitimle üretkenliği artırın.
weight: 15
url: /tr/net/outline-code-page-settings/outline-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile MS Project Outline Maskelerinde Ustalaşın

## giriiş
Aspose.Tasks for .NET'i kullanarak Microsoft Project'in anahat maskelerinin gücünden yararlanmak mı istiyorsunuz? Doğru yere geldiniz! Bu kapsamlı eğitimde, projelerinizde anahat maskelerini etkili bir şekilde nasıl yöneteceğiniz konusunda sağlam bir anlayış kazanmanızı sağlayarak süreç boyunca size adım adım rehberlik edeceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz sizi iş akışınızı optimize etmek için gereken bilgi ve becerilerle donatacaktır.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
### 1. Aspose.Tasks for .NET'in Kurulumu
Geliştirme ortamınızda Aspose.Tasks for .NET'in kurulu olduğundan emin olun. Kütüphaneyi Aspose web sitesinden indirebilirsiniz.[Burada](https://releases.aspose.com/tasks/net/).
### 2. Temel C# ve .NET Framework Bilgisi
Bu eğitimde her ikisinden de yararlanılacağı için C# programlama dili ve .NET Framework hakkında bilgi edinin.
### 3. Microsoft Proje Dosyası
Test amacıyla bir Microsoft Project dosyasını (MPP) hazır bulundurun. Mevcut bir dosyayı kullanabilir veya deneme amaçlı yeni bir dosya oluşturabilirsiniz.
## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını C# projenize aktararak başlayalım. Bu adım, Aspose.Tasks for .NET tarafından sağlanan gerekli sınıflara ve işlevlere erişiminizi sağlar.

Kod dosyanızın başına aşağıdaki ad alanlarını ekleyin:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Şimdi verilen örneği birden çok adıma ayıralım ve her adımı ayrıntılı olarak açıklayalım:
## Adım 1: Proje Nesnesini Başlatın
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 Burada yeni bir örneğini oluşturuyoruz.`Project` class'a gidin ve "OutlineValues2010.mpp" adlı mevcut bir Microsoft Project dosyasını yükleyin.
## 2. Adım: Anahat Kodlarına Erişim
```csharp
var outline = project.OutlineCodes[0];
```
Projenin taslak kodlarına ulaşıyoruz. Anahat kodları, Microsoft Project'teki görevleri kategorilere ayırmanıza ve düzenlemenize olanak tanıyan özel alanlardır.
## 3. Adım: Anahat Maskelerini Temizle
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
Bu adım, devam etmeden önce mevcut anahat maskelerinin temizlenmesini sağlar.
## Adım 4: Anahat Maskeleri Oluşturun
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
Yeni taslak maskeleri oluşturup türlerini belirliyoruz. Bu örnekte geçerli bir anahat maskesi ve yanlış bir tane oluşturuyoruz.
## Adım 5: Maskeleri Ekleme ve Düzenleme
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
Burada koleksiyona yanlış bir maske ekliyoruz ve bir maskenin uzunluğunu indeksini kullanarak düzenliyoruz.
## Adım 6: Maskeleri Çıkarın
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
Yanlış maskeyi indeksine göre koleksiyondan kaldırıyoruz.
## Adım 7: Maskeleri Yineleyin
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
Bu döngü, koleksiyondaki her anahat maskesi üzerinde yinelenir ve uzunluk, düzey, ayırıcı ve tür gibi özelliklerini yazdırır.
## Adım 8: Maskeleri Başka Bir Projeye Kopyalayın
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
Son olarak, anahat maskelerini bir projeden diğerine kopyalayarak farklı projeler arasında tutarlılık sağlıyoruz.
## Çözüm
Tebrikler! Aspose.Tasks for .NET'i kullanarak MS Project koleksiyonu anahat maskelerini nasıl yöneteceğinizi başarıyla öğrendiniz. Bu öğreticiyi takip ederek artık projelerinizde anahat maskelerini verimli bir şekilde yönetme ve sonuç olarak üretkenliğinizi ve iş akışınızı geliştirme becerileriyle donatıldınız.
## SSS'ler
### S1: Aspose.Tasks for .NET'i Microsoft Project dosyalarının farklı sürümleriyle kullanabilir miyim?
C: Evet, Aspose.Tasks for .NET, MPP, MPT ve XML formatları da dahil olmak üzere Microsoft Project dosyalarının çeşitli sürümlerini destekler.
### S2: Aspose.Tasks for .NET, .NET Core ile uyumlu mu?
C: Evet, Aspose.Tasks for .NET, .NET Core ile uyumludur ve onu platformlar arası uygulamalarda kullanmanıza olanak tanır.
### S3: Anahat maskelerinin özelliklerini proje gereksinimlerime göre özelleştirebilir miyim?
C: Kesinlikle! Uzunluklarını, düzeylerini, ayırıcılarını ve türlerini özel proje ihtiyaçlarınıza uyacak şekilde ayarlayarak anahat maskelerini özelleştirebilirsiniz.
### S4: Aspose.Tasks for .NET belge ve destek sağlıyor mu?
C: Evet, Aspose.Tasks for .NET web siteleri aracılığıyla kapsamlı belgeler ve özel destek sunuyor ve[forumlar](https://forum.aspose.com/c/tasks/15).
### S5: Aspose.Tasks for .NET'in ücretsiz deneme sürümü mevcut mu?
 C: Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümüne kendi sitelerinden erişebilirsiniz.[İnternet sitesi](https://releases.aspose.com/tasks/net/). Bir satın alma işlemi yapmadan önce özelliklerini ve işlevlerini keşfetmek için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
