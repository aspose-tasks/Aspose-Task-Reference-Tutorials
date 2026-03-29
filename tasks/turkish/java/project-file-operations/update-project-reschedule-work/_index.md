---
date: 2026-03-29
description: Aspose.Tasks for Java kullanarak tamamlanmamış işi yeniden zamanlamayı,
  proje işini güncellemeyi ve MS Project dosyalarını XML olarak kaydetmeyi öğrenin.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tamamlanmamış İşleri Yeniden Planlayın ve Aspose.Tasks ile MS Project Dosyalarını
  Güncelleyin
url: /tr/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tamamlanmamış İşleri Yeniden Planlama ve Aspose.Tasks ile MS Project Dosyalarını Güncelleme

## Giriş
Microsoft Project, ekiplerin görevleri planlamasına, kaynakları tahsis etmesine ve zaman çizelgelerini takip etmesine yardımcı olan yaygın olarak kullanılan bir proje yönetim aracıdır. Aspose.Tasks for Java, geliştiricilere Microsoft Project dosyalarını programlı olarak manipüle etmeleri için zengin bir API sunar. Bu öğreticide, Aspose.Tasks for Java kullanarak **projeyi güncelleme**, **tamamlanmamış işleri yeniden planlama** ve **MS Project dosyasını** XML formatında **kaydetme** konularını öğreneceksiniz.

## Hızlı Yanıtlar
- **“Tamamlanmamış işleri yeniden planlama” ne anlama gelir?** Kalan görev işini seçilen bir tarihten sonra başlamasını sağlayarak, tamamlanmış kısımları dokunulmaz bırakır.  
- **Hangi yöntem işi tamamlanmış olarak işaretler?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Değişiklikleri nasıl kalıcı hale getiririm?** `project.save(<path>, SaveFileFormat.Xml)` kullanın.  
- **Üretim ortamında lisansa ihtiyacım var mı?** Evet, ticari kullanım için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri tamamen desteklenir.

## “Tamamlanmamış işleri yeniden planlama” nedir?
Tamamlanmamış işleri yeniden planlamak, henüz tamamlanmamış tüm görevlerin başlangıç tarihlerini ayarlayarak, belirli bir kesim tarihinden sonra başlamalarını sağlar. Bu, proje zaman çizelgesi gecikmeler veya kapsam değişiklikleri nedeniyle kaydığında faydalıdır.

## Projeyi güncellemek ve görevleri yeniden planlamak için Aspose.Tasks'i neden kullanmalısınız?
- **İnce ayarlı kontrol:** İş tamamlama yüzdelerini ve tarihlerini doğrudan ayarlayın.  
- **Kullanıcı arayüzü gerekmez:** Çok sayıda proje dosyasında toplu güncellemeleri otomatikleştirin.  
- **Çapraz platform:** Java çalıştıran herhangi bir sistemde çalışır.  
- **Veri bütünlüğünü korur:** Tüm bağımlılıklar, kısıtlamalar ve kaynaklar tutarlı kalır.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Development Kit (JDK) yüklü.  
2. Aspose.Tasks for Java kütüphanesi. Bunu [buradan](https://releases.aspose.com/tasks/java/) indirebilirsiniz.  
3. Java programlama diline temel bir anlayış.

## Paketleri İçe Aktar
İlk olarak, Java kodunuzda gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Adım 1: Projeyi Kurun
Yeni bir `Project` nesnesi başlatın, görevleri tanımlayın, süreleri ayarlayın ve bağımlılıkları oluşturun. Bu, daha sonra güncelleyeceğimiz ve yeniden planlayacağımız temel projeyi oluşturur.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Adım 2: Proje İşini Güncelleyin
İşi belirli bir tarihe kadar tamamlanmış olarak işaretleyin. Bu adım, genellikle yeniden planlamadan önce yapılan ilk işlem olan **projeyi güncelleme** işlemini gösterir.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Adım 3: Tamamlanmamış İşleri Yeniden Planlayın
Şimdi kalan (tamamlanmamış) işleri aynı kesim tarihinden sonra başlayacak şekilde kaydırıyoruz. Bu, **tamamlanmamış işleri yeniden planlama** işlevinin temelidir.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Sonuç
Bu öğreticide, Aspose.Tasks for Java kullanarak **projeyi güncelleme**, **tamamlanmamış işleri yeniden planlama** ve **MS Project dosyasını** XML olarak **kaydetme** konularını ele aldık. Bu yetenekler, proje zaman çizelgelerinin gerçek ilerleme veya **değişen iş önceliklerine** göre ayarlanması gerektiğinde esastır.

## SSS
### S: Aspose.Tasks for Java karmaşık proje yapılarıyla başa çıkabilir mi?
Evet, Aspose.Tasks for Java, görevleri, bağımlılıkları, kaynakları ve diğer proje öğelerini verimli bir şekilde yönetmek için sağlam API'ler sunar.

### S: Aspose.Tasks for Java için bir deneme sürümü mevcut mu?
Evet, [buradan](https://releases.aspose.com/) ücretsiz bir deneme alabilirsiniz.

### S: Aspose.Tasks for Java için nasıl destek alabilirim?
Herhangi bir yardım veya soru için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.

### S: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?
Evet, geçici lisanslar [buradan](https://purchase.aspose.com/temporary-license/) satın alınabilir.

### S: Aspose.Tasks for Java için ayrıntılı belgeleri nerede bulabilirim?
Kapsamlı kılavuzlar ve API referansları için belgeleri [buradan](https://reference.aspose.com/tasks/java/) inceleyebilirsiniz.

## Ek Sık Sorulan Sorular

**S: Kaydedilen dosyanın Microsoft Project'in eski sürümleriyle uyumlu olmasını nasıl sağlarım?**  
C: Projeyi `SaveFileFormat.Xml` kullanarak kaydedin; XML, Project sürümleri arasında yaygın olarak desteklenir.

**S: Tüm proje yerine yalnızca bir görev alt kümesini yeniden planlayabilir miyim?**  
C: Evet, belirli görevler üzerinde döngü yaparak yeni başlangıç tarihini hesapladıktan sonra `task.setStart(date)` çağırabilirsiniz.

**S: Tamamlanmamış işleri yeniden planladığımda kaynak tahsisleri ne olur?**  
C: Kaynak atamaları, yeni görev başlangıç tarihleriyle eşleşecek şekilde otomatik olarak kaydırılır ve tahsis mantığı korunur.

**S: Yeniden planlama işlemini programlı olarak geri alabilir miyim?**  
C: Orijinal proje dosyasını (veya bir yedekleme) yeniden yükleyerek değişiklikleri geri alabilirsiniz.

**S: Aspose.Tasks .mpp gibi diğer formatlarda kaydetmeyi destekliyor mu?**  
C: Kesinlikle. Yerel Microsoft Project formatında kaydetmek için `SaveFileFormat.MPP` kullanın.

---

**Son Güncelleme:** 2026-03-29  
**Test Edilen:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}