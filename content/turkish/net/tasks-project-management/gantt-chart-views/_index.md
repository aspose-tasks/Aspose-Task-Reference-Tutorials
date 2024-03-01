---
title: Aspose.Tasks'ta Gantt Şeması Görünümlerinde Uzmanlaşma
linktitle: Aspose.Tasks'ta Gantt Grafiği Görünümleri
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak Microsoft Project dosyalarındaki Gantt şeması görünümlerini nasıl özelleştireceğinizi öğrenin. Etkin proje yönetimi için adım adım kılavuz.
type: docs
weight: 22
url: /tr/net/tasks-project-management/gantt-chart-views/
---
## giriiş
Gantt şemaları proje yönetiminde görevleri, zaman çizelgelerini ve bağımlılıkları görselleştirmek için kullanılan güçlü araçlardır. Aspose.Tasks for .NET, Microsoft Project dosyalarındaki Gantt şeması görünümleriyle çalışmak için güçlü yetenekler sağlar. Bu eğitimde, Gantt grafiği görünümlerini değiştirmek, görünümlerini özelleştirmek ve bunları PDF dosyaları olarak kaydetmek için Aspose.Tasks'ı nasıl kullanabileceğimizi keşfedeceğiz.
## Önkoşullar
Devam etmeden önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
### 1. Aspose.Tasks for .NET'in Kurulumu
 Aspose.Tasks for .NET'i yüklediğinizden emin olun. Kütüphaneyi adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/tasks/net/) ve belgelerde verilen kurulum talimatlarını izleyin[Burada](https://reference.aspose.com/tasks/net/).
### 2. Microsoft Proje Dosyası
Bir Microsoft Project dosyası hazırlayın (`Project2.mpp`) Gantt şeması görünümleriyle çalışmak için kullanacağınız.
### 3. Temel C# ve .NET Framework Bilgisi
Bu eğitimde, C# programlama dili ve .NET çerçevesi hakkında temel bilgiye sahip olduğunuz varsayılmaktadır.
## Ad Alanlarını İçe Aktar
Aspose.Tasks'ta Gantt şeması görünümleriyle çalışmaya başlamadan önce gerekli ad alanlarını C# kodunuza aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

Sağlanan örnek kodu birden fazla adıma ayıralım ve her adımı ayrıntılı olarak açıklayalım:
## Adım 1: Proje Dosyasını Yükleyin
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Bu adım Microsoft Project dosyasının yüklenmesini içerir (`Project2.mpp` ) bir örneğine`Project` sınıf.
## 2. Adım: Durum Tarihini Ayarlayın
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Burada projenin durum tarihini başlangıç tarihine ayarlıyoruz.
## 3. Adım: Gantt Grafiği Görünümüne Erişin
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Gantt şeması görünümüne projeden ulaşıyoruz. Aspose.Tasks, Gantt Grafiği, Ağ Diyagramı ve Görev Kullanımı gibi görünümlere erişime olanak tanır.
## Adım 4: Gantt Grafiği Görünümünü Özelleştirin
Şimdi Gantt grafiği görünümünün çeşitli yönlerini özelleştirelim:
### Çubuk Yuvarlamayı Ayarla
```csharp
view.BarRounding = false;
```
Bu, Gantt grafiğindeki çubukların en yakın güne yuvarlanıp yuvarlanmayacağını belirler.
### Çubuk Boyutunu Ayarla
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
Bu, grafikteki Gantt çubuklarının yüksekliğini belirler.
### Toplama Çubuklarını Gizle
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Özet görevleri genişletirken toplama çubuklarının gizlenip gizlenmeyeceğini belirtir.
### Çalışma Dışı Zaman Rengini Ayarla
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Gantt şemasında çalışma dışı zamanın rengini tanımlar.
### Gantt Çubuklarını Yuvarlayın
```csharp
view.RollUpGanttBars = true;
```
Gantt grafiğindeki çubukların toplanması gerekip gerekmediğini belirtir.
### Çubuk Bölmelerini Göster
```csharp
view.ShowBarSplits = true;
```
Gantt grafiğindeki görev bölmelerinin gösterilmesinin gerekip gerekmediğini belirler.
### Çizimleri Göster
```csharp
view.ShowDrawings = true;
```
Gantt şemasındaki çizimlerin gösterilmesi gerekip gerekmediğini belirtir.
### Zaman Ölçeği Boyutu Yüzdesi
```csharp
view.TimescaleSizePercentage = 10;
```
Zaman ölçeği katmanındaki birimler arasındaki aralığı ayarlamak için bir yüzde ayarlar.
## Adım 5: Gantt Grafiği Görünümünü PDF olarak kaydedin
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Son olarak özelleştirilmiş Gantt şeması görünümünü PDF dosyası olarak kaydediyoruz.
## Çözüm
Bu eğitimde Aspose.Tasks for .NET'te Gantt şeması görünümleriyle nasıl çalışılacağını öğrendik. Verilen adımları takip ederek Gantt şemalarını proje gereksinimlerinize göre verimli bir şekilde değiştirebilir ve özelleştirebilirsiniz.
## SSS'ler
### S: Gantt grafiği çubuklarının görünümünü daha da özelleştirebilir miyim?
C: Evet, Aspose.Tasks, Gantt grafiği çubuklarının görünümünü özelleştirmek için renkler, şekiller ve boyutlar da dahil olmak üzere kapsamlı seçenekler sunar.
### S: Aspose.Tasks, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mudur?
C: Evet, Aspose.Tasks, MPP, MPT ve XML formatları da dahil olmak üzere Microsoft Project dosyalarının çeşitli sürümlerini destekler.
### S: Gantt şeması görünümlerini PDF dışındaki formatlara aktarabilir miyim?
C: Kesinlikle Aspose.Tasks, Gantt şeması görünümlerinin PNG, JPEG ve XPS dahil olmak üzere birden fazla formata aktarılmasını destekler.
### S: Aspose.Tasks karmaşık proje planlama algoritmaları için destek sunuyor mu?
C: Evet, Aspose.Tasks, karmaşık proje programlarını etkili bir şekilde yönetmek için gelişmiş planlama algoritmaları sağlar.
### S: Yardım isteyebileceğim veya Aspose.Tasks ile ilgili deneyimlerimi paylaşabileceğim bir topluluk forumu var mı?
 C: Evet, ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) diğer kullanıcılarla etkileşim kurmak, sorular sormak ve sorularınıza çözüm bulmak için.