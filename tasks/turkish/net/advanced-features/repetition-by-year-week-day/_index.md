---
date: 2026-04-03
description: Aspose.Tasks'i kullanarak yinelenen görev projesi eklemeyi ve projeyi
  MPP olarak kaydetmeyi öğrenin. Bu kılavuz, Yıl Hafta Gününe göre Tekrar özelliğini
  adım adım gösterir.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Aspose.Tasks'te Yıl, Hafta, Gün Tekrarı
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks Nasıl Kullanılır – Yıl, Hafta, Gün Tekrarlama
url: /tr/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Yıl Hafta Gününe Göre Tekrarlama

## Giriş

Karmaşık yinelenen takvimleri yönetmek için **how to use Aspose.Tasks**'a ihtiyacınız olduğunda, kütüphane yıllık desenler üzerinde ayrıntılı kontrol sağlar. Bu öğreticide, belirli bir ayın belirli bir haft günü üzerinde birden fazla yıl boyunca tekrarlanan bir görev oluşturmayı adım adım göstereceğiz. Sonunda sadece birkaç C# satırıyla **add recurring task project** girişlerini ekleyebilecek ve **save project as MPP** yapabileceksiniz.

## Hızlı Yanıtlar
- **“Repetition by Year Week Day” ne anlama geliyor?** Bir görevi her yıl belirli bir ayın seçilen haft gününde (ör. ilk Pazar) tekrarlatır.  
- **Hangi .NET sürümleri destekleniyor?** Tüm modern .NET Framework ve .NET Core/5/6 sürümleri.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gereklidir.  
- **Tekrarlama aralığını değiştirebilir miyim?** Evet – bir başlangıç tarihi, bitiş tarihi veya sabit bir tekrar sayısı belirleyebilirsiniz.  
- **Çıktı bir MPP dosyası mı?** Kesinlikle – proje, Microsoft Project için hazır bir MPP dosyası olarak kaydedilir.

## “Repetition by Year Week Day” özelliği nedir?

Bu özellik, belirli bir **hafta günü** (ör. Pazar) ve ay içindeki bir **konum** (ilk, ikinci, son vb.) hedefleyen yıllık bir tekrarlamayı tanımlamanıza olanak tanır. Bu, üç aylık incelemeler, yıllık denetimler veya takvim temelli bir ritme sahip herhangi bir etkinlik gibi görevler için idealdir.

## Neden yinelenen görevler için Aspose.Tasks kullanmalı?

- **Precision** – Aylar, hafta günleri ve sıra konumları üzerinde tam kontrol.  
- **Compatibility** – Microsoft Project'te sorunsuz açılan yerel MPP dosyaları üretir.  
- **No COM interop** – Saf .NET API, Office kurulumuna gerek yok.  
- **Scalability** – Küçük projeler ve kurumsal ölçekli takvimler için aynı şekilde çalışır.

## Önkoşullar

Koda başlamadan önce, şunların olduğundan emin olun:

1. **Basic .NET knowledge** – C# ve nesne‑yönelimli kavramlara aşina olmak.  
2. **Aspose.Tasks for .NET** – [download link](https://releases.aspose.com/tasks/net/) adresinden indirin ve DLL'i projenize ekleyin.  
3. **Access to the official docs** – [documentation](https://reference.aspose.com/tasks/net/) tüm sınıflar hakkında kapsamlı detaylar içerir.  
4. **A development IDE** – Visual Studio, Rider veya uyumlu herhangi bir .NET editörü.

Şimdi hazır olduğunuzda, uygulamayı görelim.

## Aspose.Tasks'i Yinelenen Görevler için Nasıl Kullanılır

### Gerekli Ad Alanlarını İçe Aktarma

İlk olarak, projeler, görevler ve kaydetme seçenekleriyle çalışabilmek için gerekli ad alanlarını kapsam içine getirin.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Adım 1: Proje ve Görev Parametrelerini Başlatma

Yeni bir `Project` örneği oluşturun, ardından tekrarlama desenini tanımlayan bir `RecurringTaskParameters` nesnesi tanımlayın.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** `Month`, `WeekDay` ve `Position` değerlerini gerçek zamanlı takviminize göre ayarlayın.

### Adım 2: Parametreleri Projeye Ekleme

Yinelenen görev tanımını projenin köküne ekleyin.

```csharp
project.RootTask.Children.Add(parameters);
```

### Adım 3: Projeyi MPP Olarak Kaydet

Son olarak, projeyi bir MPP dosyasına kaydedin, böylece Microsoft Project ya da uyumlu bir görüntüleyicide açılabilir.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> Bu, tek bir kod satırıyla **save project as mpp** gösterir.

## Yaygın Sorunlar ve Çözümler

| Semptom | Muhtemel Neden | Çözüm |
|---------|----------------|------|
| MPP dosyası açıldıktan sonra görevler görünmüyor | Tekrarlama aralığı tarihleri proje takviminin dışındadır | `Start` ve `Finish` tarihlerinin projenin çalışma zamanına dahil olduğunu doğrulayın |
| `Add` işleminde `ArgumentNullException` istisnası | `parameters` null veya tam olarak başlatılmamış | Tüm gerekli özelliklerin (TaskName, Duration, RecurrencePattern) ayarlandığından emin olun |
| Yanlış hafta günü seçildi | `WeekDay` enum değeri uyumsuz | Gerekli olduğunda `DayOfWeek.Monday` … `DayOfWeek.Sunday` kullanın |

## Sıkça Sorulan Sorular

**S: Sağlanan örnek dışındaki tekrarlama desenini özelleştirebilir miyim?**  
A: Evet, Aspose.Tasks, herhangi bir takvime uyması için `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern` veya hatta özel `RecurrenceRange` nesnelerini birleştirmenize izin verir.

**S: Aspose.Tasks for .NET diğer proje yönetim yazılımlarıyla uyumlu mu?**  
A: Kesinlikle – kütüphane MPP, XML ve Primavera formatlarını okuyup yazar, sorunsuz veri alışverişi sağlar.

**S: Yinelenen görevlerde istisnaları veya değişiklikleri nasıl yönetebilirim?**  
A: `ExceptionTask` sınıfını belirli tekrarlar için geçersiz kılmalar oluşturmak üzere kullanın, ya da `RecurringTaskParameters`'ı düzenleyip projeyi yeniden kaydedin.

**S: Aspose.Tasks bulut tabanlı çözümleri destekliyor mu?**  
A: Evet, API'yi Azure Functions, AWS Lambda veya herhangi bir .NET uyumlu bulut hizmetinde çalıştırabilirsiniz.

**S: Aspose.Tasks for .NET için bir deneme sürümü mevcut mu?**  
A: Evet, [website](https://releases.aspose.com/) adresinden Aspose.Tasks for .NET'in ücretsiz deneme sürümüne erişebilir, satın alma kararından önce özelliklerini keşfedebilirsiniz.

**S: Mevcut bir projeye diğer verileri üzerine yazmadan yinelenen görev nasıl eklenir?**  
A: Mevcut projeyi `new Project("Existing.mpp")` ile yükleyin, `RecurringTaskParameters`'ı `RootTask.Children`'a ekleyin ve ardından dosyayı `Save` edin.

## Sonuç

**how to use Aspose.Tasks**'i **Repetition by Year Week Day** senaryosu için ustalaşarak, gerçek takvimlerle mükemmel uyumlu **add recurring task project** girişleri ekleme ve **save project as MPP** yaparak sorunsuz iş birliği sağlama yeteneği kazanırsınız. Bu kod parçacıklarını kendi çözümlerinizde kullanarak zamanlama doğruluğunu artırın ve manuel çabayı azaltın.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}