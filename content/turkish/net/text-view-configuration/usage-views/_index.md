---
title: Aspose.Tasks'ta Kullanım Görünümlerini Yapılandırma
linktitle: Aspose.Tasks'ta Kullanım Görünümlerini Yapılandırma
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te görev kullanım görünümlerini yapılandırmayı öğrenin. Ayrıntılı adımlarla proje görselleştirmesini geliştirin. Kütüphaneyi şimdi indirin!
type: docs
weight: 17
url: /tr/net/text-view-configuration/usage-views/
---
## giriiş
Proje yönetimi yeteneklerinizi geliştirmek isteyen bir .NET geliştiricisiyseniz Aspose.Tasks, Microsoft Project dosyalarını zahmetsizce değiştirmenize olanak tanıyan güçlü bir araçtır. Bu eğitimde Aspose.Tasks for .NET'i kullanarak kullanım görünümlerini yapılandırmaya odaklanacağız. Daha iyi proje görselleştirmesi için görev kullanım görünümlerinin ayrıntılarla birlikte oluşturulmasına ilişkin içgörüler kazanmak için takip edin.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Aspose.Tasks Kütüphanesi: Aspose.Tasks kütüphanesinin .NET projenize entegre olduğundan emin olun. Değilse indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/) ve kurulum talimatlarını takip edin.
- Belge Dizini: Proje belgelerinizin saklandığı bir dizin ayarlayın. Kod parçacıklarındaki "Belge Dizininiz"i, belge dizininizin gerçek yoluyla değiştirin.
## Ad Alanlarını İçe Aktar
Sağlanan kod parçacığında belirli ad alanlarının kullanımını fark edeceksiniz. Sorunsuz entegrasyon için bunları projenize eklediğinizden emin olun:
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## 1. Adım: Ayrıntılarla Görev Kullanımı Görünümünü Oluşturun
Ayrıntılarla birlikte bir görev kullanım görünümü oluşturarak başlayalım. Bu adımları takip et:
## Adım 1.1: Projeyi Yükle
```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## Adım 1.2: Görünümü Alın
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## Adım 1.3: Görünüm Ayarlarını Özelleştirin
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## Adım 1.4: Projeyi PDF olarak kaydedin
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## Adım 2: Ayrıntılar Başlık Sütunu Görüntüle
Bu adımda, ayrıntılar başlık sütununu görüntülemek ve projeyi PDF olarak kaydetmek için görünüm ayarlarını değiştireceğiz:
## Adım 2.1: Ayrıntılar Başlık Sütunu Görüntüle
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## Adım 2.2: Ayrıntılar Başlığını Tüm Satırlarda Tekrarlayın
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## Adım 2.3: Projeyi PDF olarak kaydedin
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## Çözüm
Tebrikler! Aspose.Tasks'ta kullanım görünümlerini başarıyla yapılandırdınız. Bu eğitim, Aspose.Tasks kütüphanesini kullanarak verimli proje yönetimi ve görselleştirme için bir temel sağlar.

### SSS'ler
### S: Aspose.Tasks belgelerini nerede bulabilirim?
 Kapsamlı belgeler mevcuttur[Burada](https://reference.aspose.com/tasks/net/).
### S: Aspose.Tasks for .NET'i nasıl indirebilirim?
 Kütüphaneyi indirin[Burada](https://releases.aspose.com/tasks/net/).
### S: Aspose.Tasks'ı nereden satın alabilirim?
 Aspose.Tasks'ı satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
### S: Ücretsiz deneme mevcut mu?
 Evet, ücretsiz denemeyi keşfedin[Burada](https://releases.aspose.com/).
### S: Desteğe mi ihtiyacınız var veya sorularınız mı var?
 Destek forumunu ziyaret edin[Burada](https://forum.aspose.com/c/tasks/15).