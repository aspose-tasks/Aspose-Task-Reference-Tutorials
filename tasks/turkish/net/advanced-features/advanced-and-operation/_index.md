---
date: 2026-03-16
description: Aspose.Tasks for .NET'te gelişmiş AND işlemini kullanarak birden fazla
  koşulu nasıl birleştireceğinizi ve proje görevlerini nasıl filtreleyeceğinizi öğrenin.
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Gelişmiş VE İşlemi ile Birden Çok Koşulu Nasıl Birleştirirsiniz
url: /tr/net/advanced-features/advanced-and-operation/
weight: 10
---

top-button >}}

Make sure to keep all formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Gelişmiş AND İşlemi

## Giriş

Bu öğreticide, Aspose.Tasks for .NET'te *gelişmiş AND işlemi* ile **birden fazla koşulu nasıl birleştireceğinizi** keşfedeceksiniz. Kılavuzun sonunda, **proje görevlerini** birkaç kritere göre **filtreleyebileceksiniz**—bu, özet öğeler, null olmayan girişler veya tek bir geçişte özel bayraklar gibi **görevleri nasıl filtreleyeceğinizi** bilmeniz gerektiğinde hayati öneme sahiptir.

## Hızlı Yanıtlar
- **Gelişmiş AND işlemi ne yapar?** İki veya daha fazla filtre koşulunu birleştirir, böylece yalnızca *tüm* kriterleri karşılayan görevler döndürülür.  
- **Koşulları birleştiren sınıf hangisidir?** `Util.And<T>` (API'de `And<T>` olarak sunulur).  
- **Özel bir lisansa ihtiyacım var mı?** Üretim kullanımı için normal bir Aspose.Tasks lisansı gereklidir; ücretsiz deneme sürümü mevcuttur.  
- **İki'den fazla koşulu zincirleyebilir miyim?** Evet—`And<T>` herhangi bir sayıda koşulu kabul eder.  
- **Hangi .NET sürümleri desteklenir?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## Aspose.Tasks'te “birden fazla koşulu birleştirme” nedir?

Birden fazla koşulu birleştirmek, her görevi aynı anda birden fazla kurala göre değerlendiren birleşik bir filtre oluşturmak anlamına gelir. Bu yaklaşım, kütüphanenin mantığı tek bir geçişte uygulaması nedeniyle görev listesini birden çok kez yinelemekten çok daha verimlidir.

## Neden gelişmiş AND işlemini kullanmalısınız?

- **Performans:** Görev koleksiyonu üzerindeki geçiş sayısını azaltır.  
- **Okunabilirlik:** Filtre mantığını deklaratif tutar ve bakımını kolaylaştırır.  
- **Esneklik:** Yerleşik koşulları (ör. `SummaryCondition`) özel önermelerle karıştırabilirsiniz.  

## Önkoşullar

Başlamadan önce, şunların olduğundan emin olun:

1. C# programlama temelleri.  
2. Aspose.Tasks for .NET yüklü. Henüz indirmediyseniz, **[buradan](https://releases.aspose.com/tasks/net/)** edinin.  
3. Visual Studio gibi bir IDE (herhangi bir sürüm çalışır).  

## Ad Alanlarını İçe Aktarın

İlk olarak, görev modeli ve yardımcı sınıfları sağlayan ad alanlarını içe aktarın:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## Adım 1: Projeyi Başlatın ve Görevleri Toplayın

`Project` örneği oluşturacağız ve dosyadaki tüm görevleri toplamak için `ChildTasksCollector` kullanacağız. Bu, görevlerin düz bir listesini almak için **collector'ı nasıl kullanacağınızı** gösterir.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Adım 2: Filtre Koşullarını Tanımlayın

Burada uygulamak istediğimiz bireysel koşulları tanımlıyoruz. Bu örnekte **özet görevleri filtreliyoruz** ve ayrıca görev nesnesinin null olmadığından emin oluyoruz.

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Adım 3: Koşulları AND İşlemi ile Birleştirin

Şimdi `And<T>` sınıfını kullanarak **birden fazla koşulu birleştiriyoruz**. Bu, **gelişmiş AND işleminin** çekirdeğidir.

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Adım 4: Koşulu Uygulayın ve Görevleri Filtreleyin

Birleşik koşul hazır olduğunda, birleşik mantığa göre **proje görevlerini filtrelemek** için `Filter` çağrısını yaparız.

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Adım 5: Filtrelenmiş Görevleri Çıktılayın

Son olarak, **tüm** koşulları karşılayan görevleri gösteririz. `Console.WriteLine` çağrılarını ihtiyacınıza göre herhangi bir özel işleme ile değiştirebilirsiniz.

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden Oluşur | Hızlı Çözüm |
|-------|----------------|-----------|
| `Filter` yöntemi bulunamadı | `using Aspose.Tasks.Util;` eksik | Util ad alanının içe aktarıldığından emin olun (Ad Alanlarını İçe Aktarın bölümüne bakın). |
| Görev döndürülmedi | Koşullar çok kısıtlayıcı (ör. mevcut olmayan özet görevleri filtrelemek) | Projenin gerçekten özet görevler içerdiğini doğrulayın veya koşulları ayarlayın. |
| NullReferenceException | `coll.Tasks` null girişler içeriyor | `NotNullCondition` zaten buna karşı koruma sağlar; AND zincirinde tutun. |

## SSS

### Q1: Aspose.Tasks for .NET nedir?

A: Aspose.Tasks for .NET, geliştiricilerin .NET uygulamalarında Microsoft Project dosyalarını programlı olarak manipüle etmelerini sağlayan güçlü bir API'dir.

### Q2: Util.And kullanarak iki'den fazla koşul uygulayabilir miyim?

A: Evet, Util.And herhangi bir sayıda koşulu birleştirerek karmaşık filtreleme kriterleri oluşturmak için kullanılabilir.

### Q3: Aspose.Tasks for .NET için ücretsiz deneme sürümü mevcut mu?

A: Evet, **[buradan](https://releases.aspose.com/)** ücretsiz bir deneme sürümü indirebilirsiniz.

### Q4: Aspose.Tasks for .NET belgelerini nerede bulabilirim?

A: Belgeleri **[burada](https://reference.aspose.com/tasks/net/)** bulabilirsiniz.

### Q5: Aspose.Tasks for .NET için desteği nasıl alabilirim?

A: Destek alabilirsiniz Aspose.Tasks topluluk forumundan **[burada](https://forum.aspose.com/c/tasks/15)**.

**Ekstra Soru & Cevap**

**S: Özel alan değerlerine göre görevleri nasıl filtrelerim?**  
A: Bir `CustomFieldCondition` oluşturun (veya `ICondition<Task>` uygulayın) ve bunu `And<T>` zincirine ekleyin.

**S: Aynı yaklaşımı kaynakları filtrelemek için kullanabilir miyim?**  
A: Evet—`Task` yerine `Resource` kullanın ve ilgili koşul sınıflarını kullanın.

## Sonuç

Yukarıdaki adımları izleyerek artık Aspose.Tasks for .NET'te **gelişmiş AND işlemi** kullanarak **birden fazla koşulu nasıl birleştireceğinizi** biliyorsunuz. Bu teknik, özet öğeler, null olmayan girişler veya tanımladığınız herhangi bir özel kriteri hedefleseniz de **proje görevlerini** verimli bir şekilde **filtrelemenizi** sağlar.

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Tasks for .NET (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}