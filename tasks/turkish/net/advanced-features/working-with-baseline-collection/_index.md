---
date: 2026-04-06
description: Aspose.Tasks for .NET'te tüm baseline'ları silmeyi ve baseline koleksiyonlarını
  yönetmeyi adım adım kod örnekleriyle öğrenin.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Aspose.Tasks Baseline Koleksiyonu ile Tüm Baseline'ları Sil
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks Baseline Koleksiyonu ile Tüm Baseline'ları Sil
url: /tr/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Baseline Collection ile Tüm Baseline'ları Sil

## Giriş

Aspose.Tasks for .NET, Microsoft Project dosyalarını .NET uygulamalarınızdan doğrudan manipüle etmenizi sağlar. En güçlü özelliklerden biri, bir kaynak için **tüm baseline'ları sil**me yeteneğidir; bu, bir projenin izleme verilerini sıfırlamanız veya yeni bir baseline dönemi başlatmanız gerektiğinde hayati öneme sahiptir. Bu öğreticide, bir proje dosyasını yüklemekten belirli bir kaynağa bağlı tüm baseline'ları kaldırmaya kadar tüm süreci, net ve sohbet tarzı açıklamalar ve çalıştırmaya hazır C# kodu ile adım adım inceleyeceğiz.

## Hızlı Yanıtlar
- **“delete all baselines” ne yapar?** Seçilen bir kaynak için saklanan tüm baseline kayıtlarını kaldırır, tarihsel maliyet ve iş verilerini temizler.  
- **Neden buna ihtiyacım var?** Büyük bir proje değişikliğinden sonra izlemeyi sıfırlamak veya orijinal baseline'lar artık geçerli olmadığında.  
- **Bu yeteneği hangi kütüphane sağlar?** Aspose.Tasks for .NET.  
- **Bir lisansa ihtiyacım var mı?** Üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir; ücretsiz deneme sürümü mevcuttur.  
- **Kod .NET 6+ ile uyumlu mu?** Evet, API .NET Framework 4.5+, .NET Core 3.1+ ve .NET 5/6 ile çalışır.

## Baseline Nedir ve Neden Tüm Baseline'lar Silinir?

Bir baseline, belirli bir zamanda maliyet, iş ve takvim için orijinal planı yakalar. Bir projenin yaşamı boyunca birden fazla baseline (Baseline 1, Baseline 2 vb.) oluşturabilirsiniz, böylece gerçek ilerlemeyi farklı planlama anlık görüntüleriyle karşılaştırabilirsiniz. Ancak, bir projenin kapsamının yeniden belirlenmesi veya yeni bir başlangıç gibi durumlarda bu tarihsel baseline'ları tutmak kafa karıştırıcı olabilir. Tüm baseline'ları silmek size temiz bir sayfa sağlar ve mevcut gerçekliği yansıtan yeni baseline'lar oluşturmanıza olanak tanır.

## Önkoşullar

1. **Visual Studio** – herhangi bir yeni sürüm (Community, Professional veya Enterprise).  
2. **Aspose.Tasks for .NET** – [indirme bağlantısı](https://releases.aspose.com/tasks/net/) adresinden indirin.  
3. **Temel C# bilgisi** – değişkenler, döngüler ve konsol çıktısı konusunda rahat olmalısınız.  
4. **Microsoft Project dosyası** (`.mpp`) – örneklerde *WorkWithBaselineCollection.mpp* adlı bir örnek dosya kullanılacaktır.

## Namespace'leri İçe Aktarma

İlk olarak, gerekli namespace'leri kapsam içine alın, böylece derleyici kullanacağımız sınıfların nerede olduğunu bilir.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Adım 1: Proje Dosyasını Yükleme

Mevcut bir Project dosyasını yükleyerek başlıyoruz. `DataDir` değişkenini `.mpp` dosyanızın bulunduğu klasöre işaret edecek şekilde ayarlayın.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Adım 2: Hedef Kaynağı Almak

Gösterim amacıyla UID = 1 olan kaynağı alıyoruz. Gerçek bir senaryoda kaynağı isim veya başka bir tanımlayıcı ile bulursunuz.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Adım 3: Mevcut Baseline Bilgilerini Görüntüleme

Herhangi bir şey silmeden önce, kaynağa şu anda hangi baseline'ların bağlı olduğunu görmek faydalıdır. Bu, doğru verileri kaldırdığınızdan emin olmanızı sağlar.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Adım 4: Tüm Baseline'lar Üzerinde Döngü

Burada her bir baseline üzerinden döngü yapıyoruz ve maliyet, iş ve kazanılmış değer (BCWP/BCWS) gibi temel metrikleri yazdırıyoruz. Bu adım isteğe bağlıdır ancak günlükleme veya denetim amaçları için faydalıdır.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Tüm Baseline'ları Sil

Şimdi temel eylemi gerçekleştiriyoruz: seçilen kaynak için **tüm baseline'ları sil**. Döngü sırasında koleksiyonu değiştirmemek için önce koleksiyonu bir listeye kopyalıyoruz, ardından her bir baseline'ı tek tek kaldırıyoruz.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Bu blok çalıştıktan sonra, `resource.Baselines.Count` `0` olacaktır ve tüm baseline kayıtlarının temizlendiği doğrulanır.

## Yaygın Sorunlar ve İpuçları

- **NullReferenceException** – Proje dosyasının hedeflediğiniz kaynağı gerçekten içerdiğinden emin olun; aksi takdirde `GetByUid` `null` dönecektir.  
- **Lisanslama** – Geçerli bir Aspose.Tasks lisansı olmadan çıktıda bir filigran ve sınırlı işlevsellik görürsünüz.  
- **Performans** – Çok büyük projeler için kaldırma sürecini hızlandırmak amacıyla `Parallel.ForEach` ile döngü yapmayı düşünebilirsiniz, ancak temel koleksiyonun thread‑safe olmadığını unutmayın.

## Sıkça Sorulan Sorular

**S: Aspose.Tasks büyük proje dosyalarını işleyebilir mi?**  
C: Evet, Aspose.Tasks performans için optimize edilmiştir ve çok gigabayt boyutundaki `.mpp` dosyalarını verimli bir şekilde işleyebilir.

**S: Kütüphane tüm Microsoft Project sürümleriyle uyumlu mu?**  
C: Aspose.Tasks, Project 2000'den Project 2024'e kadar destekler; hem eski `.mpp` formatlarını hem de yeni XML tabanlı dosyaları kapsar.

**S: Baseline'ları silmeden önce özelleştirebilir miyim?**  
C: Kesinlikle. Silmeye karar vermeden önce herhangi bir baseline özelliğini (maliyet, iş, tarihler) okuyabilir veya değiştirebilirsiniz.

**S: Aspose.Tasks bulut platformlarında çalışır mı?**  
C: Evet, API herhangi bir .NET uyumlu ortamda çalışır; Azure App Service, AWS Lambda (.NET Core aracılığıyla) ve Docker konteynerleri dahil.

**S: Topluluktan yardım almak için nereye başvurabilirim?**  
C: Diğer geliştiriciler ve Aspose ekibiyle iletişime geçmek için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin.

## Sonuç

Bu rehberde Aspose.Tasks for .NET kullanarak bir kaynaktan **tüm baseline'ları sil** nasıl yapılır gösterdik. Adım adım kodu izleyerek baseline verilerini sıfırlayabilir, proje takibinizi temiz tutabilir ve takviminizi yeni bir planlama döngüsü için hazırlayabilirsiniz. Silme işleminden sonra yeni baseline'lar oluşturup kütüphanenin proje dosyasını nasıl güncellediğini deneyimlemekten çekinmeyin.

---

**Son Güncelleme:** 2026-04-06  
**Test Edilen:** Aspose.Tasks 24.12 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}