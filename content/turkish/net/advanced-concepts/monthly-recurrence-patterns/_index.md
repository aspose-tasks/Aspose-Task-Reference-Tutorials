---
title: Aspose.Tasks'ta Aylık Yinelenme Modellerini İşleme
linktitle: Aspose.Tasks'ta Aylık Yinelenme Modellerini İşleme
second_title: Aspose.Tasks .NET API'si
description: Bu adım adım eğitimle Aspose.Tasks for .NET'te aylık yinelenme modellerini nasıl yöneteceğinizi öğrenin.
type: docs
weight: 18
url: /tr/net/advanced-concepts/monthly-recurrence-patterns/
---
## giriiş

Aspose.Tasks for .NET, geliştiricilerin Microsoft Project dosyalarını programlı olarak değiştirmesine olanak tanıyan güçlü bir API'dir. Sunduğu temel işlevlerden biri, yinelenen görevleri verimli bir şekilde yerine getirebilme yeteneğidir. Bu eğitimde, Aspose.Tasks'ı kullanarak aylık yineleme modelleriyle nasıl çalışılacağını adım adım inceleyeceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların kurulu olduğundan emin olun:

## Ad Alanlarını İçe Aktar

Öncelikle .NET projenize gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Şimdi aylık yinelenme modellerini ele alma sürecini birden çok adıma ayıralım:

## Adım 1: Projeyi Başlatın

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Adım 2: Yinelenen Görev Parametrelerini Ayarlayın

Görev adı, süre ve yinelenme düzeni de dahil olmak üzere yinelenen görevin parametrelerini tanımlayın:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

## Adım 3: Projeye Parametreler Ekleme

```csharp
project.RootTask.Children.Add(parameters);
```

## Adım 4: Projeyi Kaydet

Değiştirilen projeyi yinelenen görevle kaydedin:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Çözüm

Aspose.Tasks for .NET'te aylık yineleme modellerini yönetmek basit ve etkilidir. Bu eğitimde özetlenen adımları izleyerek, belirli aylık aralıklarla ve yinelenme aralıklarıyla yinelenen görevleri kolayca oluşturabilirsiniz.

## SSS'ler

### S1: Aspose.Tasks, Microsoft Project dosyalarının tüm sürümleriyle uyumlu mudur?

Cevap1: Aspose.Tasks, MPP, MPT, XML ve MPX dahil olmak üzere Microsoft Project dosyalarının çeşitli sürümlerini destekler.

### S2: Yinelenme modelini daha da özelleştirebilir miyim?

C2: Evet, Aspose.Tasks günlük, haftalık, aylık ve yıllık dahil olmak üzere yineleme düzenlerini özelleştirmek için kapsamlı seçenekler sunar.

### S3: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?

 Cevap3: Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü web sitesinden edinebilirsiniz.[Burada](https://releases.aspose.com/).

### S4: Aspose.Tasks için nasıl destek alabilirim?

 Cevap4: Yardım isteyebilir ve konuyla ilgili tartışmalara katılabilirsiniz.[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).

### S5: Aspose.Tasks lisansını nereden satın alabilirim?

 Cevap5: Aspose.Tasks için web sitesinden lisans satın alabilirsiniz.[Burada](https://purchase.aspose.com/buy)