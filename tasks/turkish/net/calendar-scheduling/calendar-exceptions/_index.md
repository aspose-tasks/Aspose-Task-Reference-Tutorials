---
date: 2026-04-13
description: Aspose.Tasks for .NET'te takvim istisnasını nasıl sileceğinizi öğrenin
  ve ASP.NET takvim planlamasını yönetirken istisna tarihini kontrol edin.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Aspose.Tasks ile Takvim İstisnasını Sil
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks ile Takvim İstisnasını Sil
url: /tr/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Takvim İstisnasını Sil

## Giriş

Bu öğreticide, **takvim istisnasını silmeyi** ve Aspose.Tasks kullanarak .NET çerçevesiyle diğer takvim istisnalarını yönetmeyi öğreneceksiniz. Takvim istisnaları, tatilleri, geçici kapanışları veya normal çalışma programının değiştiği özel dönemleri modellemenizi sağlar. Bu istisnaları ekleme, sorgulama ve kaldırma konularını anlamak, özellikle **ASP.NET takvim planlaması** senaryolarıyla çalışırken doğru proje zamanlaması için çok önemlidir.

## Hızlı Yanıtlar
- **Bir istisna kaldırmak için birincil yöntem nedir?** `CalendarException` nesnesindeki `Delete()` metodunu kullanın.  
- **Hangi sınıf bir tarihi istisna ile kontrol eder?** `CalendarException.CheckException()` — **istisna tarihini kontrol** etmek için faydalıdır.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Evet, üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **Tek bir takvime birden fazla istisna ekleyebilir miyim?** Kesinlikle; `Exceptions` koleksiyonu birçok girişi destekler.  
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Takvim İstisnası Nedir?

Bir **takvim istisnası**, normal çalışma takviminden sapmayı temsil eder—bu, “bu tarihlerde çalışma saatleri farklıdır ya da hiç çalışılmaz” diyen bir kural gibi düşünülebilir. Aspose.Tasks içinde, her istisna kendi çalışma saatlerine, yineleme desenine ve günün çalışılıp çalışılmadığını gösteren işaretçilere sahip olabilir.

## ASP.NET Takvim Planlamasında Takvim İstisnalarını Yönetmenin Nedenleri?

- **Doğru zaman çizelgeleri:** Projeler tatilleri ve özel kapanışları otomatik olarak dikkate alır, gerçekçi olmayan son tarihleri önler.  
- **Esneklik:** Günlük, haftalık, aylık veya yıllık desenler tanımlayarak gerçek dünya iş takvimleriyle eşleşebilirsiniz.  
- **Otomasyon:** Bir istisna tarihini programlı olarak kontrol etmek, ASP.NET uygulamalarında dinamik planlama mantığı oluşturmanızı sağlar.

## Ön Koşullar

- C# programlaması hakkında temel bilgi.  
- Visual Studio (herhangi bir yeni sürüm).  
- Projenize eklenmiş Aspose.Tasks for .NET kütüphanesi (NuGet aracılığıyla veya manuel referansla).  

## Ad Alanlarını İçe Aktar

İlk olarak, ihtiyacınız olan ad alanlarını içe aktarın:

```csharp
using Aspose.Tasks;
using System;
```

## Adım 1: Takvim İstisnasını Sil

İstenmeyen bir istisnayı kaldırmak basittir. Aşağıdaki kod bir projeyi yükler, ilk takvimi seçer, temel bilgileri gösterir, ilk istisnayı siler ve ardından güncellenmiş sayıyı gösterir.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **Pro ipucu:** `Delete()` metodunu çağırmadan önce istisna indeksinin mevcut olduğunu her zaman doğrulayın, aksi takdirde `IndexOutOfRangeException` alırsınız.

## Adım 2: Bir Takvim İstisnasının Çalışma Süresini Al

Bir istisna için tanımlanan çalışma saatlerini incelemeniz gerekiyorsa, `GetWorkingTime()` metodunu kullanın. Bu örnek ayrıca `CheckException` ile **istisna tarihini kontrol** etmenin nasıl yapılacağını gösterir.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Adım 3: Takvim İstisnalarını Tanımla

Aşağıda, takvim istisnalarını **ekleme**, **kontrol** etme ve **kaldırma** işlemlerini gösteren eksiksiz bir adım‑adım rehber bulunmaktadır. Belirli bir an için **istisna tarihini kontrol** etmek amacıyla `CheckException` kullanımına dikkat edin.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Yaygın Sorunlar ve İpuçları

| Sorun | Sebep | Çözüm |
|-------|--------|----------|
| **Silinirken `IndexOutOfRangeException`** | Var olmayan bir istisnayı silmeye çalışmak. | `Delete()` çağırmadan önce `calendar.Exceptions.Count` > indeks olduğundan emin olun. |
| **Yanlış çalışma saatleri** | `DayWorking` veya `WorkingTimes` doğru ayarlanmamış. | Açık dönemler tanımlamak için `exception.WorkingTimes.Add(new WorkingTime(...))` kullanın. |
| **İstisna tanınmıyor** | `CheckException` metodunun tarih tanımlı aralığın dışında olduğu için `false` döndürmesi. | `FromDate`/`ToDate` ve `Type` (Daily, Weekly, vb.) değerlerini tekrar kontrol edin. |

## Sık Sorulan Sorular

**S: Tek bir takvime birden fazla istisna ekleyebilir miyim?**  
C: Evet, tatilleri, bakım pencerelerini veya herhangi bir özel planlama kuralını temsil etmek için ihtiyacınız kadar istisna ekleyebilirsiniz.

**S: Belirli bir gün için **istisna tarihini kontrol** nasıl yaparım?**  
C: `CalendarException` örneği üzerinde `CheckException(DateTime date)` metodunu kullanın. Sağlanan tarih istisna aralığı içinde ise `true` döner.

**S: Takvimden mevcut bir istisnayı kaldırmak mümkün mü?**  
C: Kesinlikle. `Exceptions` koleksiyonuna erişin ve `Remove()` metodunu çağırın veya belirli `CalendarException` nesnesinde `Delete()` metodunu kullanın.

**S: Hangi takvim istisna türleri destekleniyor?**  
C: Aspose.Tasks, Daily, Weekly, Monthly ve Yearly istisna türlerini destekler; bu da neredeyse her yineleme desenini modellemenize esneklik sağlar.

**S: Belirli istisna tarihleri için çalışma saatlerini özelleştirebilir miyim?**  
C: Evet. Bir istisna oluşturduktan sonra, o günün başlangıç ve bitiş zamanlarını tanımlayan `WorkingTime` nesneleriyle `WorkingTimes` koleksiyonunu doldurun.

## Sonuç

**Takvim istisnasını sil** işlemlerinin tam yaşam döngüsünü, mevcut istisnaları incelemekten yeni eklemeye ve tarihleri kontrol etmeye kadar adım adım gösterdik. Bu tekniklere hâkim olmak, proje zamanlamalarınızın gerçek dünya takvimlerine saygı göstermesini sağlar ve ASP.NET takvim planlaması uygulamalarınızı sağlam ve güvenilir kılar.

---

**Son Güncelleme:** 2026-04-13  
**Test Edilen:** Aspose.Tasks for .NET (en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}