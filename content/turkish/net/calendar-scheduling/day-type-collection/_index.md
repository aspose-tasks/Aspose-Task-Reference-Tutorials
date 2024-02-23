---
title: Aspose.Tasks'ta Gün Türü Koleksiyonunu Yönetme
linktitle: Aspose.Tasks'ta Gün Türü Koleksiyonunu Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te gün türü koleksiyonlarını verimli bir şekilde nasıl yöneteceğinizi öğrenin. Takvim istisnalarını kolaylıkla oluşturun, değiştirin ve yönetin.
type: docs
weight: 28
url: /tr/net/calendar-scheduling/day-type-collection/
---
## giriiş

 Aspose.Tasks for .NET, proje yönetimi uygulamalarında haftalık takvim istisnalarını tanımlamak için çok önemli olan gün türü koleksiyonlarını yönetmek için güçlü işlevsellik sağlar. Bu derste, bu özelliğin nasıl kullanılacağını keşfedeceğiz.`DayTypeCollection` verimli bir şekilde sınıf. 

## Önkoşullar

Eğiticiye devam etmeden önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1. Visual Studio: Sisteminizde Visual Studio'nun kurulu olduğundan emin olun.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
3. Temel C# Bilgisi: C# programlama dili ve .NET çerçeve kavramlarına aşinalık.

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını C# projenize aktarmanız gerekir:

```csharp
using Aspose.Tasks;
using System;


```

Şimdi verilen örneği birden çok adıma ayıralım:

## 1. Adım: Projeyi Yükleyin ve Takvime Erişin

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Bu adım, yeni bir proje örneğini başlatır ve takvimi UID'sine göre alır.

## 2. Adım: Takvim İstisnalarını Yineleyin

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Burada, her takvim istisnasını yineliyoruz ve adını ve ilgili gün türlerini yazdırıyoruz.

## 3. Adım: Takvim İstisnalarını Değiştirin

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

Bu adım, gün türlerini ekleyerek, kaldırarak veya güncelleyerek takvim istisnalarının nasıl değiştirileceğini gösterir.

## 4. Adım: Yeni Takvim İstisnalarını Oluşturun ve Değiştirin

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

Bu son adımda, yeni takvim istisnaları oluşturuyoruz ve gün türlerini ekleyip kopyalayarak bunları değiştiriyoruz.

## Çözüm

 Sonuç olarak, Aspose.Tasks for .NET'te gün türü koleksiyonlarını yönetmek, proje yönetimi uygulamalarında haftalık takvim istisnalarını tanımlamak ve değiştirmek için çok önemlidir. Bu eğitimde sağlanan adım adım kılavuzu takip ederek, etkili bir şekilde kullanabilirsiniz.`DayTypeCollection` Çeşitli takvim işlemlerini gerçekleştirecek sınıf.

## SSS'ler

### S1: Aspose.Tasks for .NET programlı olarak Gantt grafikleri oluşturmak için kullanılabilir mi?

C1: Evet, Aspose.Tasks for .NET, .NET uygulamalarında Gantt grafikleri oluşturmak ve değiştirmek için API'ler sağlar.

### S2: Aspose.Tasks for .NET hem .NET Core hem de .NET Framework ile uyumlu mu?

C2: Evet, Aspose.Tasks for .NET hem .NET Core hem de .NET Framework'ü destekler.

### S3: Aspose.Tasks for .NET için nasıl destek alabilirim?

 C3: adresini ziyaret ederek destek alabilirsiniz.[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) soru sorabileceğiniz ve diğer kullanıcılarla etkileşime girebileceğiniz yer.

### S4: Aspose.Tasks for .NET ücretsiz deneme olanağı sunuyor mu?

 Cevap4: Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[Burada](https://releases.aspose.com/).

### S5: Aspose.Tasks for .NET için geçici bir lisans satın alabilir miyim?

 C5: Evet, geçici lisanslar şu adresten satın alınabilir:[Web sitesi](https://purchase.aspose.com/temporary-license/).