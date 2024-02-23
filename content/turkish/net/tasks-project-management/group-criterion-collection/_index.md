---
title: Aspose.Tasks ile MS Project Grup Kriterlerini Yönetin
linktitle: Aspose.Tasks'ta Grup Kriter Koleksiyonunu Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET kullanarak Group Criterion MS Project koleksiyonunu nasıl yöneteceğinizi öğrenin. Geliştiriciler için adım adım kılavuz.
type: docs
weight: 28
url: /tr/net/tasks-project-management/group-criterion-collection/
---
## giriiş
Aspose.Tasks for .NET, geliştiricilerin Microsoft Project dosyalarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir API'dir. Bu eğitimde Aspose.Tasks kullanarak MS Project'te Group Criterion koleksiyonunun nasıl yönetileceğini inceleyeceğiz.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Tasks for .NET: .NET projenizde Aspose.Tasks kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).

2. Microsoft Project Dosyası: Çalışmaya hazır bir Microsoft Project dosyasına (MPP) sahip olun.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını C# kodunuza aktarmanız gerekir. Bu adım Aspose.Tasks tarafından sağlanan işlevlere erişim için çok önemlidir.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Adım 1: Proje Dosyasını Yükleyin

 Bir başlat`Project` MPP dosyasını yükleyerek nesneyi seçin. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Adım 2: Grup Kriterlerine Erişim

Grubu projeden alın ve kriterlerine erişin.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Adım 3: Grup Kriterlerini Yineleyin

Gruptaki her kriter arasında dolaşın ve özelliklerini görüntüleyin.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Adım 4: Grup Kriterlerini Temizle

Salt okunur değilse mevcut grup ölçütlerini temizleyin.

```csharp
group.GroupCriteria.Clear();
```

## 5. Adım: Yeni Kriterler Ekleyin

Yeni bir grup kriteri oluşturun ve bunu gruba ekleyin.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Adım 6: Kriterleri Başka Bir Gruba Kopyalayın

Kriterleri bir gruptan diğerine kopyalayın.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Çözüm

Bu eğitimde, Group Criterion MS Project koleksiyonunu Aspose.Tasks for .NET kullanarak nasıl yöneteceğimizi öğrendik. Bu adımları izleyerek Microsoft Project dosyalarınız içindeki grup ölçütlerini programlı olarak etkili bir şekilde değiştirebilirsiniz.

## SSS'ler

### S1: Aspose.Tasks, Microsoft Project'in tüm sürümleriyle uyumlu mudur?

C: Evet, Aspose.Tasks, 2003, 2007, 2010, 2013 ve 2016 dahil olmak üzere çeşitli sürümlerdeki Microsoft Project dosyalarını destekler.

### S2: Tek bir gruba birden fazla kriter uygulayabilir miyim?

C: Kesinlikle, her birini yineleyerek ve bunları uygun şekilde ekleyerek bir gruba birden fazla kriter ekleyebilirsiniz.

### S3: Aspose.Tasks'ın deneme sürümü mevcut mu?

 C: Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[Burada](https://releases.aspose.com/).

### S4: Aspose.Tasks belgelerini nerede bulabilirim?

 C: Belgelere başvurabilirsiniz[Burada](https://reference.aspose.com/tasks/net/).

### S5: Herhangi bir sorunla karşılaşırsam nasıl destek alabilirim?

 C: Herhangi bir sorunuz varsa veya herhangi bir sorunla karşılaşırsanız Aspose.Tasks forumundan destek arayabilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).