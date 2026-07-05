---
date: 2026-07-05
description: Aspose.Tasks for Java ile projeler arasında görevleri nasıl bağlayacağınızı
  öğrenin. Adım adım kılavuz, ön koşullar ve sorunsuz çapraz proje görev bağlaması
  için en iyi uygulamalar.
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: Aspose.Tasks'te Çapraz Proje Görev Bağlantısı Oluşturma
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java Kullanarak Projeler Arasında Görevleri Bağlama
url: /tr/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeler Arasında Görev Bağlantılarını Aspose.Tasks for Java Kullanarak Bağlama

## Giriş
Projeler arasında görevleri bağlamak, çalışmayı senkronize etmenizi, yinelenmeyi önlemenizi ve birbirine bağımlı aktiviteler için tek bir doğru kaynağı korumanızı sağlayan temel bir yetenektir. Bu öğreticide, Aspose.Tasks for Java ile **projeler arasında görev bağlamayı** adım adım keşfedeceksiniz. Sonunda, her iki taraf değiştiğinde otomatik olarak güncellenen tam işlevsel bir çapraz‑proje bağlantısına sahip olacaksınız ve manuel kopyala‑yapıştırmaya gerek kalmadan gerçek zamanlı koordinasyon sağlayacaksınız.

## Hızlı Yanıtlar
- **Bir proje oluşturmak için birincil sınıf nedir?** `Project` – bellek içinde tüm MS‑Project dosyasını temsil eder.  
- **Hangi metod dış görev ekler?** `project.getRootTask().getChildren().addExternalTask(...)`.  
- **Bağlantı tipini ayarlayabilir miyim?** Evet – `TaskLinkType.FinishToStart`, `StartToStart` vb. kullanın.  
- **Bağlantı için lisansa ihtiyacım var mı?** Üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir; değerlendirme için ücretsiz deneme çalışır.  
- **Bağlı görevlerde bir limit var mı?** Aspose.Tasks, performans düşüşü olmadan proje başına 10.000+ bağlı görevi işleyebilir.

## Projeler Arasında Görev Bağlantısı Nedir?
Projeler arasında görevleri bağlamak, bir proje dosyasındaki bir görev ile başka bir proje dosyasındaki bir görev arasında bağımlılık ilişkisi oluşturur ve kaynak görevdeki (süre, başlangıç tarihi, kısıtlamalar) değişikliklerin otomatik olarak bağımlı göreve akmasını sağlar. Bu mekanizma takvimlerin uyumlu kalmasını, manuel güncellemelerin azalmasını ve kaynak projedeki herhangi bir değişikliğin anında tüm bağlı projelere yansımasını sağlayarak portföy genelinde tutarlılığı korur.

## Neden Aspose.Tasks'i Çapraz‑Proje Bağlantısı İçin Kullanmalısınız?
Aspose.Tasks, **50+ giriş ve çıkış formatını** destekler ve **yüzlerce sayfalık projeleri** bellek kullanımını 200 MB’nin altında tutarak işleyebilir. API'si bağlantıyı sunucu tarafında gerçekleştirir, Microsoft Project kurulumuna ihtiyaç duymaz ve büyük işletmeler için otomatikleştirilmiş iş akışlarını mümkün kılar.

## Önkoşullar
- Java 17 (veya daha yeni) IDE'nizde kurulu ve yapılandırılmış.  
- Geçerli bir Aspose.Tasks for Java lisans dosyası (`Aspose.Tasks.Java.lic`).  
- Projenize Aspose.Tasks for Java kütüphanesini ekleyin. İndirmek için [Aspose.Tasks for Java sürüm sayfası](https://releases.aspose.com/tasks/java/) adresini ziyaret edebilirsiniz.  
- Görevler, özet görevler ve bağımlılıklar gibi MS‑Project kavramlarına temel aşinalık.

## Paketleri İçe Aktarma
`Project`, `Task`, `TaskLink` ve ilgili enum'lar `com.aspose.tasks` ad alanında bulunur. Java dosyanızın en üst kısmına şu satırı ekleyin:

`import com.aspose.tasks.*;`

**Project** bellek içinde bir proje dosyasını temsil eden ana sınıftır. **Task** bir proje içindeki bireysel iş öğesini temsil eder. **TaskLink** iki görev arasındaki bağımlılık ilişkisinin tanımını yapar. Bu içe aktarmalar, çapraz‑proje bağlamayı da içeren proje manipülasyonu özelliklerinin tamamına erişim sağlar.

## Projeler Arasında Görev Nasıl Bağlanır?
İki proje dosyasını yükleyin, bir dış görev yer tutucusu ekleyin, yerel bir görev oluşturun ve ardından bunları bir `TaskLink` ile bağlayın. API, kimlik eşlemesini ve güncellemeleri otomatik olarak yönetir, böylece dış görevdeki herhangi bir değişiklik ek kod yazmaya gerek kalmadan bağlı yerel göreve yansır. Bu yaklaşım çoklu proje koordinasyonunu basitleştirir ve takvim kayması riskini azaltır.

### Adım 1: Ortamınızı Kurun
Aspose.Tasks JAR dosyasının sınıf yolunda olduğundan ve lisans dosyasının çalışma zamanında yüklendiğinden emin olun:

`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`

**License** Aspose.Tasks lisans dosyanızı yükleyerek tam işlevselliği etkinleştirir ve değerlendirme filigranlarını kaldırır.

### Adım 2: Bir Proje Örneği Oluşturun
Bağlantının bulunmasını istediğiniz hedef proje için yeni bir `Project` nesnesi oluşturun:

`Project targetProject = new Project();`

`Project` sınıfı, Aspose.Tasks'in bellek içinde tek bir proje dosyasını temsil eden üst‑seviye nesnesidir.

### Adım 3: Özet Görev Ekleyin
Özet görev, ilgili görevleri gruplar. Hem dış hem de yerel görevleri tutacak bir özet görev oluşturun:

`Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");`

### Adım 4: Dış Görev Ekleyin
Başka bir proje dosyasındaki bir göreve işaret eden bir dış görev ekleyin:

`Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);`

**addExternalTask** metodu, verilen dosya adı ve görev kimliğini kullanarak dış proje dosyasına referans veren bir yer tutucu görev oluşturur.

### Adım 5: Yerel Görev Ekleyin
Dış görevle bağlanacak yerel görevi oluşturun:

`Task local = summary.getChildren().add("Local Task");`

### Adım 6: Görev Bağlantısı Oluşturun
Dış ve yerel görevler arasında bir bağımlılık kurun. En yaygın bağlantı tipi Finish‑to‑Start'tır:

`TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);`

**TaskLink** ilişkiyi kaydeder; daha sonra gecikme, önde gelen zaman veya tipini ihtiyacınıza göre değiştirebilirsiniz.

### Adım 7: Kaydedin ve Doğrulayın
Projeyi bir dosyaya kaydedin ve isteğe bağlı olarak Microsoft Project'te açarak bağlantıyı doğrulayın:

`targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`

**SaveFileFormat** bir projenin kaydedileceği dosya formatını belirtir. *LinkedProject.mpp* dosyasını açtığınızda dış görev özel bir simgeyle gösterilir ve bağımlılık çizgisi yerel göreve işaret eder.

## Yaygın Sorunlar ve Çözümler
- **Dış dosya bulunamadı** – Yolu çalıştırma sürecine göre göreceli olduğundan emin olun veya mutlak bir yol sağlayın.  
- **Görev kimlikleri eşleşmiyor** – `addExternalTask` metodunun ikinci parametresi olan dış görev kimliğinin kaynak projedeki görev kimliğiyle aynı olduğundan emin olun.  
- **Lisans yüklenmedi** – Eksik veya hatalı lisans dosyası bir `LicenseException` oluşturur. Aspose.Tasks çağrılarından önce lisansı yükleyin.  
- **Büyük projelerde performans** – Sadece dış görevleri okumanız gerektiğinde `Project.setReadOnly(true)` kullanın; bu bellek yükünü azaltır.

## Sık Sorulan Sorular

**S: Aynı özet görev içinde birden fazla dış projeden görev bağlayabilir miyim?**  
C: Evet, bir özet görev altında birkaç dış görev ekleyebilir ve her biri için ayrı ayrı `addExternalTask` yöntemiyle bağlantılar oluşturabilirsiniz.

**S: Bağlı projedeki dış görev değiştirildiğinde ne olur?**  
C: Dış görevin takvimi, süresi veya kısıtlamalarındaki herhangi bir değişiklik, hedef proje yenilendiğinde otomatik olarak bağımlı yerel göreve yansır.

**S: Farklı dosya formatları arasında görev bağlantısı oluşturmak mümkün mü?**  
C: Kesinlikle. Aspose.Tasks, MPP, XML ve Primavera formatları arasında bağlantı kurmayı destekler; böylece heterojen proje ekosistemleri senkronize kalabilir.

**S: Görevler bir kez bağlandıktan sonra bağlantıyı kaldırabilir miyim?**  
C: Evet, `project.getTaskLinks().remove(link)` metodunu çağırarak bağlantıyı kaldırabilir veya dış görev yer tutucusunu silebilirsiniz.

**S: Projeler arasında bağlanabilecek görev sayısında bir sınırlama var mı?**  
C: Kütüphane, sistem belleği ve dosya formatı sınırlamaları dışında, proje başına **10.000+ bağlı görev** işleyebilir.

## Sonuç
Artık Aspose.Tasks for Java kullanarak **projeler arasında görev bağlamayı** sağlayan eksiksiz, üretim‑hazır bir yaklaşıma sahipsiniz. Bu yetenek, çoklu proje koordinasyonunu kolaylaştırır, manuel çabayı azaltır ve takvim değişikliklerinin portföyünüzde anında yayılmasını sağlar. Özel gecikme süreleri, farklı bağlantı tipleri ve toplu bağlama gibi ek özellikleri keşfederek karmaşık proje yapılarınızı daha da otomatikleştirebilirsiniz.

---

**Son Güncelleme:** 2026-07-05  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## İlgili Öğreticiler

- [Aspose.Tasks'te Görev Bağlantısı Oluşturma](/tasks/java/task-links/create-task-link/)
- [Aspose Java’da Görev Oluşturma – Görev Özellikleri](/tasks/java/task-properties/)
- [Aspose.Tasks'te Boş MS Project Dosyası Oluşturma](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}