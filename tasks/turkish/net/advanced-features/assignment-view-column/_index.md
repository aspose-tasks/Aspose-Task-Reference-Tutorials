---
date: 2026-03-19
description: Aspose.Tasks for .NET kullanarak bir projeyi XML olarak dışa aktarırken
  birden fazla özel sütun eklemeyi ve özel sütun genişliğini biçimlendirmeyi öğrenin.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Atama Görünümüne Birden Çok Özel Sütun Ekle
url: /tr/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Atama Görünümüne Birden Çok Özel Sütun Ekleme

## Giriş

## Hızlı Yanıtlar
- **Ne elde edebilirim?** Herhangi bir atama verisini özel sütunlarda gösterin ve görünümünü kontrol edin.  
- **Hangi format bunu destekler?** `Spreadsheet2003SaveOptions` kullanarak projeyi XML'e (veya diğer formatlara) dışa aktarın.  
- **Bir lisansa ihtiyacım var mı?** Evet, üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **Hangi .NET sürümleri çalışır?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Kaç sütun ekleyebilirim?** Sınırsız – sadece ek `AssignmentViewColumn` örnekleri oluşturun.

## Birden Çok Özel Sütun Nedir?
Birden çok özel sütun, bir proje kaydedildiğinde veya dışa aktarıldığında varsayılan atama sütunlarının yanında görünen kullanıcı tanımlı alanlardır. `ResourceAssignment` nesnesinin herhangi bir özelliğini, örneğin özel notlar, maliyet kodları veya hesaplanmış değerler gibi, gösterebilme esnekliği sağlar.

## Atama Görünümüne Birden Çok Özel Sütun Neden Eklenir?
- **Gelişmiş raporlama:** Yerleşik sütunlar tarafından kapsanmayan proje‑özel bilgileri ekleyin.  
- **Daha iyi karar‑alma:** Paydaşlar, ham dosyalara bakmadan ihtiyaç duydukları kesin verileri görebilir.  
- **Tutarlı biçimlendirme:** Temiz ve okunabilir bir çıktı için sütun genişliğini ve metin dönüşümünü kontrol edin.  

## Önkoşullar

Before we dive in, make sure you have:

1. C# programlama dili hakkında temel bilgi.  
2. Aspose.Tasks for .NET kütüphanesi yüklü. Yüklü değilse, **[buradan](https://releases.aspose.com/tasks/net/)** indirebilirsiniz.  
3. Visual Studio gibi bir bütünleşik geliştirme ortamı (IDE).  

## Adım Adım Kılavuz

### Adım 1: Ad Alanlarını İçe Aktarın
İlk olarak, projeler ve görselleştirmelerle çalışmak için ihtiyaç duyacağımız sınıfları sağlayan ad alanlarını içe aktarın.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Adım 2: Projeyi Yükleyin
`Project` örneği oluşturun ve mevcut bir MPP dosyasını yükleyin.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Adım 3: Spreadsheet Kaydetme Seçeneklerini Oluşturun
`Spreadsheet2003SaveOptions` nesnesini örnekleyin – bu nesne, dışa aktarmadan önce atama görünümünü özelleştirmemizi sağlar.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Adım 4: Özel Sütunu Tanımlayın
Göstermek istediğiniz her veri parçası için bir `AssignmentViewColumn` oluşturun. Aşağıda, genişliği 200 puan olan bir **Notes** sütunu ekliyoruz.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**İpucu:** *Birden çok* özel sütun eklemek için bu adımı farklı alan adları ve delege mantığıyla tekrarlayın, ardından her örneği `options.AssignmentView.Columns` koleksiyonuna ekleyin.

### Adım 5: Özel Sütunu Seçeneklere Ekleyin
Sütunu (veya sütunları) atama görünümünün `Columns` koleksiyonuna ekleyin.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Adım 6: Atamaları Döngüye Al (İsteğe Bağlı Hata Ayıklama)
Özel sütun metninin doğru oluşturulduğunu doğrulamak için atamaları döngüye alabilirsiniz.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

### Adım 7: Projeyi Özel Sütunlarla Kaydedin
Son olarak, projeyi kaydedin. Örnekte XML olarak kaydedilir, ancak istediğiniz herhangi bir desteklenen formatı seçebilirsiniz.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Özel Sütunlarla Projeyi XML'e Nasıl Dışa Aktarılır?
`project.Save` metodunu yapılandırılmış `Spreadsheet2003SaveOptions` ile çağırdığınızda, Aspose.Tasks proje verilerini—tüm **birden çok özel sütun** dahil—seçilen XML dosyasına yazar. Bu, zenginleştirilmiş proje bilgilerini diğer sistemlerle veya paydaşlarla kolayca paylaşmanızı sağlar.

## Daha İyi Okunabilirlik İçin Özel Sütun Genişliğini Biçimlendirin
`AssignmentViewColumn` yapıcı metodunun ikinci parametresi sütun genişliğini (puan cinsinden) kontrol eder. Beklediğiniz metin miktarına göre bu değeri ayarlayın. Örneğin, **300** genişlik uzun notlar için iyidir, **100** ise kısa bayraklar için yeterlidir.

## Yaygın Sorunlar ve Çözümler
- **Sütun metni boş görünüyor:** Delegate'in bir string döndürdüğünden ve temel atama özelliğinin (örneğin `Asn.NotesText`) doldurulduğundan emin olun.  
- **Sütunlar dışa aktarılan dosyada görünmüyor:** `Save` metodunu çağırmadan önce `options.AssignmentView.Columns` koleksiyonunun özel sütunlarınızı içerdiğini doğrulayın.  
- **Genişlik göz ardı ediliyor gibi:** Bazı dışa aktarma formatlarının kendi düzen kuralları vardır; XML genişliği korur, ancak PDF/HTML ek stil gerektirebilir.

## Sıkça Sorulan Sorular

### S1: Atama görünümüne birden çok özel sütun ekleyebilir miyim?
**C:** Evet, sadece ek `AssignmentViewColumn` nesneleri oluşturun ve her birini `options.AssignmentView.Columns` koleksiyonuna ekleyin.

### S2: Yaygın atama alanları için önceden tanımlı dönüştürücüler var mı?
**C:** Evet, Aspose.Tasks birçok standart alan için yerleşik dönüştürücüler sağlar, böylece özel delege yazmadan verileri çekmek kolay olur.

### S3: Özel sütunların görünümünü, metin biçimlendirme veya stil uygulama gibi, özelleştirebilir miyim?
**C:** Kesinlikle. Genişliği ayarlamanın yanı sıra, sütunun stil seçenekleri aracılığıyla yazı tipi, hizalama ve diğer görsel özellikleri değiştirebilirsiniz.

### S4: Atama görünümünden varsayılan sütunları kaldırmak mümkün mü?
**C:** Varsayılan sütunları `Columns` koleksiyonundan kaldırarak veya genişliklerini sıfıra ayarlayarak dışlayabilirsiniz.

### S5: Aspose.Tasks, özel sütunlu elektronik tabloların dışında başka formatlara proje dışa aktarmayı destekliyor mu?
**C:** Evet, Aspose.Tasks özel sütun tanımlarını koruyarak PDF, HTML, XML ve birçok diğer formata dışa aktarabilir.

---

**Son Güncelleme:** 2026-03-19  
**Test Edilen Versiyon:** Aspose.Tasks 24.12 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}