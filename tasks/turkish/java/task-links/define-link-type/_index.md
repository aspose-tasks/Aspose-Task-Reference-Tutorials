---
date: 2026-08-29
description: Aspose.Tasks for Java ile bağlantı türlerini nasıl ayarlayacağınızı ve
  görev bağımlılıklarını nasıl yöneteceğinizi adım adım bir öğreticide öğrenin.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Aspose.Tasks for Java'da Bağlantı Türlerini Nasıl Ayarlarsınız
og_description: Aspose.Tasks for Java ile bağlantı türlerini nasıl ayarlayacağınızı
  ve görev bağımlılıklarını nasıl yöneteceğinizi öğrenin. Geliştiriciler için adım
  adım rehber.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Aspose.Tasks for Java'da Bağlantı Türlerini Nasıl Ayarlarsınız
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Aspose.Tasks for Java'da Bağlantı Türlerini Nasıl Ayarlarsınız
url: /tr/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java'da bağlantı türlerini nasıl ayarlarsınız

## Giriş
Eğer bir projede *görev bağımlılıklarını yönetirken* görevler arasında **bağlantıyı nasıl ayarlayacağınızı** merak ediyorsanız, doğru yerdesiniz. Bu öğreticide yeni bir proje oluşturmayı, görev eklemeyi ve Aspose.Tasks for Java kullanarak bağlantı türünü (Start‑to‑Start, Finish‑to‑Start vb.) tanımlamayı adım adım göstereceğiz. Sonunda gerçek dünya zamanlama ihtiyaçlarına uygun görev ilişkilerini özelleştirme konusunda kendinize güveneceksiniz ve API'nin 10.000'e kadar görev içeren büyük ölçekli planları nasıl yönettiğini göreceksiniz.

## Hızlı cevaplar
- **Bağımlılığı temsil eden sınıf hangisidir?** `TaskLink` iki görev arasındaki bağlantıyı modelleyen temel nesnedir.  
- **İlişki türünü tanımlayan enum hangisidir?** `TaskLinkType` (örneğin, `StartToStart`, `FinishToStart`).  
- **Mevcut bağlantı türlerini okuyabilir miyim?** Evet – `Project.getTaskLinks()` üzerinde döngü yapın ve `getLinkType()` çağırın.  
- **Bu kod için lisansa ihtiyacım var mı?** Test için geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Bu, Java 8+ ile uyumlu mu?** Kesinlikle – Aspose.Tasks, Java 8'den Java 21'e kadar destek sağlar ve 13 ana sürümü kapsar.  

## Görev bağlantısı nedir?
Bir **görev bağlantısı**, proje zaman çizelgesinde iki görev arasındaki bağımlılığı modeller.  
`TaskLink` oluşturabilir, değiştirebilir veya silebilir ve öncül‑sonraki ilişkileri yansıtabilirsiniz; bu sayede zamanlayıcı başlangıç ve bitiş tarihlerini otomatik olarak hesaplar.

## Aspose.Tasks bağlantı türlerini neden kullanmalısınız?
Aspose.Tasks **30'dan fazla giriş ve çıkış formatını** destekler ve **10.000'e kadar görev** içeren projeleri tüm dosyayı belleğe yüklemeden işleyebilir. Bu ölçülebilir yetenek, kurumsal ölçekli planlarda bile hızlı performans sağlar ve kütüphane, özel alanlar ve kaynak atamaları gibi tüm Microsoft Project özelliklerini korur.

## Önkoşullar
- **Java Geliştirme Ortamı** – JDK 8 veya daha yeni bir sürüm yüklü ve yapılandırılmış.  
- **Aspose.Tasks Kütüphanesi** – En son JAR dosyasını [download link](https://releases.aspose.com/tasks/java/) adresinden indirin.  
- **Belge Dizini** – Makinenizde örnek proje dosyalarını saklayacağınız bir klasör oluşturun.  

## Paketleri içe aktar
Gerekli Aspose.Tasks sınıflarını içe aktararak başlıyoruz. Bu, IDE'nin daha sonra kullanacağımız API çağrılarını tanımasını sağlar.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## Aspose.Tasks for Java'da bağlantı türlerini nasıl ayarlarsınız?
Yeni bir `Project` örneği yükleyin, iki görev ekleyin ve ardından istediğiniz `TaskLinkType` ile bir `TaskLink` oluşturun. Bu iki adımlı desen, tek bir çağrıda dört standart bağımlılık türünden herhangi birini tanımlamanıza olanak tanır. `Project`, tüm proje dosyasını ve zaman çizelgesini temsil eder. `Task`, proje içindeki bireysel bir iş öğesidir. `TaskLink`, bir öncül görevi bir sonraki göreve bağlar. `TaskLinkType`, ilişkiyi (Start‑to‑Start, Finish‑to‑Start vb.) belirten bir enumdur.

### Adım 1: bir bağlantı türü ayarlama
`TaskLink`, iki görev arasındaki bağımlılığı temsil eder, `TaskLinkType` ise `StartToStart` gibi olası ilişki türlerini listeler. Bu adımda yeni bir proje oluşturur, iki görev ekler ve **Start‑to‑Start** ilişkisini kullanarak bunları bağlarız.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Pro tip:** `StartToStart` değerini, ihtiyacınız olan bağımlılığa göre `FinishToStart`, `StartToFinish` veya `FinishToFinish` ile değiştirebilirsiniz; böylece **görev bağımlılıklarını yönetirsiniz**.

### Adım 2: bir bağlantı türünü alma
`Project.getTaskLinks()` zaman çizelgesindeki tüm `TaskLink` nesnelerinin bir koleksiyonunu döndürür. Bu koleksiyonu döngüyle gezerek her bağlantının `TaskLinkType` değerini okuyabilir ve doğru ilişkinin kaydedildiğini doğrulayabilirsiniz.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

Konsol, `StartToStart`, `FinishToStart` gibi değerleri çıktılar ve önce ayarladığınız bağlantı türünü onaylar.

## Yaygın sorunlar ve çözümler
- **Bağlantı eklerken NullPointerException** – `TaskLink` oluşturulmadan önce hem öncül hem de sonraki görevlerin projeye eklendiğinden emin olun.  
- **Kaydetme sonrası hatalı bağlantı türü** – Bağlantı türünü ayarladıktan sonra değişiklikleri kalıcı kılmak için her zaman `project.save("output.mpp")` (veya başka bir desteklenen format) çağırın.  
- **Lisans bulunamadı** – Aspose.Tasks lisans dosyanızı projenin sınıf yoluna (classpath) koyun ve `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` kodu ile yükleyin.  

## Sıkça Sorulan Sorular

**S: Aspose.Tasks farklı Java ortamlarıyla uyumlu mu?**  
**C:** Evet, Aspose.Tasks ek bağımlılık olmadan standart Java SE, Java EE ve Android geliştirme kitleriyle bütünleşir.

**S: Proje gereksinimlerime göre bağlantı türlerini özelleştirebilir miyim?**  
**C:** Kesinlikle. `TaskLinkType` enumu dört standart tür sağlar ve gecikme değerleriyle birleştirerek karmaşık zaman çizelgeleri modelleyebilirsiniz.

**S: Aspose.Tasks for Java için ayrıntılı belgeleri nerede bulabilirim?**  
**C:** Derinlemesine rehberlik, API referansı ve kod örnekleri için [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) adresine bakın.

**S: Aspose.Tasks için geçici bir lisans nasıl alabilirim?**  
**C:** Test amaçlı geçici bir lisans edinmek için [temporary license page](https://purchase.aspose.com/temporary-license/) adresini ziyaret edin.

**S: Aspose.Tasks ile ilgili sorular için nereden destek alabilirim?**  
**C:** Yardım ve tartışmalar için [support forum](https://forum.aspose.com/c/tasks/15) adresindeki Aspose.Tasks topluluğuna katılın.

**S: Proje kaydedildikten sonra bağlantı türünü değiştirebilir miyim?**  
**C:** Evet. Projeyi yükleyin, `TaskLink`i alın, yeni enum değeriyle `setLinkType()` çağırın ve projeyi tekrar kaydedin.

**S: Aspose.Tasks Microsoft Project (MPP) dosyalarını okumayı destekliyor mu?**  
**C:** Evet. `new Project("file.mpp")` kullanarak MPP dosyalarını yükleyebilir ve yukarıdaki XML örneği gibi görev bağlantılarıyla çalışabilirsiniz.

---

**Son Güncelleme:** 2026-08-29  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks'te Çapraz Proje Görev Bağlantısı Oluşturma](/tasks/java/task-links/create-cross-project-task-link/)
- [Aspose.Tasks'te Proje Başlangıç Tarihini Ayarlama ve Üst‑Alt Görevleri Yönetme](/tasks/java/task-properties/parent-child-tasks/)
- [Aspose.Tasks ile MPP Dosyasını Java'da Yükleme - Proje Özelliklerini Yönetme](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}