---
title: Aspose.Tasks'ta Master Genişletilmiş Nitelik Tanımları MS Projesi
linktitle: Aspose.Tasks'ta Genişletilmiş Nitelik Tanımlarının Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak Microsoft Project'te genişletilmiş öznitelik tanımlarını nasıl yöneteceğinizi öğrenin. Proje verilerinizi zahmetsizce özelleştirin ve geliştirin.
type: docs
weight: 14
url: /tr/net/tasks-project-management/extended-attribute-definition-collection/
---
## giriiş
Bu eğitimde, Aspose.Tasks for .NET kullanarak Microsoft Project'te genişletilmiş öznitelik tanımlarıyla nasıl çalışılacağını inceleyeceğiz. Genişletilmiş özellikler, proje verilerini özelleştirmek ve geliştirmek için esnek bir yol sunarak kullanıcıların varsayılan olarak sağlanan standart alanların ötesinde ek alanlar eklemesine olanak tanır. Aspose.Tasks ile proje yönetimi ihtiyaçlarınızı uyarlamak için bu genişletilmiş özellikleri zahmetsizce yönetebilirsiniz.
## Önkoşullar
Devam etmeden önce aşağıdaki önkoşulların kurulu olduğundan emin olun:
- [.NET Çerçevesi](https://dotnet.microsoft.com/download)
-  Aspose.Tasks for .NET kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).

## Ad Alanlarını İçe Aktar
Öncelikle .NET projenizdeki Aspose.Tasks sınıflarına ve yöntemlerine erişmek için gerekli ad alanlarını içe aktarmanız gerekir. Bu adımları takip et:
## 1. Adım: .NET projenizi açın
.NET projenizi Visual Studio gibi tercih ettiğiniz IDE'de açın.
## 2. Adım: Aspose.Tasks ad alanını ekleyin
Aspose.Tasks ad alanını içe aktarmak için kod dosyanızın başına aşağıdaki satırı ekleyin:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Şimdi, kapsamlı bir anlayış için sağlanan kod örneklerini birden çok adıma ayıralım:
## Adım 1: Proje dosyasını yükleyin
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## 2. Adım: Mevcut genişletilmiş özellik tanımlarını temizleyin (isteğe bağlı)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## 3. Adım: Bir görev için genişletilmiş öznitelik tanımı oluşturun ve ekleyin
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## 4. Adım: Görevin genişletilmiş nitelikleri üzerinde yineleme yapın
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## 5. Adım: Bir kaynak için genişletilmiş öznitelik tanımı oluşturun ve ekleyin
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## 6. Adım: Kaynak genişletilmiş öznitelik tanımı ekleyin
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## 7. Adım: Genişletilmiş bir özelliği dizine göre kaldırın
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Çözüm
Bu eğitimde, Aspose.Tasks for .NET'i kullanarak Microsoft Project'te genişletilmiş öznitelik tanımlarıyla çalışmanın temellerini ele aldık. Bu adımları izleyerek genişletilmiş özellikleri proje yönetimi gereksinimlerinize uyacak şekilde verimli bir şekilde yönetebilir ve özelleştirebilirsiniz.
## SSS'ler
### S: Mevcut genişletilmiş öznitelik tanımlarını değiştirebilir miyim?
C: Evet, mevcut genişletilmiş özellik tanımlarını değiştirebilir veya ihtiyaçlarınıza göre yenilerini oluşturabilirsiniz.
### S: Genişletilmiş öznitelikler Microsoft Project'in tüm sürümlerinde destekleniyor mu?
C: Evet, genişletilmiş öznitelikler, en son sürümler de dahil olmak üzere Microsoft Project'in çoğu sürümünde desteklenir.
### S: Özel alanları hesaplamak için genişletilmiş öznitelikleri kullanabilir miyim?
C: Kesinlikle, tanımladığınız belirli kriterlere göre özel alanları hesaplamak için genişletilmiş özellikler kullanılabilir.
### S: Aspose.Tasks diğer .NET çerçeveleriyle uyumlu mu?
C: Aspose.Tasks çeşitli .NET çerçeveleriyle uyumludur, esneklik ve entegrasyon kolaylığı sağlar.
### S: Aspose.Tasks için daha fazla kaynağı ve desteği nerede bulabilirim?
 C: Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) destek için ve belgeleri inceleyin[Burada](https://reference.aspose.com/tasks/net/).