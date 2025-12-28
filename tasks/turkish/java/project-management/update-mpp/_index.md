---
date: 2025-12-28
description: Java için Aspose.Tasks, bir Java proje yönetimi kütüphanesini kullanarak
  görev eklemeyi ve MPP dosyalarını güncellemeyi öğrenin. MPP'de görev oluşturmak
  ve projeyi MPP olarak kaydetmek için adım adım rehberimizi izleyin.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Görev Ekleme ve MPP Dosyasını Güncelleme
url: /tr/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Görev Ekleme ve MPP Dosyasını Güncelleme

## Introduction
Bu öğreticide **görev ekleme** ve Aspose.Tasks for Java kullanarak bir MPP dosyasını güncelleme işlemini göstereceğiz; bu, önde gelen **java proje yönetimi kütüphanesidir**. Özel bir zamanlayıcı oluşturuyor ya da mevcut proje planlarını programlı olarak değiştirmek istiyor olun, bu rehber dosyayı yüklemeden değişiklikleri yeni bir MPP belgesi olarak kaydetmeye kadar tüm adımları size anlatır.

## Quick Answers
- **Bu bağlamda “how to add task” ne anlama geliyor?** Mevcut bir Microsoft Project (MPP) dosyası içinde programlı olarak yeni bir görev oluşturmayı ifade eder.  
- **İşlemi hangi kütüphane gerçekleştiriyor?** Aspose.Tasks for Java, sağlam bir java proje yönetimi kütüphanesidir.  
- **Lisans gerekir mi?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim ortamı için ticari lisans gereklidir.  
- **Sonucu MPP olarak kaydedebilir miyim?** Evet—`project.save(..., SaveFileFormat.Mpp)` kullanarak **projeyi mpp olarak kaydedin**.  
- **Hangi Java sürümü gerekiyor?** Java 8 veya üzeri.

## What is “how to add task” in an MPP file?
Görev eklemek, proje hiyerarşisine yeni bir iş öğesi eklemek, başlangıç/bitiş tarihlerini tanımlamak ve değişikliği MPP dosyasına geri yazmak anlamına gelir. Aspose.Tasks, düşük seviyeli dosya formatı detaylarını soyutlayarak iş mantığınıza odaklanmanızı sağlar.

## Why use Aspose.Tasks for Java?
- **Microsoft Project 2007‑2021 dosyalarıyla tam uyumluluk**.  
- **COM veya Office kurulumu gerekmez**—tamamen Java API'si.  
- **Zengin özellik seti**: görev bağlama, kaynak tahsisi, özel alanlar ve daha fazlası.  
- **Büyük proje dosyaları için yüksek performans**, sunucu‑tarafı otomasyon için idealdir.

## Prerequisites
1. **Java Geliştirme Ortamı** – JDK 8+ yüklü ve yapılandırılmış.  
2. **Aspose.Tasks for Java** – [indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin.  
3. **Temel Java bilgisi** – Sınıflar, nesneler ve tarih işleme konularına aşina olun.  

## Import Packages
First, import the classes you’ll need. This gives you access to project manipulation, task properties, and date handling.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Define Data Directory
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` ifadesini, kaynak MPP dosyanızın bulunduğu mutlak yol ile değiştirin.

## Step 2: Read Existing Project
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
`Project` yapıcısı **SampleMSP2010.mpp** dosyasını yükler ve üzerinde çalışabileceğiniz bir nesne modeli sunar.

## Step 3: Create a New Task (how to add task)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Bu satır, kök göreve *Task1* adlı bir alt görev ekleyerek **görevi mpp içinde oluşturur**.

## Step 4: Set Start and Finish Dates
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Burada yeni eklenen görevin takvimini tanımlıyoruz. Tarihleri proje zaman çizelgenize uygun şekilde ayarlayın.

## Step 5: Save the Project (save project as mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
Güncellenen proje, yeni görevle birlikte **AfterLinking.mpp** olarak kalıcı hale getirilir.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **File not found** | `dataDir` sonunun bir yol ayırıcı (`/` veya `\\`) içerdiğini ve dosya adının doğru olduğunu doğrulayın. |
| **Incorrect dates** | `Calendar` aylarının sıfır‑tabanlı olduğunu unutmayın; Temmuz için `Calendar.JULY` doğrudur. |
| **License exception** | Değerlendirme su işaretlerini önlemek için herhangi bir API çağrısından önce geçerli bir Aspose.Tasks lisansı yükleyin. |

## FAQ's
### Q: Aspose.Tasks for Java karmaşık proje yapılarıyla başa çıkabilir mi?
A: Evet, Aspose.Tasks for Java, karmaşık proje yapılarıyla verimli bir şekilde çalışmak için güçlü özellikler sunar.  
### Q: Aspose.Tasks for Java için ücretsiz bir deneme sürümü mevcut mu?
A: Evet, [web sitesinden](https://releases.aspose.com/) ücretsiz bir deneme sürümü indirebilirsiniz.  
### Q: Aspose.Tasks for Java farklı Microsoft Project dosya sürümlerini destekliyor mu?
A: Kesinlikle, Aspose.Tasks for Java MPP, MPT ve XML formatları dahil olmak üzere çeşitli Microsoft Project dosya sürümlerini destekler.  
### Q: Aspose.Tasks for Java için geçici lisans alabilir miyim?
A: Evet, test amaçlı geçici lisanslar mevcuttur. Bunları [geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.  
### Q: Aspose.Tasks for Java ile ilgili yardım veya destek nasıl alınır?
A: Herhangi bir sorunuz veya ihtiyacınız için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.

## Frequently Asked Questions
**Q: Birden fazla görevi aynı anda nasıl eklerim?**  
A: Görev adları koleksiyonunu döngüye alıp “görev oluştur” bloğunu döngü içinde tekrarlayın.

**Q: Yeni görev için özel alanlar ayarlayabilir miyim?**  
A: Evet—`task.set(Tsk.CUSTOM_FIELD_x, value)` kullanın; *x* alan indeksidir.

**Q: Mevcut bir görevi şablon olarak kopyalamak mümkün mü?**  
A: Kaynak görevi (`Task cloned = sourceTask.clone();`) klonlayın ve ardından istediğiniz ebeveyne ekleyin.

**Q: Yeni bir görev eklemek yerine mevcut bir görevi güncellemem gerekirse ne yapmalıyım?**  
A: Görevi ID ile alın (`Task existing = project.getRootTask().getChildren().getById(id);`) ve özelliklerini değiştirin.

**Q: Aspose.Tasks PDF veya PNG gibi diğer formatlarda kaydetmeyi destekliyor mu?**  
A: Evet—`project.save("output.pdf", SaveFileFormat.Pdf);` veya görsel temsiller için `SaveFileFormat.Png` kullanın.

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}