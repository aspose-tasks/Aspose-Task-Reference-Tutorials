---
date: 2026-06-25
description: Aspose.Tasks for Java kullanarak görev ekleme ve MPP dosyalarını güncelleme
  yöntemlerini öğrenin; Java proje yönetimi kütüphanesi, Microsoft Project görev dosyaları
  oluşturmanıza ve projeyi MPP olarak kaydetmenize olanak tanır.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Aspose.Tasks'te Görev Ekleme ve MPP Dosyasını Güncelleme
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Görev Ekleme ve MPP Dosyasını Güncelleme
url: /tr/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Görev Ekleme ve MPP Dosyasını Güncelleme

## Giriş
Bu öğreticide mevcut bir Microsoft Project (MPP) dosyasına **görev ekleme** ve ardından güncellenmiş takvimi Aspose.Tasks for Java kullanarak kaydetmeyi öğreneceksiniz, lider **java proje yönetimi kütüphanesi**. İster özel bir zamanlayıcı oluşturuyor, toplu güncellemeleri otomatikleştiriyor ya da proje verilerini daha büyük bir sisteme entegre ediyor olun, aşağıdaki adım‑adım kılavuz, bir projeyi nasıl yükleyeceğinizi, yeni bir görev ekleyeceğinizi, tarihlerini ayarlayacağınızı ve sonucu yeni bir MPP belgesi olarak nasıl kalıcı hale getireceğinizi tam olarak gösterir.

## Hızlı Yanıtlar
- **Bu bağlamda “görev ekleme” ne anlama geliyor?** Programatik olarak mevcut bir MPP dosyası içinde yeni bir iş öğesi oluşturmak anlamına gelir.  
- **İşlemi hangi kütüphane gerçekleştiriyor?** Aspose.Tasks for Java, sağlam bir java proje yönetimi kütüphanesidir.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Sonucu MPP olarak kaydedebilir miyim?** Evet—`project.save(..., SaveFileFormat.Mpp)` kullanarak **projeyi mpp olarak kaydedin**.  
- **Hangi Java sürümü gerekiyor?** Java 8 veya üzeri.

## “görev ekleme” bir MPP dosyasında ne demektir?
Görev eklemek, proje hiyerarşisine yeni bir iş öğesi eklemek, başlangıç/bitiş tarihlerini tanımlamak ve değişikliği MPP dosyasına geri kaydetmek anlamına gelir. Aspose.Tasks, düşük‑seviye dosya formatı ayrıntılarını soyutlayarak iş mantığınıza odaklanmanızı sağlar ve kaynak atamaları, takvimler ve bağımlılık hesaplamalarını otomatik olarak yönetir. Ayrıca ilgili atamaları günceller ve proje takvimini yeniden hesaplayarak bağımlı görevler arasında tutarlılığı korur.

## Neden Aspose.Tasks for Java kullanılmalı?
- **Tam uyumluluk**: Microsoft Project 2007‑2021 boyunca %100 özellik desteği (150'den fazla görev türü ve 200 kaynak alanı).  
- **Sıfır bağımlılık**: COM, Office veya yerel kütüphaneler gerekmez—saf Java API, JRE'nin çalıştığı her yerde çalışır.  
- **Zengin özellik seti**: Görev bağlama, kaynak tahsisi, özel alanlar ve yerleşik raporlama içerir.  
- **Yüksek performans**: 10.000'e kadar görevi 200 MB'den az RAM kullanarak işler, sunucu‑tarafı otomasyon için idealdir.

## Önkoşullar
1. **Java Geliştirme Ortamı** – JDK 8+ yüklü ve yapılandırılmış.  
2. **Aspose.Tasks for Java** – [indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin.  
3. **Temel Java bilgisi** – Sınıflar, nesneler ve tarih işleme konularına aşina olun.  

## Paketleri İçe Aktarma
İhtiyacınız olacak sınıfları ilk olarak içe aktarın. Bu, proje manipülasyonu, görev özellikleri ve tarih işleme erişimi sağlar.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` bellekte yüklü bir Microsoft Project dosyasını temsil eder. `SaveFileFormat` MPP veya PDF gibi kaydedebileceğiniz formatları listeler. `Task` proje hiyerarşisindeki bireysel bir iş öğesini modeller. `Tsk` görev alanları için değer ayarlarken veya alırken kullanılan sabitleri sağlar. `Calendar` takvim tanımlamaları için tarih‑zaman yardımcıları sunar.

## Adım 1: Veri Dizinini Tanımlama
```java
String dataDir = "Your Data Directory";
```  
`"Your Data Directory"` ifadesini, kaynak MPP dosyanızın bulunduğu mutlak yol ile değiştirin.

## Adım 2: Mevcut Projeyi Okuma
`Project` sınıfı, Aspose.Tasks'ın bellekte bir Microsoft Project dosyasını temsil eden çekirdek nesnesidir.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
Yapıcı, **SampleMSP2010.mpp** dosyasını yükleyerek tam manipüle edilebilir bir nesne modeli oluşturur.

## Adım 3: Yeni Bir Görev Oluşturma (görev ekleme)
`Task` sınıfı, proje hiyerarşisi içinde bireysel bir iş öğesini temsil eder.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Bu satır, kök göreve *Task1* adlı bir alt görev ekleyerek **görevi mpp içinde oluşturur**.

## Adım 4: Başlangıç ve Bitiş Tarihlerini Ayarlama
`Calendar` sınıfı tarih‑zaman yardımcıları sağlar; aylar sıfır‑tabanlıdır (ör. `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Burada yeni eklenen görevin takvimini tanımlıyoruz. Tarihleri projenizin zaman çizelgesine göre ayarlayın.

## Adım 5: Projeyi Kaydetme (projeyi mpp olarak kaydet)
`SaveFileFormat.Mpp`, Aspose.Tasks'ın dosyayı yerel Microsoft Project formatında geri yazmasını söyler.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
Güncellenen proje, artık yeni görevi içeriyor ve **AfterLinking.mpp** olarak kalıcı hale getiriliyor.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Dosya bulunamadı** | `dataDir`'in bir yol ayırıcı (`/` veya `\\`) ile bittiğini ve dosya adının doğru olduğunu doğrulayın. |
| **Yanlış tarih** | `Calendar` aylarının sıfır‑tabanlı olduğunu unutmayın; Temmuz için `Calendar.JULY` doğrudur. |
| **Lisans istisnası** | Değerlendirme filigranlarından kaçınmak için herhangi bir API çağrısı yapmadan önce geçerli bir Aspose.Tasks lisansı yükleyin. |

## Sık Sorulan Sorular
**S: Aynı anda birden fazla görev nasıl eklenir?**  
C: Görev adları koleksiyonunu döngüye alıp “görev oluştur” bloğunu döngü içinde tekrarlayın.

**S: Yeni görev için özel alanlar ayarlanabilir mi?**  
C: Evet—`task.set(Tsk.CUSTOM_FIELD_x, value)` kullanın; *x* alan indeksidir.

**S: Mevcut bir görev şablon olarak kopyalanabilir mi?**  
C: Kaynak görevi klonlayın (`Task cloned = sourceTask.clone();`) ve ardından istediğiniz ebeveyne ekleyin.

**S: Yeni bir görev eklemek yerine mevcut bir görevi güncellemem gerekirse ne yapmalıyım?**  
C: Görevi ID ile alın (`Task existing = project.getRootTask().getChildren().getById(id);`) ve özelliklerini değiştirin.

**S: Aspose.Tasks PDF veya PNG gibi diğer formatlarda kaydetmeyi destekliyor mu?**  
C: Evet—`project.save("output.pdf", SaveFileFormat.Pdf);` veya görsel temsiller için `SaveFileFormat.Png` kullanın.

---

**Son Güncelleme:** 2026-06-25  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Öğreticiler

- [How to Create MPP File – Create & Save Empty Project in MPP Format with Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [How to Create Project – Set New Task Attributes with Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Create Task List Java – MS Project Baseline using Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}