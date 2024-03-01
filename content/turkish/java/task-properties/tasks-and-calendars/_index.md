---
title: Aspose.Tasks'ta Görevler ve Takvimler
linktitle: Aspose.Tasks'ta Görevler ve Takvimler
second_title: Aspose.Tasks Java API'si
description: Görevleri ve takvimleri verimli bir şekilde yönetme konusunda Aspose.Tasks for Java'nın gücünü keşfedin. Kusursuz bir proje yönetimi deneyimi için hemen indirin!
type: docs
weight: 33
url: /tr/java/task-properties/tasks-and-calendars/
---
## giriiş
Aspose.Tasks for Java ile proje yönetimi oyununuzu geliştirmeye hazır mısınız? Bu kapsamlı kılavuz, Aspose.Tasks'ı kullanarak görevlerin ve takvimlerin karmaşık dünyasında size yol gösterecek ve verimli proje planlama ve yürütme için Aspose.Tasks'ın tüm potansiyelinden yararlanmanıza olanak tanıyacak.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Java Geliştirme Kiti (JDK): Sisteminizde Java'nın kurulu olduğundan emin olun.
- Aspose.Tasks Kütüphanesi: Aspose.Tasks kütüphanesini indirin ve projenize ekleyin. Kütüphaneyi bulabilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
## Paketleri İçe Aktar
Aspose.Tasks için gerekli paketleri Java projenize aktarın:
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```
## 1. Adım: Projenizi Kurun
Yeni bir Java projesi oluşturup Aspose.Tasks kütüphanesini içe aktararak başlayın.
## Adım 2: Aspose.Tasks Nesnelerini Başlatın
Yeni bir proje örneği ve bir kök görev oluşturun. Projeye "Görev1" adlı bir görev ekleyin.
```java
Project project = new Project();
Task tsk = project.getRootTask().getChildren().add("Task1");
```
## 3. Adım: Takvim Oluşturun
Aşağıdaki kodu kullanarak projenize standart bir takvim ekleyin:
```java
Calendar cal = project.getCalendars().add("TaskCal1");
```
## 4. Adım: Görevi Takvimle İlişkilendirin
Görevin oluşturulan takvimle ilişkili olduğundan emin olun:
```java
tsk.set(Tsk.CALENDAR, cal);
```
Projeniz için gereken birden fazla görev ve takvim için bu adımları tekrarlayın.
## Çözüm
Tebrikler! Aspose.Tasks for Java'da görevleri ve takvimleri yönetmenin karmaşıklıklarını başarıyla aştınız. Bu güçlü araç, etkili proje yönetimi için bir olasılıklar dünyasının kapılarını açar.
## Sıkça Sorulan Sorular
### Aspose.Tasks for Java'yı nasıl indirebilirim?
 Ziyaret etmek[bu bağlantı](https://releases.aspose.com/tasks/java/) Kütüphaneyi indirmek için.
### Aspose.Tasks belgelerini nerede bulabilirim?
 Belgeleri keşfedin[Burada](https://reference.aspose.com/tasks/java/).
### Ücretsiz deneme mevcut mu?
Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Tasks için nasıl destek alabilirim?
 Şu adresteki topluluğa katılın:[Aspose.Tasks Forumu](https://forum.aspose.com/c/tasks/15) destek için.
### Aspose.Tasks için lisans satın alabilir miyim?
 Evet, lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).