---
title: Aspose.Tasks'ta Hesaplama Modu
linktitle: Aspose.Tasks'ta Hesaplama Modu
second_title: Aspose.Tasks .NET API'si
description: Proje planlamasını ve görev bağımlılıklarını kolaylaştırmak için Aspose.Tasks for .NET'te hesaplama modlarını etkili bir şekilde nasıl yöneteceğinizi öğrenin.
weight: 29
url: /tr/net/advanced-features/calculation-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Hesaplama Modu

## giriiş

Aspose.Tasks for .NET, geliştiricilerin .NET uygulamalarında Microsoft Project dosyalarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir API'dir. Proje dosyalarıyla çalışmanın önemli yönlerinden biri, görevlerin ve proje zamanlamalarının nasıl hesaplanacağını ve güncelleneceğini belirleyen hesaplama modlarının yönetilmesidir. Bu eğitimde Aspose.Tasks for .NET tarafından desteklenen çeşitli hesaplama modlarını inceleyeceğiz ve bunların nasıl etkili bir şekilde kullanılacağını göstereceğiz.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Visual Studio: Sisteminizde Visual Studio'nun kurulu olduğundan emin olun.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
3. C# programlamanın temel anlayışı: C# programlama kavramlarına aşina olun.

## Ad Alanlarını İçe Aktar

Aspose.Tasks for .NET ile çalışmaya başlamadan önce gerekli ad alanlarını içe aktaralım:

```csharp
using Aspose.Tasks;
using System;


```

## Otomatik Hesaplama Modunu Uygulama

### 1. Adım: Yeni bir Proje örneği oluşturun

 Yeni bir başlangıç başlat`Project` nesneyi ve onu ayarlayın`CalculationMode` mülkiyet`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### 2. Adım: Proje başlangıç tarihini ayarlayın ve görevleri ekleyin

Projenin başlangıç tarihini tanımlayın ve ona görevler ekleyin.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### 3. Adım: Görevleri bağlayın

Görevler arasında bağımlılıklar oluşturun.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### 4. Adım: Yeniden hesaplanan tarihleri doğrulayın

Tarihlerin otomatik olarak yeniden hesaplanıp hesaplanmadığını kontrol edin.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Gerektiğinde daha fazla doğrulama ekleyin
```

## Manuel Hesaplama Modunu Uygulama

### 1. Adım: Yeni bir Proje örneği oluşturun

 Yeni bir başlangıç başlat`Project` nesneyi ve onu ayarlayın`CalculationMode` mülkiyet`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### 2. Adım: Proje başlangıç tarihini ayarlayın ve görevleri ekleyin

Projenin başlangıç tarihini tanımlayın ve ona görevler ekleyin.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### 3. Adım: Görev özelliklerini doğrulayın

Görev özelliklerinin manuel modda doğru ayarlanıp ayarlanmadığını kontrol edin.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Gerektiğinde daha fazla doğrulama ekleyin
```

### 4. Adım: Görevleri bağlayın ve tarihleri doğrulayın

Görevleri birbirine bağlayın ve tarihlerinin yeniden hesaplanıp hesaplanmadığını kontrol edin.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Hiçbiri Hesaplama Modunun Uygulanması

### 1. Adım: Yeni bir Proje örneği oluşturun

 Yeni bir başlangıç başlat`Project` nesneyi ve onu ayarlayın`CalculationMode` mülkiyet`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### 2. Adım: Yeni bir görev ekleyin

Projeye yeni bir görev ekleyin.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### 3. Adım: Görev özelliklerini doğrulayın

Görev özelliklerinin otomatik olarak hesaplanıp hesaplanmadığını kontrol edin.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Gerektiğinde daha fazla doğrulama ekleyin
```

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'te bulunan hesaplama modlarını araştırdık ve bunların pratik senaryolarda nasıl uygulanacağını öğrendik. Otomatik, manuel veya hesaplamasız moda ihtiyacınız olsun, Aspose.Tasks projenizin gereksinimlerine uyacak esnekliği sağlar.

## SSS'ler

### S1: Çalışma zamanı sırasında hesaplama modunu dinamik olarak değiştirebilir miyim?

Cevap1: Evet, bir projenin hesaplama modunu çalışma zamanı sırasında herhangi bir noktada değiştirerek değiştirebilirsiniz.`CalculationMode` mülk.

### S2: Aspose.Tasks, Microsoft Project'in yanı sıra diğer proje yönetimi dosya formatlarını da destekliyor mu?

Cevap2: Aspose.Tasks öncelikli olarak Microsoft Project dosya formatlarına odaklanır ancak Primavera P6 XML, Primavera DB ve Asta Powerproject XML gibi diğer formatları da destekler.

### S3: Aspose.Tasks hem küçük ölçekli hem de kurumsal düzeydeki projeler için uygun mu?

A3: Kesinlikle! Aspose.Tasks, kapsamlı özellikleri ve güçlü API'leri ile hem küçük ölçekli hem de kurumsal düzeydeki projelerin ihtiyaçlarını karşılamak üzere tasarlanmıştır.

### S4: Aspose.Tasks'ı diğer .NET kütüphaneleri ve çerçeveleriyle entegre edebilir miyim?

Cevap4: Evet, uygulamalarınızın işlevselliğini geliştirmek için Aspose.Tasks'i diğer .NET kütüphaneleri ve çerçeveleriyle sorunsuz bir şekilde entegre edebilirsiniz.

### S5: Aspose.Tasks kullanıcıları için bir topluluk forumu veya destek kanalı var mı?

 A5: Evet, ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) topluluk desteği ve tartışmalar için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
