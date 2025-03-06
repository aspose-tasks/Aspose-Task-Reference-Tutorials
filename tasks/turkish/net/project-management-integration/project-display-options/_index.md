---
title: Aspose.Tasks'ta MS Project Görüntüleme Seçeneklerini Yapılandırma
linktitle: Aspose.Tasks'ta Proje Görüntüleme Seçeneklerini Yapılandırma
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project görüntüleme seçeneklerini programlı olarak nasıl yapılandıracağınızı öğrenin. Projenizin görünümünü zahmetsizce özelleştirin.
type: docs
weight: 17
url: /tr/net/project-management-integration/project-display-options/
---
## giriiş
Microsoft Project, projenizin görünümünü özelleştirmek için çok sayıda görüntüleme seçeneği sunar. Aspose.Tasks for .NET, bu seçenekleri programlı olarak yönetmek için sağlam bir çerçeve sağlar. Bu eğitimde Aspose.Tasks'ı kullanarak MS Project görüntüleme seçeneklerini nasıl yapılandıracağımızı keşfedeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET: Kitaplığı şuradan indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
2. Microsoft Project Dosyası: Görüntüleme seçeneklerini uygulamak için geçerli bir MS Project dosyasını (.mpp) hazır bulundurun.
3. Temel C# Bilgisi: C# programlama diline aşinalık gereklidir.

## Ad Alanlarını İçe Aktarma
Öncelikle gerekli ad alanlarını C# kodunuza aktardığınızdan emin olun:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Adım 1: Proje Dosyasını Yükleyin
 MS Project dosyasını kullanarak yükleyin.`Project` Aspose.Tasks tarafından sağlanan sınıf:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## 2. Adım: Ekran Seçeneklerini Yapılandırın
Şimdi MS Project'te bulunan çeşitli görüntüleme seçeneklerini yapılandıralım:
### Görev Zamanlaması Uyarılarını Devre Dışı Bırak
Manuel olarak zamanlanmış görevlerle zamanlama çakışmalarına ilişkin uyarıları devre dışı bırakmak için (Project 2010 ve sonrası için mevcuttur):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Etiketten Önce Boşluk Ekle
Sayı değeri ve saat kısaltmasından önce boşluk eklenecek şekilde ayarlayın:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Zaman Birimleri için Etiket Görünümünü Yapılandırma
Farklı zaman birimlerinin nasıl görüntüleneceğini özelleştirin:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Proje Özeti Görevini Göster
Projenin tamamı hakkındaki özet bilgileri tek bir satırda görüntüleyin:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Görev Zamanlaması Önerilerini Etkinleştir
Manuel olarak zamanlanmış görevlerle zamanlama çakışmaları için önerilerin görüntülenmesine izin ver:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Köprülerin Altını Çizin
Proje içindeki köprülerin altını çizmeye ayarlayın:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Adım 3: Projeyi Kaydet
Son olarak projeyi uygulanan görüntüleme seçenekleriyle kaydedin:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Çözüm
Bu eğitimde Aspose.Tasks for .NET'i kullanarak MS Project görüntüleme seçeneklerini nasıl yapılandıracağımızı öğrendik. Bu yeteneklerle proje dosyalarınızın görünümünü programlı olarak verimli bir şekilde özelleştirebilirsiniz.
## SSS'ler
### S: Bu görüntüleme seçeneklerini yalnızca belirli görevlere uygulayabilir miyim?
C: Evet, Aspose.Tasks API'yi kullanarak görüntüleme seçeneklerini ayrı ayrı görevlere seçerek uygulayabilirsiniz.
### S: Bu görüntüleme seçenekleri temeldeki proje verilerini etkiler mi?
C: Hayır, bu seçenekler yalnızca projenin görsel sunumunu değiştirir ve temel verileri değiştirmez.
### S: Bu görüntüleme seçenekleri Microsoft Project'in tüm sürümleriyle uyumlu mu?
C: Hayır, bazı seçenekler MS Project'in belirli sürümlerine özel olabilir. Uyumluluk ayrıntıları için belgelere bakın.
### S: Görüntüleme seçeneklerini varsayılan ayarlara geri döndürebilir miyim?
C: Evet, Aspose.Tasks API'yi kullanarak görüntüleme seçeneklerini varsayılan değerlerine sıfırlayabilirsiniz.
### S: Görüntüleme seçeneklerini programlı olarak özelleştirmede herhangi bir sınırlama var mı?
C: Aspose.Tasks kapsamlı özelleştirme yetenekleri sunsa da, MS Project dosya formatındaki sınırlamalar nedeniyle belirli görüntüleme seçeneklerine program aracılığıyla erişilemeyebilir.