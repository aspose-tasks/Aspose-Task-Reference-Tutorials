---
title: Aspose.Tasks'ta Takvim İstisnalarının Toplanması
linktitle: Aspose.Tasks'ta Takvim İstisnalarının Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks'ı kullanarak .NET projelerinizde takvim istisnalarını nasıl verimli bir şekilde yöneteceğinizi, doğru planlama ve kaynak yönetimini nasıl sağlayacağınızı öğrenin.
type: docs
weight: 13
url: /tr/net/calendar-scheduling/calendar-exception-collection/
---
## giriiş

Proje yönetiminde kesin planlama başarı için hayati öneme sahiptir. Ancak gerçek dünya senaryoları genellikle tatiller, özel etkinlikler veya diğer faktörler nedeniyle standart programlardan sapmalar gerektirir. Aspose.Tasks for .NET, Takvim İstisna Toplama özelliği aracılığıyla bu tür istisnaları yönetmek için güçlü bir çözüm sunar. Bu eğitim, bu işlevselliği adım adım kullanma sürecinde size rehberlik edecektir.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1.  Aspose.Tasks for .NET: Kütüphanenin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/tasks/net/).
2. Temel C# bilgisi: C# programlama diline aşinalık, örneklerin anlaşılmasında yardımcı olacaktır.
3. Geliştirme Ortamı: Visual Studio veya JetBrains Rider gibi tercih ettiğiniz geliştirme ortamını kurun.

## Ad Alanlarını İçe Aktar

Aspose.Tasks for .NET ile çalışmaya başlamadan önce gerekli ad alanlarını projenize aktarmanız gerekir. Bu adım, takvim istisnalarını yönetmek için gerekli sınıflara ve yöntemlere erişmenizi sağlar.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Şimdi verilen örneği birden çok adıma ayıralım:

## Adım 1: Projeyi Yükleyin ve Takvimi Alın

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

Bu adımda bir proje dosyası yüklüyoruz ve istenen takvimi UID'sine göre alıyoruz.

## 2. Adım: Mevcut İstisnaları Temizleyin ve Standart Takvimi Ayarlayın

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Bu adım, takvimdeki mevcut tüm istisnaları temizler ve takvimi standart bir yapılandırmaya ayarlar.

## 3. Adım: Çalışma Süresi İstisnasını Tanımlayın ve Ekleyin

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

Bu adım, belirli başlangıç ve bitiş tarihleriyle birlikte bu tarihler içindeki çalışma süreleriyle birlikte bir çalışma süresi istisnası tanımlar ve bunu takvime ekler.

## Adım 4: Çalışma Dışı Zaman İstisnalarını Tanımlayın ve Ekleyin

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Gerekirse daha fazla istisna ekleyin

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

Bu adım, tatiller gibi çalışma dışı zaman istisnalarını tanımlar ve bunları takvime ekler.

## 5. Adım: Takvim İstisnalarını Görüntüleyin

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

Bu adım, eklenen takvim istisnalarını ayrıntılarıyla birlikte görüntüler.

## Adım 6: Tüm İstisnaları Kaldır

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Son olarak, bu adım takvimdeki tüm istisnaları kaldırır.

## Çözüm

Takvim istisnalarını yönetmek, doğru proje planlaması için çok önemlidir. Aspose.Tasks for .NET, Takvim İstisna Koleksiyonu da dahil olmak üzere kapsamlı bir dizi özellik sunarak bu görevi basitleştirir. Bu öğreticide özetlenen adımları izleyerek projelerinizdeki çeşitli planlama senaryolarını verimli bir şekilde yönetebilirsiniz.

## SSS'ler

### S1: Tek bir takvime birden fazla istisna ekleyebilir miyim?

 Cevap1: Evet, bir takvime birden fazla istisna ekleyebilirsiniz.`AddRange` yöntem.

### S2: Haftalık tatiller gibi yinelenen istisnaları nasıl halledebilirim?

Cevap2: Yinelenen istisnaları programlı olarak hesaplayabilir ve bunları özel mantığı kullanarak takvime ekleyebilirsiniz.

### S3: Takvim istisnalarını dış kaynaklardan içe aktarmak mümkün müdür?

C3: Evet, veritabanları veya CSV dosyaları gibi harici kaynaklardan takvim istisnalarını okuyabilir ve bunları projenize entegre edebilirsiniz.

### S4: Takvimde çakışan istisnalar varsa ne olur?

Cevap4: Aspose.Tasks for .NET, proje gereksinimlerinize göre öncelikleri tanımlayarak veya çakışmaları çözerek çakışan istisnaları ele almanızı sağlar.

### S5: İstisnai durumlar dahilinde her gün için çalışma sürelerini özelleştirebilir miyim?

C5: Evet, belirli planlama ihtiyaçlarını karşılamak amacıyla istisna dahilinde tek tek günler için özel çalışma süreleri belirleyebilirsiniz.