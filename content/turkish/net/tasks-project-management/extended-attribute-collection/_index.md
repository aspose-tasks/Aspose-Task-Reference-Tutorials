---
title: Aspose.Tasks'ta MS Project Nitelik Koleksiyonunu Yönetme
linktitle: Aspose.Tasks'ta Genişletilmiş Özellik Koleksiyonunu Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project'in genişletilmiş niteliklerini verimli bir şekilde nasıl yöneteceğinizi öğrenin. Adım adım rehberlikle görev niteliklerini sorunsuz bir şekilde yönetin.
type: docs
weight: 12
url: /tr/net/tasks-project-management/extended-attribute-collection/
---
## giriiş
Aspose.Tasks for .NET'i kullanarak MS Project'in genişletilmiş özelliklerini verimli bir şekilde yönetmek mi istiyorsunuz? Bu eğitimde size süreç boyunca adım adım rehberlik edeceğiz. Hadi dalalım!
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Visual Studio: Visual Studio'yu sisteminize yükleyin.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET'i şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
3. Temel C# Bilgisi: C# programlama dilinin temellerine aşina olun.

## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını projenize aktararak başlayın:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Adım 1: Proje Dosyasını Yükleyin
Öncelikle aşağıdaki kod parçasını kullanarak MS Project dosyasını yükleyin:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Adım 2: Göreve ve Genişletilmiş Niteliklere Erişim
Belirli bir göreve ve onun genişletilmiş özelliklerine erişin:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## 3. Adım: Genişletilmiş Nitelikleri Temizle
Gerekirse mevcut genişletilmiş özellikleri temizleyin:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Adım 4: Genişletilmiş Öznitelik Tanımları Oluşturun
Yeni genişletilmiş nitelikler için tanımlar oluşturun:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Adım 5: Görev Genişletilmiş Nitelikleri Üzerinde Yineleme Yapın
Görev genişletilmiş nitelikleri üzerinde yineleme yapın:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Adım 6: Genişletilmiş Nitelikler Ekleme
Göreve yeni genişletilmiş özellikler ekleyin:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Adım 7: Genişletilmiş Niteliklerle Çalışma
Gerektiğinde genişletilmiş öznitelikler üzerinde işlemler gerçekleştirin.
## Adım 8: Genişletilmiş Nitelikleri Kaldırma
Genişletilmiş nitelikleri dizine göre veya koşullu olarak kaldırın:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Adım 9: Nitelikleri Başka Bir Göreve Kopyalayın
Nitelikleri aynı veya farklı proje içindeki başka bir göreve kopyalayın:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Çözüm
Aspose.Tasks for .NET ile MS Project'in genişletilmiş öznitelik koleksiyonlarını yönetmek kusursuz hale geliyor. Bu eğitimde özetlenen adımları izleyerek, genişletilmiş öznitelikleri verimli bir şekilde yönetebilir ve proje yönetimi yeteneklerinizi geliştirebilirsiniz.
## SSS'ler
### S: Genişletilmiş öznitelikleri birden çok projede değiştirebilir miyim?
C: Evet, Aspose.Tasks for .NET'i kullanarak genişletilmiş nitelikleri farklı projelerdeki görevler arasında kopyalayabilirsiniz.
### S: Görev başına genişletilmiş öznitelik sayısında sınırlamalar var mı?
C: Aspose.Tasks for .NET, görev başına genişletilmiş özniteliklerin sayısına herhangi bir doğal sınırlama getirmez.
### S: Özel genişletilmiş öznitelik alanları oluşturabilir miyim?
C: Kesinlikle! Aspose.Tasks for .NET, proje gereksinimlerinize göre uyarlanmış özel genişletilmiş öznitelik alanları tanımlamanıza olanak tanır.
### S: Aspose.Tasks for .NET, çeşitli sürümlerdeki MS Project dosyalarının okunmasını ve yazılmasını destekliyor mu?
C: Evet, Aspose.Tasks for .NET, farklı sürümlerdeki MS Project dosya formatlarını destekler.
### S: Aspose.Tasks for .NET'in deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).