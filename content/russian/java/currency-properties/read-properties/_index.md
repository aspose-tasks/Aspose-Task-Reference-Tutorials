---
title: Чтение свойств валюты в проектах Aspose.Tasks
linktitle: Чтение свойств валюты в проектах Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как извлечь информацию о валюте из файлов MS Project с помощью Aspose.Tasks для Java. Предоставлено пошаговое руководство.
type: docs
weight: 10
url: /ru/java/currency-properties/read-properties/
---
## Введение
В этом уроке мы узнаем, как использовать Aspose.Tasks для Java для чтения свойств валюты из файлов Microsoft Project. Aspose.Tasks — это мощный Java API, который позволяет разработчикам манипулировать документами Microsoft Project, не требуя установки Microsoft Project. Выполнив шаги, описанные ниже, вы сможете легко извлечь информацию, связанную с валютой.
## Предварительные условия
Прежде чем приступить к изучению этого руководства, убедитесь, что у вас есть следующие предварительные условия:
1. Java Development Kit (JDK): убедитесь, что в вашей системе установлен JDK.
2.  Aspose.Tasks for Java JAR: Загрузите библиотеку Aspose.Tasks for Java с сайта[здесь](https://releases.aspose.com/tasks/java/) и включите его в свой Java-проект.
## Импортировать пакеты
Начните с импорта необходимых пакетов в ваш класс Java:
```java
import com.aspose.tasks.*;
```
## Шаг 1. Настройте каталог проекта
Сначала настройте каталог проекта, в котором находится файл Microsoft Project. Вы можете определить этот путь к каталогу следующим образом:
```java
String dataDir = "Your Data Directory";
```
 Заменять`"Your Data Directory"` с фактическим путем к каталогу вашего проекта.
## Шаг 2. Создайте экземпляр средства чтения проектов
 Создать экземпляр`Project` объект, указав путь к файлу Microsoft Project:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Обязательно замените`"project.mpp"` с именем вашего файла MS Project.
## Шаг 3. Отображение свойств валюты
Получите и отобразите свойства валюты из файла проекта:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Этот сегмент кода извлекает такую информацию, как код валюты, цифры, символ и положение символа, из файла MS Project и выводит их на консоль.
## Шаг 4: Завершение процесса
Наконец, выведите сообщение об успешном завершении процесса:
```java
System.out.println("Process completed Successfully");
```
## Заключение
В этом руководстве мы рассмотрели, как читать свойства валюты из файлов Microsoft Project с помощью Aspose.Tasks для Java. Следуя описанным шагам, вы сможете легко программно извлекать информацию, связанную с валютой, из файлов вашего проекта, обеспечивая плавную интеграцию в ваши приложения Java.
## Часто задаваемые вопросы
### Вопрос: Совместим ли Aspose.Tasks со всеми версиями Microsoft Project?
О: Aspose.Tasks поддерживает различные версии Microsoft Project, включая файлы MPP, созданные MS Project 2003-2021.
### Вопрос: Могу ли я изменить свойства валюты с помощью Aspose.Tasks?
О: Да, Aspose.Tasks позволяет вам программно читать и изменять свойства валюты в файлах MS Project.
### Вопрос: Подходит ли Aspose.Tasks для коммерческого использования?
 О: Да, Aspose.Tasks — это коммерческая библиотека, предназначенная для профессионального использования. Вы можете приобрести лицензию[здесь](https://purchase.aspose.com/buy).
### Вопрос: Предлагает ли Aspose.Tasks бесплатную пробную версию?
 О: Да, вы можете воспользоваться бесплатной пробной версией Aspose.Tasks от[здесь](https://releases.aspose.com/).
### Вопрос: Где я могу получить помощь или поддержку по Aspose.Tasks?
 О: Вы можете посетить форум Aspose.Tasks.[здесь](https://forum.aspose.com/c/tasks/15) для любой помощи или вопросов.