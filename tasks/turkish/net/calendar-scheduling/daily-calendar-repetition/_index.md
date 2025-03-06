---
title: Aspose.Tasks'ta Günlük Takvim Tekrarı
linktitle: Aspose.Tasks'ta Günlük Takvim Tekrarı
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te günlük takvim tekrarlarıyla yinelenen görevlerin nasıl oluşturulacağını öğrenin. Proje yönetimi verimliliğini zahmetsizce artırın.
weight: 25
url: /tr/net/calendar-scheduling/daily-calendar-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Günlük Takvim Tekrarı

## giriiş

 Aspose.Tasks for .NET, görevleri ve projeleri programlı bir şekilde yönetmek için güçlü bir araç seti sağlar. Dikkate değer özelliklerinden biri, günlük takvim tekrarlarını verimli bir şekilde gerçekleştirebilmesidir. Bu derste, bu özelliğin nasıl kullanılacağını keşfedeceğiz.`DailyCalendarRepetition` Belirli bir takvime dayalı olarak günlük tekrarlarla yinelenen görevler oluşturmak için diğer ilgili sınıflarla birlikte sınıf.

## Önkoşullar

Başlamadan önce aşağıdaki kurulumlara sahip olduğunuzdan emin olun:

1.  Kurulum: Aspose.Tasks for .NET'in kurulu olduğundan emin olun. Değilse, adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/tasks/net/).

2. Ad Alanını İçe Aktarma: Gerekli ad alanlarını projenize aktarın:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## Adım 1: Projeyi Başlatın

Öncelikle mevcut bir projeyi yüklememiz veya çalışmak için yeni bir proje oluşturmamız gerekiyor:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## 2. Adım: Takvimi Tanımlayın

Daha sonra 24 saatlik bir takvim oluşturup bunu projeyle ilişkilendiriyoruz:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## Adım 3: Yinelenen Görev Parametrelerini Ayarlayın

Şimdi yinelenen görevimizin parametrelerini ayarlayalım. Adını, süresini, yinelenme modelini ve aralığını tanımlarız:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## 4. Adım: Görev için Takvimi Ayarlayın

Tanımlanan takvimi görevle ilişkilendirin:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## Adım 5: Projeye Görev Ekleme

Görevi tanımlanmış parametrelerle projeye ekleyin:

```csharp
project.RootTask.Children.Add(parameters);
```

## Adım 6: Projeyi Kaydet

Son olarak, eklenen yinelenen görevle birlikte projeyi kaydedin:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

Artık Aspose.Tasks for .NET'i kullanarak 24 saatlik bir takvime dayalı olarak günlük olarak tekrarlanacak şekilde ayarlanmış yinelenen görev içeren bir projeyi başarıyla oluşturdunuz!

## Çözüm

Bu eğitimde, günlük takvim tekrarlarını verimli bir şekilde gerçekleştirmek için Aspose.Tasks for .NET'in nasıl kullanılacağını gösterdik. Bu adımları izleyerek yinelenen görevleri projelerinize sorunsuz bir şekilde entegre edebilir, üretkenliği ve organizasyonu artırabilirsiniz.

## SSS'ler

### S1: Her tekrarın süresini özelleştirebilir miyim?

Cevap1: Evet, koddaki parametreleri değiştirerek her tekrarın süresini ihtiyaçlarınıza göre ayarlayabilirsiniz.

### S2: Aynı proje içindeki farklı görevler için farklı takvimler ayarlamak mümkün mü?

Cevap2: Kesinlikle Aspose.Tasks, bireysel görevlere belirli takvimler atamanıza olanak tanıyarak planlamada esneklik sunar.

### S3: Aspose.Tasks günlük dışında başka yinelenme modellerini de destekliyor mu?

C3: Evet, Aspose.Tasks, farklı proje ihtiyaçlarını karşılayan haftalık, aylık, yıllık vb. gibi çok çeşitli tekrarlama kalıpları sunar.

### S4: Aspose.Tasks kullanılarak oluşturulan yinelenen görevleri görselleştirebilir miyim?

Cevap4: Kesinlikle Aspose.Tasks, yinelenen görevleri etkili bir şekilde analiz etmenize ve izlemenize yardımcı olacak görselleştirme seçenekleri sunuyor.

### S5: Aspose.Tasks'ın deneme sürümü mevcut mu?

 Cevap5: Evet, Aspose.Tasks'ın ücretsiz deneme sürümünden yararlanabilirsiniz.[Burada](https://releases.aspose.com/) Bir satın alma işlemi yapmadan önce özelliklerini keşfetmek için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
