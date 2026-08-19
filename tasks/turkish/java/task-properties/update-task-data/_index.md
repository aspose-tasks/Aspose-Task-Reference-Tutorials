---
date: 2026-03-03
description: Asposetasks Java kullanarak görev verilerini MPP formatına nasıl güncelleyeceğinizi
  öğrenin. Verimli proje yönetimi için adım adım rehberimizi izleyin.
linktitle: Update Task Data to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Görev Verilerini MPP Formatına Güncelle
url: /tr/java/task-properties/update-task-data/
weight: 35
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Görev Verilerini MPP Formatına Güncelleme

## Introduction
Adım adım **Aspose.Tasks for Java kullanarak görev verilerini MPP formatına güncelleme** rehberimize hoş geldiniz. Bu öğreticide *aspose tasks java* ile proje dosyalarını programlı olarak nasıl manipüle edeceğinizi, bir özet görev oluşturmayı ve bir XML projesini MPP dosyasına dönüştürmeyi öğreneceksiniz. Sonunda proje görevlerini verimli bir şekilde yönetebilecek ve çözümü Java uygulamalarınıza entegre edebileceksiniz.

## Quick Answers
- **Bu öğretici neyi kapsıyor?** Aspose.Tasks for Java ile görev verilerini güncelleme ve projeyi MPP olarak kaydetme.  
- **Lisans gerekli mi?** Üretim kullanımı için geçici veya tam lisans gereklidir; ücretsiz deneme sürümü mevcuttur.  
- **Hangi IDE en iyisi?** Herhangi bir Java IDE'si (IntelliJ IDEA, Eclipse, VS Code) çalışır.  
- **XML'i MPP'ye dönüştürebilir miyim?** Evet – örnek bir XML projesi yükler ve MPP olarak kaydeder.  
- **Kaç görev oluşturuluyor?** Örnek bir ana görev, bir özet görev ve on ek görev oluşturur.

## What is Aspose.Tasks for Java?
Aspose.Tasks for Java, geliştiricilerin Microsoft Project dosyalarını (MPP, XML ve daha fazlası) Microsoft Project yüklü olmadan okuyup, yazıp ve değiştirmesine olanak tanıyan güçlü bir API'dir. Görev oluşturma, kısıtlama yönetimi ve dosya formatı dönüşümü gibi tam proje‑seviyesi manipülasyonları destekler.

## Why use Aspose.Tasks Java for project management?
- **Full control** görev özellikleri üzerinde tam kontrol (başlangıç tarihi, süre, kısıtlamalar vb.).  
- **Seamless conversion** XML ve MPP arasında sorunsuz dönüşüm, mevcut proje veri akışlarıyla entegrasyon sağlar.  
- **No COM interop** – saf Java, çapraz‑platform ortamlar için idealdir.  
- **High performance** büyük proje dosyaları için yüksek performans, kurumsal ölçekli çözümler için uygundur.

## Prerequisites
Öğreticiye başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
- Aspose.Tasks for Java: Aspose.Tasks kütüphanesinin yüklü olduğundan emin olun. İndirmek için [release page](https://releases.aspose.com/tasks/java/) adresini ziyaret edebilirsiniz.
- Java Development Kit (JDK): Sisteminizde Java kurulu olmalı.
- Integrated Development Environment (IDE): Java geliştirme için tercih ettiğiniz bir IDE kullanın.

## Import Packages
Java projenize gerekli paketleri içe aktarmakla başlayın. Aşağıdaki snippet paketlerin nasıl içe aktarılacağını gösterir:

```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```

## How to Create a Summary Task
Özet görev, ilgili alt görevleri gruplar ve iş paketlerinin yüksek‑seviye görünümünü sağlar. Aşağıdaki kodda bir özet görev oluşturup ilk görevi çocuğu olarak ekliyoruz.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Continue with the rest of the code)
```

## How to Set Start Date for a Task
Başlangıç tarihinin ayarlanması doğru zamanlama için kritiktir. Örnek, proje başlangıcını tanımlamak için bir `Calendar` örneği kullanır ve bunu göreve atar.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Continue with the rest of the code)
```

## How to Convert XML to MPP
API, bir XML proje dosyasını okuyabilir ve doğrudan MPP dosyası olarak kaydedebilir; bu sayede eski formatlardan kolayca geçiş yapılır.

```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Continue with the rest of the code)
```

## How to Set Deadline and Add Task Notes
Son tarihler görevlerin zamanında tamamlanmasını sağlar, notlar ise ekip üyeleri için bağlam sunar.

```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Continue with the rest of the code)
```

## How to Configure Task Constraints and Update Task Duration
*Finish No Later Than* gibi kısıtlamalar zamanlayıcıyı yönlendirir. Süre formatını tahmini günleri yansıtacak şekilde de değiştirebilirsiniz.

```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Continue with the rest of the code)
```

## How to Create Additional Tasks (Managing Project Tasks)
Aşağıdaki döngü, toplu veri içe aktarmada sıkça ihtiyaç duyulan birden fazla görevi programlı olarak oluşturmayı gösterir.

```java
// Create 10 new tasks
for (int i = 0; i < 10; i++) {
    //... (Continue with the rest of the code)
}
//... (Continue with the rest of the code)
```

## How to Save the Project (Export to MPP)
Son olarak, değişiklikleri bir MPP dosyası olarak kaydederek projeyi kalıcı hale getirin.

```java
// Save the Project
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```

Bu adımları izleyerek **aspose tasks java kullanarak görev verilerini MPP formatına güncellediniz**. Artık proje görevlerini yönetmek, özet görevler oluşturmak, başlangıç tarihlerini ayarlamak ve XML projelerini MPP'ye dönüştürmek için sağlam bir temele sahipsiniz.

## Conclusion
Tebrikler! Aspose.Tasks for Java kullanarak görev verilerini MPP formatına güncelleme konusunda kapsamlı bir rehberi tamamladınız. Bu güçlü kütüphane, proje yönetimi görevlerini basitleştirir ve **project tasks** programlı olarak yönetmesi gereken Java geliştiricileri için değerli bir araçtır.

## Frequently Asked Questions

### Q: Where can I find the Aspose.Tasks for Java documentation?
A: The documentation is available [here](https://reference.aspose.com/tasks/java/).

### Q: How can I download Aspose.Tasks for Java?
A: You can download it from the [release page](https://releases.aspose.com/tasks/java/).

### Q: Is there a free trial available?
A: Yes, you can access the free trial [here](https://releases.aspose.com/).

### Q: Where can I get support for Aspose.Tasks for Java?
A: Visit the support forum [here](https://forum.aspose.com/c/tasks/15).

### Q: Do you offer temporary licenses for testing purposes?
A: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Tasks for Java 24.11 (latest)  
**Author:** Aspose