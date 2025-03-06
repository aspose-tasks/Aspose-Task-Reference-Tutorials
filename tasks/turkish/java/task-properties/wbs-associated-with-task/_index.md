---
title: Aspose.Tasks'ta Görevle İlişkili WBS
linktitle: Aspose.Tasks'ta Görevle İlişkili WBS
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java ile WBS'de ustalaşın - Görev WBS kodlarını okumayı ve yeniden numaralandırmayı öğrenin. Proje yönetimi verimliliğini artırın!
weight: 36
url: /tr/java/task-properties/wbs-associated-with-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Görevle İlişkili WBS

## giriiş
Aspose.Tasks for Java ile proje yönetimi dünyasına hoş geldiniz! Bu eğitimde Aspose.Tasks for Java'yı kullanan görevlerle ilişkili İş Kırılım Yapısının (WBS) inceliklerini inceleyeceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz İKY kodlarını verimli bir şekilde yönetmenin temelleri arasında gezinmenize yardımcı olacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Makinenizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Tasks for Java kütüphanesi indirildi ve projenize eklendi. Şu adresten alabilirsiniz:[Burada](https://releases.aspose.com/tasks/java/).
## Paketleri İçe Aktar
Projenizi başlatmak için gerekli paketleri içe aktardığınızdan emin olun:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## WBS Kodlarını Okuyun
Görevlerle ilişkili WBS kodlarını okuyarak başlayalım. Bu adımları takip et:
## Adım 1: Projeyi Yükleyin
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## 2. Adım: Görevleri Toplayın
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## 3. Adım: Ayrıştırma ve Özelleştirme
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Bu kod parçası, projenizdeki görevlerle ilişkili WBS kodlarını okur ve özelleştirir.
## Görev ÇÇY Kodlarını Yeniden Numaralandır
Şimdi görevler için WBS kodlarını yeniden numaralandırmayı inceleyelim:
## Adım 1: Projeyi Yükleyin
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Adım 2: Tüm Görevleri Seçin
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Adım 3: İlk WBS Kodlarını Çıktılayın
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Adım 4: WBS Kodlarını Yeniden Numaralandırın
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Adım 5: Güncellenmiş WBS Kodlarının Çıktısı
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Bu adımları izleyerek projenizdeki görevler için WBS kodlarını etkili bir şekilde yeniden numaralandıracaksınız.
## Çözüm
Tebrikler! Aspose.Tasks for Java'yı kullanarak WBS kodlarıyla nasıl çalışacağınızı başarıyla öğrendiniz. Bu bilgi, projenizin görev hiyerarşisini verimli bir şekilde yönetmenizi ve özelleştirmenizi sağlayacaktır.
## SSS
### S: Aspose.Tasks for Java belgelerini nerede bulabilirim?
 C: Belgeler mevcut[Burada](https://reference.aspose.com/tasks/java/).
### S: Aspose.Tasks for Java'yı nasıl indirebilirim?
 Cevap: İndirebilirsin[Burada](https://releases.aspose.com/tasks/java/).
### S: Aspose.Tasks for Java'nın ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for Java için nereden destek alabilirim?
 C: Ziyaret edin[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) destek için.
### S: Aspose.Tasks for Java için geçici bir lisans alabilir miyim?
 C: Evet, geçici lisans alın[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
