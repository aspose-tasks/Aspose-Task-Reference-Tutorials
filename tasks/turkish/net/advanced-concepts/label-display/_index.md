---
date: 2026-03-08
description: Aspose.Tasks for .NET kullanarak proje yönetiminde etiket görüntülemeyi
  ayarlamayı ve gün etiketini özelleştirmeyi öğrenin, okunabilirliği ve netliği artırın.
linktitle: Displaying Labels in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks for .NET'te Etiket Görüntülemeyi Nasıl Ayarlarsınız
url: /tr/net/advanced-concepts/label-display/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET'te Etiket Görüntülemeyi Nasıl Ayarlarsınız

## Giriş

Aspose.Tasks for .NET ile bir proje‑management çözümü oluştururken, **how to set label** seçeneklerini ayarlayabilmek, takvimlerin okunmasını kolaylaştırmak için çok önemlidir. İster dakikada dakikaya hassasiyet, ister yıllık üst‑seviye bir görünüm ihtiyacınız olsun, etiket görüntüsünü özelleştirerek zaman çizelgesini paydaşlarınızın beklediği şekilde sunabilirsiniz. Bu öğreticide, dakikalar, saatler, günler, haftalar, aylar ve yıllar için etiket görüntülerini ayarlama adımlarını adım adım inceleyecek ve ayrıca **customize day label** biçimlendirmesini en yüksek açıklık için nasıl yapacağınızı göstereceğiz.

## Hızlı Yanıtlar
- **What does “how to set label” mean?** Bu, zaman birimlerinin bir proje dosyasında nasıl görüneceğini kontrol eden `DisplayOptions` özelliklerini yapılandırmayı ifade eder.  
- **Which label can I change?** Dakikalar, saatler, günler, haftalar, aylar ve yıllar hepsi yapılandırılabilir.  
- **Do I need a license?** Üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir; ücretsiz deneme sürümü test için çalışır.  
- **Is this supported on .NET Core?** Evet, API .NET Core, .NET 5/6 ve tam .NET Framework ile çalışır.  
- **Can I change the label at runtime?** Kesinlikle – projeyi kaydetmeden önce istediğiniz zaman görüntüleme seçeneklerini değiştirebilirsiniz.

## Aspose.Tasks'te etiket görüntüsü nedir?

Etiket görüntüsü, Gantt şemasında ve zaman ölçeğinde zaman birimlerinin (dakika, saat, gün vb.) metinsel temsili belirler. Uygun `DisplayOptions` özelliğini ayarlayarak Aspose.Tasks'in bu birimleri nasıl render edeceğini belirlersiniz; bu, proje okunabilirliğini büyük ölçüde artırabilir.

## Neden etiket görüntülerini özelleştirirsiniz?

- **Improved readability:** Paydaşlar takvim detayını anında kavrayabilir.  
- **Consistent reporting:** Görsel çıktıyı kurumsal standartlarla (ör. aylar için “Mo” kullanmak) hizalar.  
- **Flexibility:** Detaylı ve üst‑seviye görünümler arasında, temel takvim verisini değiştirmeden geçiş yapabilirsiniz.

## Önkoşullar

1. **C# knowledge** – C# sözdizimi ve .NET proje yapısına temel aşinalık.  
2. **Aspose.Tasks for .NET** – kütüphaneyi [buradan](https://releases.aspose.com/tasks/net/) indirin ve kurun.  
3. **Development environment** – Visual Studio, VS Code veya .NET geliştirmeyi destekleyen herhangi bir IDE.

## Ad Alanlarını İçe Aktarın

Başlamadan önce gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Tasks;
using Aspose.Tasks;
```

## Dakika etiket görüntüsünü nasıl ayarlarsınız

### 1. Dakika Etiketlerini Görüntüleme

Dakika etiketini ayarlamak için `MinuteLabel` özelliğini kullanın:

```csharp
public void WorkWithMinuteLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the minute label is displayed
    project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.M;
}
```

## Saat etiket görüntüsünü nasıl ayarlarsınız

### 2. Saat Etiketlerini Görüntüleme

```csharp
public void WorkWithHourLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the hour label is displayed
    project.DisplayOptions.HourLabel = HourLabelDisplay.H;
}
```

## Gün etiket görüntüsünü özelleştirin

### 3. Gün Etiketlerini Görüntüleme

```csharp
public void WorkWithDayLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the day label is displayed
    project.DisplayOptions.DayLabel = DayLabelDisplay.D;
}
```

## Hafta etiket görüntüsünü nasıl ayarlarsınız

### 4. Hafta Etiketlerini Görüntüleme

```csharp
public void WorkWithWeekLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the week label is displayed
    project.DisplayOptions.WeekLabel = WeekLabelDisplay.W;
}
```

## Ay etiket görüntüsünü nasıl ayarlarsınız

### 5. Ay Etiketlerini Görüntüleme

```csharp
public void WorkWithMonthLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the month label is displayed
    project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mo;
}
```

## Yıl etiket görüntüsünü nasıl ayarlarsınız

### 6. Yıl Etiketlerini Görüntüleme

```csharp
public void WorkWithYearLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the year label is displayed
    project.DisplayOptions.YearLabel = YearLabelDisplay.Y;
}
```

## Yaygın Tuzaklar ve İpuçları

- **Tip:** Etiket görüntüsünü her zaman projeyi kaydetmeden *önce* ayarlayın; kaydettikten sonra yapılan değişiklikler dosyada yansıtılmaz.  
- **Pitfall:** Desteklenmeyen bir enum değeri kullanmak `ArgumentException` hatası verir. Sağlanan `*LabelDisplay` enum'larına bağlı kalın.  
- **Tip:** Ayrı görünümler için farklı etiket stillerine ihtiyacınız varsa, ayrı `Project` örnekleri oluşturun veya `DisplayOptions` nesnesini klonlayın.

## Sonuç

**how to set label** seçeneklerini Aspose.Tasks'te ustalaşarak, proje takvimlerinizin görsel sunumunu ince ayarlarla kontrol edebilirsiniz. Günlük bir scrum tahtası için gün etiketini özelleştiriyor ya da çok‑yıllı bir yol haritası için yıl etiketini ayarlıyor olun, bu ayarlar daha net ve profesyonel proje belgeleri sunmanıza yardımcı olur.

## SSS

### S1: Projenin belirli bölümleri için etiket görüntülerini özelleştirebilir miyim?

Evet, Aspose.Tasks for .NET, etiket görüntüleri üzerinde ayrıntılı kontrol sağlar ve gerektiğinde projenin belirli bölümleri için özelleştirmeye olanak tanır.

### S2: Aspose.Tasks popüler .NET framework'leriyle uyumlu mu?

Evet, Aspose.Tasks for .NET, .NET Core ve .NET Framework dahil olmak üzere çeşitli .NET framework'leriyle uyumludur.

### S3: Proje gereksinimlerine göre etiket görüntülerini dinamik olarak değiştirebilir miyim?

Kesinlikle, Aspose.Tasks for .NET'in esnekliği, gelişen proje gereksinimlerine göre etiket görüntülerinde dinamik ayarlamalar yapmanıza olanak tanır.

### S4: Etiket görüntülerinin özelleştirilmesinde herhangi bir sınırlama var mı?

Aspose.Tasks for .NET, etiket görüntüleri için kapsamlı özelleştirme seçenekleri sunar; sınırlamalar çok azdır ve kullanıcılara geniş bir esneklik sağlar.

### S5: Aspose.Tasks diğer proje yönetim araçlarıyla entegrasyonu destekliyor mu?

Evet, Aspose.Tasks sorunsuz entegrasyon yetenekleri sunar ve diğer proje yönetim araçları ve platformlarıyla birlikte çalışabilirliği kolaylaştırır.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}