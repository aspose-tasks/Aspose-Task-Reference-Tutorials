---
title: Aspose.Tasks'ta MS Project Veritabanından Proje Verilerini Okumak
linktitle: Aspose.Tasks'ta Microsoft Project Veritabanından Proje Verilerini Okumak
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak proje verilerini Microsoft Project Veritabanından nasıl okuyacağınızı öğrenin. Kod örnekleri içeren adım adım kılavuz.
type: docs
weight: 12
url: /tr/java/project-data-reading/read-project-database/
---
## giriiş
Bu eğitimde Aspose.Tasks for Java kullanarak Microsoft Project Veritabanından proje verilerinin nasıl okunacağını inceleyeceğiz. Aspose.Tasks, geliştiricilerin Microsoft Project'in kurulmasına gerek kalmadan Microsoft Project belgelerini değiştirmesine olanak tanıyan güçlü bir Java API'sidir. Bu kılavuzda özetlenen adımları izleyerek, proje verilerini bir veritabanından verimli bir şekilde nasıl çıkaracağınızı ve istediğiniz formatta nasıl kaydedeceğinizi öğreneceksiniz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java programlamanın temel bilgisi.
2. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
3. Aspose.Tasks for Java kütüphanesi indirildi ve projenizde yapılandırıldı.

## Paketleri İçe Aktar
Başlamak için gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```
## 1. Adım: Veritabanı Bağlantısını Kurun
Öncelikle Microsoft Project Veritabanına bağlantıyı kurmanız gerekiyor. Bu, veritabanı URL'sini, sunucu adını, bağlantı noktası numarasını, veritabanı adını, kullanıcı adını ve şifreyi belirtmeyi içerir.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## Adım 2: JDBC Sürücüsünü Ekle
Daha sonra JDBC sürücüsünü projenize eklemeniz gerekir. Bu sürücü, Java uygulamaları ile Microsoft SQL Server veritabanı arasındaki iletişimi kolaylaştırır.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## 3. Adım: Proje Verilerini Okuyun
 Şimdi bir tane oluşturun`Project` önceden tanımlanmış ayarları kullanarak proje verilerini nesneye aktarın ve veritabanından yükleyin.
```java
Project project = new Project(settings);
```
## Adım 4: Proje Verilerini Kaydedin
Son olarak proje verilerini istediğiniz formatta kaydedin. Bu örnekte onu XML dosyası olarak kaydediyoruz.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Tebrikler! Aspose.Tasks for Java'yı kullanarak Microsoft Project Veritabanındaki proje verilerini başarıyla okudunuz.

## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak Microsoft Project Veritabanından proje verilerini okuma sürecini ele aldık. Belirtilen adımları izleyerek proje bilgilerini sorunsuz bir şekilde çıkarabilir ve gereksinimlerinize göre değiştirebilirsiniz. Aspose.Tasks, Microsoft Project belgelerinin işlenmesini basitleştirerek verimli veri çıkarma ve işleme olanağı sağlar.
## SSS'ler
### S: Aspose.Tasks, proje verilerini Microsoft Project dışındaki diğer veritabanlarından okumak için kullanılabilir mi?
C: Evet, Aspose.Tasks, XML dosyaları, Primavera ve Microsoft Project veritabanları dahil olmak üzere çeşitli kaynaklardan proje verilerinin okunmasını destekler.
### S: Aspose.Tasks, Microsoft Project'in farklı sürümleriyle uyumlu mudur?
C: Evet, Aspose.Tasks, uyumluluk ve kusursuz entegrasyon sağlayarak Microsoft Project'in farklı sürümleriyle çalışacak şekilde tasarlanmıştır.
### S: Proje verilerini kaydetmeden önce değiştirebilir miyim?
C: Aspose.Tasks kesinlikle proje verilerinin işlenmesi için görev eklemek, kaynakları güncellemek ve proje özelliklerini ayarlamak gibi çok çeşitli özellikler sunuyor.
### S: Aspose.Tasks birden fazla çıktı formatını destekliyor mu?
C: Evet, Aspose.Tasks, XML, PDF, HTML ve PNG ve JPEG gibi görüntü formatları dahil olmak üzere çeşitli çıktı formatlarını destekler.
### S: Aspose.Tasks ile ilgili daha fazla desteği veya yardımı nereden bulabilirim?
 C: Ek destek veya yardım için Aspose.Tasks forumunu ziyaret edebilir veya web sitesinde bulunan belgeleri inceleyebilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).