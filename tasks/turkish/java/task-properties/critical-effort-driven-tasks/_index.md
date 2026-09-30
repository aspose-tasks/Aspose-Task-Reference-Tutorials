---
date: 2026-09-30
description: Aspose.Tasks ile Java projelerindeki kritik görevleri yönetin. Kritik
  ve effort‑driven görevlerin nasıl ele alınacağını öğrenin, kütüphaneyi indirin ve
  proje yönetimi iş akışınızı hızlandırın.
keywords:
- manage critical tasks java
- effort‑driven tasks Aspose.Tasks
- Java project management
lastmod: 2026-09-30
linktitle: Aspose.Tasks'te Kritik ve Effort-Driven Görevleri Yönetin
og_description: Aspose.Tasks ile Java geliştiricilerinin karşılaştığı kritik görevleri
  yönetin. Bu rehber, Java projelerinde kritik ve effort‑driven görevlerin adım adım
  nasıl ele alınacağını gösterir (150‑160 karakter).
og_image_alt: Screenshot of Aspose.Tasks Java API managing critical and effort‑driven
  tasks
og_title: Aspose.Tasks kullanarak Java'da kritik görevleri nasıl yönetilir
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Manage critical tasks Java projects with Aspose.Tasks. Learn to handle
    critical and effort‑driven tasks, download the library and boost your project
    management workflow.
  headline: How to manage critical tasks in Java using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is platform‑independent and runs on Windows,
      Linux, and macOS.
    question: Can I use Aspose.Tasks for Java in both Windows and Linux environments?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java on the [Aspose.Tasks
      free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find support for Aspose.Tasks for Java?
  - answer: You can acquire a temporary license on the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: You can purchase Aspose.Tasks for Java from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- critical tasks
- effort‑driven tasks
- Aspose.Tasks
- Java
- project management
title: Aspose.Tasks kullanarak Java'da kritik görevleri nasıl yönetilir
url: /tr/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da Aspose.Tasks ile kritik ve çaba‑türetilmiş görevleri yönetin

Modern proje yönetiminde, **manage critical tasks java** geliştiriciler için takvimleri yolunda tutarken çaba‑türetilmiş iş öğelerini yönetmek günlük bir zorluktur. Aspose.Tasks for Java, kritik ve çaba‑türetilmiş görevleri manuel elektronik tablo karışıklığı olmadan tanımlamanın, incelemenin ve güncellemenin temiz, programatik bir yolunu sunar.

## Hızlı cevaplar
- **Ana fayda nedir?** Otomatik olarak kritik görevleri işaretler ve çaba‑türetilmiş zamanlamayı tek bir API çağrısında ayarlar.  
- **Bir lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Hangi Java sürümleri destekleniyor?** Java 8 ‑ 17, hem OpenJDK hem de Oracle dağıtımları.  
- **Büyük projeleri işleyebilir miyim?** Evet – Aspose.Tasks, 10 000'e kadar görev içeren projeleri verimli bir şekilde işler.  
- **Çapraz platform mu?** Kütüphane, yerel bağımlılıklar olmadan Windows, Linux ve macOS'ta çalışır.

## Aspose.Tasks for Java'da kritik ve çaba‑türetilmiş görevleri nasıl yönetilir?
Proje dosyanızı `Project` sınıfı ile yükleyin, tüm görevleri toplamak için `ChildTasksCollector` kullanın ve ardından her görevin `Critical` ve `EffortDriven` özelliklerini inceleyin. Toplanan listeyi yineleyerek bir durum raporu oluşturabilir veya zamanlama kurallarını otomatik olarak değiştirebilirsiniz; tüm bunlar sadece birkaç satır Java kodu ile saniyeler içinde çalışır.

Aspose.Tasks for Java, **30'dan fazla giriş ve çıkış proje formatını** (Microsoft Project 2019, 2022 ve Primavera P6 dahil) destekler ve **10 000'e kadar görev** içeren dosyaları tipik bir sunucuda bellek kullanımını 200 MB'nin altında tutarak işleyebilir. Bu nicel yetenekler, kurumsal ölçekli planlama için uygun olmasını sağlar.

## Önkoşullar
- **Aspose.Tasks for Java** kütüphanesi – [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) adresinden indirin.  
- **Java Development Kit (JDK)** – makinenizde yüklü 8 veya daha yeni bir sürüm.  
- **IDE** tercih ettiğiniz (IntelliJ IDEA, Eclipse, VS Code vb.).  
- Demo için kullanacağınız XML (veya .mpp) formatında bir örnek proje dosyası.

## Paketleri içe aktar
Java kaynak dosyanıza gerekli paketleri ekleyin:

```java
import com.aspose.tasks.*;
import java.util.*;
```

Bu içe aktarmalar, `Project`, `Task` ve yardımcı yardımcı sınıflar gibi temel görev‑yönetimi sınıflarına erişim sağlar.

## Kritik görev nedir?
Bir **kritik görev**, gecikmesinin doğrudan projenin bitiş tarihini uzattığı, yani zaman çizelgesinin kritik yolunda yer alan herhangi bir aktivitedir. Aspose.Tasks'te, bir görevin kritik olup olmadığını `Task.isCritical()` metodunu çağırarak belirleyebilirsiniz; bu metod, görev projenin toplam tamamlanma süresini etkilediğinde `true` döner.

## Çaba‑türetilmiş görev nedir?
Bir **çaba‑türetilmiş görev**, süresi değiştirildiğinde kalan işini otomatik olarak yeniden dağıtarak, toplam çaba miktarının zaman çizelgesi boyunca sabit kalmasını sağlar. Bu davranış, sabit bir oranla çalışan kaynaklar için faydalıdır. Aspose.Tasks'te, `Task.isEffortDriven()` özelliği bu özelliği gösteren görevler için `true` döner.

## Adım 1: ChildTasksCollector kullanarak görevleri topla
`ChildTasksCollector` sınıfı, belirli bir üst görev altındaki tüm görevleri toplar.  
`ChildTasksCollector`, görev hiyerarşisini dolaşan ve `Task` nesnelerinin düz bir listesini döndüren bir yardımcıdır.

```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector);
List<Task> allTasks = collector.getTasks();
```

## Adım 2: Toplanan görevler üzerinde yineleme yap
Liste üzerinde döngü kurarak her görevin kritik ve çaba‑türetilmiş durumunu yazdırın.

```java
for (Task t : allTasks) {
    boolean isCritical = t.get(Tsk.Critical);
    boolean isEffortDriven = t.get(Tsk.EffortDriven);
    System.out.println("Task ID " + t.get(Tsk.Id) + 
        ": critical=" + isCritical + ", effortDriven=" + isEffortDriven);
}
```

Bu basit iki‑adımlı desen, projenin zamanlama sağlığının tam bir görünümünü sunar.

## Yaygın sorunlar ve hata ayıklama
- **Görev özelliklerinde NullPointerException** – Görevlere erişmeden önce proje dosyasının tamamen yüklendiğinden emin olun (`project = new Project("file.mpp")`).  
- **Yanlış kritik işareti** – Projenin hesaplama modunun `CalculationMode.Automatic` olarak ayarlandığını doğrulayın, böylece Aspose.Tasks değişikliklerden sonra kritik yolu yeniden hesaplayabilir.  
- **Büyük dosyalar yavaşlamaya neden olur** – Dosyayı yalnızca okuma modunda açmak için `Project.set(Prj.ReadOnly, true)` kullanın; bu, yalnızca okuma analizleri için bellek yükünü azaltır.

## Sıkça sorulan sorular

**Q: Aspose.Tasks for Java'ı hem Windows hem de Linux ortamlarında kullanabilir miyim?**  
A: Evet, Aspose.Tasks for Java platform‑bağımsızdır ve Windows, Linux ve macOS'ta çalışır.

**Q: Aspose.Tasks for Java için ücretsiz deneme mevcut mu?**  
A: Evet, Aspose.Tasks for Java için ücretsiz denemeye [Aspose.Tasks ücretsiz deneme indirme sayfasından](https://releases.aspose.com/) erişebilirsiniz.

**Q: Aspose.Tasks for Java desteğini nereden bulabilirim?**  
A: Topluluk desteği ve tartışmalar için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin.

**Q: Aspose.Tasks for Java için geçici bir lisans nasıl alabilirim?**  
A: [Geçici lisans talep sayfasından](https://purchase.aspose.com/temporary-license/) geçici bir lisans edinebilirsiniz.

**Q: Aspose.Tasks for Java'ı nereden satın alabilirim?**  
A: [Satın alma sayfasından](https://purchase.aspose.com/buy) Aspose.Tasks for Java'ı satın alabilirsiniz.

---

**Son güncelleme:** 2026-09-30  
**Test edildi:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

## İlgili Eğitimler

- [Kritik Yol MS Project – Aspose.Tasks Java Eğitimi](/tasks/java/project-management/critical-path/)
- [Aspose.Tasks'te Proje Yönetimi Görev Bağlantılarını Oluşturma](/tasks/java/task-links/create-task-link/)
- [Proje Yönetimi Java: Aspose.Tasks kullanarak Görev % Tamamlanması](/tasks/java/task-properties/percentage-complete-calculations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}