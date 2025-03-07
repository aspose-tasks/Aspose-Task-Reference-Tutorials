---
title: Leer propiedades de moneda en proyectos Aspose.Tasks
linktitle: Leer propiedades de moneda en proyectos Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a extraer información monetaria de archivos de MS Project utilizando Aspose.Tasks para Java. Se proporciona una guía paso a paso.
weight: 10
url: /es/java/currency-properties/read-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leer propiedades de moneda en proyectos Aspose.Tasks

## Introducción
En este tutorial, aprenderemos cómo utilizar Aspose.Tasks para Java para leer propiedades de moneda de archivos de Microsoft Project. Aspose.Tasks es una potente API de Java que permite a los desarrolladores manipular documentos de Microsoft Project sin necesidad de instalar Microsoft Project. Si sigue los pasos que se describen a continuación, podrá extraer información relacionada con la moneda sin esfuerzo.
## Requisitos previos
Antes de continuar con este tutorial, asegúrese de tener los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema.
2.  Aspose.Tasks para Java JAR: descargue la biblioteca Aspose.Tasks para Java desde[aquí](https://releases.aspose.com/tasks/java/) e inclúyalo en su proyecto Java.
## Importar paquetes
Comience importando los paquetes necesarios a su clase Java:
```java
import com.aspose.tasks.*;
```
## Paso 1: configure su directorio de proyectos
Primero, configure el directorio de su proyecto donde se encuentra su archivo de Microsoft Project. Puede definir esta ruta de directorio de la siguiente manera:
```java
String dataDir = "Your Data Directory";
```
 Reemplazar`"Your Data Directory"` con la ruta real al directorio de su proyecto.
## Paso 2: crear una instancia de lector de proyectos
 Crear una instancia de`Project` objeto proporcionando la ruta a su archivo de Microsoft Project:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Asegúrese de reemplazar`"project.mpp"` con el nombre de su archivo de MS Project.
## Paso 3: Mostrar propiedades de moneda
Recupere y muestre propiedades de moneda del archivo del proyecto:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Este segmento de código obtiene información como código de moneda, dígitos, símbolo y posición del símbolo del archivo de MS Project y los imprime en la consola.
## Paso 4: finalización del proceso
Por último, imprima un mensaje indicando la finalización exitosa del proceso:
```java
System.out.println("Process completed Successfully");
```
## Conclusión
En este tutorial, exploramos cómo leer propiedades de moneda de archivos de Microsoft Project usando Aspose.Tasks para Java. Si sigue los pasos descritos, puede extraer sin esfuerzo información relacionada con la moneda de los archivos de su proyecto mediante programación, lo que permite una integración perfecta en sus aplicaciones Java.
## Preguntas frecuentes
### P: ¿Aspose.Tasks es compatible con todas las versiones de Microsoft Project?
R: Aspose.Tasks admite varias versiones de Microsoft Project, incluidos los archivos MPP generados por MS Project 2003-2021.
### P: ¿Puedo modificar las propiedades de la moneda usando Aspose.Tasks?
R: Sí, Aspose.Tasks le permite leer y modificar propiedades de moneda en archivos de MS Project mediante programación.
### P: ¿Aspose.Tasks es adecuado para uso comercial?
 R: Sí, Aspose.Tasks es una biblioteca comercial diseñada para uso profesional. Puedes comprar una licencia[aquí](https://purchase.aspose.com/buy).
### P: ¿Aspose.Tasks ofrece una prueba gratuita?
 R: Sí, puede aprovechar una prueba gratuita de Aspose.Tasks desde[aquí](https://releases.aspose.com/).
### P: ¿Dónde puedo buscar ayuda o soporte para Aspose.Tasks?
 R: Puedes visitar el foro de Aspose.Tasks[aquí](https://forum.aspose.com/c/tasks/15) para cualquier ayuda o consulta.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
