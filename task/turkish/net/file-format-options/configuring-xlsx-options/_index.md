---
title: Aspose.Tasks for .NET'te MS Project XLSX Seçeneklerini Yapılandırma
linktitle: Aspose.Tasks'ta XLSX Seçeneklerini Yapılandırma
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te MS Project XLSX seçeneklerini nasıl yapılandıracağınızı öğrenin. Sütunları, kodlamayı ve daha fazlasını zahmetsizce özelleştirin.
type: docs
weight: 11
url: /tr/net/file-format-options/configuring-xlsx-options/
---
## giriiş
Microsoft Project (MS Project), proje yönetimi için güçlü bir araçtır ve Aspose.Tasks for .NET, MS Project dosyalarıyla programlı olarak çalışmak için kusursuz entegrasyon sağlar. Bu eğitimde Aspose.Tasks for .NET'i kullanarak MS Project XLSX seçeneklerini yapılandırma sürecini anlatacağız.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
### 1. Aspose.Tasks for .NET Yüklendi
 Geliştirme ortamınızda Aspose.Tasks for .NET'in kurulu olduğundan emin olun. Değilse, adresinden indirebilirsiniz.[Aspose.Tasks for .NET indirme sayfası](https://releases.aspose.com/tasks/net/).
### 2. C# ve .NET Framework'ün Temel Anlayışı
Bu eğitimin devamı için C# programlama dili ve .NET çerçevesine aşinalık gereklidir.
### 3. Microsoft Proje Dosyası
Yapılandırmak ve XLSX dosyası olarak kaydetmek istediğiniz bir Microsoft Project dosyasını (MPP) hazır bulundurun.

## Ad Alanlarını İçe Aktarma
Başlamak için gerekli ad alanlarını içe aktarın:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Adım 1: Projeyi Yükleyin
```csharp
var project = new Project("YourProjectFile.mpp");
```
Yapılandırmak istediğiniz Microsoft Project dosyasını yükleyin.
## Adım 2: XlsxOptions'ı tanımlayın
```csharp
var options = new XlsxOptions();
```
 Bir örneğini oluşturun`XlsxOptions` XLSX olarak kaydetme ayarlarını yapılandırmak için.
## 3. Adım: Gantt Grafiği Sütunlarını Ekleyin
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
İstediğiniz Gantt Grafiği sütunlarını seçeneklere ekleyin.
## 4. Adım: Kaynak Görünümü Sütunlarını Ekleyin
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Kaynak görünümü için istenen sütunları seçeneklere ekleyin.
## 5. Adım: Ödev Görünümü Sütunlarını Ekleme
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Seçeneklerde atama görünümü için istediğiniz sütunları ekleyin.
## Adım 6: Kodlamayı Ayarlayın
```csharp
options.Encoding = Encoding.Unicode;
```
Çıktı dosyasının kodlamasını ayarlayın.
## Adım 7: Projeyi XLSX olarak kaydedin
```csharp
project.Save("OutputFile.xlsx", options);
```
Projeyi yapılandırılan seçeneklerle XLSX dosyası olarak kaydedin.

## Çözüm
Bu eğitimde Aspose.Tasks for .NET'i kullanarak MS Project XLSX seçeneklerini nasıl yapılandıracağımızı öğrendik. Bu adımları izleyerek çıktı formatını gereksinimlerinize göre özelleştirerek proje yönetimi iş akışınızın esnekliğini ve kullanılabilirliğini artırabilirsiniz.
## SSS'ler

### S: Gantt Grafiği, Kaynak Görünümü ve Atama Görünümü için farklı sütunları ayrı ayrı yapılandırabilir miyim?

C: Evet, Aspose.Tasks for .NET'i kullanarak sütunları her görünüm için bağımsız olarak özelleştirebilirsiniz.

### S: Aspose.Tasks for .NET'i satın almadan önce deneme sürümü mevcut mu?

 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Aspose.Tasks for .NET sürüm sayfası](https://releases.aspose.com/).

### S: Uygulama sırasında herhangi bir sorunla karşılaşırsam veya sorularım olursa nasıl destek alabilirim?

 C: Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) topluluktan ve Aspose destek ekibinden yardım almak için.

### S: Windows dışındaki platformlarda Aspose.Tasks for .NET ile XLSX dosyaları oluşturabilir miyim?

C: Aspose.Tasks for .NET öncelikle Windows platformları için tasarlanmıştır ancak diğer platformlar için uyumluluk seçeneklerini de keşfedebilirsiniz.

### S: Test amaçlı herhangi bir geçici lisans seçeneği var mı?

 C: Evet, geçici lisansı şu adresten alabilirsiniz:[Aspose.Tasks geçici lisans sayfası](https://purchase.aspose.com/temporary-license/).