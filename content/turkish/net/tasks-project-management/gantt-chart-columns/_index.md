---
title: Aspose.Tasks ile Gantt Grafiği Sütunlarını Özelleştirin
linktitle: Aspose.Tasks'taki Gantt Grafiği Sütunları
second_title: Aspose.Tasks .NET API'si
description: Belirli görev bilgilerini verimli bir şekilde görüntülemek için Aspose.Tasks for .NET'te Gantt şeması sütunlarını nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 21
url: /tr/net/tasks-project-management/gantt-chart-columns/
---
## giriiş
Gantt şemaları, proje yönetiminde görevlerin, zaman çizelgelerinin ve kaynakların görsel bir temsilini sağlayan temel bir araçtır. Aspose.Tasks for .NET, belirli görev bilgilerini görüntülemek için sütunları özelleştirmek de dahil olmak üzere, Gantt grafiklerini yönetmek için güçlü yetenekler sunar. Bu eğitimde Aspose.Tasks for .NET'i kullanarak Gantt şeması sütunlarıyla nasıl çalışılacağını inceleyeceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Kurulum: Aspose.Tasks for .NET sisteminizde kuruludur. Değilse, buradan indirip yükleyin.[Burada](https://releases.aspose.com/tasks/net/).
2. .NET Geliştirme Ortamı: C# ve .NET çerçevesi hakkında çalışma bilgisi.
3. Örnek Proje Dosyası: Örnek bir Microsoft Project dosyasına sahip olun (`.mpp`) deneme yapmak için kullanışlıdır. Eğer elinizde yoksa MS Project'te basit bir proje oluşturup kaydedebilirsiniz.

## Ad Alanlarını İçe Aktar
Öncelikle Aspose.Tasks for .NET ile çalışmak için gerekli ad alanlarını içe aktarmanız gerekir:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Adım 1: Proje Dosyasını Yükleyin
 Proje dosyasını kullanarak yükleyin.`Project` Aspose.Tasks tarafından sağlanan sınıf:
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Adım 2: Gantt Grafiği Sütunlarını Tanımlayın
Gantt grafiğinde görüntülemek istediğiniz sütunları tanımlayın. Yerleşik alanları belirtebilir veya özel alanlar oluşturabilirsiniz:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## Adım 3: Sütunlar Üzerinde Yineleme Yapın
Özelliklerine erişmek ve bilgileri görüntülemek için tanımlanmış sütunları yineleyin:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## Adım 4: Gantt Grafiği'ni CSV'ye kaydedin
Gantt grafiğini tanımlanmış sütunlarla birlikte bir CSV dosyasına kaydedin:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Bu adımları izleyerek Aspose.Tasks for .NET'te Gantt şeması sütunlarıyla etkili bir şekilde çalışabilir, görev bilgilerini gerektiği gibi özelleştirip görüntülemenize olanak tanıyabilirsiniz.

## Çözüm
Aspose.Tasks for .NET'te Gantt şeması sütunlarının manipülasyonunda ustalaşmak, proje yönetimi görsellerini özel ihtiyaçlarınıza göre uyarlamak için sonsuz olasılıkların kapısını açar. Bu öğreticide özetlenen adımları izleyerek görev bilgilerini verimli bir şekilde yönetebilir ve proje netliğini ve organizasyonunu geliştirebilirsiniz.
## SSS'ler
### S: Aspose.Tasks for .NET'te özel sütunlar oluşturabilir miyim?
C: Evet, proje gereksinimlerinize göre belirli görev niteliklerini görüntülemek için özel sütunlar tanımlayabilirsiniz.
### S: Aspose.Tasks for .NET, Microsoft Project dosyalarının tüm sürümleriyle uyumlu mudur?
C: Aspose.Tasks for .NET, Microsoft Project dosyalarının çeşitli sürümlerini destekleyerek farklı proje ortamları arasında uyumluluk sağlar.
### S: Aspose.Tasks for .NET ile karmaşık proje yapılarını nasıl halledebilirim?
C: Aspose.Tasks for .NET, karmaşık proje yapılarını yönetmek için esneklik ve ölçeklenebilirlik sunan kapsamlı API'ler ve özellikler sağlar.
### S: Gantt grafiğine ekleyebileceğim sütun sayısında herhangi bir sınırlama var mı?
C: Aspose.Tasks for .NET, kapsamlı özelleştirme seçenekleri sunarak, Gantt grafiklerine sınırlama olmaksızın önemli sayıda sütun eklemenizi sağlar.
### S: Aspose.Tasks for .NET için ek destek ve kaynakları nerede bulabilirim?
C: Kapsamlı kaynaklara ve yardıma erişmek için Aspose.Tasks for .NET tarafından sağlanan belgeleri, topluluk forumlarını ve destek kanallarını keşfedebilirsiniz.