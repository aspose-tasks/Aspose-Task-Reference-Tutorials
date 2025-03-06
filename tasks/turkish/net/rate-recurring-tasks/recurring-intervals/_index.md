---
title: Aspose.Tasks'ta Zahmetsiz MS Projesi Yinelenen Aralıklar
linktitle: Aspose.Tasks'ta Tekrarlanan Aralıkları Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project'te yinelenen aralıkları zahmetsizce nasıl yönetebileceğinizi keşfedin.
weight: 12
url: /tr/net/rate-recurring-tasks/recurring-intervals/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Zahmetsiz MS Projesi Yinelenen Aralıklar

## giriiş
Aspose.Tasks for .NET'i kullanarak Microsoft Project dosyalarında yinelenen aralıkları verimli bir şekilde yönetmek mi istiyorsunuz? Bu kapsamlı eğitim, projelerinizde yinelenen aralıkları zahmetsizce yönetebilmenizi sağlayacak şekilde süreç boyunca size adım adım rehberlik edecektir. Eğiticiye dalmadan önce, başlamaya hazır olduğunuzdan emin olmak için bazı önkoşulların üzerinden geçelim.
## Önkoşullar
Bu eğitime devam etmeden önce aşağıdakilere sahip olduğunuzdan emin olun:
1. C# Programlama Bilgisi: C# programlama dilinin ve sözdiziminin temel düzeyde anlaşılması gerekir.
2. Visual Studio Yüklü: .NET uygulamalarını kodlamak ve derlemek için sisteminizde Visual Studio'nun yüklü olduğundan emin olun.
3. Aspose.Tasks for .NET Kütüphanesi: Aspose.Tasks for .NET kütüphanesini indirin ve yükleyin. Şu adresten alabilirsiniz:[Burada](https://releases.aspose.com/tasks/net/).

## Ad Alanlarını İçe Aktar
Aspose.Tasks for .NET kütüphanesinin sağladığı işlevlere erişmek için gerekli ad alanlarını içe aktararak başlayın.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Şimdi her örneği birden fazla adıma ayıralım ve bunları ayrıntılı olarak açıklayalım.
## Adım 1: Proje Nesnesini Başlatın:
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
 Burada yeni bir örneğini başlatıyoruz.`Project` Microsoft Project dosyasının yolunu sağlayarak sınıf.
## Adım 2: Durum Tarihini Ayarlayın:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Bu adım, projenin durum tarihini başlangıç tarihine ayarlar.
## 3. Adım: Gantt Tablosu Görünümüne Erişin:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Projenin Gantt Chart görünümüne ulaşıyoruz.
## Adım 4: İlerleme Satırını Okuyun:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
Bu adım, Gantt Grafiği görünümünden ilerleme çizgileri için yinelenen aralığı alır.
## Adım 5: Aralık Bilgilerini Görüntüleyin:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Burada aralık, haftalık hafta sayısı ve haftalık günlerle ilgili bilgileri görüntüleriz.
## Adım 6: Yinelenen Aralığı Yeniden Tanımlayın:
```csharp
var newInterval = new RecurringInterval();
```
 Yeni bir örneğini oluşturuyoruz`RecurringInterval` yinelenen aralığı yeniden tanımlamak için.
## Adım 7: Aylık İlerleme Çizgilerini Ayarlayın:
```csharp
// Aylık ilerleme çizgilerini güne göre ayarlayın.
interval.MonthlyDay = true;
// Aylık ilerleme satırlarının gün sayısını ayarlayın.
interval.MonthlyDayDayNumber = 1;
// Aylık ilerleme satırlarının ay sayısını ayarlayın.
interval.MonthlyDayMonthNumber = 1;
// İlerleme çizgilerini ilk veya son önceden tanımlanmış güne göre ayarlayın.
interval.MonthlyFirstLast = true;
// Aylık ilerleme satırlarının ilk veya son gün türünü ayarlayın.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// İlerleme satırlarının ay sayısını ayarlayın.
interval.MonthlyFirstLastMonthNumber = 1;
```
Bu adımlar, aylık ilerleme satırlarını belirtilen parametrelere göre yapılandırır.
## Adım 8: İlerleme Çizgilerini Güncelleyin:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Gantt Grafiği görünümündeki ilerleme satırlarını yeni tanımlanan yinelenen aralıkla güncelliyoruz.
## Adım 9: Projeyi PDF olarak kaydedin:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Son olarak projeyi güncellenen yinelenen aralıkla PDF dosyası olarak kaydediyoruz.

## Çözüm
Sonuç olarak, Aspose.Tasks for .NET'i kullanarak Microsoft Project dosyalarındaki yinelenen aralıkları yönetmek, kütüphanenin sağladığı kapsamlı işlevler sayesinde basitleştirilmiştir. Bu eğitimde özetlenen adım adım kılavuzu takip ederek projelerinizde yinelenen aralıkları verimli bir şekilde yönetebilir, üretkenliği ve organizasyonu artırabilirsiniz.
### SSS'ler
### Aspose.Tasks for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
Evet, Aspose.Tasks for .NET, C# ve VB.NET gibi .NET destekli herhangi bir dille kullanılabilir.
### Aspose.Tasks for .NET'in deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Tasks for .NET için nasıl destek alabilirim?
 Aspose.Tasks forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks for .NET için geçici bir lisans satın alabilir miyim?
 Evet, adresinden geçici bir lisans satın alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Tasks for .NET'in tüm belgelerini nerede bulabilirim?
 Tüm dokümantasyonu bulabilirsiniz[Burada](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
