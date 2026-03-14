---
date: 2026-03-14
description: Aspose.Tasks for .NET'te nullable (null olabilen) boolean değerlerini
  nasıl kullanacağınızı öğrenin; nullable boolean değerlerini dönüştürme ve nullable
  boolean özelliklerini ayarlamayı da içerir.
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Nullable Boolean Değerleri Nasıl Kullanılır
url: /tr/net/advanced-concepts/nullable-booleans/
weight: 21
---

 kept.

Check for italic: *undefined* remains.

Check for code formatting: backticks remain.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Nullable Booleans Nasıl Kullanılır

Bu öğreticide, Aspose.Tasks .NET API'si ile çalışırken **nullable** booleans nasıl kullanılacağını göstereceğiz. Nullable booleans size üç olası durum sağlar—`true`, `false` veya *undefined*—ki bu, açıkça belirtilmemiş olabilecek proje‑seviyesi ayarlar için özellikle kullanışlıdır. Nullable boolean değerlerini nasıl oluşturacağınızı, dönüştüreceğinizi ve **set nullable boolean** değerlerini nasıl ayarlayacağınızı göreceksiniz, ve nullable booleans'ı doğru şekilde ele almanın zamanlama uygulamalarınızdaki beklenmeyen davranışları önleyebileceğini öğreneceksiniz.

## Hızlı Yanıtlar
- **Nullable boolean nedir?** `true`, `false` değerlerini tutabilen veya undefined olabilen bir tip.  
- **Aspose.Tasks'te nullable booleans neden kullanılır?** Varsayılan bir değer tahmin etmeden isteğe bağlı proje özelliklerini temsil etmenizi sağlar.  
- **Nullable bir boole'ı normal bool'a nasıl dönüştürürsünüz?** Önce `IsDefined` kontrol edin veya örtük dönüşümü kullanın.  
- **Ana sınıf nedir?** `Aspose.Tasks` ad alanındaki `NullableBool`.  
- **Lisans gerekiyor mu?** Evet, üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir.

## Nullable Boolean Nedir?

Nullable bir boolean (`NullableBool`), normal `bool` tipine bir *IsDefined* bayrağı ekleyerek genişletir. `IsDefined` `false` olduğunda, değer undefined kabul edilir ve “false” ile “set edilmemiş” arasında ayrım yapmanızı sağlar.

## Proje Ayarlarında Nullable Booleans Neden Ele Alınmalı?

Birçok proje seçeneği—**ActualsInSync** veya **HonorConstraints** gibi—isteğe bağlıdır. Düz bir `bool` kullanmak, `true` veya `false` seçmenizi zorunlu kılar ve bu, kullanıcının niyetini istemeden geçersiz kılabilir. **Nullable booleans'ı ele alarak**, orijinal durumu korur ve kazara yapılandırma değişikliklerinden kaçınırsınız.

## Önkoşullar

Başlamadan önce şunların yüklü olduğundan emin olun:

1. **Visual Studio** (veya herhangi bir .NET‑uyumlu IDE).  
2. **Aspose.Tasks for .NET** – indirmek için [buraya](https://releases.aspose.com/tasks/net/) tıklayın.

## Ad Alanlarını İçe Aktarma

İlk olarak, gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

Şimdi her örneği adım adım inceleyelim.

## `NullableBool` ile Çalışma

### Adım 1: Yeni bir `Project` örneği oluşturun.

```csharp
var project = new Project();
```

### Adım 2: Belirtilen değerlerle bir `NullableBool` nesnesi örnekleyin.

```csharp
var actualsInSync = new NullableBool(false, false);
```

### Adım 3: `NullableBool` nesnesinin değerini ve tanımlı durumunu kontrol edin.

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### Adım 4: Projede **Set nullable boolean** ayarlayın.

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### Adım 5: Tek bir değerle başka bir `NullableBool` nesnesi örnekleyin.

```csharp
var honorConstraints = new NullableBool(true);
```

### Adım 6: `NullableBool` nesnesinin string temsilini gösterin.

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### Adım 7: Projede ayarlayarak `NullableBool` örneğini kullanın.

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## `NullableBool` Örneklerini Karşılaştırma

### Adım 1: İki `NullableBool` nesnesi örnekleyin.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Adım 2: Her `NullableBool` nesnesinin string temsilini kontrol edin.

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### Adım 3: `bool`'a örtük dönüşüm ve sonucu yazdırma.

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### Adım 4: İki `NullableBool` nesnesini eşitlik açısından karşılaştırın.

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## `NullableBool`'ın Hash Kodunu Alma

### Adım 1: İki `NullableBool` nesnesi örnekleyin.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Adım 2: Her `NullableBool` nesnesinin hash kodunu yazdırın.

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## Yaygın Tuzaklar ve İpuçları

- **Nullable bir boolean'ın tanımlı olduğunu asla varsaymayın.** `Value` kullanmadan önce her zaman `IsDefined` kontrol edin.  
- **Kontrol etmeden normal bir bool'a dönüştürmek**, değer undefined ise bir istisna fırlatabilir. Örtük dönüşümü yalnızca tanımlı olduğundan emin olduğunuzda kullanın.  
- **Proje özelliklerini ayarlarken**, gerektiğinde undefined durumunu korumak için `Set` metodunu bir `NullableBool` ile kullanın.

## Sıkça Sorulan Sorular

**S: Nullable bir boolean nedir?**  
C: Nullable bir boolean `true`, `false` veya undefined bir durumu temsil edebilir; bu, üç ayrı sonuç sağlar.

**S: Nullable bir boolean'ı güvenli bir şekilde normal bool'a nasıl dönüştürebilirim?**  
C: Önce `IsDefined` kontrol edin, ardından `Value` özelliğini kullanın veya tanımlı olduğundan emin olduğunuzda örtük dönüşüme güvenin.

**S: Aspose.Tasks'te düz bool'lar yerine nullable booleans kullanmalıyım?**  
C: İsteğe bağlı proje ayarlarını dokunulmamış tutar, kazara üzerine yazılmaları önler.

**S: Nullable bir boolean'ı undefined olarak ayarlayabilir miyim?**  
C: Evet—sadece tanımlı bayrağını kabul eden yapıcıyı kullanın, örn. `new NullableBool(false, false)`.

**S: Aspose.Tasks for .NET hakkında daha fazla belgeleri nerede bulabilirim?**  
C: Ayrıntılı belgeleri [burada](https://reference.aspose.com/tasks/net/) bulabilirsiniz.

---

**Son Güncelleme:** 2026-03-14  
**Test Edilen Versiyon:** Aspose.Tasks for .NET (en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}