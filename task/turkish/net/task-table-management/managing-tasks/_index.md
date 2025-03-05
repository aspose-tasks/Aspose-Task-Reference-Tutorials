---
title: Aspose.Tasks'ta Görevleri Yönetme
linktitle: Aspose.Tasks'ta Görevleri Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET ile görevleri yönetmeye ilişkin kapsamlı kılavuzu keşfedin. Eklemeyi, bölünmüş parçaları görüntülemeyi, taşımayı, özellikleri almayı/ayarlamayı ve daha fazlasını öğrenin.
type: docs
weight: 15
url: /tr/net/task-table-management/managing-tasks/
---
## giriiş
Projelerinizdeki görevleri verimli bir şekilde yönetmek isteyen bir .NET geliştiricisiyseniz Aspose.Tasks for .NET güçlü bir çözüm sunar. Bu eğitim, Aspose.Tasks kullanarak görevleri yönetmenin çeşitli yönleri konusunda size rehberlik edecek, adım adım talimatlar ve kod örnekleri sunacaktır. Görev ekleme, bölünmüş parçaları görüntüleme, görevleri aynı üst öğe altında taşıma, görev özelliklerini alma/ayarlama, görev atamaları üzerinde yineleme yapma, görev taban çizgilerini okuma veya görevleri silme gibi işlemler yapıyorsanız, bu kılavuz size her konuda yardımcı olacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1. Aspose.Tasks for .NET Library: Aspose.Tasks for .NET kütüphanesinin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/tasks/net/).
2. Belge Dizini: Proje belgelerinizin saklanacağı bir dizin ayarlayın.
## Ad Alanlarını İçe Aktar
.NET projenize Aspose.Tasks ile çalışmak için gerekli ad alanlarını ekleyin:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Projeye Görev Ekleme
```csharp
// Yeni bir proje oluştur
var project = new Project();
// Görev ekle
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Projeyi kaydet
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Görevin Bölünmüş Parçalarını Görüntüleme
```csharp
// Bölünmüş görevlere sahip bir proje yükleme
var project = new Project(DataDir + "ViewSplitTasks.mpp");
// Bir göreve erişme
var task = project.RootTask.Children.GetById(4);
// Bölünmüş parçaları göster
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Bir Görevi Aynı Ebeveynin Altına Taşımak
```csharp
try
{
    // Bir proje yükle
    var project = new Project(DataDir + "MoveTask.mpp");
    // Kimliği 5 olan görevleri, kimliği 3 olan görevden önce taşı
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Değiştirilen projeyi kaydet
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Görev Özelliklerini Alma/Ayarlama
```csharp
// Yeni bir proje oluştur
var project = new Project();
// Görev ekleme ve özellikleri ayarlama
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Görev özelliklerini toplayın ve görüntüleyin
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Görev Atamaları Üzerinde Yineleme Yapmak
```csharp
// Atamaları olan bir projeyi yükleme
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Görev atamalarını toplayın ve görüntüleyin
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Görevin Temellerini Okumak
```csharp
// Yeni bir proje oluştur
var project = new Project();
// Bir görev ekleyin ve bir temel belirleyin
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Görev temel süresini görüntüle
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Görevi Silme
```csharp
// Yeni bir proje oluştur
var project = new Project();
// Görev ekle
var task = project.RootTask.Children.Add("Task");
//Silme işleminden önceki ve sonraki görev sayısını görüntüleme
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Görevi sil
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Çözüm
Aspose.Tasks for .NET'te görevleri yönetmek, sağlanan örneklerle sorunsuz bir süreçtir. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu teknikleri birleştirmek proje yönetimi becerilerinizi geliştirecektir.
## Sıkça Sorulan Sorular
### S: Aspose.Tasks tüm .NET çerçeveleriyle uyumlu mudur?
C: Evet, Aspose.Tasks çeşitli .NET çerçevelerini destekleyerek geliştirme ortamınızla uyumluluğu garanti eder.
### S: Aspose.Tasks için nasıl geçici lisans alabilirim?
 C: 30 günlük geçici lisansı şu adresten alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Tasks'ta bölünmüş görevlerle çalışırken herhangi bir sınırlama var mı?
 C: Bölünmüş görevler güçlü bir özelliktir ve ayrıntılı belgeler bulunabilir[Burada](https://reference.aspose.com/tasks/net/).
### S: Görev özelliklerini örneklerde gösterilenin ötesinde özelleştirebilir miyim?
C: Kesinlikle! Aspose.Tasks, görev özellikleri için kapsamlı özelleştirme seçenekleri sunar. Daha fazla ayrıntı için belgelere bakın.
### S: Aspose.Tasks için nasıl destek alabilirim?
 C: Ziyaret edin[Aspose.Tasks Forumu](https://forum.aspose.com/c/tasks/15) topluluk desteği ve tartışmalar için.