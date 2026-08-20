---
date: 2026-03-14
description: Aspose.Tasks for .NET'te görevleri “not” işlemiyle nasıl filtreleyeceğinizi
  öğrenin ve esnek görev sorguları için “apply not” koşuluyla “not” filtresini nasıl
  kullanacağınızı keşfedin.
linktitle: Working with NOT Operation in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'ta görevleri filtreleme işlemi.
url: /tr/net/advanced-concepts/not-operation/
weight: 20
---

 produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# filter tasks not operation in Aspose.Tasks

## Introduction

Bu öğreticide **NOT işlemi** kullanarak Aspose.Tasks for .NET ile **görevleri dışarıda bırakma (not) filtresi** nasıl uygulanır öğrenileceksiniz. NOT işlemi, bir filtre koşulunu tersine çevirerek belirli bir ölçütü **karşılamayan** tüm görevleri seçmenizi sağlar. Bu yetenek, değer içermeyen görevler gibi belirli öğeleri dışlamak ya da ekstra kod yazmadan karmaşık sorgular oluşturmak istediğinizde çok önemlidir.

## Quick Answers
- **NOT işlemi ne yapar?** Bir filtre koşulunu tersine çevirir ve orijinal testi geçemeyen öğeleri döndürür.  
- **filter tasks not operation neden kullanılır?** Dışlama mantığını basitleştirir ve kodunuzun okunabilirliğini artırır.  
- **NOT sınıfını hangi namespace sağlar?** `Aspose.Tasks.Util`.  
- **Üretim için lisansa ihtiyacım var mı?** Evet, deneme dışı kullanım için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **NOT’u diğer koşullarla birleştirebilir miyim?** Kesinlikle—`AndCondition`, `OrCondition` vb. ile birleştirebilirsiniz.

## What is filter tasks not operation?
**filter tasks not operation**, bir görev filtresine uygulanan mantıksal bir olumsuzlamadır. Bir koşulu karşılayan görevleri seçmek yerine, *karşılamayan* görevleri seçer. Boş alanları, belirli durumları veya dışlamak istediğiniz herhangi bir özelliği göz ardı etmek istediğinizde özellikle kullanışlıdır.

## Why apply not condition when filtering tasks?
**not condition** uygulamak, proje verileriniz üzerinde birden fazla geçiş yapma ihtiyacını azaltır. Kısa, sürdürülebilir kod yazmanıza olanak tanır ve değerlendirmeyi Aspose.Tasks’in optimize edilmiş motoruna devrederek performansı artırır.

## Prerequisites

Başlamadan önce aşağıdakilerin kurulu olduğundan emin olun:

1. Visual Studio: Kod örneklerini takip edebilmek için çalışan bir Visual Studio kurulumuna ihtiyacınız var.  
2. Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini [web sitesinden](https://releases.aspose.com/tasks/net/) indirip kurun.  
3. C# Temel Bilgisi: C# programlama diline aşina olmak, kod örneklerini anlamanızı kolaylaştıracaktır.

## Import Namespaces

İlk olarak kodumuz için gerekli namespace’leri içe aktaralım:

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

## Step 1: Set Up Project and Tasks

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

`Project` sınıfını kullanarak **Project2.mpp** adlı proje dosyasını yüklüyoruz. Proje dosyasının belirtilen dizinde mevcut olduğundan emin olun.

## Step 2: Collect Project Tasks

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

Burada, projedeki tüm görevleri toplamak için bir `ChildTasksCollector` nesnesi oluşturuyoruz. Ardından `TaskUtils.Apply` ile projenin görev hiyerarşisini dolaşıp her alt görevi topluyoruz.

## Step 3: Define Filter Condition

```csharp
var filter = new NullCondition();
```

`NullCondition` adlı özel bir sınıf kullanarak bir filtre koşulu tanımlıyoruz. Bu koşul, **null** değerine sahip görevleri seçer.  

> **İpucu:** `NullCondition` yerine `EqualsCondition` gibi başka bir koşul kullanarak farklı özellikleri hedefleyebilirsiniz.

## Step 4: Apply NOT Operation

```csharp
var condition = new Not<Task>(filter);
```

Aspose.Tasks tarafından sağlanan `Not<T>` sınıfını kullanarak filtre koşuluna **NOT işlemini** uyguluyoruz. Bu, orijinal koşulu tersine çevirir; böylece filtre artık **null değere sahip olmayan** görevleri seçer. Bu, **how to use not filter** tekniğinin temelidir.

## Step 5: Filter Tasks

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

Özel bir `Filter` metodu ile toplanan görevleri uygulanan koşula göre filtreliyoruz. Metot, bir görev koleksiyonu ve bir filtre koşulu alır, **apply not condition** koşulunu sağlayan görevlerin bir listesini döndürür.

## Step 6: Process Filtered Tasks

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Work with other properties...
}
```

Son olarak, filtrelenmiş görevler üzerinde döngü kurup istenen işlemleri gerçekleştiriyoruz. Bu örnekte, görev adlarını konsola yazdırıyoruz; ancak bu bloğu alanları güncellemek, görevleri taşımak veya raporlar oluşturmak için genişletebilirsiniz.

## Common Use Cases

- **Tamamlanmış görevleri dışlamak** istediğinizde bekleyen iş listesi oluşturmak.  
- **Özel alanları eksik görevleri bulmak** (ör. null “Owner” sütunu).  
- **Diğer koşullarla birleştirerek** “null olmayan ve başlangıç tarihi bugünden önce olan görevler” gibi karmaşık sorgular oluşturmak.

## Troubleshooting & Tips

| Issue | Reason | Fix |
|-------|--------|-----|
| No tasks returned | Orijinal koşul çok kısıtlayıcı olabilir. | Koşul mantığını kontrol edin veya `new TrueCondition()` gibi daha basit bir filtreyle test edin. |
| `NullReferenceException` | `DataDir` yolu yanlış. | `DataDir`'in *Project2.mpp* dosyasının bulunduğu klasöre işaret ettiğinden emin olun. |
| Unexpected results | `Not<T>` diğer koşullarla hatalı birleştirilmiş. | Parantez kullanın: `new AndCondition(new Not<Task>(filter), otherCondition)`. |

## Frequently Asked Questions

**Q: Aspose.Tasks’i diğer .NET framework’leriyle kullanabilir miyim?**  
A: Evet, Aspose.Tasks .NET Core, .NET Standard ve klasik .NET Framework’ü destekler.

**Q: Aspose.Tasks için ücretsiz deneme sürümü var mı?**  
A: Evet, ücretsiz deneme sürümünü [web sitesinden](https://releases.aspose.com/) indirebilirsiniz.

**Q: Aspose.Tasks için destek nasıl alabilirim?**  
A: Herhangi bir destek sorusu veya teknik yardım için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.

**Q: Aspose.Tasks için geçici bir lisans satın alabilir miyim?**  
A: Evet, [satın alma sayfasından](https://purchase.aspose.com/temporary-license/) geçici lisans temin edebilirsiniz.

**Q: Aspose.Tasks için kapsamlı dokümantasyonu nereden bulabilirim?**  
A: Tam dokümantasyona [Aspose.Tasks dokümantasyon sayfasından](https://reference.aspose.com/tasks/net/) ulaşabilirsiniz.

## Conclusion

**filter tasks not operation** ve **apply not condition** kullanarak görev seçimi üzerinde ince ayar yapmayı öğrendiğinizde, Aspose.Tasks içinde daha temiz kod yazabilir, manuel dışlamalardan kaçınabilir ve güçlü proje‑yönetimi araçları oluşturabilirsiniz.

---

**Last Updated:** 2026-03-14  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}