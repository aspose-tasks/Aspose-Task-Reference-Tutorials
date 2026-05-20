---
date: 2026-05-20
description: Aspose.Tasks for Java kullanarak projeye kaynak eklemeyi ve kaynak atamaları
  oluşturmayı öğrenin, güçlü bir Java proje yönetimi kütüphanesi.
keywords:
- add resource to project
- how to add task
- assign resource to task
- java project management library
linktitle: Aspose.Tasks'te Kaynak Atamaları Oluşturma
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  headline: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  name: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  steps:
  - name: Create a Project Object
    text: 'The `Project` class is the top‑level container that represents a single
      project file in memory. Instantiate a `Project` object, which represents the
      project file you''re working with:'
  - name: Add a Task to the Project
    text: 'The `Task` class models an individual work item within the schedule. Add
      a task to the project using the `addChild` method of the root task:'
  - name: Add a Resource to the Project
    text: 'The `Resource` class defines a person, equipment, or material that can
      be assigned to tasks. Add a resource to the project using the `add` method of
      the `Resources` collection:'
  - name: Create a Resource Assignment
    text: 'The `ResourceAssignment` class links a `Task` and a `Resource` and stores
      allocation details such as work hours and cost. Create a resource assignment
      for the task and resource using the `add` method of the `ResourceAssignments`
      collection:'
  type: HowTo
- questions:
  - answer: Yes, you can update assignment properties such as `Work`, `Cost`, and
      `Start` using the setters provided by the `ResourceAssignment` class.
    question: Can I modify resource assignments after creation?
  - answer: Absolutely, Aspose.Tasks for Java supports MPP, XML, CSV, and many other
      formats, allowing seamless import and export.
    question: Is Aspose.Tasks for Java compatible with different project file formats?
  - answer: Yes, a valid commercial license is required. A free evaluation license
      is available for testing purposes.
    question: Does Aspose.Tasks for Java require a license for commercial use?
  - answer: Yes, the library is fully thread‑safe and can be integrated into servlet‑based
      or Spring‑Boot web services.
    question: Can I use Aspose.Tasks for Java in my web applications?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for technical assistance and community discussions.
    question: Where can I find additional support for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Projeye Kaynak Ekleme ve Kaynak Atamaları Oluşturma
url: /tr/java/resource-assignments/create-resource-assignments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeye Kaynak Ekle – Aspose.Tasks'te Kaynak Atamaları Oluşturma

## Giriş
Modern proje yönetiminde, **add resource to project** etkili zamanlama ve maliyet kontrolünün temel taşıdır. Aspose.Tasks for Java, IDE'nizden çıkmadan kaynakları, görevleri ve atamaları yönetmenizi sağlayan programatik, yüksek performanslı bir yol sunar. Bu öğreticide, bir projeye nasıl kaynak ekleyeceğinizi, bir göreve nasıl ilişkilendireceğinizi ve atama detaylarını nasıl ince ayar yapacağınızı göreceksiniz — hepsi temiz, üretim‑hazır Java kodu ile.

## Hızlı Yanıtlar
- **İlk adım nedir?** Projenizin .mpp veya .xml dosyasını temsil eden bir `Project` örneği oluşturun.  
- **Görev nasıl eklenir?** Kök görevin `addChild` metodunu kullanın ve göreve bir ad verin.  
- **Kaynak nasıl eklenir?** `project.getResources().add` metodunu bir `Resource` nesnesi ile çağırın.  
- **Kaynak bir göreve nasıl bağlanır?** `project.getResourceAssignments().add(task, resource)` metodunu kullanın.  
- **Lisans gerekli mi?** Evet – üretim kullanımında geçerli bir Aspose.Tasks for Java lisansı gereklidir.

## “add resource to project” nedir?
**Add resource to project**, proje dosyasında bir `Resource` nesnesi oluşturmak ve onu bir veya daha fazla görevle ilişkilendirmek anlamına gelir; böylece iş, maliyet ve takvim verileri otomatik olarak hesaplanır. Bu işlem, zaman çizelgesi‑odaklı herhangi bir uygulamanın bel kemiğidir.

## Neden Aspose.Tasks for Java seçilmeli?
Aspose.Tasks for Java, **30+ giriş ve çıkış formatını** (MPP, XML ve CSV dahil) destekler ve **10.000+ görev** içeren projeleri, bellek kullanımını 200 MB'nin altında tutarak işleyebilir. Kütüphane Java 8‑17 üzerinde çalışır, Microsoft Project kurulumu gerektirmez ve sunucu‑tarafı otomasyon için thread‑safe API'ler sağlar.

## Önkoşullar
Kaynak atamaları oluşturma konusuna girmeden önce, aşağıdakilere sahip olduğunuzdan emin olun:

### Java Geliştirme Ortamı
Sisteminizde Java Development Kit (JDK) kurulu olduğundan emin olun. JDK'yı [buradan](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) indirebilir ve kurabilirsiniz.

### Aspose.Tasks for Java Kütüphanesi
Aspose.Tasks for Java kütüphanesini [indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin. Kütüphaneyi Java projenize kurmak için kurulum talimatlarını izleyin.

## Projeye kaynak nasıl eklenir?
Projenizi yükleyin, bir görev oluşturun, bir kaynak ekleyin ve sonunda onları birbirine bağlayın – tüm bunlar dört kısa adımda. Aşağıdaki kod parçacıkları (yer tutucular) tam API çağrılarını gösterir; yalnızca yer tutucu metni kendi dosya yollarınız ve adlarınızla değiştirmeniz gerekir.

### Adım 1: Project Nesnesi Oluşturma
`Project` sınıfı, bellekte tek bir proje dosyasını temsil eden üst‑seviye konteynerdir.  
Çalıştığınız proje dosyasını temsil eden bir `Project` nesnesi örnekleyin:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

### Adım 2: Projeye Görev Ekleme
`Task` sınıfı, takvim içinde bireysel bir iş öğesini modeller.  
Kök görevin `addChild` metodunu kullanarak projeye bir görev ekleyin:
```java
Project project = new Project();
```

### Adım 3: Projeye Kaynak Ekleme
`Resource` sınıfı, görevlere atanabilecek bir kişi, ekipman veya malzemeyi tanımlar.  
Projeye bir kaynak eklemek için `Resources` koleksiyonunun `add` metodunu kullanın:
```java
Task task = project.getRootTask().getChildren().add("Task");
```

### Adım 4: Kaynak Ataması Oluşturma
`ResourceAssignment` sınıfı, bir `Task` ve bir `Resource`'ı bağlar ve iş saatleri ve maliyet gibi tahsis detaylarını saklar.  
Görev ve kaynak için bir kaynak ataması oluşturmak üzere `ResourceAssignments` koleksiyonunun `add` metodunu kullanın:
```java
Resource rsc = project.getResources().add("Rsc");
```

## Yaygın Sorunlar ve Çözümler
- **`addChild` üzerinde NullPointerException** – `project.getRootTask()` metodunu çocuk eklemeden önce çağırdığınızdan emin olun.  
- **Lisans bulunamadı** – `Aspose.Tasks.lic` dosyanızı sınıf yoluna (classpath) yerleştirin veya lisansı programatik olarak `License license = new License(); license.setLicense("Aspose.Tasks.lic");` kodu ile ayarlayın.  
- **Büyük proje yavaşlaması** – Yalnızca veri okumanız gerektiğinde `project.setReadOnly(true)` kullanın; bu bellek yükünü azaltır.

## Sıkça Sorulan Sorular

**Q: Kaynak atamalarını oluşturduktan sonra değiştirebilir miyim?**  
A: Evet, `ResourceAssignment` sınıfı tarafından sağlanan setter'ları kullanarak `Work`, `Cost` ve `Start` gibi atama özelliklerini güncelleyebilirsiniz.

**Q: Aspose.Tasks for Java farklı proje dosyası formatlarıyla uyumlu mu?**  
A: Kesinlikle, Aspose.Tasks for Java MPP, XML, CSV ve birçok diğer formatı destekler, sorunsuz içe ve dışa aktarım sağlar.

**Q: Aspose.Tasks for Java ticari kullanım için lisans gerektiriyor mu?**  
A: Evet, geçerli bir ticari lisans gereklidir. Test amaçları için ücretsiz bir değerlendirme lisansı mevcuttur.

**Q: Aspose.Tasks for Java'ı web uygulamalarımda kullanabilir miyim?**  
A: Evet, kütüphane tamamen thread‑safe'dir ve servlet‑tabanlı veya Spring‑Boot web servislerine entegre edilebilir.

**Q: Aspose.Tasks for Java için ek destek nereden bulunabilir?**  
A: Teknik yardım ve topluluk tartışmaları için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.

---

**Son Güncelleme:** 2026-05-20  
**Test Edilen:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Kaynakları Oluşturma – Aspose.Tasks for Java ile Kaynak Yönetimi](/tasks/java/resource-management/)
- [Aspose.Tasks'te Kaynak Atamalarına Not Ekleme](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Projeye Kaynak Ekleme ve Aspose.Tasks'te Düzeyleme Gecikme Özelliklerini Yönetme](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}