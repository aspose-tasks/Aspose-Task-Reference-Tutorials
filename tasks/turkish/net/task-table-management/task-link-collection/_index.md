---
title: Aspose.Tasks'ta Görev Bağlantılarını Yönetme
linktitle: Aspose.Tasks'ta Görev Bağlantılarını Yönetme
second_title: Aspose.Tasks .NET API'si
description: Proje görev bağlantılarını verimli bir şekilde yönetme konusunda Aspose.Tasks for .NET'in gücünü keşfedin. Proje yönetimi deneyiminizi geliştirmek için adım adım kılavuzumuzu izleyin.
weight: 19
url: /tr/net/task-table-management/task-link-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Görev Bağlantılarını Yönetme

## giriiş
Aspose.Tasks for .NET'te görev bağlantılarının yönetimine ilişkin adım adım kılavuza hoş geldiniz! Görev bağlantıları, proje yönetiminde çok önemli bir rol oynar ve görevler arasında ilişkiler kurmanıza ve bağımlılıklar oluşturmanıza olanak tanır. Bu eğitimde Aspose.Tasks'ı kullanarak görev bağlantısı koleksiyonlarıyla çalışma sürecinde size yol göstereceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1.  Aspose.Tasks for .NET Library: Aspose.Tasks kütüphanesini indirip yükleyin. Kütüphaneyi bulabilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
2. Örnek Proje Dosyası: Örneklerle birlikte takip edilecek örnek bir proje dosyası (örneğin, "SampleProject.mpp") hazırlayın.
Şimdi başlayalım!
## Ad Alanlarını İçe Aktar
.NET projenizde Aspose.Tasks ile çalışmak için gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Adım 1: Projeyi Yükleyin ve Görevlere Erişin
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
// Projeyi yükle
var project = new Project(DataDir + "SampleProject.mpp");
// Görevlere kimliğe göre erişme
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## 2. Adım: Görev Bağlantıları Oluşturun
Bağımlılıklar oluşturmak için görevleri birbirine bağlayın:
```csharp
// FinishToStart bağımlılığını kullanarak görevleri bağlama
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## 3. Adım: Görev Bağlantılarını Yazdırın
Projenin görev bağlantılarını yazdırın:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
//Görev bağlantılarını yineleyin
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## 4. Adım: Görev Bağlantısını Düzenleyin
Bir görev bağlantısını dizin erişimine göre düzenleyin:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## 5. Adım: Görev Bağlantılarını Kaldır
Projedeki tüm görev bağlantılarını kaldırın:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## Çözüm
Tebrikler! Aspose.Tasks for .NET'te görev bağlantılarının nasıl yönetileceğini başarıyla öğrendiniz. Bu kapsamlı kılavuz, bir projenin yüklenmesini, görev bağlantılarının oluşturulmasını, bağlantıların yazdırılmasını, bağlantıların düzenlenmesini ve görev bağlantılarının kaldırılmasını kapsıyordu.
Proje yönetimi deneyiminizi geliştirmek için Aspose.Tasks'ın sunduğu daha fazla özellik ve işlevi keşfetmekten çekinmeyin.
## SSS
### Aspose.Tasks .NET'in tüm sürümleriyle uyumlu mu?
Evet, Aspose.Tasks, .NET'in tüm sürümleriyle sorunsuz çalışacak şekilde tasarlanmıştır.
### Aspose.Tasks'ı kullanarak özel görev bağlantı türleri oluşturabilir miyim?
Aspose.Tasks şu anda standart görev bağlantı türlerini desteklemektedir ve özel bağlantı türleri mevcut değildir.
### Aspose.Tasks'taki görevlere kısıtlamaları nasıl uygulayabilirim?
 kullanarak kısıtlamaları uygulayabilirsiniz.`ConstraintType` mülkiyeti`Task` Aspose.Tasks'taki sınıf.
### Aspose.Tasks'ın işleyebileceği proje dosyalarının boyutunda herhangi bir sınırlama var mı?
Aspose.Tasks, büyük proje dosyalarını minimum performans etkisi ile verimli bir şekilde işleyebilir.
### Aspose.Tasks desteği için bir topluluk forumu var mı?
 Evet, destek bulabilir ve toplulukla etkileşime geçebilirsiniz.[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
