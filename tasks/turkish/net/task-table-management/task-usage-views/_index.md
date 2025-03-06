---
title: Aspose.Tasks for .NET'te Görev Kullanım Görünümlerinde Uzmanlaşma
linktitle: Aspose.Tasks'ta Görev Kullanımı Görünümlerini Yapılandırma
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i keşfedin ve görev kullanım görünümlerini nasıl yapılandıracağınızı öğrenin. Zaman ölçeği ayarlarını özelleştirin ve proje yönetimi görsellerinizi geliştirin.
type: docs
weight: 24
url: /tr/net/task-table-management/task-usage-views/
---
## giriiş
Proje yönetimi alanında görev kullanımını görselleştirmek etkili planlama ve yürütme açısından çok önemlidir. Aspose.Tasks for .NET, görev kullanım görünümlerini oluşturmak için güçlü bir çözüm sunarak zaman ölçeği ayarlarını ve sunum formatlarını özelleştirmenize olanak tanır. Bu eğitimde Aspose.Tasks'ı kullanarak görev kullanım görünümlerini yapılandırma adımlarını anlatacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1.  Aspose.Tasks for .NET: Aspose.Tasks kütüphanesinin .NET projenize entegre olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/tasks/net/).
2. .NET Ortamı: Makinenizde çalışan bir .NET ortamı kurun.
## Ad Alanlarını İçe Aktar
Aspose.Tasks işlevlerine erişmek için .NET projenize gerekli ad alanlarını içe aktarın. Kodunuza aşağıdaki satırları ekleyin:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 1. Adım: Belge Dizini Yolunu Ayarlayın
 Aspose.Tasks işlevleriyle çalışmaya başlamadan önce belgeler dizininizin yolunu ayarlayın. Yer değiştirmek`"Your Document Directory"` gerçek yol ile.
```csharp
String DataDir = "Your Document Directory";
```
## Adım 2: Projeyi Yükleyin
 Aspose.Tasks'ı başlatın`Project` proje dosyanızı (örneğin, TaskUsageView.mpp) yükleyerek nesneyi seçin.
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## 3. Adım: SaveOptions'ı tanımlayın
 Oluşturmak`SaveOptions`Oluşturma seçeneklerini belirtmek için nesne. Zaman ölçeğini 'Günler' ve sunum biçimini 'Görev Kullanımı' olarak ayarlayın.
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## 4. Adım: Gün Zaman Çizelgesi ile Tasarruf Edin
Projeyi önceden tanımlanmış 'Günler' zaman ölçeği ayarlarıyla kaydedin.
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Adım 5: ThirdsOfMonths Zaman Çizelgesi ile Tasarruf Edin
Zaman ölçeği ayarlarını 'ThirdsOfMonths' olarak değiştirin ve projeyi kaydedin.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Adım 6: Aylık Zaman Çizelgesi ile Tasarruf Edin
Zaman ölçeğini 'Ay' olarak ayarlayın ve projeyi güncellenen ayarlarla kaydedin.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Çözüm
Aspose.Tasks for .NET ile görev kullanım görünümlerini yapılandırmak basit bir işlemdir. Zaman ölçeği ayarlarını özelleştirerek proje görevlerinizin görselleştirilmesini özel ihtiyaçlarınıza göre uyarlayabilirsiniz.
 Daha fazla özellik ve işlevi keşfetmekten çekinmeyin.[dokümantasyon](https://reference.aspose.com/tasks/net/).
## Sıkça Sorulan Sorular
### Zaman ölçeğini önceden tanımlanmış ayarların ötesinde özelleştirebilir miyim?
Evet, aralıkları ve birimleri belirterek özel bir zaman ölçeği ayarlayabilirsiniz.
### Başka sunum formatları mevcut mu?
Aspose.Tasks, GanttChart, ResourceUsage ve daha fazlası dahil olmak üzere çeşitli sunum formatlarını destekler.
### Aspose.Tasks farklı proje dosyası formatlarıyla uyumlu mu?
Evet, Aspose.Tasks MPP, XML ve CSV gibi popüler proje dosyası formatlarını destekler.
### Belirli görevlere farklı zaman ölçeği ayarları uygulayabilir miyim?
Kesinlikle, projenizdeki bireysel görevler için zaman ölçeği ayarlarını özelleştirebilirsiniz.
### Aspose.Tasks için nasıl destek alabilirim veya yardım isteyebilirim?
 Ziyaret edin[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) topluluk desteği ve rehberlik için.