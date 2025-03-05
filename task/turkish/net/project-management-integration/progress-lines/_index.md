---
title: Aspose.Tasks ile MS Project İlerleme Satırlarını Yönetme
linktitle: Aspose.Tasks'ta İlerleme Çizgilerini Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project dosyalarındaki ilerleme çizgilerini nasıl değiştireceğinizi, proje görselleştirmesini ve yönetimini nasıl geliştireceğinizi öğrenin.
type: docs
weight: 15
url: /tr/net/project-management-integration/progress-lines/
---
## giriiş
Microsoft Project (MS Project), kullanıcıların projelerinin çeşitli yönlerini takip etmelerine olanak tanıyan güçlü bir proje yönetimi aracıdır. MS Project'in önemli özelliklerinden biri, paydaşların projenin durumunu ve gidişatını anlamalarına yardımcı olan ilerleme çizgilerini görselleştirme yeteneğidir. Bu eğitimde, .NET için Aspose.Tasks kütüphanesini kullanarak MS Project'te ilerleme satırlarının nasıl ele alınacağını keşfedeceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Visual Studio: Visual Studio'yu veya tercih edilen herhangi bir .NET geliştirme ortamını yükleyin.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET'i şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
3. Temel C# Bilgisi: C# programlama diline aşina olmak faydalı olacaktır.

## Ad Alanlarını İçe Aktarma
Başlamak için gerekli ad alanlarını içe aktaralım:
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
Şimdi ilerleme çizgilerini ele alırken her adımı ayrı ayrı ele alalım:
## Adım 1: Proje Dosyasını Yükleyin
```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 Burada MS Project dosyasını yüklüyoruz.`Project2.mpp` ve durum tarihini ayarlayın.
## Adım 2: Gantt Grafiği Görünümünü Tanımlayın
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Daha fazla düzenleme için projenin görünümünü Gantt şeması görünümüne aktardık.
## 3. Adım: İlerleme Çizgilerini Tanımlayın
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
Gantt şeması görünümü için ilerleme satırlarını başlatıyoruz.
## Adım 4: İlerleme Çizgisi Ayarlarını Yapılandırma
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
Burada ilerleme çizgileri için çizgi rengi, desen, yazı tipi vb. gibi çeşitli özellikleri ayarlıyoruz.
## Adım 5: İlerleme Çizgileri Yapılandırmasını Kontrol Edin
```csharp
// Çıkış ilerleme çizgileri ayarları
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// Diğer ayarların çıktısını alın...
```
Doğrulama için yapılandırılmış ilerleme çizgisi ayarlarının çıktısını alıyoruz.
## Adım 6: Proje Dosyasını Kaydedin
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
Son olarak değiştirilen proje dosyasını ilerleme satırlarıyla birlikte kaydediyoruz.

## Çözüm
Bu eğitimde Aspose.Tasks for .NET'i kullanarak MS Project ilerleme satırlarını nasıl yöneteceğimizi öğrendik. Bu adımları izleyerek, MS Project dosyalarınızdaki ilerleme satırlarını programlı olarak etkili bir şekilde özelleştirebilir ve görselleştirebilirsiniz.
## SSS'ler
### S: İlerleme çizgilerinin görünümünü daha da özelleştirebilir miyim?
C: Evet, çizgi rengi, desen ve yazı tipi gibi çeşitli özellikleri gereksinimlerinize uyacak şekilde ayarlayabilirsiniz.
### S: Aspose.Tasks diğer proje yönetimi özelliklerini destekliyor mu?
C: Evet, Aspose.Tasks, görevler, kaynaklar ve takvimler de dahil olmak üzere MS Project dosyalarının çeşitli yönlerini değiştirmek için kapsamlı destek sağlar.
### S: Aspose.Tasks'ı diğer .NET kütüphaneleriyle entegre edebilir miyim?
C: Kesinlikle, Aspose.Tasks diğer .NET kitaplıklarıyla sorunsuz bir şekilde entegre olacak şekilde tasarlanmıştır ve proje yönetimi uygulamalarınızı daha da geliştirmenize olanak tanır.
### S: Aspose.Tasks desteği için bir topluluk forumu var mı?
 C: Evet, Aspose.Tasks forumunda faydalı kaynaklar bulabilir ve yardım alabilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).
### S: Aspose.Tasks değerlendirme amaçlı geçici lisanslar sunuyor mu?
 C: Evet, değerlendirme için geçici bir lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).