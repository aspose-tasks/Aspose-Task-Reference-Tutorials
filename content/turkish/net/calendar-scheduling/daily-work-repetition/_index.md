---
title: Aspose.Tasks'ta Günlük İş Tekrarı
linktitle: Aspose.Tasks'ta Günlük İş Tekrarı
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak Microsoft Project dosyalarında günlük yinelenen görevleri nasıl oluşturacağınızı öğrenin. Verimliliği ve organizasyonu zahmetsizce artırın.
type: docs
weight: 26
url: /tr/net/calendar-scheduling/daily-work-repetition/
---
## giriiş

Aspose.Tasks for .NET, geliştiricilerin Microsoft Project dosyalarını kolaylıkla yönetmelerini sağlayan güçlü bir kitaplıktır. Sayısız özelliği arasında yinelenen görevleri verimli bir şekilde yerine getirme yeteneği de vardır. Bu eğitimde, bir proje içinde günlük olarak tekrarlanan görevlerin oluşturulmasına olanak tanıyan Günlük İş Tekrarı işlevini inceleyeceğiz.

## Önkoşullar

Bu eğitime dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Temel C# ve .NET framework bilgisi.
- Sisteminizde Visual Studio yüklü.
-  Aspose.Tasks for .NET kütüphanesi. İndirebilirsin[Burada](https://releases.aspose.com/tasks/net/).
- Microsoft Project dosyalarına (.mpp) aşinalık.

## Ad Alanlarını İçe Aktar

Başlamadan önce gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Sağlanan örneği birden çok adıma ayıralım:

## Adım 1: Proje Dosyasını Yükleyin

 İlk önce proje dosyasını kullanarak yükleyin.`Project` sınıf:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Adım 2: Yinelenen Görev Parametrelerini Tanımlayın

Tekrarlanan görevin parametrelerini tanımlayın:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## 3. Adım: Takvimi ve Görev Başlangıç Tarihini Ayarlayın

Görevin takvimini ve başlangıç tarihini ayarlayın:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## Çözüm

Bu eğitimde, günlük iş tekrarı ile yinelenen görevler oluşturmak için Aspose.Tasks for .NET'in nasıl kullanılacağını araştırdık. Bu adımları izleyerek projelerinizdeki görevleri verimli bir şekilde yönetebilir, sorunsuz iş akışı ve organizasyon sağlayabilirsiniz.

## SSS'ler

### S1: Yinelenme modelini daha da özelleştirebilir miyim?

Cevap1: Evet, yineleme modelini ihtiyaçlarınıza göre uyarlamak için başlangıç tarihi, oluşum sayısı ve tekrar aralığı gibi parametreleri ayarlayabilirsiniz.

### S2: Aspose.Tasks, Microsoft Project'in farklı sürümleriyle uyumlu mudur?

C2: Evet, Aspose.Tasks, Microsoft Project'in çeşitli sürümlerini destekleyerek uyumluluk ve kusursuz entegrasyon sağlar.

### S3: Yinelenen görevlerdeki istisnaları veya değişiklikleri nasıl halledebilirim?

Cevap3: Aspose.Tasks, yinelenen görevler içindeki istisnaları ve değişiklikleri yönetmek için güçlü bir işlevsellik sağlayarak esneklik ve özelleştirmeye olanak tanır.

### S4: Projeyi farklı formatlara aktarabilir miyim?

Cevap4: Kesinlikle Aspose.Tasks, projeleri PDF, HTML, XML ve daha fazlasını içeren çeşitli formatlara aktarma desteği sunarak kolay paylaşım ve işbirliğini kolaylaştırır.

### S5: Aspose.Tasks teknik destek sunuyor mu?

C5: Evet, Aspose.Tasks, yardım arayabileceğiniz, deneyimlerinizi paylaşabileceğiniz ve diğer kullanıcılarla iletişim kurabileceğiniz forum aracılığıyla kapsamlı teknik destek sağlıyor.