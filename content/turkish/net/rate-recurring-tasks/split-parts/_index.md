---
title: Aspose.Tasks'ta MS Project Bölünmüş Parçaları İşleme
linktitle: Aspose.Tasks'ta Bölünmüş Parçaların Kullanımı
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET ile MS Project'in bölünmüş parçalarını verimli bir şekilde nasıl yöneteceğinizi öğrenin. Proje yönetimi iş akışınızı geliştirin.
type: docs
weight: 18
url: /tr/net/rate-recurring-tasks/split-parts/
---

## giriiş
Aspose.Tasks for .NET kullanıldığında MS Project'in bölünmüş parçalarını yönetmek, proje yönetiminin çok önemli bir yönü olabilir. Bu eğitimde, adım adım rehberlik kullanarak bölünmüş parçaların nasıl etkili bir şekilde ele alınacağını keşfedeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET Kurulumu: Aspose.Tasks for .NET'i aşağıdaki adresten indirip yükleyin:[İnternet sitesi](https://releases.aspose.com/tasks/net/).
   
2. Temel C# Anlayışı: C# programlama diline aşina olmak faydalı olacaktır.

## Ad Alanlarını İçe Aktar
C# kodunuzda gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## 1. Adım: Proje Örneği Oluşturma
```csharp
var project = new Project();
```
 Yeni bir örneğini oluşturun`Project` sınıf.
## Adım 2: Proje Başlangıç ve Bitiş Tarihlerini Ayarlama
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Projenin başlangıç ve bitiş tarihlerini belirleyin.
## 3. Adım: Görev Ekleme
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Projeye yeni bir görev ekleyin.
## Adım 4: Görev Özelliklerini Ayarlama
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Görevin manuel durumu, başlangıç tarihi ve süresi gibi özellikleri ayarlayın.
## Adım 5: Kaynak Atamaları Ekleme
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Göreve kaynak atamaları ekleyin.
## Adım 6: Atama Özelliklerini Ayarlama
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Atama için başlangıç tarihi, iş ve bitiş tarihi gibi özellikleri ayarlayın.
## Adım 7: Zaman Aşamalı Veri Oluşturma
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Proje takvimine göre atama için zaman aşamalı veriler oluşturun.
## Adım 8: Görevi Bölme
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Görevi belirtilen zaman dilimi içinde birden fazla parçaya bölün.
## Adım 9: Bölünmüş Parçalar Üzerinde Yineleme Yapmak
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Görevin bölünmüş bölümleri üzerinde yineleyin ve bunların başlangıç ve bitiş tarihlerini yazdırın.

## Çözüm
Aspose.Tasks for .NET'te MS Project bölünmüş parçalarının etkili bir şekilde işlenmesi, proje yönetimi verimliliği açısından çok önemlidir. Bu eğitimde özetlenen adımları izleyerek bölünmüş görevleri sorunsuz bir şekilde yönetebilir ve proje yönetimi iş akışınızı geliştirebilirsiniz.
## SSS'ler
### S: Aspose.Tasks for .NET'i diğer .NET çerçeveleriyle birlikte kullanabilir miyim?
C: Evet, Aspose.Tasks for .NET, .NET Core ve .NET Standard dahil çeşitli .NET çerçeveleriyle uyumludur.
### S: Aspose.Tasks for .NET'in ücretsiz deneme sürümü mevcut mu?
 C: Evet, şu adresten ücretsiz deneme sürümü alabilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for .NET kaynak yönetimini destekliyor mu?
C: Evet, Aspose.Tasks for .NET proje kaynaklarını verimli bir şekilde yönetmenize olanak tanır.
### S: Aspose.Tasks for .NET'i kullanarak proje takvimlerini özelleştirebilir miyim?
C: Kesinlikle proje takvimlerini proje gereksinimlerinize göre özelleştirebilirsiniz.
### S: Aspose.Tasks for .NET desteğini nerede bulabilirim?
 C: Destek ve yardımı şu adreste bulabilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).