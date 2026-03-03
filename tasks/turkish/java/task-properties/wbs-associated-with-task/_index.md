---
date: 2026-03-03
description: Aspose.Tasks for Java'da WBS'yi yeniden numaralandırmayı öğrenin, iş
  bölümlendirmesini yönetin ve adım adım örneklerle WBS kodlarını verimli bir şekilde
  özelleştirin.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java'da WBS'yi Nasıl Yeniden Numaralandırılır
url: /tr/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java'da WBS Nasıl Yeniden Numaralandırılır

## Giriş
Microsoft Project dosyasında **WBS nasıl yeniden numaralandırılır** sorusuna Aspose.Tasks for Java ile yanıt arıyorsanız doğru yerdesiniz. Bu öğreticide mevcut WBS kodlarını okuma, özelleştirme ve ardından hiyerarşiyi yeniden numaralandırarak projenizin düzenli kalmasını sağlayacaksınız. İster eski bir takvimi temizliyor, ister sıfırdan yeni bir takvim oluşturuyor olun, bu adımları öğrenmek **iş kırılımı** yapılarını güvenle yönetmenize yardımcı olur.

## Hızlı Yanıtlar
- **WBS yeniden numaralandırma ne işe yarar?** Görevlerin hiyerarşik numaralandırmasını, yapılan yapısal değişiklikleri yansıtacak şekilde yeniden hesaplar.  
- **Hangi sınıf yeniden numaralandırmayı gerçekleştirir?** `Project.renumberWBSCode`.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Üretim ortamında geçerli bir Aspose.Tasks lisansı gereklidir.  
- **WBS formatını özelleştirebilir miyim?** Evet—herhangi bir dize atamak için `Task.set(Tsk.WBS, "...")` kullanabilirsiniz.  
- **Ana önkoşullar nelerdir?** Java JDK, Aspose.Tasks for Java kütüphanesi ve geçerli bir proje dosyası (.mpp).

## İş Kırılım Yapısı (WBS) Nedir?
İş Kırılım Yapısı (WBS), bir projenin teslimat ve görevlerini hiyerarşik olarak temsil eder. Her göreve, hiyerarşideki konumunu gösteren bir kod (ör. 1.2.3) atanır. Görevler eklendiğinde, silindiğinde veya yeniden sıralandığında kodların mantıklı ve okunabilir kalmasını sağlamak için yeniden numaralandırma gerekir.

## Neden iş kırılımını yönetmeli ve WBS kodlarını özelleştirmelisiniz?
- **Açıklık:** Net WBS kodları, paydaşların görevleri kolayca bulmasını sağlar.  
- **Raporlama:** Birçok raporlama aracı tutarlı numaralandırmaya dayanır.  
- **Esneklik:** Özel kodlar, proje yapısını iç standartlarla hizalamanıza olanak tanır.  

## Önkoşullar
Kodlara geçmeden önce aşağıdakilerin kurulu olduğundan emin olun:

- Makinenizde Java Development Kit (JDK) yüklü.  
- Projenize eklenmiş Aspose.Tasks for Java kütüphanesi. İndirmek için [buraya](https://releases.aspose.com/tasks/java/) tıklayın.  

## Paketleri İçe Aktarın
Projenizi başlatmak için gerekli paketleri içe aktarın:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## WBS Kodlarını Okuma
İlk olarak mevcut WBS kodlarını okuyacağız, böylece neyle çalıştığınızı görebileceksiniz.

### Adım 1: Projeyi Yükleme
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Adım 2: Görevleri Toplama
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Adım 3: Ayrıştırma ve Özelleştirme
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

Yukarıdaki snippet, her görevin mevcut WBS ve seviyesini yazdırır, ardından **WBS kodlarını özelleştirme** örneği gösterir.

## Görev WBS Kodlarını Yeniden Numaralandırma
Şimdi WBS hiyerarşisini gerçekten yeniden numaralandıralım.

### Adım 1: Projeyi Yükleme (Yeniden Numaralandırma Örneği)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Adım 2: Tüm Görevleri Seçme
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Adım 3: İlk WBS Kodlarını Çıktı Alma
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Adım 4: WBS Kodlarını Yeniden Numaralandırma
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Adım 5: Güncellenmiş WBS Kodlarını Çıktı Alma
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Bu adımları izleyerek proje dosyanızdaki herhangi bir görev kümesi için **WBS nasıl yeniden numaralandırılır** sorusunun cevabını almış olacaksınız.

## Yaygın Sorunlar ve Çözümler
- **`set` çağrısından sonra WBS değişmiyor:** Doğru görev örneğiyle çalıştığınızdan ve değişikliklerden sonra projenin kaydedildiğinden emin olun.  
- **`renumberWBSCode` bir istisna fırlatıyor:** Üst‑seviye görev sayısıyla eşleşen bir ID listesi sağladığınızdan emin olun; aksi takdirde yeni numaralar doğru eşlenemez.  
- **WBS değerleri eksik:** Bazı görevler, WBS tanımlı olmayan bir dosyadan içe aktarıldıysa `null` WBS alabilir. Yazdırmadan önce bir yedek değer kullanın.

## Sık Sorulan Sorular

**S: Aspose.Tasks for Java belgelerine nereden ulaşabilirim?**  
C: Belgeler [burada](https://reference.aspose.com/tasks/java/) mevcuttur.

**S: Aspose.Tasks for Java'ı nasıl indirebilirim?**  
C: İndirme bağlantısı [burada](https://releases.aspose.com/tasks/java/).

**S: Aspose.Tasks for Java için ücretsiz deneme sürümü var mı?**  
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

**S: Aspose.Tasks for Java desteği nereden alınır?**  
C: Destek için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin.

**S: Aspose.Tasks for Java için geçici bir lisans alabilir miyim?**  
C: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

**S: Yeniden numaralandırdıktan sonra WBS formatını yeniden adlandırabilir miyim?**  
C: Kesinlikle. `renumberWBSCode` çağrısından sonra görevler üzerinde döngü kurarak `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` şeklinde istediğiniz adlandırma kurallarını uygulayabilirsiniz.

**S: Yeniden numaralandırma görev bağımlılıklarını etkiler mi?**  
C: Hayır. Metot yalnızca WBS dizesini günceller; görev bağlantıları ve kısıtlamalar değişmez.

---

**Son Güncelleme:** 2026-03-03  
**Test Edilen Sürüm:** Aspose.Tasks for Java 24.12 (en yeni)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}