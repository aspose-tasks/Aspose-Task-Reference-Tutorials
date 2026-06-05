---
date: 2026-01-23
description: Aspose.Tasks for Java kullanarak çapraz proje görevlerini nasıl tanımlayacağınızı
  öğrenin. Sorunsuz entegrasyonu ve verimli yönetimi keşfedin.
linktitle: Identify Cross Project Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Çapraz Proje Görevlerini Belirle
url: /tr/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Çapraz Proje Görevlerini Tanımlama

## Introduction
Aspose.Tasks for Java ile çapraz proje görevlerini verimli bir şekilde **nasıl tanımlayacağınızı** anlatan kapsamlı eğitimimize hoş geldiniz. İster deneyimli bir geliştirici olun, ister yeni başlıyor olun, bu kılavuz Java uygulamalarınıza bu özelliği entegre etmek için gereken tüm adımları size gösterecek.

## Quick Answers
- **“Çapraz proje görevlerini tanımlamak” ne anlama geliyor?** Başka bir proje dosyasındaki görevlere başvuran veya onlara bağımlı olan görevleri bulmak demektir.  
- **Görev kimliğini (ID) hangi yöntem yazdırır?** Görev kimliğini yazdırmak için `externalTask.get(Tsk.ID)` kullanın.  
- **Belge dizinini nasıl ayarlarım?** Klasör yolunu bir `String` değişkenine (ör. `dataDir`) atayın.  
- **Bir görevi UID ile hangi özellik getirir?** `getChildren().getByUid(yourUid)` çağırın.  
- **Üretim ortamında lisansa ihtiyacım var mı?** Evet, ticari dağıtımlar için geçerli bir Aspose.Tasks lisansı gereklidir.

## What is “identify cross project tasks”?
Çapraz‑proje görevlerini tanımlamak, birden fazla Microsoft Project dosyasına yayılmış görevler arasındaki ilişkileri izlemeyi sağlar. Bu, görevlerin paylaşıldığı veya dış takvimlere bağımlı olduğu büyük ölçekli proje portföyleri için hayati öneme sahiptir.

## Why use Aspose.Tasks for Java?
- **Microsoft Project gerekmez** – .mpp dosyalarıyla doğrudan Java içinde çalışın.  
- **Tam API erişimi** – ID'leri, dış ID'leri, UID'leri ve daha fazlasını alın.  
- **Çapraz‑platform** – herhangi bir JVM uyumlu ortamda çalıştırın.

## Prerequisites
İlerlemeye başlamadan önce şunların olduğundan emin olun:

- Java programlama temelleri.  
- Aspose.Tasks for Java yüklü. **[Buradan](https://releases.aspose.com/tasks/java/)** indirebilirsiniz.

## Import Packages
Projeyi manipüle etmeyi sağlayan temel Aspose.Tasks sınıflarını içe aktarın.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Step 1: Set the Document Directory
.mpp dosyalarınızın bulunduğu klasörü tanımlayın. Bu adım, ikincil anahtar kelime **set document directory** ile uyumludur.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Step 2: Load External Project
Harici proje dosyasını (ör. *External.mpp*) yükleyin, böylece görevlerini inceleyebilirsiniz.

```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Step 3: Retrieve External Task by UID
Görevin **UID** (Unique Identifier) değerini kullanarak ilgilendiğiniz belirli görevi alın. Bu, ikincil anahtar kelime **get task uid** ile eşleşir.

```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Step 4: Print Task ID (Primary Use‑Case)
Artık görev nesnesine sahip olduğunuzda, iç kimliğini (ID) yazdırın. Bu, ikincil anahtar kelime **print task id** örneğidir.

```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Step 5: Print Original (External) Task ID
Görevin orijinal proje dosyasındaki kimliğini de alabilirsiniz.

```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Yukarıdaki adımları, projeler arasında izlemek istediğiniz ek görevler için tekrarlayın.

## Common Issues & Tips
- **Yol hataları** – `dataDir`'in uygun dosya ayırıcıyla (`/` veya `\\`) bittiğinden emin olun.  
- **UID bulunamadı** – UID'nin harici projede mevcut olduğunu doğrulayın; kullanılabilir UID'leri listelemek için `externalProject.getRootTask().getChildren().size()` kullanın.  
- **Lisans istisnaları** – Eksik veya geçersiz bir lisans çalışma zamanında lisans istisnası fırlatır.

## Frequently Asked Questions

**S: Aspose.Tasks'i başka programlama dilleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks Java, .NET ve daha fazlası dahil olmak üzere birden çok dili destekler.

**S: Aspose.Tasks for Java için ayrıntılı belgeleri nereden bulabilirim?**  
C: Belgeler **[burada](https://reference.aspose.com/tasks/java/)** mevcuttur.

**S: Aspose.Tasks for Java için ücretsiz deneme sürümü var mı?**  
C: Evet, ücretsiz deneme **[buradan](https://releases.aspose.com/)** alınabilir.

**S: Aspose.Tasks için geçici lisans nasıl alınır?**  
C: Geçici lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** temin edebilirsiniz.

**S: Yardıma ihtiyacım var ya da özel sorularım var; ne yapmalıyım?**  
C: Aspose.Tasks destek forumunu **[burada](https://forum.aspose.com/c/tasks/15)** ziyaret edin.

---

**Last Updated:** 2026-01-23  
**Tested With:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}