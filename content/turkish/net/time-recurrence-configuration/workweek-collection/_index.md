---
title: Aspose.Tasks'ta Çalışma Haftalarını Özelleştirin
linktitle: Aspose.Tasks'ta Workweek'lerin toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te çalışma haftalarını nasıl özelleştireceğinizi öğrenin. Kişiselleştirilmiş proje takvimleri oluşturmak için adım adım kılavuz. Şimdi İndirin!
type: docs
weight: 17
url: /tr/net/time-recurrence-configuration/workweek-collection/
---
## giriiş
Aspose.Tasks for .NET'i kullanarak özel bir çalışma haftası oluşturma eğitimimize hoş geldiniz! Bu adım adım kılavuzda, projenizdeki bir takvim için kişiselleştirilmiş bir çalışma haftası tanımlama sürecinde size yol göstereceğiz. Aspose.Tasks, geliştiricilerin .NET uygulamalarında Microsoft Project belgeleriyle verimli bir şekilde çalışmasını sağlayan güçlü bir kitaplıktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Visual Studio: Makinenizde Visual Studio'nun kurulu olduğundan emin olun.
2.  Aspose.Tasks for .NET: Aspose.Tasks kütüphanesini indirip yükleyin. İndirme linkini bulabilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
3. Temel C# bilgisi: C# programlama dilinin temellerine aşina olun.
## Ad Alanlarını İçe Aktar
C# projenizde gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Adım: Proje ve Takvim Oluşturun
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## 2. Adım: Özel Bir Çalışma Haftası Tanımlayın
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## 3. Adım: Çalışma Günlerini Ayarlayın
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## 4. Adım: Çalışma Haftası Bilgilerini Görüntüleyin
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Bu kapsamlı kılavuz, Aspose.Tasks for .NET'i kullanarak özel çalışma haftalarını verimli bir şekilde oluşturmanıza ve yönetmenize olanak tanır.
## Çözüm
Sonuç olarak Aspose.Tasks for .NET, özel çalışma haftaları içeren proje takvimlerinin yönetilmesi için güçlü bir çözüm sunar. Bu öğreticiyi takip ederek projenizdeki özel çalışma haftaları hakkındaki bilgileri nasıl oluşturacağınızı ve görüntüleyeceğinizi öğrendiniz.
## SSS
### Tek bir projede birden fazla özel çalışma haftasına sahip olabilir miyim?
Evet, bir proje takvimine birden fazla özel çalışma haftası ekleyebilirsiniz.
### Mevcut çalışma haftalarını nasıl değiştirebilirim?
 Sağlananları kullanın`WorkWeek` Mevcut çalışma haftalarını değiştirmeye yönelik özellikler ve yöntemler.
### Aspose.Tasks .NET Core ile uyumlu mu?
Evet, Aspose.Tasks .NET Core'u destekler.
### Özel çalışma haftaları içeren projeyi Microsoft Project dosya formatına aktarabilir miyim?
Kesinlikle Aspose.Tasks, projenizi Microsoft Project dahil olmak üzere çeşitli formatlarda kaydetmenize olanak tanır.
### Aspose.Tasks ile ilgili sorgular için nereden destek alabilirim?
 ziyaret edin[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) herhangi bir destek veya yardım için.