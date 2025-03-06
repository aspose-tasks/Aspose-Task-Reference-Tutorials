---
title: Aspose.Tasks'ta Ağaç Algoritmasını Kullanmak
linktitle: Aspose.Tasks'ta Ağaç Algoritmasını Kullanmak
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks'ın Ağaç Algoritmasını kullanarak .NET projelerinizde görev hiyerarşilerini etkili bir şekilde nasıl yönetebileceğinizi öğrenin.
type: docs
weight: 13
url: /tr/net/advanced-concepts/tree-algorithm/
---
## giriiş

Aspose.Tasks for .NET, proje yönetimi görevleri, kaynakları ve zamanlamalarıyla çalışmak için güçlü işlevler sağlar. Bu özelliklerden biri, kullanıcıların görev hiyerarşilerini verimli bir şekilde değiştirmelerine olanak tanıyan Ağaç Algoritmasıdır. Bu eğitimde, Aspose.Tasks for .NET'teki Ağaç Algoritmasının, ortak işleri toplamak ve bir proje içindeki iş değerlerini güncellemek için nasıl kullanılacağını keşfedeceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. Visual Studio: Sisteminizde Visual Studio'nun kurulu olduğundan emin olun.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET'i şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
3. Temel C# anlayışı: Örnekleri takip etmek için C# programlama diline aşinalık gereklidir.

## Ad Alanlarını İçe Aktar

Aspose.Tasks işlevleriyle çalışmak için C# projenize gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Şimdi her örneği birden fazla adıma ayıralım:

## Adım 1: Proje Dosyasını Yükleyin

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Proje dosyasını kullanarak belleğe yükleyin.`Project` sınıf.

## Adım 2: Görev Hiyerarşisini Tanımlayın

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Üst ve alt görevleri ekleyerek görev hiyerarşisini tanımlayın.

## 3. Adım: Görev Özelliklerini Ayarlayın

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Görevler için başlangıç tarihi, süre ve bitiş tarihi gibi özellikleri ayarlayın.

## 4. Adım: Kaynak Ekle

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Kaynakları projeye ekleyin ve bunları gerektiği gibi görevlere atayın.

## Adım 5: Ağaç Algoritmasını Uygulayın

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Başlat`WorkAccumulator` ortak çalışmalar toplamak için Ağaç Algoritmasını sınıflandırın ve uygulayın.

## Adım 6: Görev Çalışmasını Güncelleyin

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Toplanan bilgilere göre görevlerin çalışma değerlerini güncelleyin.

## Çözüm

Bu eğitimde, görev hiyerarşilerini etkili bir şekilde yönetmek için Aspose.Tasks for .NET'teki Ağaç Algoritmasını nasıl kullanacağımızı öğrendik. Adım adım kılavuzu takip ederek projelerinizdeki görevleri ve kaynakları verimli bir şekilde yönetebilirsiniz.

## SSS'ler

### S1: Aspose.Tasks for .NET nedir?

Cevap1: Aspose.Tasks for .NET, geliştiricilerin Microsoft Project dosyalarını C# kullanarak programlı olarak değiştirmelerine olanak tanıyan güçlü bir API'dir.

### S2: Aspose.Tasks for .NET'in ücretsiz deneme sürümünü indirebilir miyim?

 C2: Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).

### S3: Aspose.Tasks for .NET belgelerini nerede bulabilirim?

 Cevap3: Aspose.Tasks for .NET belgelerini bulabilirsiniz[Burada](https://reference.aspose.com/tasks/net/).

### S4: Aspose.Tasks for .NET için nasıl destek alabilirim?

 Cevap4: Aspose.Tasks for .NET ile ilgili destek için şu adresi ziyaret edebilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).

### S5: Test amaçlı geçici bir lisans mevcut mu?

 C5: Evet, test amaçlı olarak geçici lisansı şu adresten alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).