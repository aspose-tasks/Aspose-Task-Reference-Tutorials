---
title: Aspose.Tasks'ta Görev Verilerini MPP Formatına Güncelleyin
linktitle: Aspose.Tasks'ta Görev Verilerini MPP Formatına Güncelleyin
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak görev verilerini MPP formatına nasıl güncelleyeceğinizi öğrenin. Etkin proje yönetimi için adım adım kılavuzumuzu izleyin.
type: docs
weight: 35
url: /tr/java/task-properties/update-task-data/
---
## giriiş
Aspose.Tasks for Java'yı kullanarak görev verilerini MPP formatına güncellemeye ilişkin adım adım kılavuzumuza hoş geldiniz. Bu eğitimde size süreç boyunca yol göstererek her adımı net bir şekilde kavramanızı sağlayacağız. Aspose.Tasks for Java, Microsoft Project dosyalarıyla çalışmak için sağlam bir çözüm sunar ve bu kılavuzun sonunda MPP formatındaki görev verilerini verimli bir şekilde güncelleyebileceksiniz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.Tasks for Java: Aspose.Tasks kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[yayın sayfası](https://releases.aspose.com/tasks/java/).
- Java Geliştirme Kiti (JDK): Sisteminizde Java'nın kurulu olduğundan emin olun.
- Entegre Geliştirme Ortamı (IDE): Java geliştirme için seçtiğiniz bir IDE'yi kullanın.
## Paketleri İçe Aktar
Gerekli paketleri Java projenize aktararak başlayın. Aşağıdaki kod parçası paketlerin nasıl içe aktarılacağını gösterir:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. İlk Görevi Oluşturun ve Yapılandırın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Kodun geri kalanıyla devam edin)
```
## 2. Başlangıç Tarihini ve Süreyi Ayarlayın
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Kodun geri kalanıyla devam edin)
```
## 3. Özet Görev Oluşturun
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Kodun geri kalanıyla devam edin)
```
## 4. Son Tarihi ve Görev Notlarını Belirleyin
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Kodun geri kalanıyla devam edin)
```
## 5. Görev Kısıtlamalarını Yapılandırın
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Kodun geri kalanıyla devam edin)
```
## 6. Ek Görevler Oluşturun
```java
//10 yeni görev oluşturun
for (int i = 0; i < 10; i++) {
    //... (Kodun geri kalanıyla devam edin)
}
//... (Kodun geri kalanıyla devam edin)
```
## 7. Projeyi Kaydet
```java
// Projeyi Kaydet
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Bu adımları izleyerek Aspose.Tasks for Java'yı kullanarak görev verilerini başarıyla MPP formatına güncellediniz.
## Çözüm
Tebrikler! Aspose.Tasks for Java'yı kullanarak MPP formatındaki görev verilerini güncellemeye ilişkin kapsamlı bir kılavuzu tamamladınız. Bu güçlü kitaplık, proje yönetimi görevlerini basitleştirerek onu Java geliştiricileri için değerli bir araç haline getirir.
## SSS
### S: Aspose.Tasks for Java belgelerini nerede bulabilirim?
 C: Belgeler mevcut[Burada](https://reference.aspose.com/tasks/java/).
### S: Aspose.Tasks for Java'yı nasıl indirebilirim?
 Cevap: Buradan indirebilirsiniz.[yayın sayfası](https://releases.aspose.com/tasks/java/).
### S: Ücretsiz deneme mevcut mu?
 C: Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for Java için nereden destek alabilirim?
 C: Destek forumunu ziyaret edin[Burada](https://forum.aspose.com/c/tasks/15).
### S: Test amaçlı geçici lisanslar sunuyor musunuz?
 C: Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).