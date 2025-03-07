---
title: Aspose.Tasks'ta Gantt Grafiği Zaman Ölçeği Katmanlarını Yapılandırma
linktitle: Aspose.Tasks'ta Zaman Ölçeği Katmanlarını Yapılandırma
second_title: Aspose.Tasks .NET API'si
description: Hassas proje zaman çizelgesi görselleştirmesi için Gantt Grafiği görünümünüzdeki zaman ölçeği katmanlarını yapılandırmak üzere Aspose.Tasks for .NET'i keşfedin. #Aspose.Tasks #MS Projesi
weight: 16
url: /tr/net/text-view-configuration/timescale-tiers/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Gantt Grafiği Zaman Ölçeği Katmanlarını Yapılandırma

## giriiş
Proje yönetiminin dinamik ortamında, zaman çizelgelerini ve son teslim tarihlerini anlamak için etkili görselleştirme çok önemlidir. Aspose.Tasks for .NET güçlü bir araç seti sağlar ve bu eğitimde Gantt Grafiği görünümünde en iyi temsil için zaman ölçeği katmanlarının nasıl yapılandırılacağını keşfedeceğiz. Proje görselleştirmenizi geliştirmek için bu adım adım talimatları izleyin.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Temel C# ve .NET bilgisi.
-  Aspose.Tasks for .NET kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/tasks/net/).
- .NET uygulama geliştirme için kurulmuş bir geliştirme ortamı.
## Ad Alanlarını İçe Aktar
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Şimdi verilen örneğin her adımını ayrı ayrı inceleyelim.
## 1. Adım: Projeyi Başlatın ve Görev Bağlantıları Ekleyin
```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Burada bir proje oluşturup "Görev 1" ile "Görev 2" arasında görev bağlantıları kuruyoruz.
## Adım 2: Gantt Grafiği Görünümünü Yapılandırma
```csharp
var view = (GanttChartView)project.DefaultView;
```
Özelleştirme için Gantt Grafiği görünümüne erişin.
## 3. Adım: Orta Zaman Ölçeği Katmanını Ayarlayın
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Haftaları belirli etiketler ve hizalamalarla görüntülemek için orta zaman ölçeği katmanını özelleştirin.
## 4. Adım: En İyi Zaman Ölçeği Katmanını Ekleyin
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Ayları temsil edecek bir üst zaman ölçeği katmanı ekleyin.
## 5. Adım: Orta Seviye Tarihlerini Özelleştirin
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Daha iyi görselleştirme için ay etiketlerini kişiselleştirin.
## Adım 6: Proje Zaman Çizelgesini Ayarlayın
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Genel zaman çizelgesini kontrol etmek için proje zaman çizelgesini tanımlayın.
## Adım 7: Projeyi Özelleştirilmiş Zaman Çizelgesi ile Kaydedin
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Projeyi tanımlanan zaman ölçeği ayarlarıyla kaydedin.
## Çözüm
Sonuç olarak, Aspose.Tasks for .NET'te zaman ölçeği katmanlarını yapılandırmak, proje zaman çizelgelerinin daha özelleştirilmiş ve görsel olarak çekici bir temsiline olanak tanır. Bu adımlar, proje yönetimi ihtiyaçlarınızı tam olarak karşılayan bir Gantt Grafiği görünümü oluşturmanıza olanak sağlar.
## SSS
### Aspose.Tasks'ı diğer .NET kütüphaneleriyle kullanabilir miyim?
Evet, Aspose.Tasks diğer .NET kitaplıklarıyla sorunsuz bir şekilde bütünleşerek geliştirme yığınınızda esneklik sunar.
### Test amaçlı geçici bir lisans mevcut mu?
 Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/) Evrim için.
### Gantt Grafiği görünümü için ek özelleştirme seçenekleri var mı?
Kesinlikle Aspose.Tasks, Gantt Grafiği görünümünün çeşitli proje gereksinimlerine uyacak şekilde kapsamlı özelleştirme seçenekleri sunuyor.
### Zaman ölçeklerini farklı formatlarda oluşturabilir miyim?
Elbette, projenizin bağlamına en iyi şekilde uyacak zaman ölçeği gösterimi için çeşitli formatları ve stilleri keşfedebilirsiniz.
### Aspose.Tasks desteği için bir topluluk forumu var mı?
 Evet, ziyaret edin[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) topluluk desteği ve tartışmalar için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
