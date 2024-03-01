---
title: Aspose.Tasks'ta Çalışma Sürelerinde Uzmanlaşmak
linktitle: Aspose.Tasks'ta Çalışma Sürelerinin Toplanması
second_title: Aspose.Tasks .NET API'si
description: Proje zaman çizelgelerini verimli bir şekilde yönetme konusunda Aspose.Tasks for .NET'in gücünü keşfedin. Takvimleri özelleştirin, çalışma sürelerini ayarlayın ve projelerinizi kolaylıkla kolaylaştırın.
type: docs
weight: 14
url: /tr/net/time-recurrence-configuration/working-time-collection/
---
## giriiş
Aspose.Tasks for .NET'te çalışma sürelerini yönetme sanatında ustalaşmak mı istiyorsunuz? Başka yerde arama! Bu adım adım kılavuzda, Aspose.Tasks'ı kullanarak çalışma zamanı toplamanın inceliklerini inceleyerek, özel takvimleri verimli bir şekilde yönetmenizi ve proje zaman çizelgelerinizi düzene koymanızı sağlayacağız.
## Önkoşullar
Bu yolculuğa çıkmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
-  Aspose.Tasks for .NET Kütüphanesi: Aspose.Tasks for .NET kütüphanesini aşağıdaki adresten indirip yükleyin:[Aspose.Tasks sürüm sayfası](https://releases.aspose.com/tasks/net/).
- Çalışma Ortamı: Tercihen .NET uyumlu bir IDE kullanarak uygun bir geliştirme ortamı kurun.
## Ad Alanlarını İçe Aktar
Aspose.Tasks işlevlerine erişmek için projenize gerekli ad alanlarını içe aktarın:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Şimdi, sorunsuz bir öğrenme deneyimi sağlamak için öğreticiyi birden fazla adıma ayıralım.
## 1. Adım: Özel Bir Takvim Oluşturun
Yeni bir proje oluşturup ona özel bir takvim ekleyerek başlayın:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Adım 2: Çalışma Günlerini Tanımlayın
Pazartesi'den Cuma'ya kadar varsayılan çalışma günlerini ayarlayın:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## 3. Adım: Cumartesi Çalışma Sürelerini Yapılandırın
Cumartesi günleri için çalışma saatlerini belirtin:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Adım 4: Cumartesi Çalışma Dönemlerini Yazdırın
Cumartesi için yapılandırılmış çalışma sürelerini yazdırın:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## 5. Adım: Pazar Çalışma Sürelerini Yapılandırın
Pazar günleri için çalışma saatlerini tanımlayın:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Adım 6: Pazar Çalışma Dönemlerini Yazdırın
Pazar günü için yapılandırılmış çalışma sürelerini yazdırın:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## 7. Adım: Takvime Özel Günler Ekleme
Yapılandırılmış Cumartesi ve Pazar günlerini takvime ekleyin:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Adım 8: Çalışma Sürelerini Geçin
Çalışma süreleri arasında geçiş yapın ve bunları takvimde her gün için görüntüleyin:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Artık adımları başarılı bir şekilde geçtiğinize göre, çalışma sürelerini etkili bir şekilde yönetmek için Aspose.Tasks for .NET'in gücünden yararlanabilecek donanıma sahipsiniz.
## Çözüm
Aspose.Tasks'ta çalışma sürelerinin toplanması konusunda uzmanlaşmak, proje takvimlerini özelleştirmenize olanak tanıyarak hassas planlama ve verimli kaynak kullanımı sağlar. Bu kapsamlı kılavuzdan edinilen bilgilerle donanmış olarak projelerinize güvenle dalın.
## Sıkça Sorulan Sorular
### Aspose.Tasks büyük ölçekli proje yönetimine uygun mu?
Evet, Aspose.Tasks, farklı boyutlardaki projelerin üstesinden gelmek üzere tasarlanmış olup verimli proje yönetimi için sağlam özellikler sunar.
### Aspose.Tasks'ı diğer .NET kütüphaneleriyle entegre edebilir miyim?
Kesinlikle! Aspose.Tasks, diğer .NET kitaplıklarıyla sorunsuz bir şekilde bütünleşerek çok yönlülüğünü ve uyumluluğunu artırır.
### Aspose.Tasks ne sıklıkla güncellenir?
 Aspose.Tasks, yeni özellikleri, geliştirmeleri ve uyumluluk iyileştirmelerini içerecek şekilde düzenli olarak güncellenmektedir. Kontrol edin[yayın sayfası](https://releases.aspose.com/tasks/net/) En son güncellemeler için.
### Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?
 Evet, Aspose.Tasks'ı ziyaret ederek ücretsiz deneme sürümüyle keşfedebilirsiniz.[bu bağlantı](https://releases.aspose.com/).
### Aspose.Tasks için nereden destek alabilirim?
 Sorularınız veya yardım için şu adresi ziyaret edin:[Aspose.Tasks destek forumu](https://forum.aspose.com/c/tasks/15).