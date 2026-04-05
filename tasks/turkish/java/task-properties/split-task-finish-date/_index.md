---
date: 2026-02-26
description: Aspose.Tasks for Java kullanarak görev bitiş tarihlerini nasıl bölüp
  proje zaman çizelgelerini yöneteceğinizi öğrenin. Bu rehber, görevi verimli bir
  şekilde nasıl böleceğinizi gösterir.
linktitle: Split Task Finish Date in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Proje Zaman Çizelgelerini Yönet – Aspose.Tasks'te Bölünmüş Görev Bitiş Tarihi
url: /tr/java/task-properties/split-task-finish-date/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Görev Bitiş Tarihini Bölme

## Introduction
Projelerin zaman çizelgelerini etkili bir şekilde **manage project timelines** yönetmek, başarılı proje teslimatının temel taşıdır. Bir görevin süresi değiştiğinde, takvimin doğru kalması için bitiş tarihinin yeniden hesaplanması gerekir. Bu öğreticide, Aspose.Tasks for Java ile **how to split task** görev bitiş tarihlerini nasıl böleceğinizi göstererek projenizin zaman çizelgesi üzerinde kesin kontrol sağlayacağız.

## Quick Answers
- **splitting a task finish date** ne sağlar?  
  Herhangi bir sürenin bitiş tarihini hesaplamanızı sağlar, böylece takvimleri anında ayarlayabilirsiniz.  
- **Hangi kütüphane gereklidir?**  
  Aspose.Tasks for Java (official site’den indirilebilir).  
- **Geliştirme için lisansa ihtiyacım var mı?**  
  Geçici bir lisans test için çalışır; üretim için tam lisans gereklidir.  
- **Bunu herhangi bir proje takvimiyle kullanabilir miyim?**  
  Evet, API proje takvimini kullanarak çalışma günlerini ve tatilleri dikkate alır.  
- **Kaç satır kod gerekir?**  
  Herhangi bir süre için bitiş tarihini elde etmek için on satırdan az.

## What is “manage project timelines” in the context of Aspose.Tasks?
Projelerin zaman çizelgelerini yönetmek, her görevin başlangıç ve bitiş tarihlerini takvimler, kaynaklar ve görev bağımlılıkları dikkate alarak genel takvimle senkronize tutmak anlamına gelir. Doğru bitiş‑tarihi hesaplamaları, gerçekçi projeksiyonlar ve paydaş güveni için hayati öneme sahiptir.

## Why split a task’s finish date?
- **Esneklik:** Farklı çalışma saatleri tahsislerinin teslimatı nasıl etkilediğini hızlıca görebilirsiniz.  
- **Risk değerlendirmesi:** Orijinal planı değiştirmeden “what‑if” senaryolarını değerlendirin.  
- **Kaynak planlaması:** Görev sürelerini ekip kapasitesi ve takvim kısıtlamalarıyla hizalayın.

## Prerequisites
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:
- Java programlama temelleri.  
- Aspose.Tasks for Java kütüphanesi yüklü. Bunu [here](https://releases.aspose.com/tasks/java/) adresinden indirebilirsiniz.  
- Bir Java geliştirme ortamı kurulu.

## Import Packages
Java projenize gerekli paketleri ekleyerek başlayın:
```java
import com.aspose.tasks.*;
```

## Step 1: Find a Split Task
Projede bölmek istediğiniz görevi bulun:
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read project
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```

## Step 2: Find the Project Calendar
Doğru tarih hesaplamaları için proje takvimini alın:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```

## Step 3: Calculate Task Finish Date with Different Durations
Şimdi, görevin bitiş tarihini çeşitli süreler için hesaplayın.

### Step 3.1: Duration of 8 Hours
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```

*Yukarıdaki kodu farklı süreler için tekrarlayın, saatleri buna göre ayarlayarak her değişikliğin bitiş tarihine nasıl etki ettiğini görün.*

## Common Issues and Solutions
- **Yanlış takvim referansı:** Yeni bir takvim oluşturmak yerine proje takvimini (`project.get(Prj.CALENDAR)`) aldığınızdan emin olun.  
- **Yanlış görev UID'si:** UID, gerçekten var olan bir göreve eşleşmelidir; aksi takdirde `getByUid` `null` döner ve `NullPointerException` oluşur.  
- **Saat dilimi uyumsuzlukları:** API takvimin saat dilimiyle çalışır; sonuçlar yanlış görünüyorsa sisteminizin varsayılan saat dilimini kontrol edin.

## Conclusion
Görev bitiş tarihlerini bölerek **manage project timelines** sanatını ustalaşmak, etkili proje yönetimi için hayati öneme sahiptir. Aspose.Tasks for Java bu süreci basitleştirir, takvimlerinizi zahmetsizce düzenlemenizi sağlar.

## FAQs
### Q1: Aspose.Tasks for Java'ı nasıl indirebilirim?
A1: Bunu [here](https://releases.aspose.com/tasks/java/) adresinden indirebilirsiniz.

### Q2: Aspose.Tasks için belgeleri nerede bulabilirim?
A2: Belgeleri [here](https://reference.aspose.com/tasks/java/) adresinden inceleyin.

### Q3: Aspose.Tasks için geçici bir lisans nasıl alabilirim?
A3: Geçici lisansı [here](https://purchase.aspose.com/temporary-license/) adresinden edinin.

### Q4: Aspose.Tasks için destek nereden alabilirim?
A4: Destek forumunu [here](https://forum.aspose.com/c/tasks/15) adresinden ziyaret edin.

### Q5: Aspose.Tasks'ı satın alabilir miyim?
A5: Evet, [here](https://purchase.aspose.com/buy) adresinden satın alabilirsiniz.

## Additional Frequently Asked Questions

**Q: Bu tekniği özel bir takvimle kullanabilir miyim?**  
A: Kesinlikle. `project.get(Prj.CALENDAR)` ifadesini kendi özel `Calendar` örneğinizle değiştirmeniz yeterlidir.

**Q: Metod çalışma gün olmayan günleri dikkate alıyor mu?**  
A: Evet, takvimin çalışma zamanı tanımları bitiş tarihi hesaplanırken uygulanır.

**Q: Kesirli saatler (ör. 3.5 saat) için bitiş tarihini almanın bir yolu var mı?**  
A: `getTaskFinishDateFromDuration` metoduna `3.5d` gibi bir `double` değer geçirin; API kesirli süreleri işler.

**Q: Çıktı tarihini nasıl biçimlendirebilirim?**  
A: Dönen `Date` nesnesi üzerinde `java.time.format.DateTimeFormatter` kullanarak istediğiniz formatta görüntüleyin.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}