---
title: Aspose.Tasks'ta Görev Koleksiyonlarını Yönetme
linktitle: Aspose.Tasks'ta Görev Koleksiyonlarını Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te verimli görev toplama yönetimini keşfedin. Oluşturma aşamasından düzenleme aşamasına kadar proje yönetiminde kolaylıkla uzmanlaşın.
weight: 18
url: /tr/net/task-table-management/task-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Görev Koleksiyonlarını Yönetme

## giriiş
.NET kullanarak proje yönetimi dünyasına giriyorsanız Aspose.Tasks, görev koleksiyonlarının sorunsuz bir şekilde yönetilmesi için başvuracağınız çözümdür. Bu eğitim, görev koleksiyonlarını verimli bir şekilde yönetme sürecinde size rehberlik edecek ve bu güçlü kitaplıktan en iyi şekilde yararlanmanızı sağlayacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Temel C# programlama dili bilgisi.
- Makinenizde Visual Studio yüklü.
- Aspose.Tasks for .NET kütüphanesini indirip projenizde referans olarak kullanabilirsiniz.
## Ad Alanlarını İçe Aktar
Başlamak için gerekli ad alanlarını C# projenize aktaralım:
```csharp
	using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Bu ad alanları, etkili görev yönetimi için gereken temel sınıflara ve yöntemlere erişim sağlar.
Şimdi öğreticiyi bir dizi adıma bölerek netlik ve basitlik sağlayalım.
## 1. Adım: Proje Örneği Oluşturma
```csharp
var project = new Project();
```
 kullanarak yeni bir proje başlatın.`Project` sınıf.
## 2. Adım: Görev Toplama Hazırlığını Kontrol Etme
```csharp
Console.WriteLine("Is task collection read-only: " + project.RootTask.Children.IsReadOnly);
```
Görev koleksiyonunun salt okunur olup olmadığını doğrulayın.
## 3. Adım: Görev Oluşturma
```csharp
var task1 = project.RootTask.Children.Add();
task1.Set(Tsk.Name, "Task 1");
// Başlangıç, süre ve bitiş gibi ek görev özelliklerini ayarlayın
// Görev 2 ve Görev 3 için benzer adımlar
```
Proje içinde görevler oluşturun ve özelliklerini ayarlayın.
## Adım 4: Proje Görevlerini Yazdırma
```csharp
foreach (var child in project.RootTask.Children)
{
    // Görev ayrıntılarını yazdır
    Console.WriteLine("Task name: " + child.Get(Tsk.Name));
    Console.WriteLine("Task start: " + child.Get(Tsk.Start));
    Console.WriteLine("Task duration: " + child.Get(Tsk.Duration));
    Console.WriteLine("Task finish: " + child.Get(Tsk.Finish));
    Console.WriteLine();
}
```
Proje içindeki her görevin ayrıntılarını yazdırın.
## Adım 5: Görevleri Düzenleme
```csharp
var task1ToEdit = project.RootTask.Children.GetById(1);
task1ToEdit.Set(Tsk.Name, "Task 1 (Edited)");
var taskToEdit2 = project.RootTask.Children.GetByUid(2);
taskToEdit2.Set(Tsk.Name, "Task 2 (Edited)");
```
Kimliklerini veya UID'lerini kullanarak görevleri düzenleyin.
## Adım 6: Yinelenen Görev Ekleme
```csharp
var parameters = new RecurringTaskParameters
{
    // Yinelenen görev parametrelerini ayarlayın
};
var recurring = project.RootTask.Children.Add(parameters);
Console.WriteLine("Task name: " + recurring.Get(Tsk.Name));
```
Projeye yinelenen bir görev ekleyin.
## Adım 7: Koleksiyonu Listeye Dönüştürme
```csharp
List<Task> tasks = project.RootTask.Children.ToList();
foreach (var task in tasks)
{
    task.Delete();
}
```
Görev koleksiyonunu bir listeye dönüştürün ve her görev üzerinde işlemler gerçekleştirin.
## Çözüm
Aspose.Tasks for .NET'te görev koleksiyonlarını yönetmek, bu adım adım kılavuzla çok kolay. Görevleri oluştururken, düzenlerken veya silerken Aspose.Tasks, proje yönetimini sorunsuz bir şekilde yürütmenizi sağlar.
## Sıkça Sorulan Sorular
### Aspose.Tasks .NET Core ile uyumlu mu?
Evet, Aspose.Tasks, .NET Core'u destekleyerek onu platformlar arası uygulamalarda kullanmanıza olanak tanır.
### Proje görevlerini farklı dosya formatlarına aktarabilir miyim?
Kesinlikle! Aspose.Tasks, PDF, XLSX ve MPP dahil olmak üzere çok yönlü dışa aktarma seçenekleri sunar.
### Görevler arasındaki bağımlılıkları nasıl halledebilirim?
 Görev bağımlılıklarını kullanarak ayarlayabilirsiniz.`TaskLink` Aspose.Tasks tarafından sağlanan sınıf.
### Aspose.Tasks desteği için bir topluluk forumu var mı?
 Evet, şu adresten destek bulabilir ve toplulukla etkileşime geçebilirsiniz:[Aspose.Tasks Forumu](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks için geçici lisans alabilir miyim?
 Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
