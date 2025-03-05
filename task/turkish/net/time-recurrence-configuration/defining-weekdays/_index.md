---
title: Aspose.Tasks for .NET'te Hafta İçi Günlerde Uzmanlaşmak
linktitle: Aspose.Tasks'ta Hafta İçi Günleri Tanımlama
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks .NET'te hafta içi günleri tanımlamanın gücünü keşfedin. Proje takvimlerini verimli bir şekilde yönetmek, çalışma sürelerini özelleştirmek ve daha fazlasını yapmak için ayrıntılı eğitimimizi izleyin.
type: docs
weight: 10
url: /tr/net/time-recurrence-configuration/defining-weekdays/
---
## giriiş
Aspose.Tasks for .NET'i kullanarak proje yönetimi dünyasına dalıyorsanız, hafta içi günleri anlamak ve yönetmek çok önemli bir husustur. Proje takviminizde hafta içi günleri verimli bir şekilde yönetmek ve özelleştirmek, proje zaman çizelgelerini önemli ölçüde etkileyebilir. Bu eğitimde, Aspose.Tasks'ı kullanarak hafta içi günleri tanımlama sürecinde size rehberlik edeceğiz ve daha iyi anlaşılırlık için adım adım talimatlar ve örnekler sunacağız.
## Önkoşullar
Bu yolculuğa çıkmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- C# programlama dilinin temel anlayışı.
-  Aspose.Tasks for .NET kütüphanesi kuruldu. Değilse, şuradan indirin:[Burada](https://releases.aspose.com/tasks/net/).
## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını projenize aktararak başlayın:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Hafta İçi Eşitliğini Kontrol Edin
```csharp
// Belge dizininiz
String DataDir = "Your Document Directory";
// Proje dosyasını yükle
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// Hafta içi günlere erişim
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// Çeşitli özelliklere göre eşitliği kontrol edin
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// DayWorking, FromDate, ToDate ve WorkTimes için benzer çıktı ifadeleri ekleyin
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. Hafta içi bir günü klonlayın
```csharp
// Proje dosyasını yükle
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// Hafta içi günün derin bir kopyasını oluşturun
var weekDay2 = weekDay1.Clone();
// Her iki hafta içi günün çıktı özellikleri
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// DayWorking, FromDate, ToDate ve WorkTimes için benzer çıktı ifadeleri ekleyin
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. Hafta İçi Bir Günün Karma Kodunu Alın
```csharp
// Proje dosyasını yükle
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// Her iki hafta içi günün çıktı özellikleri
// DayWorking, FromDate, ToDate ve WorkTimes için benzer çıktı ifadeleri ekleyin
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. Tanımlanmış Hafta Günleri ile Yeni Bir Takvim Oluşturun
```csharp
// Yeni bir proje oluştur
var project = new Project();
// Bir takvim tanımlayın
var calendar = project.Calendars.Add("Calendar1");
// Çalışma günlerini ve istisna gününü ekleyin
// FromDate ve ToDate için benzer çıktı ifadeleri ekleyin
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// Cuma için çalışma saatlerini ayarlayın
// DayWorking, FromDate, ToDate ve WorkTimes için benzer çıktı ifadeleri ekleyin
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. Bir Gün İçin Varsayılan Çalışma Süresini Ayarlayın
```csharp
// Yeni bir proje oluştur
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// Pazartesi'den Cuma'ya kadar varsayılan çalışma sürelerini ekleyin
// DayWorking, FromDate, ToDate ve WorkTimes için benzer çıktı ifadeleri ekleyin
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// Salı, Çarşamba, Perşembe ve Cuma için tekrarlayın
// Cumartesi ve Pazar için çalışma dışı günler belirleyin
// DayWorking, FromDate, ToDate ve WorkTimes için benzer çıktı ifadeleri ekleyin
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## Çözüm
Bu eğitimde Aspose.Tasks for .NET'te hafta içi günleri tanımlamanın temel yönlerini ele aldık. Hafta içi günleri yönetmek, etkili proje yönetimi için önemli bir beceridir. Sunulan örneklerle denemeler yapın, bunları projenizin ihtiyaçlarına göre uyarlayın ve Aspose.Tasks'ın tüm potansiyelini ortaya çıkarın.
## SSS
### Her gün için özel çalışma saatleri tanımlayabilir miyim?
Evet, verilen örnekleri kullanarak haftanın belirli günleri için özel çalışma saatleri ayarlayabilirsiniz.
### Takvime birden fazla istisna günü eklemek mümkün mü?
Kesinlikle. Ek istisna günlerini eklemek için dördüncü örnekteki kodu değiştirin.
### Haftanın belirli bir gününü takvimden nasıl kaldırabilirim?
Gerektiğinde hafta içi günleri kaldırmak için Aspose.Tasks kütüphanesi tarafından sağlanan uygun yöntemleri kullanın.
### Hafta içi günlerde yapılan değişiklikler proje dosyasında kalıcı mı?
Evet, hafta içi günlerde yapılan değişiklikler kaydedildiğinde proje dosyasına yansıtılır.
### Aspose.Tasks'ı diğer programlama dilleriyle kullanabilir miyim?
Aspose.Tasks çeşitli programlama dillerini destekler ancak buradaki örnekler özellikle .NET içindir.