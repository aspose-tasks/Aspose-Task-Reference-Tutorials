---
title: Aspose.Tasks'ta Gelişmiş AND Operasyonu
linktitle: Aspose.Tasks'ta Gelişmiş AND Operasyonu
second_title: Aspose.Tasks .NET API'si
description: Proje görevlerini birden fazla kritere göre verimli bir şekilde filtrelemek için Aspose.Tasks for .NET'te gelişmiş AND işlemlerini nasıl gerçekleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/advanced-features/advanced-and-operation/
---
## giriiş

 Bu eğitimde, görevleri ve projeleri yönetmek için güçlü bir araç olan Aspose.Tasks for .NET'teki gelişmiş AND operasyonunu derinlemesine inceleyeceğiz. kullanarak proje görevlerini birden çok koşula göre nasıl filtreleyeceğimizi keşfedeceğiz.`Util.And` sınıf.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Temel C# programlama dili bilgisi.
2.  .NET için Aspose.Tasks'ı yükledim. Değilse, adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/tasks/net/).
3. Visual Studio gibi entegre geliştirme ortamı (IDE).

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını C# projemize aktaralım:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## Adım 1: Projeyi Başlatın ve Görevleri Toplayın

Yeni bir Aspose.Tasks projesi başlatarak ve içindeki tüm görevleri toplayarak başlayın:

```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Adım 2: Filtre Koşullarını Tanımlayın

Daha sonra filtre koşullarını tanımlayın. Bu örnek için iki koşul oluşturacağız: biri özet görevleri filtrelemek için, diğeri ise boş olmayan görevleri filtrelemek için:

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Adım 3: Koşulları VE İşlemiyle Birleştirin

 Şimdi koşulları kullanarak birleştirin.`Util.And` bileşik bir koşul oluşturmak için sınıf:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## 4. Adım: Koşul Uygula ve Görevleri Filtrele

Birleştirilmiş koşulu toplanan görevlere uygulayın ve bunları buna göre filtreleyin:

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Adım 5: Çıkış Filtreli Görevler

Son olarak, filtrelenen görevlerin çıktısını alın:

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Burada ek işlemler yapılabilir
}
```

## Çözüm

 Bu eğitimde Aspose.Tasks for .NET'te gelişmiş AND işlemlerinin nasıl gerçekleştirileceğini öğrendik. Koşulları birleştirerek`Util.And` sınıf, görevleri birden çok kritere göre verimli bir şekilde filtreleyebiliriz.

## SSS'ler

### S1: Aspose.Tasks for .NET nedir?

C: Aspose.Tasks for .NET, geliştiricilerin Microsoft Project dosyalarını .NET uygulamalarında programlı olarak değiştirmelerine olanak tanıyan sağlam bir API'dir.

### S2: Util.And'ı kullanarak ikiden fazla koşulu uygulayabilir miyim?

C: Evet, Util.And karmaşık filtreleme kriterleri oluşturmak amacıyla herhangi bir sayıda koşulu birleştirmek için kullanılabilir.

### S3: Aspose.Tasks for .NET'in ücretsiz deneme sürümü mevcut mu?

 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).

### S4: Aspose.Tasks for .NET belgelerini nerede bulabilirim?

 C: Belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/tasks/net/).

### S5: Aspose.Tasks for .NET için nasıl destek alabilirim?

 C: Aspose.Tasks topluluk forumundan destek alabilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).