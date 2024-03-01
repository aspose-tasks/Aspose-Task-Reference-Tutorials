---
title: Aspose.Tasks'ta Görevlerin Sürelerini Yönetin
linktitle: Aspose.Tasks'ta Görevlerin Sürelerini Yönetin
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı keşfedin ve görev sürelerini zahmetsizce yönetmeyi öğrenin. Etkili proje planlama ve yürütme için adım adım kılavuzumuzu izleyin.
type: docs
weight: 20
url: /tr/java/task-properties/manage-durations/
---
## giriiş
Aspose.Tasks for Java, proje görevlerini ve sürelerini verimli bir şekilde yönetmek için güçlü bir çözüm sunar. Bu eğitimde Aspose.Tasks'ı kullanarak görevlerin sürelerini nasıl yöneteceğinizi keşfedeceğiz ve her adımda size yol göstereceğiz. İster deneyimli bir geliştirici olun ister yeni başlayan biri olun, bu kılavuz projelerinizde görev süreleriyle çalışmanın temellerini kavramanıza yardımcı olacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
-  Java Geliştirme Kiti (JDK): Makinenizde Java'nın kurulu olduğundan emin olun. İndirebilirsin[Burada](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks Kütüphanesi: Aspose.Tasks kütüphanesini indirin ve projenize ekleyin. Kütüphaneyi bulabilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
## Paketleri İçe Aktar
Aspose.Tasks ile çalışmak için gerekli paketleri Java projenize aktarın:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## 1. Adım: Projenizi Kurun
```java
// Yeni bir proje oluştur
Project project = new Project();
```
## 2. Adım: Yeni Bir Görev Ekleme
```java
// Projeye yeni bir görev ekleme
Task task = project.getRootTask().getChildren().add("Task");
```
## 3. Adım: Görev Süresini Alın ve Dönüştürün
```java
// Gün cinsinden görev süresini alın (varsayılan zaman birimi)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Süreyi saat zaman birimine dönüştür
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## 4. Adım: Görev Süresini 1 Haftaya Güncelleyin
```java
// Görev süresini 1 haftaya çıkarın
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Adım 5: Görev Süresini Azaltın
```java
// Görev süresini azaltın
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Bu adımları izleyerek Aspose.Tasks for Java projenizdeki görevlerin sürelerini başarıyla yönettiniz.
## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak görev sürelerini yönetmenin temellerini ele aldık. Artık etkili görev süresi yönetimi için bu teknikleri projelerinize güvenle dahil edebilirsiniz.
## SSS
### Aspose.Tasks tüm Java sürümleriyle uyumlu mu?
Aspose.Tasks, Java 6 ve sonraki sürümlerle uyumludur.
### Aspose.Tasks'ı ticari projeler için kullanabilir miyim?
 Evet, Aspose.Tasks'ı hem kişisel hem de ticari projeleriniz için kullanabilirsiniz. Ziyaret etmek[Burada](https://purchase.aspose.com/buy) lisans ayrıntıları için.
### Ek destek ve kaynakları nerede bulabilirim?
 Ziyaret edin[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) topluluk desteği ve tartışmalar için.
### Test amaçlı geçici lisansı nasıl alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/) Test ve değerlendirme için.
### Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/) Bir satın alma işlemi yapmadan önce Aspose.Tasks'ı keşfetmek için.