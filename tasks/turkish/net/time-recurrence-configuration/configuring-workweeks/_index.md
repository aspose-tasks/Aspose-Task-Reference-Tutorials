---
title: Aspose.Tasks'ta Workweek Yapılandırmasında Uzmanlaşma
linktitle: Aspose.Tasks'ta Workweeks'i Yapılandırma
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te çalışma haftalarını zahmetsizce nasıl yapılandıracağınızı öğrenin. Adım adım kılavuzumuzla proje planlamasını ve kaynak yönetimini geliştirin.
weight: 16
url: /tr/net/time-recurrence-configuration/configuring-workweeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Workweek Yapılandırmasında Uzmanlaşma

## giriiş
Aspose.Tasks for .NET'te çalışma haftalarını yapılandırmaya ilişkin kapsamlı kılavuzumuza hoş geldiniz. Çalışma haftalarını verimli bir şekilde yönetmek, proje planlama ve zamanlama için çok önemlidir. Aspose.Tasks bu süreci basitleştirerek çalışma haftalarınızı projenizin ihtiyaçlarına göre özelleştirmenize olanak tanır. Bu eğitimde, çalışma haftalarını sorunsuz bir şekilde yapılandırma adımlarında size yol göstereceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1.  Aspose.Tasks Kütüphanesi: .NET projenizde Aspose.Tasks kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Aspose.Tasks web sitesi](https://releases.aspose.com/tasks/net/).
2. .NET Ortamı: .NET ortamında çalıştığınızdan ve C# programlama konusunda temel bilgiye sahip olduğunuzdan emin olun.
## Ad Alanlarını İçe Aktar
Başlamak için projenize gerekli ad alanlarını ekleyin:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Adım: Projenizi ayarlayın
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project();
```
## 2. Adım: Standart bir takvim oluşturun
```csharp
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## 3. Adım: Özel bir çalışma haftası tanımlayın
```csharp
var item = new WorkWeek();
item.Name = "My Work Week";
item.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
item.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## 4. Adım: Çalışma günlerini belirtin
```csharp
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
item.WeekDays.Add(new WeekDay(DayType.Saturday));
item.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(item);
```
## 5. Adım: Çalışma haftası ayrıntılarını görüntüleyin
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    // Çalışma haftası ayrıntılarını görüntüle
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    Console.WriteLine();
    // Her gün için özel çalışma saatlerini görüntüleyin
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        // Çalışma sürelerini görüntüle
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Bu adımları izleyerek Aspose.Tasks'ta çalışma haftalarını kolayca yapılandırarak proje yönetimi becerilerinizi geliştirebilirsiniz.
## Çözüm
Sonuç olarak, çalışma haftalarını yönetmek proje planlamasının temel bir yönüdür ve Aspose.Tasks, güçlü özellikleriyle bu süreci basitleştirir. Çalışma haftalarını projenizin gereksinimlerine göre özelleştirerek verimli kaynak kullanımı ve daha iyi proje planlaması sağlayabilirsiniz.
## SSS
### Tek bir projede birden fazla çalışma haftasını yapılandırabilir miyim?
Evet, Aspose.Tasks'ı kullanarak aynı proje içinde birden fazla çalışma haftası yapılandırabilirsiniz.
### Belirli günler için farklı çalışma saatleri ayarlamak mümkün müdür?
Kesinlikle. Aspose.Tasks, bir çalışma haftasındaki her gün için benzersiz çalışma süreleri tanımlamanıza olanak tanır.
### Projeler arasında çalışma haftalarını içe/dışa aktarabilir miyim?
Aspose.Tasks güçlü içe/dışa aktarma yetenekleri sağlarken, çalışma haftaları genellikle projeye özeldir ve doğrudan aktarılamayabilir.
### Bir projede oluşturabileceğim çalışma haftası sayısında bir sınır var mı?
Mevcut sürüm itibarıyla, bir projede yapılandırabileceğiniz çalışma haftası sayısına ilişkin önceden tanımlanmış bir sınır yoktur.
### Ortak çalışma haftaları için yerleşik şablonlar var mı?
Evet, Aspose.Tasks projeniz için başlangıç noktası olarak kullanabileceğiniz standart bir takvim şablonu içerir.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
