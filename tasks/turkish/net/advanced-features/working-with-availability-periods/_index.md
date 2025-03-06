---
title: Aspose.Tasks'ta Kullanılabilirlik Dönemleriyle Çalışmak
linktitle: Aspose.Tasks'ta Kullanılabilirlik Dönemleriyle Çalışmak
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak kaynak kullanılabilirlik sürelerini verimli bir şekilde nasıl yöneteceğinizi öğrenin. Bu öğretici, .NET projelerinizde kullanılabilirlik dönemleriyle çalışmaya yönelik adım adım bir kılavuz sağlar.
weight: 17
url: /tr/net/advanced-features/working-with-availability-periods/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Kullanılabilirlik Dönemleriyle Çalışmak

## giriiş

Bu eğitimde Aspose.Tasks for .NET'te kullanılabilirlik dönemleriyle nasıl çalışılacağını keşfedeceğiz. Kullanılabilirlik dönemleri, proje yönetimi senaryolarında kaynakları verimli bir şekilde yönetmek için çok önemlidir. Süreç boyunca size adım adım rehberlik edeceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1. Visual Studio: Visual Studio'yu veya .NET geliştirme için tercih edilen herhangi bir IDE'yi yükleyin.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
3. C# programlamanın temel anlayışı: C# programlama dilinin temellerine aşina olmak faydalı olacaktır.

## Ad Alanlarını İçe Aktar

Koda dalmadan önce gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Örnek kodu birden çok adıma ayıralım:

## 1. Adım: Yeni bir Proje örneği oluşturun

```csharp
var project = new Project();
```

Bu satır, Aspose.Tasks'taki bir projeyi temsil eden Project sınıfının yeni bir örneğini başlatır.

## 2. Adım: Kaynak Ekleme

```csharp
var resource = project.Resources.Add("Work Resource");
```

Burada projeye "Work Resource" ismiyle yeni bir kaynak ekliyoruz.

## 3. Adım: Kullanılabilirlik Dönemlerini Tanımlayın

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 biz diyoruz`GetPeriods()` Kullanılabilirlik dönemlerinin bir koleksiyonunu alma yöntemi.

## 4. Adım: Kaynağa Kullanılabilirlik Dönemleri Ekleme

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Önceki adımda elde edilen kullanılabilirlik dönemlerinin toplanmasını yineliyoruz ve bunları kaynağa ekliyoruz.

## Adım 5: Kullanılabilirlik Dönemi Ayrıntılarını Görüntüleyin

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Son olarak, kaynakla ilişkili kullanılabilirlik dönemleri arasında geçiş yaparız ve başlangıç tarihi, bitiş tarihi ve kullanılabilir birimler dahil ayrıntılarını yazdırırız.

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'te kullanılabilirlik dönemleriyle nasıl çalışılacağını öğrendik. Adım adım kılavuzu takip ederek proje yönetimi uygulamalarınızda kaynak kullanılabilirliğini verimli bir şekilde yönetebilirsiniz.

## SSS'ler

### S1: Aspose.Tasks for .NET'i ticari projelerde kullanabilir miyim?

 C1: Evet, Aspose.Tasks for .NET ticari projelerde kullanılabilir. Lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).

### S2: Aspose.Tasks for .NET'in ücretsiz deneme sürümü mevcut mu?

C2: Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümünü edinebilirsiniz[Burada](https://releases.aspose.com/).

### S3: Aspose.Tasks for .NET belgelerini nerede bulabilirim?

 A3: Belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/tasks/net/).

### S4: Aspose.Tasks for .NET için nasıl destek alabilirim?

 Cevap4: Topluluk forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15).

### S5: Aspose.Tasks for .NET için geçici lisanslar sunuyor musunuz?

 Cevap5: Evet, geçici lisanslar mevcut[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
