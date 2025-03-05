---
title: Aspose.Tasks'ta MS Project Görev Temeli Oluşturun
linktitle: Aspose.Tasks'ta Görev Temeli Oluşturma
second_title: Aspose.Tasks Java API'si
description: Proje verilerini zahmetsizce yönetmek için güçlü bir kütüphane olan Aspose.Tasks'ı kullanarak Java'da bir Microsoft Project görev temelini nasıl oluşturacağınızı öğrenin.
type: docs
weight: 11
url: /tr/java/task-baselines/create-task-baseline/
---
## giriiş
Bu eğitimde Aspose.Tasks for Java'yı kullanarak bir Microsoft Project görev temeli oluşturma sürecini ayrıntılı olarak ele alacağız. Aspose.Tasks, geliştiricilerin Microsoft Project'in kurulmasına gerek kalmadan Microsoft Project dosyalarıyla çalışmasına olanak tanıyan güçlü bir Java kitaplığıdır. Aspose.Tasks ile proje yönetimi görevlerini kolaylaştırmak için görevler, kaynaklar ve takvimler dahil olmak üzere proje verilerini zahmetsizce değiştirebilirsiniz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Aspose.Tasks for Java, sisteminizde JDK'nın kurulu olmasını gerektirir. JDK'yı Oracle web sitesinden indirip yükleyebilirsiniz.
2.  Aspose.Tasks for Java Kütüphanesi: Aspose.Tasks for Java kütüphanesini şu adresten indirin:[İndirme: {link](https://releases.aspose.com/tasks/java/) tedarik edilen.

## Paketleri İçe Aktar
Java projenizde Aspose.Tasks ile çalışmaya başlamak için gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Adım 1: Proje Nesnesi Oluşturun
```java
Project project = new Project();
```
 İlk önce yeni bir tane oluşturun`Project` nesne. Bu nesne, üzerinde çalışacağınız Microsoft Project dosyasını temsil eder.
## Adım 2: Projeye Görev Ekleme
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 Kullanmak`getRootTask()` yöntemini kullanarak projenin kök görevine erişin ve ardından ona yeni bir görev ekleyin.`add()` yöntem. Parantez içindeki göreve bir ad verin.
## 3. Adım: Belirtilen Görevler için Taban Çizgisini Ayarlayın
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Belirli görevler için bir temel belirlemek üzere bir görev listesi oluşturun (`myList` bu durumda) ve bunu temeli ayarlamak istediğiniz görevlerle doldurun. Daha sonra şunu kullanın:`setBaseline()` Temel türü ve görev listesini belirten yöntem.
## Adım 4: Tüm Proje için Temel Çizgiyi Belirleyin
```java
project.setBaseline(BaselineType.Baseline);
```
 Alternatif olarak, yalnızca çağrı yaparak tüm proje için bir temel belirleyebilirsiniz.`setBaseline()` belirtilen temel türe sahip yöntem.

## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak bir Microsoft Project görev tabanının nasıl oluşturulacağını araştırdık. Yukarıda özetlenen adımları izleyerek proje verilerini verimli bir şekilde yönetebilir ve proje yönetimi görevlerini kolaylıkla kolaylaştırabilirsiniz.
## SSS'ler
### Aspose.Tasks for Java'yı Microsoft Project yüklü olmadan kullanabilir miyim?
Evet, Aspose.Tasks for Java, sisteminizde Microsoft Project'in kurulu olmasına gerek kalmadan Microsoft Project dosyalarıyla çalışmanıza olanak tanır.
### Aspose.Tasks for Java, Microsoft Project'in farklı sürümleriyle uyumlu mu?
Evet, Aspose.Tasks for Java, Microsoft Project'in çeşitli sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.
### Aspose.Tasks for Java'yı kullanarak proje kaynaklarını değiştirebilir miyim?
Aspose.Tasks for Java kesinlikle proje kaynaklarını yönetmek için, gerektiğinde kaynak eklemek, güncellemek ve kaldırmak dahil olmak üzere güçlü özellikler sağlar.
### Aspose.Tasks for Java görev bağımlılıklarını ayarlamayı destekliyor mu?
Evet, Aspose.Tasks for Java'yı kullanarak görev bağımlılıklarını zahmetsizce ayarlayabilir, böylece projenizdeki görevlerin sırasını oluşturabilirsiniz.
### Aspose.Tasks for Java için teknik destek mevcut mu?
 Evet, Aspose.Tasks for Java teknik desteğine şu adresten ulaşabilirsiniz:[destek Forumu](https://forum.aspose.com/c/tasks/15), soru sorabileceğiniz ve topluluktan ve Aspose destek personelinden yardım isteyebileceğiniz yer.