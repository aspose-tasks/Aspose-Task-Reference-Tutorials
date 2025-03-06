---
title: Aspose.Tasks for Java ile Primavera'dan MS Project'i okuyun
linktitle: Aspose.Tasks'ta Primavera'dan Projeyi Okuyun
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project dosyalarını Primavera XML'den sorunsuz bir şekilde nasıl okuyacağınızı öğrenin. Proje yönetimi verimliliğinizi artırın.
type: docs
weight: 20
url: /tr/java/project-management/read-primavera/
---
## giriiş
Proje yönetiminde, farklı yazılım platformları arasındaki birlikte çalışabilirlik, kusursuz iş akışı için çok önemlidir. Aspose.Tasks for Java, Microsoft Project dosyalarını Primavera XML'den okumak için güçlü işlevsellik sağlar. Bu eğitim, Aspose.Tasks for Java'yı kullanarak Primavera'dan MS Project dosyalarını okuma sürecinde size rehberlik edecek ve görevlerin Primavera'ya özgü özelliklerini verimli bir şekilde incelemenize olanak tanıyacak.
## Önkoşullar
Devam etmeden önce aşağıdaki önkoşulların yüklendiğinden ve ayarlandığından emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java: Aspose.Tasks for Java'yı şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/java/).

## Paketleri İçe Aktar
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## 1. Adım: Veri Dizinini Ayarlayın
```java
String dataDir = "Your Data Directory";
```
 Değiştirildiğinden emin olun`"Your Data Directory"` veri dizininizin gerçek yolu ile.
## Adım 2: Primavera XML'den Projeyi Okuyun
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Değiştirildiğinden emin olun`"PrimaveraProject.xml"` Primavera XML dosyanızın gerçek adıyla.
## Adım 3: Görevleri Yineleyin ve Primavera'ya Özgü Özellikleri Alın
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Bu kod, projedeki her görev boyunca yinelenerek ilgili Primavera'ya özgü özellikleri yazdırır.

## Çözüm
Bu eğitimde Aspose.Tasks for Java kullanarak MS Project dosyalarını Primavera XML'den nasıl okuyacağınızı öğrendiniz. Bu işlevsellik, proje verilerinin farklı platformlarda kusursuz entegrasyonunu ve analizini sağlayarak genel proje yönetimi verimliliğini artırır.
## SSS'ler
### S: Aspose.Tasks for Java'yı kullanarak görevlerin Primavera'ya özgü özelliklerini değiştirebilir miyim?
C: Evet, Aspose.Tasks for Java, görevlerin Primavera'ya özgü özelliklerini gerektiği gibi değiştirmek için API'ler sağlar.
### S: Aspose.Tasks for Java diğer proje dosyası formatlarını okumayı destekliyor mu?
C: Evet, Aspose.Tasks for Java, MPP, XML ve Primavera XML dahil olmak üzere çeşitli proje dosyası formatlarının okunmasını destekler.
### S: Aspose.Tasks for Java, kurumsal düzeyde proje yönetimi uygulamaları için uygun mudur?
C: Kesinlikle, Aspose.Tasks for Java, güçlü özellikler ve ölçeklenebilirlik sunarak kurumsal düzeydeki proje yönetimi uygulamaları için uygun hale getiriyor.
### S: Aspose.Tasks for Java'yı kullanarak Primavera projelerinden kaynak bilgilerini çıkarabilir miyim?
C: Evet, Aspose.Tasks for Java, Primavera projelerinden görev ayrıntılarının yanı sıra kaynak bilgilerini de çıkarmanıza olanak tanır.
### S: Aspose.Tasks for Java için ek desteği veya belgeleri nerede bulabilirim?
 C: Kapsamlı belgeler bulabilir ve destek için forumlara erişim sağlayabilirsiniz.[Java belgeleri için Aspose.Tasks](https://reference.aspose.com/tasks/java/) sayfa.