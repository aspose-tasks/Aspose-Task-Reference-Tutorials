---
title: Aspose.Tasks'ta MS Project'i Güncelleyin ve Yeniden Planlayın
linktitle: Aspose.Tasks'ta Projeyi Güncelleyin ve Tamamlanmamış Çalışmaları Yeniden Planlayın
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project dosyalarını programlı olarak nasıl güncelleyeceğinizi ve yeniden planlayacağınızı öğrenin.
type: docs
weight: 23
url: /tr/java/project-file-operations/update-project-reschedule-work/
---
## giriiş
Microsoft Project, kullanıcıların görevleri, kaynakları ve zaman çizelgelerini verimli bir şekilde yönetmelerine olanak tanıyan, yaygın olarak kullanılan bir proje yönetimi yazılımıdır. Aspose.Tasks for Java, Microsoft Project dosyalarını programlı olarak yönetmek için güçlü bir API seti sağlar. Bu eğitimde Aspose.Tasks for Java'yı kullanarak MS Project dosyalarını nasıl güncelleyeceğimizi ve tamamlanmamış işleri nasıl yeniden planlayacağımızı öğreneceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
2.  Aspose.Tasks Java kütüphanesi için. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
3. Java programlama dilinin temel anlayışı.

## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java kodunuza aktarın:
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
## 1. Adım: Projeyi Kurun
Yeni bir Proje nesnesi başlatın ve içindeki görevleri süreleri ve bağımlılıklarıyla birlikte tanımlayın.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Görevleri ve sürelerini tanımlayın
// ...
// Görev bağımlılıklarını tanımlayın
// ...
// Başlangıçtaki proje durumunu kaydedin
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Adım 2: Proje Çalışmasını Güncelleyin
Proje çalışmasını belirli bir tarihe kadar tamamlandı olarak işaretlemek için güncelleyin.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Güncellenen projeyi kaydet
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## 3. Adım: Tamamlanmamış Çalışmayı Yeniden Planlayın
Tamamlanmamış işleri belirli bir tarihten sonra başlayacak şekilde yeniden planlayın.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Yeniden planlanan projeyi kaydet
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak MS Project dosyalarını nasıl güncelleyeceğimizi ve tamamlanmamış işleri nasıl yeniden planlayacağımızı öğrendik. Bu, proje zaman çizelgelerinin ilerlemeye veya değişen önceliklere göre ayarlanması gereken senaryolarda özellikle yararlı olabilir.

## SSS'ler
### S: Aspose.Tasks for Java karmaşık proje yapılarını yönetebilir mi?
C: Evet, Aspose.Tasks for Java, görevleri, bağımlılıkları, kaynakları ve diğer proje öğelerini verimli bir şekilde yönetmek için güçlü API'ler sağlar.
### S: Aspose.Tasks for Java'nın deneme sürümü mevcut mu?
 C: Evet, şu adresten ücretsiz deneme sürümünden yararlanabilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for Java için nasıl destek alabilirim?
 C: Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) herhangi bir yardım veya sorularınız için.
### S: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?
 C: Evet, geçici lisanslar satın alınabilir[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Tasks for Java'nın ayrıntılı belgelerini nerede bulabilirim?
 C: Belgelere başvurabilirsiniz[Burada](https://reference.aspose.com/tasks/java/) kapsamlı kılavuzlar ve API referansları için.