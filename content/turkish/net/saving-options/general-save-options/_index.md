---
title: Aspose.Tasks için MS Project Kaydetme Seçeneklerinde Uzmanlaşma
linktitle: Aspose.Tasks için Genel Kaydetme Seçenekleri
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project dosyalarını verimli bir şekilde kaydetmeyi öğrenin. Projeleriniz için çıktı seçeneklerini zahmetsizce özelleştirin.
type: docs
weight: 17
url: /tr/net/saving-options/general-save-options/
---
## giriiş
Aspose.Tasks for .NET, Microsoft Project dosyalarını programlı olarak yönetmek için güçlü özellikler sunar. Bu eğitimde Aspose.Tasks tarafından sağlanan çeşitli seçenekleri kullanarak MS Project dosyalarını kaydetmenin inceliklerini inceleyeceğiz. Özellikle Aspose.Tasks için mevcut olan genel kaydetme seçeneklerine odaklanacağız ve çıktıyı özel gereksinimlerinize göre uyarlamanıza olanak tanıyacağız.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET Kurulumu: Aspose.Tasks for .NET'i aşağıdaki adresten indirip yükleyin:[İndirme: {link](https://releases.aspose.com/tasks/net/).
2. .NET Framework'ün Temel Anlaşılması: .NET programlama kavramlarına aşinalık faydalıdır.

## Ad Alanlarını İçe Aktarma
Koda dalmadan önce gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Adım 1: Proje Dosyasını Yükleyin
Öncelikle Aspose.Tasks'ı kullanarak MS Project dosyasını yüklemeniz gerekir:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## 2. Adım: Kaydetme Seçeneklerini Tanımlayın
 Kaydetme seçeneklerini gereksinimlerinize göre tanımlayın. Bu örnekte, şunu kullanıyoruz,`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## 3. Adım: Görünüm Sütunlarını Özelleştirin
Gantt şeması, kaynak görünümü ve atama görünümü gibi görünüm sütunlarını özelleştirebilirsiniz. Her birine sütunların nasıl ekleneceği aşağıda açıklanmıştır:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Adım 4: Projeyi Seçeneklerle Kaydedin
Son olarak projeyi belirtilen seçeneklerle kaydedin:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Çözüm
Aspose.Tasks for .NET ile genel MS Project kaydetme seçeneklerinde uzmanlaşmak, çıktı formatını projenizin ihtiyaçlarına göre verimli bir şekilde özelleştirmenize olanak sağlar.
## SSS'ler
### S: Aspose.Tasks, MS Project dosyalarının farklı sürümleriyle uyumlu mudur?
C: Evet, Aspose.Tasks, MS Project dosyalarının çeşitli sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.
### S: Satın almadan önce Aspose.Tasks'ı deneyebilir miyim?
 C: Evet, Aspose.Tasks'ı ücretsiz deneme sürümüyle keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks belgelerini nerede bulabilirim?
C: Ayrıntılı belgeler bulunabilir[Burada](https://reference.aspose.com/tasks/net/)Aspose.Tasks özelliklerinin kullanımına ilişkin kapsamlı rehberlik sağlar.
### S: Aspose.Tasks için nasıl geçici lisans alabilirim?
 C: Değerlendirme amacıyla geçici lisanslar mevcuttur.[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Tasks ile ilgili sorgular için nereden destek alabilirim?
 C: Aspose.Tasks topluluk forumuna katılabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15) uzmanlardan ve diğer geliştiricilerden yardım almak.