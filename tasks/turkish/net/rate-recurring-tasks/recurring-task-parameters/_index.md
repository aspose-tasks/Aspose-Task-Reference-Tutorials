---
title: Aspose.Tasks'ta Tekrarlanan Görev Parametrelerini Ayarlama
linktitle: Aspose.Tasks'ta Tekrarlanan Görev Parametrelerini Ayarlama
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak Microsoft Project'te yinelenen görev parametrelerini nasıl ayarlayacağınızı öğrenin. Adım adım kılavuzla kapsamlı eğitim.
weight: 14
url: /tr/net/rate-recurring-tasks/recurring-task-parameters/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Tekrarlanan Görev Parametrelerini Ayarlama

## giriiş
Bu eğitimde, Aspose.Tasks for .NET'i kullanarak Microsoft Project yinelenen görev parametrelerini ayarlama sürecinde size rehberlik edeceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. C# programlama dilinin temel anlayışı.
2. Visual Studio veya başka bir C# IDE'yi yükledim.
3. Aspose.Tasks for .NET kütüphanesi projenizde kurulu ve referans alınmıştır.

## Ad Alanlarını İçe Aktar
Öncelikle C# kodunuza gerekli ad alanlarını içe aktarmanız gerekir:
```csharp
using Aspose.Tasks;
using System;

```
## Adım 1: Belge Dizinini Tanımlayın
```csharp
String DataDir = "Your Document Directory";
```
 Yer değiştirmek`"Your Document Directory"` belge dizininizin yolu ile.
## Adım 2: Proje Dosyasını Yükleyin
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Bu kod satırı Microsoft Project dosyasını`project` değişken.
## Adım 3: Yinelenen Görev Parametrelerini Tanımlayın
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Burada, yinelenen göreve ilişkin görev adı, süre, yinelenme düzeni, yinelenme aralığı ve kaynak takviminin göz ardı edilip edilmeyeceği gibi parametreleri tanımlarsınız.
## 4. Adım: Yinelenen Görev için Takvimi Ayarlayın
```csharp
parameters.SetCalendar(project, "Standard");
```
Bu adım, yinelenen görevin takvimini ayarlar. Bu örnekte takvimi "Standart" olarak ayarlıyor.
## Adım 5: Projeye Parametreler Ekleme
```csharp
project.RootTask.Children.Add(parameters);
```
Son olarak parametreleri projenin kök görevine ekleyin.

## Çözüm
Bu eğitimde, Aspose.Tasks for .NET'i kullanarak Microsoft Project yinelenen görev parametrelerinin nasıl ayarlanacağını gösterdik. Bu adımları izleyerek projelerinizde yinelenen görevleri verimli bir şekilde yönetebilirsiniz.
## SSS
### Yinelenme modelini daha da özelleştirebilir miyim?
Evet, Aspose.Tasks, proje gereksinimlerinize göre özelleştirebileceğiniz çeşitli yineleme modelleri ve seçenekleri sunar.
### Satın almadan önce deneme sürümü mevcut mu?
 Evet, Aspose.Tasks'tan ücretsiz deneme sürümünü indirebilirsiniz[İnternet sitesi](https://purchase.aspose.com/buy) Kütüphanenin özelliklerini değerlendirmek.
### Aspose.Tasks diğer proje dosyası formatlarını destekliyor mu?
Evet, Aspose.Tasks MPP, XML, XLSX ve daha fazlasını içeren çeşitli proje dosyası formatlarını destekler.
### Uygulama sırasında herhangi bir sorunla karşılaşırsam destek alabilir miyim?
Evet, topluluktan yardım almak için Aspose.Tasks forumunu ziyaret edebilir veya doğrudan yardım için destek ekibiyle iletişime geçebilirsiniz.
### Aspose.Tasks için nasıl geçici lisans alabilirim?
 Geçici lisansı adresinden alabilirsiniz.[İnternet sitesi](https://purchase.aspose.com/temporary-license/) test amaçlı.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
