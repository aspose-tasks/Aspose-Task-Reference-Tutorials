---
date: 2026-04-09
description: Aspose.Tasks kullanarak .NET projelerinizde standart takvim ayarlamayı
  ve proje tatillerini yönetmeyi öğrenin, böylece doğru zamanlama elde edersiniz.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Aspose.Tasks'te Standart Takvimi Ayarlayın ve İstisnaları İşleyin
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Standart Takvimi Ayarlayın ve İstisnaları İşleyin
url: /tr/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Standart Takvimi Ayarla ve Aspose.Tasks'te İstisnaları Yönet

## Giriş

Doğru zamanlama, herhangi bir başarılı projenin temelidir ve gerçek dünya planları, tatiller, özel etkinlikler veya beklenmedik kapanışlar nedeniyle varsayılan çalışma takviminden sapmak zorunda kalabilir. Aspose.Tasks for .NET, **standart takvim** ayarlarını kolayca yapmanızı ve ardından özel istisnalar eklemenizi sağlar. Bu öğreticide bir proje takvimini nasıl yükleyeceğinizi, standart takvimi nasıl ayarlayacağınızı ve Takvim İstisna Koleksiyonu özelliğiyle proje tatillerini nasıl yöneteceğinizi öğreneceksiniz.

## Hızlı Yanıtlar
- **“set standard calendar” ne yapar?** Özel istisnalar eklemeden önce takvimi varsayılan çalışma saatlerine (09:00‑17:00, Pazartesi‑Cuma) sıfırlar.  
- **Hangi yöntem mevcut istisnaları temizler?** `Calendar.Exceptions.Clear()` daha önce tanımlanmış tüm istisnaları kaldırır.  
- **Nasıl tatil ekleyebilirim?** `DayWorking = false` olan bir `CalendarException` oluşturup koleksiyona ekleyin.  
- **Değişikliklerden sonra projeyi yeniden yüklemem gerekir mi?** Hayır, değişiklikler doğrudan bellek içindeki `Project` nesnesine uygulanır.  
- **Hangi kütüphaneler gereklidir?** Aspose.Tasks for .NET (desteklenen herhangi bir .NET sürümü) ve `System` ad alanları.

## Önkoşullar

1. **Aspose.Tasks for .NET** – [buradan](https://releases.aspose.com/tasks/net/) indirin.  
2. **C#** temel bilgisi – birkaç kısa kod parçacığı yazacaksınız.  
3. **Visual Studio** veya **JetBrains Rider** gibi bir geliştirme ortamı.

## Ad Alanlarını İçe Aktar

Bu `using` yönergeleri, takvim manipülasyonu için gereken sınıflara erişmenizi sağlar.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Takvim İstisnası Nedir?

*Takvim istisnası*, normal çalışma programının değiştiği bir dönemi temsil eder – örneğin, şirket çapında bir tatil veya geçici bir fazla mesai programı. Bir takvime istisnalar ekleyerek temel takvimi değiştirmeden gerçek dünya kısıtlamalarını modelleyebilirsiniz.

## Aspose.Tasks'te Standart Takvimi Nasıl Ayarlarsınız

İlk adım, proje dosyanızı yüklemek ve üzerinde çalışmak istediğiniz takvimi almak.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Adım 1: Mevcut İstisnaları Temizle ve Standart Takvime Sıfırla

Yeni kurallar eklemeden önce, eski istisnaları temizlemek ve **standart takvimi ayarlamak** iyi bir uygulamadır. Bu, temiz bir temel sağlar.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Adım 2: Çalışma Süresi İstisnası Tanımla

Bazen geçici bir program oluşturmanız gerekir (ör. bir ürün lansmanı için uzatılmış saatler). Aşağıdaki kod parçacığı, birkaç günü kapsayan ve günlük iki çalışma periyodu içeren bir çalışma süresi istisnası tanımlar.

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### Adım 3: Çalışma Dışı Zaman İstisnaları (Tatil) Ekle

**Proje tatillerini yönetmek** için `DayWorking` değeri `false` olan istisnalar oluşturun. Aşağıdaki örnek iki günlük bir tatil bloğu ekler.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Adım 4: Takvim İstisnalarını Görüntüle (Doğrulama)

İstisnalar eklendikten sonra, genellikle doğru kaydedildiklerini doğrulamak istersiniz. Aşağıdaki döngü, her istisnanın ayrıntılarını konsola yazdırır.

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### Adım 5: Tüm İstisnaları Kaldır (Temizleme)

Takvimi orijinal durumuna geri döndürmeniz gerekiyorsa, tüm istisnaları programlı olarak kaldırabilirsiniz.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Yaygın Sorunlar ve Çözümler

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| Kaydedildikten sonra istisnalar görünmüyor | Değişikliklerden sonra proje kaydedilmedi | `project.Save("output.mpp")` değişikliklerden sonra çağırın. |
| Çakışan istisnalar beklenmeyen çalışma saatlerine neden oluyor | Aspose.Tasks, çakışan dönemler için en son eklenen istisnayı kullanır | `Add` çağrılarınızı dikkatlice sıralayın veya öncelikleri manuel olarak ayarlayın. |
| `MakeStandardCalendar` özel çalışma saatlerini sıfırlar | Özel saatleri kasıtlı olarak temizler; gerekirse çağrıdan sonra tekrar ekleyin. | `MakeStandardCalendar` çağrıldıktan sonra özel `WorkingTime` nesnelerinizi ekleyin. |

## Sıkça Sorulan Sorular

**S: Tek bir takvime birden fazla istisna ekleyebilir miyim?**  
C: Evet, `AddRange` yöntemiyle bir takvime birden fazla istisna ekleyebilirsiniz.

**S: Haftalık tatiller gibi yinelenen istisnaları nasıl yönetirim?**  
C: Yinelenen istisnaları programlı olarak hesaplayıp özel mantıkla takvime ekleyebilirsiniz.

**S: Takvim istisnalarını dış kaynaklardan içe aktarmak mümkün mü?**  
C: Evet, veritabanları veya CSV dosyaları gibi dış kaynaklardan takvim istisnalarını okuyup projenize entegre edebilirsiniz.

**S: Takvimde çakışan istisnalar varsa ne olur?**  
C: Aspose.Tasks for .NET, çakışan istisnaları öncelik tanımlayarak veya proje gereksinimlerinize göre çakışmaları çözerek yönetmenize olanak tanır.

**S: Bir istisna içinde her gün için çalışma saatlerini özelleştirebilir miyim?**  
C: Evet, belirli planlama ihtiyaçlarını karşılamak için bir istisna içinde bireysel günler için özel çalışma saatleri belirtebilirsiniz.

## Sonuç

**Standart takvimi** önce ayarlayıp ardından özel istisnalar ekleyerek, proje zamanlaması üzerinde tam kontrol elde eder, **proje tatillerini** ve diğer özel zaman çizelgelerini yönetmeyi kolaylaştırırsınız. Aspose.Tasks'teki Takvim İstisna Koleksiyonu, gerçek dünya takvimlerini .NET uygulamalarınız içinde doğrudan modellemenin temiz, programatik bir yolunu sunar.

---

**Son Güncelleme:** 2026-04-09  
**Test Edilen Versiyon:** Aspose.Tasks 24.12 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}