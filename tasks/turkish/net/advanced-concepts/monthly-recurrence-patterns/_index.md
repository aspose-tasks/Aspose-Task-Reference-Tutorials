---
date: 2026-03-08
description: Aspose.Tasks for .NET'te aylık yinelenen bir görevi nasıl oluşturacağınızı
  bu adım adım öğreticide öğrenin.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Aylık Tekrarlayan Görev Nasıl Oluşturulur
url: /tr/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aylık Yinelenen Görev Oluşturma Aspose.Tasks Kullanarak

## Giriş

Aspose.Tasks for .NET, Microsoft Project dosyalarını programlı olarak manipüle etmenizi sağlar ve en yaygın gerçek‑dünya ihtiyaçlarından biri **aylık yinelenen görev** takvimleri oluşturmaktır. Bir proje‑takip aracı geliştiriyor, kaynak tahsislerini otomatikleştiriyor ya da yinelenen bakım iş öğeleri üretiyor olun, bu öğretici bir göreve aylık yineleme deseni eklemek için gereken adımları ayrıntılı açıklamalar ve pratik ipuçlarıyla size gösterir.

İlerleyen bölümlerde projeyi nasıl kuracağınızı, yineleme parametrelerini nasıl tanımlayacağınızı ve güncellenmiş dosyayı nasıl kaydedeceğinizi göreceksiniz — hepsi net açıklamalar ve uygulamalı önerilerle.

## Hızlı Yanıtlar
- **“Aylık yinelenen görev” ne anlama gelir?** Görevin her ay tanımlı bir gün‑veya‑hafta desenine göre tekrarlanması.  
- **Hangi API sınıfı yinelemeyi yönetir?** `RecurringTaskParameters` ve `MonthlyRecurrencePattern`.  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme yeterlidir; üretim için lisans gereklidir.  
- **Aralığı değiştirebilir miyim?** Evet – `RepetitionInterval` değerini tekrarlar arasındaki ay sayısı olarak ayarlayın.  
- **Hangi dosya formatları destekleniyor?** Hem `.mpp` hem de `.xml` Project dosyaları yüklenip kaydedilebilir.

## Aylık Yineleme Deseni Nedir?

Aylık yineleme deseni, Microsoft Project (ve Aspose.Tasks) için bir görevin her ay ne sıklıkla tekrarlanması gerektiğini belirtir. Ayın sabit bir gününü (ör. 1.) ya da göreli bir konumu (ör. son Cuma) belirtebilirsiniz. API bu kuralları temel Project dosya yapısına dönüştürür.

## Neden Aspose.Tasks Kullanmalı?

- **Tam kontrol** – UI sınırlamaları yok; deseni kod içinde her ayrıntısıyla tanımlarsınız.  
- **Çapraz‑platform** – .NET Framework, .NET Core ve .NET 5/6+ üzerinde çalışır.  
- **Microsoft Project gerekmez** – Sunucu ya da CI pipeline’ında dosya oluşturabilir veya değiştirebilirsiniz.  

## Ön Koşullar

Başlamadan önce şunların yüklü olduğundan emin olun:

- .NET 6 (veya .NET 5/Framework 4.7+) yüklü.  
- Projenize eklenmiş Aspose.Tasks for .NET NuGet paketi.  
- Bilinen bir klasöre (`DataDir`) yerleştirilmiş örnek Project dosyası (`Project1.mpp`).  

## Ad Alanlarını İçe Aktarın

Görevlerle çalışmak ve projeleri kaydetmek için gereken ad alanlarını içe aktarın:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Adım 1: Projeyi Başlatın

Mevcut `.mpp` dosyanıza işaret eden bir `Project` örneği oluşturun. Bu, dosyayı belleğe yükleyerek değiştirmenizi sağlar.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **İpucu:** Dosya mevcut değilse, Aspose.Tasks otomatik olarak yeni bir boş proje oluşturur.

## Adım 2: Yinelenen Görev Parametrelerini Ayarlayın

Yinelenen görevin detaylarını, adı, süresi ve uygulamak istediğiniz aylık deseni dahil olmak üzere tanımlayın.

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

- `DayPosition = 1` görevin **ayın ilk günü** gerçekleştiği anlamına gelir.  
- `RepetitionInterval = 2` görevin **her iki ayda bir** tekrarlanmasını sağlar.  
- `Start` ve `Finish` yinelemenin aktif olduğu genel zaman aralığını tanımlar.

## Adım 3: Parametreleri Projeye Ekleyin

`RecurringTaskParameters` nesnesini kök görevin alt görev koleksiyonuna ekleyin. Bu, proje hiyerarşisinde yinelenen görevi etkili bir şekilde oluşturur.

```csharp
project.RootTask.Children.Add(parameters);
```

## Adım 4: Projeyi Kaydedin

Değişiklikleri yeni bir dosyaya kaydederek kalıcı hale getirin. İstediğiniz desteklenen formatı seçebilirsiniz; burada yerel `.mpp` formatını kullanıyoruz.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Kodu çalıştırdıktan sonra, oluşturulan dosyayı Microsoft Project’te açarak az önce oluşturduğunuz aylık yinelenen görevi görebilirsiniz.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|------|
| Görev kaydedildikten sonra görünmüyor | Proje UI’da yenilenmedi | Dosyayı yeniden açın veya kaydetmeden önce `project.UpdateTaskLinks()` çağırın. |
| Başlangıç tarihi yanlış | `Start` bir hafta sonuna ayarlanmış | Çalışma günü olan bir `DateTime` kullanın veya takvimi ayarlayın. |
| Yineleme aralığı göz ardı ediliyor | `ByMonthDayRepetition` ile `DayPosition` = 0 kullanılmış | `DayPosition` değerinin 1‑31 arasında olduğundan emin olun. |

## Sonuç

Bu adımları izleyerek Aspose.Tasks for .NET ile **aylık yinelenen görev** takvimleri oluşturmayı öğrendiniz. API, yineleme aralıkları, başlangıç/bitiş aralıkları ve belirli gün desenleri üzerinde ayrıntılı kontrol sağlar; böylece karmaşık proje planlama senaryolarını otomatikleştirebilirsiniz.

## SSS'ler

### S1: Aspose.Tasks tüm Microsoft Project dosya sürümleriyle uyumlu mu?

C1: Aspose.Tasks, MPP, MPT, XML ve MPX dahil olmak üzere çeşitli Microsoft Project dosya sürümlerini destekler.

### S2: Yineleme desenini daha da özelleştirebilir miyim?

C2: Evet, Aspose.Tasks günlük, haftalık, aylık ve yıllık dahil olmak üzere yineleme desenlerini özelleştirmek için kapsamlı seçenekler sunar.

### S3: Aspose.Tasks için ücretsiz bir deneme mevcut mu?

C3: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) edinebilirsiniz.

### S4: Aspose.Tasks için destek nasıl alınır?

C4: [Aspose.Tasks forumunda](https://forum.aspose.com/c/tasks/15) yardım isteyebilir ve tartışmalara katılabilirsiniz.

### S5: Aspose.Tasks lisansı nereden satın alınır?

C5: Lisansı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sıkça Sorulan Sorular

**S: Bu kodu bir .NET Core uygulamasında kullanabilir miyim?**  
C: Kesinlikle. Aspose.Tasks for .NET, .NET Core 3.1 ve sonraki sürümleri tam olarak destekler.

**S: Yinelemeyi “ayın son iş günü” olarak nasıl değiştiririm?**  
C: `ByMonthDayRepetition` ile `DayPosition = -1` (negatif değerler ayın sonundan sayar) ve `WeekDay` değerini uygun şekilde ayarlayın.

**S: Yineleme aralığı projenin takvimini aşıyorsa ne olur?**  
C: API proje takvimine saygı gösterir; çalışma günü olmayan günlerdeki oluşumlar takvimin ayarlarına göre ya atlanır ya da taşınır.

**S: Yinelenen bir görevin belirli bir oluşumunu silebilir miyim?**  
C: Evet. Yinelenen görevi ekledikten sonra `Task.GetOccurrences()` ile bireysel oluşumları alabilir ve ihtiyacınız olmayanları silebilirsiniz.

**S: Aspose.Tasks zaman dilimi farklarını otomatik olarak yönetiyor mu?**  
C: Kütüphane tarihleri UTC olarak saklar; gerekirse standart .NET `DateTime` yöntemleriyle yerel zamana dönüştürebilirsiniz.

---

**Son Güncelleme:** 2026-03-08  
**Test Edilen Versiyon:** Aspose.Tasks 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}