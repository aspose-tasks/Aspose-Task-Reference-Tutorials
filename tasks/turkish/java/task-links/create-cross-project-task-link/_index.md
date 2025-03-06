---
title: Aspose.Tasks'ta Projeler Arası Görev Bağlantısı Oluşturun
linktitle: Aspose.Tasks'ta Projeler Arası Görev Bağlantısı Oluşturun
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java ile proje işbirliğini geliştirin. Projeler arası görev bağlantılarını adım adım oluşturmayı öğrenin. Şimdi verimliliği artırın!
weight: 10
url: /tr/java/task-links/create-cross-project-task-link/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Projeler Arası Görev Bağlantısı Oluşturun

## giriiş
Proje yönetiminin dinamik dünyasında verimlilik ve işbirliği çok önemlidir. Aspose.Tasks for Java, proje yönetimi yeteneklerinizi geliştirmek için güçlü bir çözüm sunar. Bu eğitimde Aspose.Tasks for Java'yı kullanarak projeler arası görev bağlantıları oluşturma sürecini derinlemesine inceleyeceğiz. Bu adım adım kılavuz, daha iyi koordinasyonu ve kolaylaştırılmış iş akışlarını teşvik ederek, farklı projelerdeki görevleri sorunsuz bir şekilde birbirine bağlama becerileriyle donatacaktır.
## Önkoşullar
Bu eğitime başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Java programlama konusunda çalışma bilgisi.
-  Aspose.Tasks for Java kuruldu. adresinden indirebilirsiniz.[Aspose.Tasks for Java sürüm sayfası](https://releases.aspose.com/tasks/java/).
- Proje yönetimi ve görev bağımlılıklarına ilişkin temel bir anlayış.
## Paketleri İçe Aktar
Süreci başlatmak için gerekli paketleri Java ortamınıza aktaralım. Bu, Aspose.Tasks for Java işlevlerine erişebilmenizi sağlar. Aşağıdaki kod parçacığını kullanın:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
Şimdi yukarıdaki kodu anlaşılır adımlara ayıralım:
## 1. Adım: Ortamınızı Kurun
Koda dalmadan önce Java'nın kurulu olduğundan ve Aspose.Tasks for Java kütüphanesinin projenize doğru şekilde eklendiğinden emin olun.
## 2. Adım: Proje Örneği Oluşturun
Aspose.Tasks kütüphanesini kullanarak yeni bir proje başlatın:
```java
Project project = new Project();
```
## 3. Adım: Özet Görev Ekleme
Bağlantılı görevleri düzenlemek ve yönetmek için bir özet görev oluşturun:
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## 4. Adım: Harici Görev Ekle
Başka bir projeden bir göreve bağlantı oluşturmak için özet göreve harici bir görev ekleyin:
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## 5. Adım: Yerel Görev Ekle
Özet göreve yerel bir görev ekleyin. Bu, harici göreve bağlı görev olacaktır:
```java
Task t = summary.getChildren().add("Task");
```
## Adım 6: Görev Bağlantısı Oluşturun
Harici görev ile yerel görev arasında görev bağlantısını kurun:
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## Adım 7: Sonuçları Görüntüleyin
Son olarak dönüşümün sonucunu görüntüleyin:
```java
System.out.println("Process completed Successfully");
```
## Çözüm
Tebrikler! Aspose.Tasks for Java'yı kullanarak projeler arası görev bağlantılarını nasıl oluşturacağınızı başarıyla öğrendiniz. Bu işlevsellik, proje yönetiminde işbirliğini ve koordinasyonu geliştirerek farklı projelerdeki görevler arasında kusursuz entegrasyon sağlar.
## SSS
### Birden fazla harici projedeki görevleri aynı özet görevde bağlayabilir miyim?
Evet, benzer bir süreci izleyerek, farklı harici projelerdeki görevleri aynı özet görev içinde bağlayabilirsiniz.
### Bağlantılı projedeki harici görev değiştirilirse ne olur?
Harici görevde yapılan herhangi bir değişiklik mevcut projenizdeki bağlantılı göreve yansıtılacaktır.
### Farklı dosya formatlarındaki görevler arasında bağlantılar oluşturmak mümkün mü?
Evet, Aspose.Tasks for Java, çeşitli dosya formatlarındaki projeler arasındaki görevlerin bağlanmasını destekler.
### Görevler projelere bağlandıktan sonra görevlerin bağlantısını kaldırabilir miyim?
Evet, uygun Aspose.Tasks yöntemlerini kullanarak görev bağlantısını kaldırarak görevlerin bağlantısını kaldırabilirsiniz.
### Projeler arasında ilişkilendirilebilecek görev sayısında herhangi bir sınırlama var mı?
Bağlanabilecek görevlerin sayısı Aspose.Tasks lisansınızın yeteneklerine ve sınırlamalarına tabidir.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
