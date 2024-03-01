---
title: Aspose.Tasks'ta Süre İşleme
linktitle: Aspose.Tasks'ta Süre İşleme
second_title: Aspose.Tasks .NET API'si
description: Adım adım eğitimlerle Aspose.Tasks for .NET'te süreleri etkili bir şekilde nasıl yöneteceğinizi öğrenin.
type: docs
weight: 30
url: /tr/net/calendar-scheduling/duration-handling/
---
## giriiş

Proje yönetimi uygulamalarında sürelerin etkin bir şekilde ele alınması çok önemlidir. Aspose.Tasks for .NET, sürelerin verimli bir şekilde yönetilmesi için güçlü işlevsellik sağlar. Bu eğitimde Aspose.Tasks for .NET'i kullanarak süre işlemenin çeşitli yönlerini inceleyeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1. Temel C# Bilgisi: Örnekleri anlamak ve uygulamak için C# programlama diline aşina olmak çok önemlidir.
2. Visual Studio: .NET uygulamalarını oluşturmak ve çalıştırmak için Visual Studio IDE'yi yükleyin.
3.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kitaplığını indirip yükleyin. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).

## Ad Alanlarını İçe Aktar

Öncelikle Aspose.Tasks işlevlerini kullanmak için gerekli ad alanlarını içe aktaralım:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Adım adım kılavuz formatında her örneği birden fazla adıma ayıralım:

## Görev Sürelerinin Güncellenmesi

### Adım 1: Proje Dosyasını Yükleyin

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 2. Adım: Görevi ve Süreyi Alın

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### 3. Adım: Güncelleme Süresi

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Adım 4: Güncelleme Süresini Görüntüleyin

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Görev Sürelerinin Çıkarılması

### Adım 1: Proje Dosyasını Yükleyin

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 2. Adım: Görevi ve Süreyi Alın

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Adım 3: Süreyi Çıkarın

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Adım 4: Güncelleme Süresini Görüntüleyin

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Süreyi TimeSpan'a Dönüştürme

### Adım 1: Proje Dosyasını Yükleyin

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 2. Adım: Görevi ve Süreyi Alın

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### 3. Adım: Süreyi TimeSpan'a Dönüştürün

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## Süreyi String'e Dönüştürme

### Adım 1: Proje Dosyasını Yükleyin

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 2. Adım: Görevi ve Süreyi Alın

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### 3. Adım: Süreyi Dizeye Dönüştürün

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'te süre işlemenin çeşitli yönlerini ele aldık. Süreleri anlamak ve etkili bir şekilde yönetmek, başarılı proje yönetimi için hayati öneme sahiptir. Aspose.Tasks, .NET uygulamalarınızdaki süre yönetimi görevlerini basitleştirmek için kapsamlı işlevler sağlar.

## SSS'ler

### S1: Aspose.Tasks for .NET nedir?

Cevap1: Aspose.Tasks for .NET, .NET uygulamalarında Microsoft Project dosyalarıyla çalışmak için güçlü bir kütüphanedir.

### S2: Aspose.Tasks karmaşık proje yapılarını yönetebilir mi?

C2: Evet, Aspose.Tasks karmaşık proje yapılarını kolaylıkla yönetebilir ve manipülasyon için kapsamlı API'ler sağlar.

### S3: Aspose.Tasks for .NET, .NET Core ile uyumlu mu?

C3: Evet, Aspose.Tasks for .NET, .NET Core ile uyumludur ve onu platformlar arası uygulamalarda kullanmanıza olanak tanır.

### S4: Aspose.Tasks, Microsoft Project dosyalarının okunmasını ve yazılmasını destekliyor mu?

Cevap4: Evet, Aspose.Tasks, MPP, XML ve MPX dahil olmak üzere çeşitli formatlardaki Microsoft Project dosyalarının okunmasını ve yazılmasını destekler.

### S5: Aspose.Tasks for .NET'in deneme sürümü mevcut mu?

Cevap5: Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[Burada](https://releases.aspose.com/).