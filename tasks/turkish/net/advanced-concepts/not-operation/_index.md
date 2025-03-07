---
title: Aspose.Tasks'ta NOT İşlemi ile Çalışmak
linktitle: Aspose.Tasks'ta NOT İşlemi ile Çalışmak
second_title: Aspose.Tasks .NET API'si
description: Görevleri etkili bir şekilde filtrelemek için Aspose.Tasks for .NET'te NOT işlemini nasıl kullanacağınızı öğrenin. Proje yönetimi becerilerinizi şimdi geliştirin.
weight: 20
url: /tr/net/advanced-concepts/not-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta NOT İşlemi ile Çalışmak

## giriiş

Bu eğitimde Aspose.Tasks for .NET'te NOT işleminin nasıl kullanılacağını inceleyeceğiz. NOT işlemi, bir filtre koşulunu tersine çevirmemizi sağlayarak, belirli bir kriteri karşılamayan öğeleri seçmemizi sağlar.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Visual Studio: Kod örneklerini takip etmek için çalışan bir Visual Studio kurulumuna ihtiyacınız var.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini aşağıdaki adresten indirip yükleyin:[İnternet sitesi](https://releases.aspose.com/tasks/net/).
3. Temel C# Anlayışı: C# programlama diline aşinalık, kod örneklerini anlamada yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Öncelikle kodumuz için gerekli ad alanlarını içe aktaralım:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. Adım: Projeyi ve Görevleri Ayarlayın

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 "Project2.mpp" adlı bir proje dosyasını kullanarak başlıyoruz.`Project` Aspose.Tasks tarafından sağlanan sınıf. Proje dosyasının belirtilen dizinde bulunduğundan emin olun.

## Adım 2: Proje Görevlerini Toplayın

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Burada bir oluşturuyoruz`ChildTasksCollector` proje içindeki tüm görevleri toplama nesnesi. Daha sonra kullanırız`TaskUtils.Apply` Projenin görev hiyerarşisinde geçiş yapma ve tüm alt görevleri toplama yöntemini kullanın.

## 3. Adım: Filtre Durumunu Tanımlayın

```csharp
var filter = new NullCondition();
```

 Adlı özel bir sınıf kullanarak bir filtre koşulu tanımlarız.`NullCondition`. Bu koşul, null değeri olan görevleri seçer.

## Adım 4: NOT İşlemini Uygulayın

```csharp
var condition = new Not<Task>(filter);
```

 DEĞİL işlemini filtre koşuluna aşağıdakileri kullanarak uygularız:`Not<T>`Aspose.Tasks tarafından sağlanan sınıf. Bu, boş değere sahip olmayan görevleri seçerek filtre durumunu tersine çevirecektir.

## Adım 5: Görevleri Filtrele

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 Toplanan görevleri uygulanan koşula göre özel bir filtre kullanarak filtreliyoruz`Filter` yöntem. Bu yöntem, giriş parametreleri olarak numaralandırılabilir bir görev koleksiyonunu ve bir filtre koşulunu alır ve koşulu karşılayan görevlerin bir listesini döndürür.

## Adım 6: Filtrelenmiş Görevleri İşleyin

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Diğer mülklerle çalışın...
}
```

Son olarak, filtrelenen görevleri yineliyoruz ve istenen işlemleri gerçekleştiriyoruz. Bu örnekte, görevlerin adlarını konsola yazdırıyoruz.

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'te NOT işlemiyle nasıl çalışılacağını öğrendik. Filtre koşullarını tersine çevirerek, belirli kriterleri karşılamayan öğeleri seçici olarak seçebilir, böylece projeler içindeki görev manipülasyonunda esnekliğimizi artırabiliriz.

## SSS'ler

### S1: Aspose.Tasks'ı diğer .NET çerçeveleriyle kullanabilir miyim?

C: Evet, Aspose.Tasks, .NET Core, .NET Standard ve .NET Framework dahil olmak üzere çeşitli .NET çerçevelerini destekler.

### S2: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?

 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[İnternet sitesi](https://releases.aspose.com/).

### S3: Aspose.Tasks için nasıl destek alabilirim?

 C: Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) Her türlü destek sorgusu veya teknik yardım için.

### S4: Aspose.Tasks için geçici bir lisans satın alabilir miyim?

 C: Evet, geçici lisansı şu adresten satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/temporary-license/).

### S5: Aspose.Tasks için kapsamlı belgeleri nerede bulabilirim?

 C: Belgelerin tamamına şu adresten erişebilirsiniz:[Aspose.Tasks dokümantasyon sayfası](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
