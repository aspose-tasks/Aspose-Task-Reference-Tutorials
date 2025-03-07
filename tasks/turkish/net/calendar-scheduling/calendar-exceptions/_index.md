---
title: Aspose.Tasks'ta Takvim İstisnalarını Yönetme
linktitle: Aspose.Tasks'ta Takvim İstisnalarını Yönetme
second_title: Aspose.Tasks .NET API'si
description: Adım adım eğitimler ve örneklerle Aspose.Tasks for .NET'te takvim istisnalarını nasıl yöneteceğinizi öğrenin.
weight: 12
url: /tr/net/calendar-scheduling/calendar-exceptions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Takvim İstisnalarını Yönetme

## giriiş

Bu eğitimde, .NET çerçevesini kullanarak Aspose.Tasks'ta takvim istisnalarının nasıl yönetileceğini inceleyeceğiz. Takvim istisnaları, bir proje takviminde tatiller veya geçici kapanışlar gibi normal çalışma programının değiştirildiği özel tarihler veya dönemler tanımlamamıza olanak tanır. Aspose.Tasks for .NET'i kullanarak takvim istisnalarını adım adım ele almak için çeşitli yöntemleri ele alacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Temel C# programlama dili bilgisi.
- Sisteminizde Visual Studio yüklü.
- Aspose.Tasks for .NET kütüphanesi projenize eklendi.

## Ad Alanlarını İçe Aktar

Öncelikle projemiz için gerekli namespace’leri import edelim:

```csharp
using Aspose.Tasks;
using System;


```

## 1. Adım: Takvim İstisnasını Silme

Bir takvim istisnasını silmek için şu adımları izleyin:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Takvim bilgilerini görüntüle
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // İlk istisnayı kaldır
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## 2. Adım: Bir Takvim İstisnasının Çalışma Süresini Alma

Bir takvim istisnasının çalışma süresini almak için şu adımları izleyin:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Takvim ve istisna bilgilerini görüntüle
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Çalışma süresini alın ve ayrıntıları görüntüleyin
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## 3. Adım: Takvim İstisnalarını Tanımlama

Takvim istisnalarını eklemek veya kaldırmak için şu adımları izleyin:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Yeni bir takvim istisnası oluştur
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // İstisna ayrıntılarını ayarlayın
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Tarihin istisna olup olmadığını kontrol edin
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // İstisnayı takvime ekleyin
    calendar.Exceptions.Add(exception);

    // Varsa bir istisnayı kaldırın
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Yeni bir istisna ekle
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // İstisnaları yazdır
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Çözüm

Bu makalede Aspose.Tasks for .NET'te takvim istisnalarının ele alınmasının çeşitli yönlerini ele aldık. Verilen adımları takip ederek proje programlarınızdaki istisnaları etkili bir şekilde yönetebilir, çalışma saatlerinin ve özel etkinliklerin doğru şekilde gösterilmesini sağlayabilirsiniz.

## SSS'ler

### S1: Tek bir takvime birden fazla istisna ekleyebilir miyim?

C1: Evet, çeşitli özel tarih veya dönemlere uyum sağlamak için bir takvime birden fazla istisna ekleyebilirsiniz.

### S2: Belirli bir tarihin istisna olup olmadığını nasıl kontrol edebilirim?

 A2: kullanabilirsiniz`CheckException()` Belirli bir tarihin istisna kapsamına girip girmediğini doğrulamaya yönelik yöntem.

### S3: Mevcut bir istisnayı takvimden kaldırmak mümkün müdür?

 C3: Evet, şuraya erişerek istisnaları kaldırabilirsiniz:`Exceptions` takvimin toplanması ve kullanılması`Remove()` yöntem.

### S4: Ne tür takvim istisnaları destekleniyor?

Cevap4: Aspose.Tasks, günlük, haftalık, aylık ve yıllık istisnalar dahil olmak üzere çeşitli istisna türlerini destekleyerek istisna kurallarının tanımlanmasında esneklik sağlar.

### S5: Belirli istisna tarihleri için çalışma saatlerini özelleştirebilir miyim?

C5: Evet, Aspose.Tasks tarafından sağlanan uygun yöntemleri kullanarak ayrı ayrı istisna tarihleri için özel çalışma süreleri tanımlayabilirsiniz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
