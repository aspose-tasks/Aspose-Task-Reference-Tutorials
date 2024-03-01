---
title: Aspose.Tasks'taki Risk Öğeleri İstatistikleri
linktitle: Aspose.Tasks'taki Risk Öğeleri İstatistikleri
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project dosyalarındaki risk analizinin gücünü ortaya çıkarın. İçgörüler elde edin, belirsizlikleri azaltın ve proje başarısını zahmetsizce artırın.
type: docs
weight: 21
url: /tr/net/resource-risk-analysis/risk-item-statistics/
---
## giriiş
Aspose.Tasks for .NET'i kullanarak proje yönetimi becerilerinizi geliştirmek mi istiyorsunuz? MS Project dosyalarındaki risk öğelerine ilişkin istatistiklerin elde edilmesine ilişkin adım adım eğitimimizle risk analizi alanına adım atın. Aspose.Tasks'ın güçlü yeteneklerinden yararlanarak proje belirsizlikleri hakkında paha biçilmez bilgiler edinebilir ve riskleri etkili bir şekilde azaltmak için bilinçli kararlar alabilirsiniz.
## Önkoşullar
Bu yolculuğa çıkmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1.  Aspose.Tasks for .NET Library: Kütüphaneyi şuradan indirip yükleyin:[Aspose.Tasks for .NET belgeleri](https://reference.aspose.com/tasks/net/). Bu kitaplık, MS Project dosyalarını programlı olarak işlemek için sizi güçlü araçlarla donatır.
2. .NET Geliştirme Ortamı: Aspose.Tasks'ın projelerinize kusursuz entegrasyonunu kolaylaştırmak için Visual Studio veya seçtiğiniz herhangi bir IDE dahil .NET geliştirme ortamınızı kurun.

## Ad Alanlarını İçe Aktar
Aspose.Tasks'ın işlevselliklerinden yararlanmak için gerekli ad alanlarını projenize ekleyin:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## 1. Adım: Veri Dizinini Tanımlayın
```csharp
String DataDir = "Your Document Directory";
```
 Değiştirildiğinden emin olun`"Your Document Directory"` MS Project dosyalarınızın bulunduğu belge dizininizin yolu ile birlikte.
## Adım 2: Risk Analizi Ayarlarını Yapılandırın
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Ayarlayın`IterationsCount`Risk analizinin hassasiyetini kontrol etmek için proje gereksinimlerinize dayalı parametre.
## Adım 3: MS Proje Dosyasını Yükleyin
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 İstenilen MS Project dosyasını`project` Daha fazla analiz için nesne.
## Adım 4: Görevi Tanımlayın ve Risk Kalıbını Başlatın
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
Risk analizi için görevi belirtin ve risk modelini dağıtım türü, iyimser ve kötümser süreler ve güven düzeyi gibi uygun parametrelerle yapılandırın.
## Adım 5: Proje Risklerini Analiz Edin
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Tanımlanan ayarları ve proje verilerini kullanarak risk analizi sürecini başlatın.
## Adım 6: İstatistikleri Alma ve Görüntüleme
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
Beklenen değer, standart sapma, yüzdelikler, minimum ve maksimum değerler dahil olmak üzere MS Project dosyasındaki risk öğeleriyle ilgili çeşitli istatistiksel ölçümleri alın ve görüntüleyin.

## Çözüm
Sonuç olarak, Aspose.Tasks for .NET'i kullanarak MS Project dosyalarındaki risk analizinde uzmanlaşmak, proje yöneticileri ve paydaşlar için bir dizi olasılığın kapısını aralıyor. Kapsamlı eğitimimizi takip ederek belirsizliklerin üstesinden güvenle gelebilir ve başarılı proje sonuçları elde edebilirsiniz.
## SSS'ler
### Daha fazla işlevsellik için Aspose.Tasks'ı diğer .NET kütüphaneleriyle entegre edebilir miyim?
Kesinlikle! Aspose.Tasks, çeşitli .NET kitaplıklarıyla sorunsuz bir şekilde bütünleşerek, proje gereksinimlerinize göre yeteneklerini geliştirmenize olanak tanır.
### Aspose.Tasks for .NET'in deneme sürümü mevcut mu?
 Evet, Aspose.Tasks'ın özelliklerini şuraya erişerek keşfedebilirsiniz:[ücretsiz deneme](https://releases.aspose.com/) web sitemizde mevcuttur.
### Aspose.Tasks için güncellemeler ve geliştirmeler ne sıklıkla yayınlanıyor?
Aspose.Tasks'i periyodik olarak güncellemeler ve geliştirmeler yayınlayarak sürekli olarak iyileştirmeye çalışıyoruz, böylece her zaman en yeni özelliklere ve optimizasyonlara erişebilmenizi sağlıyoruz.
### Aspose.Tasks için teknik destek alabilir miyim?
Kesinlikle! Özel destek ekibimize şu adresten kolayca ulaşabilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) Uygulama yolculuğunuz sırasında karşılaşabileceğiniz her türlü soru veya zorlukta size yardımcı olmak.
### Kısa vadeli projeler için geçici lisanslar sunuyor musunuz?
 Evet, eğer kısa vadeli bir proje için Aspose.Tasks'a ihtiyacınız varsa, kullanışlı hizmetlerimizden yararlanabilirsiniz.[geçici lisans](https://purchase.aspose.com/temporary-license/) Lisans ihtiyaçlarınızı uzun vadeli taahhütler olmadan karşılama seçeneği.