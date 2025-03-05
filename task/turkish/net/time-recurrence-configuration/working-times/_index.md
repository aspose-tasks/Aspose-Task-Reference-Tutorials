---
title: Aspose.Tasks'ta Çalışma Sürelerini Yapılandırma
linktitle: Aspose.Tasks'ta Çalışma Sürelerini Yapılandırma
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks ile .NET'te proje planlamasını geliştirin. Hassas kaynak yönetimi için çalışma sürelerini zahmetsizce yapılandırın. Kütüphaneyi şimdi indirin!
type: docs
weight: 13
url: /tr/net/time-recurrence-configuration/working-times/
---
## giriiş
Proje yönetiminde, doğru planlama ve kaynak tahsisi için çalışma süreleri üzerinde hassas kontrol çok önemlidir. Aspose.Tasks for .NET, projelerinizde çalışma süresi bilgilerinin işlenmesi için güçlü bir çözüm sunar. Bu eğitim, .NET ortamında Aspose.Tasks'ı kullanarak çalışma sürelerini yapılandırma sürecinde size rehberlik edecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- C# programlama dilinin temel anlayışı.
-  Aspose.Tasks for .NET kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/tasks/net/).
- Visual Studio veya tercih edilen herhangi bir C# geliştirme ortamı kurulumu.
## Ad Alanlarını İçe Aktar
Aspose.Tasks işlevlerine erişmek için gerekli ad alanlarını içe aktararak başlayın:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## 1. Adım: Takvim Oluşturun
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
Burada yeni bir proje başlatıyoruz ve standart takvimi baz alarak "MyCalendar" adında bir takvim oluşturuyoruz. Bu takvim belirli çalışma sürelerini tanımlamak için kullanılacaktır.

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## Adım 2: Çalışma Haftası Bilgilerini Görüntüleyin
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
Bu adım, belirtilen takvimdeki toplam iş günü sayısını yazdırır.
## Adım 3: Çalışma Süreleri Ayrıntıları
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
Bu bölümde, haftanın her gününü yineleyerek gün türünü ve ilgili çalışma sürelerini yazdırıyoruz. Proje gereksinimlerinize göre hafta içi her gün için çalışma saatlerini özelleştirebilirsiniz.
## Çözüm
Aspose.Tasks for .NET'te çalışma sürelerinin etkili bir şekilde yapılandırılması, doğru proje planlaması ve kaynak yönetimi sağlar. Bu adım adım kılavuzu izleyerek çalışma süresi ayarlamalarını proje iş akışlarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## Sıkça Sorulan Sorular
### Aspose.Tasks büyük ölçekli proje yönetimine uygun mu?
Evet, Aspose.Tasks, çeşitli boyutlardaki projelerin üstesinden gelmek üzere tasarlanmış olup verimli proje yönetimi için sağlam özellikler sunar.
### Farklı ekip üyeleri için farklı çalışma süreleri ayarlayabilir miyim?
Kesinlikle. Çalışma sürelerini kaynak bazında özelleştirerek kişiselleştirilmiş programlara izin verebilirsiniz.
### Aspose.Tasks diğer proje yönetimi araçlarıyla entegrasyonu destekliyor mu?
Evet, Aspose.Tasks çeşitli proje yönetimi araçlarıyla entegrasyonu kolaylaştırarak birlikte çalışabilirliği artırır.
### Proje verilerini farklı formatlarda içe/dışa aktarmak mümkün mü?
Aspose.Tasks birden fazla dosya formatını destekleyerek proje verileri için sorunsuz içe/dışa aktarma işlemlerine olanak tanır.
### Aspose.Tasks güncellemeleri ne sıklıkta yayınlanıyor?
En son teknolojilerle uyumluluğu sağlamak ve kullanıcı geri bildirimlerini dikkate almak için güncellemeler düzenli olarak yayınlanmaktadır.