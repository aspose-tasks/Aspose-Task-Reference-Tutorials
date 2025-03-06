---
title: Aspose.Tasks'ta Ay Hafta Güne Göre Tekrarlama
linktitle: Aspose.Tasks'ta Ay Hafta Güne Göre Tekrarlama
second_title: Aspose.Tasks .NET API'si
description: Yinelenen görevleri verimli bir şekilde otomatikleştirmek için Aspose.Tasks for .NET'te tekrarları aya, haftaya ve güne göre nasıl ayarlayacağınızı öğrenin.
weight: 26
url: /tr/net/advanced-features/repetition-by-month-week-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Ay Hafta Güne Göre Tekrarlama

## giriiş

Yazılım geliştirme alanında, özellikle proje yönetimi uygulamalarında, yinelenen görevleri verimli bir şekilde ele alma becerisi çok önemlidir. Aspose.Tasks for .NET, yinelenenler de dahil olmak üzere proje görevlerinin oluşturulmasını ve yönetimini kolaylaştırmak için tasarlanmış güçlü bir kütüphanedir. Aspose.Tasks'ın sağladığı işlevselliklerden biri de tekrarları aya, haftaya ve güne göre ayarlayarak görevlerin manuel müdahale olmadan planlandığı gibi yürütülmesini sağlamaktır.

## Önkoşullar

Aspose.Tasks for .NET'i kullanarak tekrarları ay, hafta ve güne göre ayarlamanın inceliklerine dalmadan önce, aşağıdaki önkoşulların yerine getirildiğinden emin olun:

1. Temel C# Anlayışı: Sağlanan kod örneklerini anlamak ve uygulamak için C# programlama diline aşina olmak çok önemlidir.
   
2.  Aspose.Tasks for .NET Kurulumu: Aspose.Tasks for .NET kütüphanesini indirip yüklediğinizden emin olun. Kütüphaneyi adresinden temin edebilirsiniz.[indirme sayfası](https://releases.aspose.com/tasks/net/).

3. .mpp Proje Dosyasına Erişim: Bir Microsoft Project dosyasını (.mpp) hazır bulundurun, çünkü onu ay, hafta ve güne göre tekrarların uygulanmasını göstermek için kullanacağız.

## Ad Alanlarını İçe Aktar

Aspose.Tasks for .NET'i C# uygulamanızda kullanmaya başlamak için gerekli ad alanlarını içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Her bir parçayı iyice anlamak için sağlanan kod pasajını birden fazla adıma ayıralım.

## Adım 1: Proje Dosyasını Yükleyin

```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Bu adım, yeni bir örneğinin oluşturulmasını içerir.`Project` sınıf ve mevcut bir Microsoft Project dosyasını yükleme (`Project1.mpp`) belirtilen dizinden.

## Adım 2: Yinelenen Görev Parametrelerini Tanımlayın

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Bu adımda yinelenen bir görevin parametrelerini tanımlıyoruz. Görevin adını, süresini, tekrarlama düzenini (aylık) ve yinelenme aralığını (belirli bir tarihe kadar) belirtiriz.

## 3. Adım: Projeye Yinelenen Görev Ekleme

```csharp
project.RootTask.Children.Add(parameters);
```

Burada tanımlı yinelenen görev parametrelerini projenin kök görevine ekliyoruz.

## Adım 4: Proje Dosyasını Kaydet

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Son olarak, değiştirilen proje dosyasını eklenen yinelenen görevle birlikte kaydediyoruz.

## Çözüm

Sonuç olarak, Aspose.Tasks for .NET'te tekrarların ay, hafta ve güne göre ayarlanması, geliştiricilerin projeleri içindeki yinelenen görevlerin yönetimini verimli bir şekilde otomatikleştirmesine olanak tanıyan basit bir süreçtir. Bu öğreticide özetlenen adımları izleyerek, bu işlevselliği C# uygulamalarınıza sorunsuz bir şekilde entegre edebilir, proje yönetiminde zamandan ve emekten tasarruf edebilirsiniz.

## SSS'ler

###S1: Yinelenme modelini sağlanan örneklerin ötesinde özelleştirebilir miyim?

C1: Evet, Aspose.Tasks for .NET yineleme kalıpları için kapsamlı özelleştirme seçenekleri sunarak bunları özel gereksinimlerinize göre uyarlamanıza olanak tanır.

###S2: Aspose.Tasks for .NET'in deneme sürümü mevcut mu?

 C2: Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[sürümler sayfası](https://releases.aspose.com/).

###S3: Aspose.Tasks for .NET desteğini nasıl edinebilirim?

 Cevap 3: Yardım isteyebilir ve toplulukla etkileşime geçebilirsiniz.[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).

###S4: Aspose.Tasks for .NET için geçici lisanslar mevcut mu?

 Cevap4: Evet, geçici lisansları şu adresten alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/temporary-license/) test ve değerlendirme amaçlıdır.

###S5: Aspose.Tasks for .NET için kapsamlı belgeleri nerede bulabilirim?

 A5: detaylı bilgilere başvurabilirsiniz[dokümantasyon](https://reference.aspose.com/tasks/net/) Kütüphanenin kullanımıyla ilgili ayrıntılı rehberlik için Aspose web sitesinde mevcuttur.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
