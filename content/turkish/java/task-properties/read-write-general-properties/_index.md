---
title: Aspose.Tasks'ta Görev Özelliklerinde Uzmanlaşmak
linktitle: Aspose.Tasks'ta Görevlerin Genel Özelliklerini Okuma ve Yazma
second_title: Aspose.Tasks Java API'si
description: Görev özelliklerini zahmetsizce yönetme konusunda Aspose.Tasks for Java'nın gücünü keşfedin. Adım adım kılavuzumuzu kullanarak kolaylıkla okuyun ve yazın.
type: docs
weight: 26
url: /tr/java/task-properties/read-write-general-properties/
---
## giriiş
Aspose.Tasks ile Java'daki görev yönetiminin tüm potansiyelini ortaya çıkarın. Bu kapsamlı kılavuzda Aspose.Tasks for Java'yı kullanarak görevlerin genel özelliklerini okuma ve yazma konusunu derinlemesine inceleyeceğiz. İster deneyimli bir geliştirici olun ister yeni başlayan biri olun, bu eğitim sizi görev özelliklerini zahmetsizce değiştirebilmeniz için gereken becerilerle donatacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Tasks for Java kütüphanesi indirildi ve kuruldu. İndirme linkini bulabilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
- IntelliJ IDEA veya Eclipse gibi bir kod düzenleyici.
## Paketleri İçe Aktar
İşleri başlatmak için gerekli paketleri Java projenize aktarın. Bu adım Aspose.Tasks işlevlerine erişmenizi sağlar. İşte size yol gösterecek bir pasaj:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Görevlerin Genel Özelliklerini Okuma
## 1. Adım: Görev Oluşturun
Projenizde bir görev oluşturarak başlayın. Bu, görev adının, başlangıç tarihinin ve diğer ilgili ayrıntıların ayarlanmasını içerir. İşte bir örnek:
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## Adım 2: Görev Özelliklerini Okuyun
Artık bir görev oluşturduğunuza göre, genel özelliklerini alıp görüntüleyelim. Aşağıdaki kod parçacığı bunu başarır:
```java
// Görevlerin Genel Özelliklerini Okuma
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
## Görevlerin Genel Özelliklerinin Yazılması
## Adım 3: Projeyi Yükleyin ve Toplayıcı Oluşturun
 Genel özellikleri yazmak için mevcut bir projeyi yükleyin ve bir`ChildTasksCollector`:
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## Adım 4: Özellikleri Ayrıştırın ve Görüntüleyin
Son olarak, toplanan görevleri ayrıştırın ve özelliklerini görüntüleyin:
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
Tebrikler! Aspose.Tasks for Java'yı kullanarak görevlerin genel özelliklerini başarıyla okuyup yazdınız.
## Çözüm
Bu eğitimde Aspose.Tasks for Java ile görev özelliklerini sorunsuz bir şekilde yönetmek için temel adımları inceledik. Bu tekniklerde uzmanlaşarak Java geliştirme becerilerinizi geliştirebilir ve projelerinizde görev yönetimini kolaylaştırabilirsiniz.
## SSS
### Aspose.Tasks Java 11 ile uyumlu mu?
Evet, Aspose.Tasks, Java 11 ve sonraki sürümlerle uyumludur.
### Aspose.Tasks'ı ticari projeler için kullanabilir miyim?
 Kesinlikle! Aspose.Tasks, hem kişisel hem de ticari projeler için güçlü bir araçtır. Ziyaret etmek[Burada](https://purchase.aspose.com/buy) Lisanslama seçeneklerini keşfetmek için.
### Test amaçlı geçici lisansı nasıl alabilirim?
 Geçici lisans alın[Burada](https://purchase.aspose.com/temporary-license/) Test ve değerlendirme için.
### Aspose.Tasks için topluluk desteğini nerede bulabilirim?
 Topluluk tartışmasına katılın[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) yardım ve işbirliği için.
### Referans için herhangi bir örnek proje var mı?
 Belgelerin örnekler bölümünü inceleyin[Burada](https://reference.aspose.com/tasks/java/) örnek projeler ve kod parçacıkları için.