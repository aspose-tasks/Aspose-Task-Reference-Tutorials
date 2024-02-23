---
title: Aspose.Tasks'ta Ay Günlerine Göre Tekrarlama
linktitle: Aspose.Tasks'ta Ay Günlerine Göre Tekrarlama
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks ile .NET projelerinde yinelenen görevleri nasıl yöneteceğinizi öğrenin. Ayın gününe göre tekrarlamayı ele almak için adım adım kılavuz.
type: docs
weight: 25
url: /tr/net/advanced-features/repetition-by-month-day/
---
## giriiş

.NET geliştirme alanında Aspose.Tasks, proje görevlerini ve programlarını yönetmek için güçlü bir araç olarak duruyor. Tekrarlanan görevlerin yerine getirilmesi de dahil olmak üzere proje yönetimi iş akışlarını kolaylaştırmak için çok sayıda işlevsellik sunar. Ayın gününe göre tekrarlama, proje planlamasında yaygın bir gerekliliktir ve Aspose.Tasks bu senaryo için güçlü bir destek sağlar.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1. Temel C# Anlayışı: Bu eğitimde tartışılan kavramları kavramak için C# programlama diline aşinalık gereklidir.
2. Aspose.Tasks for .NET Kurulumu: Aspose.Tasks for .NET'i yüklediğinizden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
3. Entegre Geliştirme Ortamı (IDE): Kodlama kolaylığı için sisteminizde Visual Studio benzeri bir IDE yüklü olsun.

## Ad Alanlarını İçe Aktar

Aspose.Tasks işlevlerine erişmek için C# projenize gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Sağlanan kod örneğini adım adım kılavuz formatına ayıralım:

## Adım 1: Proje Dosyasını Yükleyin

```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Bu kod satırı yeni bir örneğini başlatır.`Project` sınıf, "Project1.mpp" adlı proje dosyasını yüklüyor.

## Adım 2: Yinelenen Görev Parametrelerini Tanımlayın

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

Bu bölüm, adı, süresi, yineleme düzeni ve yinelenme aralığı dahil olmak üzere yinelenen görevin parametrelerini tanımlar.

## 3. Adım: Projeye Görev Ekleme

```csharp
project.RootTask.Children.Add(parameters);
```

Burada yinelenen görev parametrelerini projeye ekliyoruz.

## Adım 4: Proje Dosyasını Kaydet

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Son olarak, değiştirilen proje, eklenen yinelenen görevle birlikte kaydedilir.

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'te ay günlerine göre tekrarlamanın nasıl ele alınacağını araştırdık. Sağlanan adımları takip ederek proje programlarınızdaki yinelenen görevleri verimli bir şekilde yönetebilirsiniz.

## SSS'ler

### S1: Aspose.Tasks .NET'in tüm sürümleriyle uyumlu mu?

Cevap1: Aspose.Tasks, .NET framework'ün çeşitli versiyonlarını destekleyerek farklı ortamlar arasında uyumluluk sağlar.

### S2: Yinelenme modelini daha da özelleştirebilir miyim?

C2: Evet, Aspose.Tasks, belirli proje gereksinimlerine göre yinelenme modellerini tanımlamak için kapsamlı özelleştirme seçenekleri sunar.

### S3: Aspose.Tasks diğer proje yönetimi işlevleri için destek sağlıyor mu?

Cevap3: Aspose.Tasks kesinlikle proje yönetimi için görev takibi, kaynak tahsisi ve Gantt grafiği oluşturma gibi çok çeşitli özellikler sunuyor.

### S4: Aspose.Tasks'ın deneme sürümü mevcut mu?

 C4: Evet, şu adresten ücretsiz denemeden yararlanabilirsiniz:[Burada](https://releases.aspose.com/) satın alma kararı vermeden önce Aspose.Tasks'ın yeteneklerini keşfetmek için.

### S5: Sorunlarla karşılaşırsam veya sorularım olursa nereden yardım isteyebilirim?

 A5: ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) topluluktan veya Aspose ekibinden destek istemek.