---
title: Aspose.Tasks for .NET ile WBS Kod Maskelerinde Uzmanlaşma
linktitle: Aspose.Tasks'ta WBS Kod Maskelerinin Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET ile proje yönetimini geliştirin. Bu kapsamlı eğitimde WBS Kod Maskelerini zahmetsizce oluşturmayı, yönetmeyi ve aktarmayı öğrenin.
type: docs
weight: 15
url: /tr/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## giriiş
Proje yönetiminin dinamik dünyasında görevlerin verimli bir şekilde organize edilmesi çok önemlidir. Aspose.Tasks for .NET, proje iş kırılım yapısı (WBS) kodlarını zahmetsizce yönetmek için güçlü bir çözüm sunar. Bu eğitimde, WBS Kod Maskeleri Koleksiyonunu derinlemesine inceleyerek bunların Aspose.Tasks for .NET kullanılarak nasıl uygulanacağını ve değiştirileceğini keşfedeceğiz.
## Önkoşullar
Bu kodlama yolculuğuna çıkmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- C# programlama dili hakkında çalışma bilgisi.
-  Aspose.Tasks for .NET, geliştirme ortamınıza kuruludur. Değilse indirin[Burada](https://releases.aspose.com/tasks/net/).
- Sorunsuz bir kodlama deneyimi için Visual Studio gibi bir kod düzenleyici.
## Ad Alanlarını İçe Aktar
Başlamak için gerekli ad alanlarını içe aktaralım:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Projeyi ve İKY Kodu Tanımını Başlatın
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. İKY Kod Maskelerini Tanımlayın
Mevcut kod maskelerini temizleyin ve yenilerini ekleyin:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Kod Maskeleri Bilgilerini Görüntüleyin
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Projeye Görevler Ekleyin
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Görev Bilgilerini Alın
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Kod Maskelerini Yönetin
Kod maskesini kaldırın ve kaldırıldığından emin olun:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Kod Maskelerini Başka Bir Projeye Kopyalayın
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Kod Maskelerini Başka Bir Projede Görüntüleyin
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Diğer Projeye Görevler Ekleyin
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. WBS Kodlarını Diğer Projede Görüntüleyin
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Çözüm
Aspose.Tasks for .NET ile WBS kodlarını yönetmek zahmetsiz bir iş haline gelir. Bu eğitim, WBS Kod Maskelerinin oluşturulmasını, değiştirilmesini ve aktarılmasını kapsamakta ve proje yönetimi deneyiminizi geliştirmek için size kapsamlı bir kılavuz sağlamaktadır.
## SSS
### S: Aspose.Tasks for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
C: Aspose.Tasks öncelikli olarak .NET dillerini destekler ancak diğer dillerle birlikte çalışabilirlik seçeneklerini de keşfedebilirsiniz.
### S: Aspose.Tasks for .NET'in deneme sürümü mevcut mu?
 C: Evet, deneme sürümünü indirebilirsiniz.[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for .NET ile ilgili nasıl yardım alabilirim veya sorunları nasıl bildirebilirim?
 C: Ziyaret edin[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) Destek ve tartışmalar için.
### S: Proje yönetiminde WBS kodlarının amacı nedir?
C: WBS kodları, proje planlamasına sistematik bir yaklaşım sağlayarak proje görevlerini hiyerarşik olarak düzenlemeye ve yapılandırmaya yardımcı olur.
### S: Aspose.Tasks for .NET'te WBS kodlarının formatını özelleştirebilir miyim?
C: Kesinlikle, Aspose.Tasks for .NET'i kullanarak WBS kodlarının formatı ve yapısı üzerinde tam kontrole sahipsiniz.