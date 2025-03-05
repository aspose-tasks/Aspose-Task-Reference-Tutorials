---
title: Aspose.Tasks'a MPP Proje Özeti Yazma
linktitle: Aspose.Tasks'a MPP Proje Özeti Yazma
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks'ı kullanarak Java'da MPP proje özetlerini nasıl yazacağınızı öğrenin. Proje bilgilerini zahmetsizce ayarlayın ve alın.
type: docs
weight: 27
url: /tr/java/project-file-operations/write-mpp-project-summary/
---
## giriiş
Bu eğitimde MPP proje özetleri yazmak için Aspose.Tasks for Java'yı nasıl kullanacağımızı öğreneceğiz. Aspose.Tasks, Microsoft Project dosyalarıyla çalışmak için güçlü bir Java kütüphanesidir. Aşağıda özetlenen adımları takip ederek, bu kütüphaneyi kullanarak bir proje hakkında çeşitli özet bilgileri ayarlayabilecek ve alabileceksiniz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java: Aspose.Tasks for Java kütüphanesini indirip yükleyin. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
3. Entegre Geliştirme Ortamı (IDE): Java geliştirme için IntelliJ IDEA, Eclipse veya NetBeans gibi tercih ettiğiniz IDE'yi seçin.

## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java sınıfınıza aktarın:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Adım 1: Projeyi Kurun ve Özet Bilgiyi Tanımlayın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Data Directory";
//Proje dosyanızın yolunu içeren yeni bir Proje nesnesi başlatın
Project project = new Project(dataDir + "project.mpp");
// Proje hakkında özet bilgileri ayarlayın
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Projenin oluşturulma tarihini ayarlayın
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Proje için anahtar kelimeler belirleyin
project.set(Prj.KEYWORDS, "MPP Aspose");
// Projenin son basım tarihini ayarlayın
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Adım 2: Proje Özet Bilgilerini Kaydedin
```java
// Projeyi tekrar MPP formatında kaydedin
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Bir başarı mesajı görüntüle
System.out.println("Process completed Successfully");
```
## 3. Adım: Proje Özet Bilgilerini Okuyun
```java
// Proje Özet Bilgilerinin Okunması
project = new Project(dataDir + "MppAspose.xml");
// Projenin yazarını yazdır
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Projenin son yazarını yazdır
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Projenin revizyon numarasını yazdırın
System.out.println("Revision: " + project.get(Prj.REVISION));
// Projenin anahtar kelimelerini yazdırın
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Projenin yorumlarını yazdır
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Projenin oluşturulma tarihini yazdırın
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Projenin anahtar kelimelerini yazdırın (tekrar)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Projenin son basım tarihini yazdır
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak MPP proje özetlerinin nasıl yazılacağını ele aldık. Bu adımları izleyerek proje dosyalarınız hakkındaki çeşitli özet bilgileri etkili bir şekilde ayarlayabilir ve alabilirsiniz. Aspose.Tasks, Java uygulamalarında Microsoft Project dosyalarıyla çalışma sürecini basitleştirerek sağlam işlevsellik ve kullanım kolaylığı sunar.
## SSS'ler
### S: Aspose.Tasks for Java'yı diğer Java kütüphaneleriyle birlikte kullanabilir miyim?
C: Evet, Aspose.Tasks for Java, proje yönetimi yeteneklerinizi geliştirmek için diğer Java kitaplıklarıyla sorunsuz bir şekilde entegre edilebilir.
### S: Aspose.Tasks for Java'nın deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for Java ne sıklıkta güncellenir?
C: Aspose.Tasks for Java, Java ve Microsoft Project dosyalarının en son sürümleriyle uyumluluğun sağlanması amacıyla düzenli olarak güncellenmektedir.
### S: Proje özeti bilgilerini daha da özelleştirebilir miyim?
C: Kesinlikle, Aspose.Tasks for Java, proje özet bilgilerini özel gereksinimlerinize göre özelleştirmek için kapsamlı seçenekler sunar.
### S: Aspose.Tasks for Java için nereden destek alabilirim?
C: Aspose.Tasks topluluk forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15).