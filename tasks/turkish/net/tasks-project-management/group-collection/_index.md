---
title: Aspose.Tasks'ta Proje Koleksiyonlarını Yönetme
linktitle: Aspose.Tasks'ta Grup Koleksiyonunu Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project koleksiyonlarını verimli bir şekilde nasıl yöneteceğinizi öğrenin. Adım adım kılavuzumuzu takip edin.
type: docs
weight: 26
url: /tr/net/tasks-project-management/group-collection/
---
## giriiş
Bu eğitimde, Aspose.Tasks for .NET kullanarak grup MS Project koleksiyonlarının nasıl yönetileceğini inceleyeceğiz. Grup koleksiyonlarını yönetmek, projenizdeki görevleri ve kaynakları verimli bir şekilde organize etmek ve yönetmek için çok önemlidir.
## Önkoşullar
Bu eğitime devam etmeden önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET Kütüphanesi: Aspose.Tasks for .NET kütüphanesini aşağıdaki adresten indirip yükleyin:[İndirme: {link](https://releases.aspose.com/tasks/net/).
2. Temel C# Bilgisi: Bu eğitim C#'ta kodlamayı içerdiğinden, C# programlama dilinin temellerine aşina olun.
3. Geliştirme Ortamı: Visual Studio veya .NET geliştirmeyi destekleyen başka bir IDE gibi bir geliştirme ortamı kurun.

## Ad Alanlarını İçe Aktar
Öncelikle C# kodumuzda Aspose.Tasks işlevleriyle çalışmak için gerekli ad alanlarını içe aktaralım.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Adım 1: Projeyi Yükleyin
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Bu adım, MS Project dosyasını Aspose.Tasks proje nesnesine yüklemeyi ve üzerinde işlemler yapmamızı sağlar.
## Adım 2: Görev Grupları Üzerinde Yineleme Yapın
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Burada proje içindeki görev gruplarını yineliyoruz, her grup için dizin, ad ve menüdeki görünürlük gibi ayrıntıları yazdırıyoruz.
## 3. Adım: Kaynak Grupları Üzerinde Yineleme Yapın
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
Benzer şekilde, bu adım kaynak grupları üzerinde yinelenir ve bunların dizinlerini, adlarını ve menüdeki görünürlüğünü görüntüler.
## 4. Adım: Grupları Temizleyin ve Başka Bir Projeye Kopyalayın
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Diğer projenin gruplarını temizle
otherProject.TaskGroups.Clear();
// Grupları başka projeye kopyala
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Burada başka bir projenin gruplarını temizliyoruz ve ardından grupları orijinal projeden ona kopyalıyoruz.
## 5. Adım: Özel Görev Grubu Ekleme
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
Bu adımda özel bir görev grubu oluşturup, eğer mevcut değilse onu diğer projeye ekliyoruz.
## Adım 6: Tüm Grupları Kaldır
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Son olarak diğer projedeki tüm grupları kaldırıyoruz.

## Çözüm
Aspose.Tasks for .NET'te grup MS Project koleksiyonlarını yönetmek, proje verilerini verimli bir şekilde organize etmek ve yönetmek için çok önemlidir. Bu öğreticide özetlenen adımları izleyerek projelerinizdeki görev ve kaynak gruplarını etkili bir şekilde yönetebilir ve genel proje yönetimini geliştirebilirsiniz.
## SSS'ler
### Aspose.Tasks for .NET, MS Project'in tüm sürümleriyle uyumlu mu?
Aspose.Tasks for .NET, Microsoft Project'in 2003, 2007, 2010, 2013, 2016 ve 2019 dahil olmak üzere çeşitli sürümlerini destekler.
### Aspose.Tasks for .NET'i kullanarak grup özelliklerini özelleştirebilir miyim?
Evet, Aspose.Tasks for .NET'i kullanarak ad ve görünürlük gibi grup özelliklerini özelleştirebilirsiniz.
### Aspose.Tasks for .NET platformlar arası uyumluluk sunuyor mu?
Aspose.Tasks for .NET öncelikle .NET çerçevesini hedefler ancak .NET Core ve .NET Standard ile platformlar arası senaryolarda kullanılabilir.
### Aspose.Tasks for .NET için nasıl destek alabilirim?
 Aspose.Tasks for .NET için destek alabilirsiniz.[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks for .NET'in deneme sürümü mevcut mu?
 Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[İnternet sitesi](https://releases.aspose.com/).