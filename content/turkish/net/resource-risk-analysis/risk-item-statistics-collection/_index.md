---
title: Aspose.Tasks'ta MS Project Risk Öğesi İstatistiklerini Toplayın
linktitle: Aspose.Tasks'ta Risk Öğesi İstatistiklerinin Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET kullanarak MS Project dosyalarından risk öğesi istatistiklerini nasıl toplayacağınızı öğrenin. Proje yönetimi yeteneklerinizi geliştirin.
type: docs
weight: 22
url: /tr/net/resource-risk-analysis/risk-item-statistics-collection/
---
## giriiş
Bu eğitimde, Aspose.Tasks for .NET kullanarak MS Project dosyalarından risk öğesi istatistiklerinin nasıl toplanacağını inceleyeceğiz. Bu kütüphane, risk değerlendirmesi ve istatistiksel analiz de dahil olmak üzere proje verilerini analiz etmek için güçlü işlevler sağlar.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Aspose.Tasks for .NET: Aspose.Tasks kütüphanesini indirip yükleyin. Şu adresten alabilirsiniz:[indirme sayfası](https://releases.aspose.com/tasks/net/).
2. Geliştirme Ortamı: .NET programlama için ayarlanmış bir geliştirme ortamına sahip olun.

## Ad Alanlarını İçe Aktar
Kodlamaya başlamadan önce projenize gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Adım 1: Proje Dosyasını Yükleyin
Öncelikle MS Project dosyasını uygulamanıza yüklemeniz gerekmektedir. Bunu nasıl başarabileceğiniz aşağıda açıklanmıştır:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Adım 2: Risk Analizi Ayarlarını Tanımlayın
Yineleme sayısı da dahil olmak üzere risk analizi ayarlarını aşağıda gösterildiği gibi başlatın:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## 3. Adım: Bir Risk Kalıbını Başlatın
Dağıtım türünü, iyimser ve kötümser yüzdeleri ve güven düzeyini belirterek analiz için bir risk modeli oluşturun:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## Adım 4: Risk Analizinin Gerçekleştirilmesi
 Örnekleyin`RiskAnalyzer` projeyi sınıflandırın ve analiz edin:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Adım 5: İstatistikleri Alın
Analiz sonucundan erken bitiş gibi risk öğesi istatistiklerini alın:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Adım 6: İstatistikleri Yazdır
İstatistikleri yineleyin ve ayrıntıları yazdırın:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Diğer ilgili istatistikleri yazdırın...
}
```

## Çözüm
Bu eğitimde, MS Project dosyalarından risk öğesi istatistiklerini toplamak için Aspose.Tasks for .NET'i nasıl kullanacağımızı öğrendik. Bu adımları izleyerek proje verilerini etkili bir şekilde analiz edebilir ve potansiyel riskleri değerlendirebilir, daha iyi karar alma ve proje yönetimine yardımcı olabilirsiniz.

## SSS'ler
### S: Aspose.Tasks büyük MS Project dosyalarını işleyebilir mi?
C: Evet, Aspose.Tasks, büyük MS Project dosyalarını verimli bir şekilde yönetebilme yeteneğine sahiptir ve güvenilir performans ve ölçeklenebilirlik sunar.
### S: Aspose.Tasks, .mpp dışında diğer proje dosyası formatlarını da destekliyor mu?
C: Evet, Aspose.Tasks, XML ve MPT dahil olmak üzere çeşitli proje dosyası formatlarını destekler.
### S: Aspose.Tasks kurumsal düzeyde proje yönetimi uygulamalarına uygun mu?
C: Kesinlikle, Aspose.Tasks, güçlü özellikler ve kapsamlı belgeler sunarak kurumsal düzeydeki proje yönetimi uygulamalarının taleplerini karşılamak üzere tasarlanmıştır.
### S: Aspose.Tasks'ta risk analizi ayarlarını özelleştirebilir miyim?
C: Evet, Aspose.Tasks, risk analizi ayarlarını özel proje gereksinimlerinize ve senaryolarınıza uyacak şekilde yapılandırma konusunda esneklik sunar.
### S: Aspose.Tasks kullanıcıları için teknik destek mevcut mu?
 C: Evet, Aspose.Tasks kullanıcıları Aspose aracılığıyla teknik desteğe erişebilirler.[forumlar](https://forum.aspose.com/c/tasks/15)Soru sorabilecekleri, sorunları bildirebilecekleri ve toplulukla etkileşime girebilecekleri yer.