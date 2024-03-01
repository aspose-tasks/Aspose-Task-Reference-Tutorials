---
title: Aspose.Tasks'ta Yıl Gününe Göre Tekrarlama
linktitle: Aspose.Tasks'ta Yıl Gününe Göre Tekrarlama
second_title: Aspose.Tasks .NET API'si
description: Yinelenen görev yönetimini verimli bir şekilde kolaylaştırmak için Aspose.Tasks for .NET'te yıl içi tekrarları nasıl yöneteceğinizi öğrenin.
type: docs
weight: 27
url: /tr/net/advanced-features/repetition-by-year-day/
---
## giriiş

Proje yönetimi alanında, verimli görev planlama ve yineleme, zamanında yürütme ve sorunsuz iş akışını sağlamada önemli rol oynar. Aspose.Tasks for .NET, geliştiricilerin uygulamalarında yinelenen görevleri zahmetsizce gerçekleştirebilmeleri için güçlü bir çözüm sunar. Bu eğitimde, Aspose.Tasks'ı kullanarak yıllık gün tekrarlarıyla çalışmanın inceliklerini inceleyerek, yıllık kalıplara dayalı yinelenen görevler oluşturmak için kapsamlı bir kılavuz sağlıyoruz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

1.  Aspose.Tasks for .NET Kütüphanesi: Aspose.Tasks for .NET kütüphanesini aşağıdaki adresten indirip yükleyin:[İnternet sitesi](https://releases.aspose.com/tasks/net/).
   
2. Geliştirme Ortamı: Visual Studio veya .NET geliştirme için tercih edilen herhangi bir IDE ile uygun bir geliştirme ortamı oluşturun.

3. Temel C# Bilgisi: Kod örneklerini takip etmek için C# programlama dilinin temellerini öğrenin.

4. Proje Yönetimi Kavramları: Proje yönetimi kavramlarının ve görev zamanlamasının anlaşılması, eğitim kavramlarının etkili bir şekilde anlaşılmasına yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Kodlamaya başlamadan önce Aspose.Tasks for .NET'i kullanarak görev düzenlememizi kolaylaştırmak için gerekli ad alanlarını içe aktaralım.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Şimdi verilen örneği birden fazla adıma ayıralım ve her adımı ayrıntılı olarak açıklayalım.

## Adım 1: Proje Dosyasını Yükleyin

```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Burada yeni bir başlangıç başlatıyoruz`Project` nesnesini oluşturun ve "Project1.mpp" adlı mevcut bir proje dosyasını yükleyin.

## Adım 2: Yinelenen Görev Parametrelerini Tanımlayın

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

 Bu adımda yinelenen görevimizin parametrelerini tanımlıyoruz. Görev adını, süresini ve yinelenme modelini belirtiyoruz. Yıllık yineleme için şunu kullanırız:`YearlyRecurrencePattern` ve tekrarı kullanarak Temmuz ayının 1. gününde gerçekleşecek şekilde ayarlayın.`ByYearDayRepetition`. Ayrıca yinelenme aralığını 1 Temmuz 2018'den 1 Temmuz 2019'a kadar tanımlıyoruz.

## 3. Adım: Projeye Görev Ekleme

```csharp
project.RootTask.Children.Add(parameters);
```

Burada tanımlı yinelenen görev parametrelerini projenin kök görevine ekliyoruz.

## Adım 4: Projeyi Kaydet

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Son olarak, değiştirilen proje dosyasını eklenen yinelenen görevle birlikte kaydediyoruz.

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'te yıl gün tekrarlarıyla çalışma sürecini inceledik. Geliştiriciler, sağlanan adımları izleyerek yinelenen görev işlevselliğini uygulamalarına sorunsuz bir şekilde entegre edebilir ve proje yönetimi yeteneklerini geliştirebilir.

## SSS'ler

### S1: Aspose.Tasks karmaşık tekrarlanma modellerini yönetebilir mi?

Cevap1: Evet, Aspose.Tasks, yıllık, aylık, haftalık ve günlük tekrarlar gibi karmaşık olanlar da dahil olmak üzere çeşitli yinelenme kalıpları için kapsamlı destek sağlar.

### S2: Aspose.Tasks farklı proje dosyası formatlarıyla uyumlu mudur?

Cevap2: Aspose.Tasks kesinlikle MPP, XML ve CSV gibi popüler proje dosyası formatlarını destekleyerek farklı proje yönetimi araçları arasında uyumluluk sağlar.

### S3: Aspose.Tasks geliştiriciler için dokümantasyon ve destek sunuyor mu?

C3: Evet, geliştiriciler kapsamlı belgelere erişebilir ve karşılaştıkları sorular veya sorunlar için Aspose.Tasks topluluk forumlarından yardım isteyebilirler.

### S4: Aspose.Tasks'ı kullanarak süre ve başlangıç tarihi gibi görev özelliklerini özelleştirebilir miyim?

Cevap4: Kesinlikle Aspose.Tasks, görev özelliklerini dinamik olarak değiştirmek için güçlü API'ler sağlayarak geliştiricilerin süreleri, başlangıç tarihlerini, bağımlılıkları ve daha fazlasını özelleştirmesine olanak tanır.

### S5: Aspose.Tasks hem küçük ölçekli hem de kurumsal düzeydeki projeler için uygun mu?

Cevap5: Aslında Aspose.Tasks, bireysel görevlerden büyük ölçekli kurumsal projelere kadar her ölçekteki proje üzerinde çalışan geliştiricilerin ihtiyaçlarını karşılamak üzere tasarlanmıştır.