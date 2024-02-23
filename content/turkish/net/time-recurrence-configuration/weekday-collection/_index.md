---
title: Aspose.Tasks'ta Hafta İçi Günlerde Uzmanlaşmak
linktitle: Aspose.Tasks'ta Hafta İçi Günlerin Toplanması
second_title: Aspose.Tasks .NET API'si
description: Hafta içi günleri zahmetsizce yönetme konusunda Aspose.Tasks for .NET'in gücünü keşfedin. Çalışma günlerini özelleştirin, hafta sonlarını kaldırın ve kolaylıkla özel takvimler oluşturun.
type: docs
weight: 11
url: /tr/net/time-recurrence-configuration/weekday-collection/
---
## giriiş
Aspose.Tasks for .NET, proje yönetimi verilerinin verimli şekilde değiştirilmesini kolaylaştıran güçlü bir kütüphanedir. Bu eğitimde, Aspose.Tasks'teki hafta içi gün koleksiyonunu keşfederek çalışma günlerini özelleştirmenize, hafta sonlarını kaldırmanıza ve proje gereksinimlerinizi karşılamak için özel takvimler oluşturmanıza olanak sağlayacağız. İster deneyimli bir geliştirici olun ister yeni başlayan biri olun, bu adım adım kılavuz Aspose.Tasks for .NET'te hafta içi çalışma sürecinde size yol gösterecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.Tasks for .NET kitaplığını yükleyin. adresinden indirebilirsiniz.[Aspose.Tasks for .NET indirme sayfası](https://releases.aspose.com/tasks/net/).
- C# programlama diline aşinalık.
- Visual Studio gibi entegre geliştirme ortamı (IDE).
## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını C# projenize aktararak başlayın:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Adım: Proje Örneği Oluşturun
Yeni bir Aspose.Tasks projesi başlatın:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## 2. Adım: Takvime Erişin
Proje takvimini alın:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## 3. Adım: Hafta İçi Günleri Özelleştirin
Mevcut hafta içi günlerini temizleyin ve varsayılan çalışma günlerini ayarlayın:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Haftanın diğer günlerini de benzer şekilde ekleyin...
```
## 4. Adım: Çalışma Sürelerini Ekleyin
Haftanın belirli günleri için çalışma saatleri ekleyin:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Adım 5: Takvim Bilgilerini Görüntüleyin
Takvim ayrıntılarını konsola aktarın:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Hafta içi her günü ve çalışma saatlerini görüntüleyin...
```
## Adım 6: Hafta Sonlarını Kaldır
Cumartesi ve Pazar'ı hafta içi günlerden çıkarın:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Adım 7: Güncellenmiş Çalışma Sürelerini Görüntüleyin
Hafta sonları kaldırıldıktan sonra güncellenen çalışma sürelerinin çıktısı:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Güncellenen her hafta içi günü ve çalışma saatlerini görüntüleyin...
```
## Adım 8: 24 Saatlik Takvim Oluşturun
24 saatlik bir takvim oluşturun ve hafta içi günleri kopyalayın:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Çözüm
Bu eğitimde Aspose.Tasks for .NET'in proje takvimlerindeki hafta içi günlerini yönetme konusundaki güçlü yeteneklerini araştırdık. Aspose.Tasks, çalışma günlerini özelleştirmekten özel 24 saatlik takvimler oluşturmaya kadar süreci basitleştirerek proje yönetiminde esneklik ve kontrol sunar.
## Sıkça Sorulan Sorular
### S: Aspose.Tasks for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
C: Aspose.Tasks öncelikli olarak .NET dillerini destekler ancak Java için de sürümler sunar.
### S: Aspose.Tasks for .NET'in ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Aspose.Tasks sürüm sayfası](https://releases.aspose.com/).
### S: Aspose.Tasks for .NET için nasıl destek alabilirim?
 C: Ziyaret edin[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) topluluk desteği için veya bir destek planı satın almayı düşünün.
### S: Aspose.Tasks for .NET'in kapsamlı belgelerini nerede bulabilirim?
 C: Bkz.[Aspose.Tasks for .NET belgeleri](https://reference.aspose.com/tasks/net/) detaylı bilgi için.
### S: Aspose.Tasks for .NET için nasıl geçici lisans edinebilirim?
 C: Geçici lisansı şu adresten alabilirsiniz:[geçici lisans sayfası](https://purchase.aspose.com/temporary-license/).