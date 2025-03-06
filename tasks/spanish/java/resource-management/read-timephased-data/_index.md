---
title: Leer datos de fases temporales para recursos en Aspose.Tasks
linktitle: Leer datos de fases temporales para recursos en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a extraer datos en fases temporales de recursos de MS Project utilizando Aspose.Tasks para Java. Tutorial paso a paso.
weight: 15
url: /es/java/resource-management/read-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leer datos de fases temporales para recursos en Aspose.Tasks

## Introducción
En este tutorial, lo guiaremos a través del proceso de lectura de datos en fases temporales para recursos de MS Project usando Aspose.Tasks para Java. Esta biblioteca proporciona potentes funcionalidades para administrar archivos de Microsoft Project mediante programación.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1.  Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema. Puedes descargarlo desde el[sitio web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) y siga las instrucciones de instalación.
2.  Biblioteca Aspose.Tasks para Java: descargue la biblioteca Aspose.Tasks para Java desde[pagina de descarga](https://releases.aspose.com/tasks/java/) y siga las instrucciones de instalación proporcionadas en la documentación.

## Importar paquetes
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Paso 1: configurar el directorio de datos
Primero, defina el directorio donde se encuentra su archivo de MS Project.
```java
String dataDir = "Your Data Directory";
```
## Paso 2: leer el archivo de plantilla de MS Project
Especifique el nombre de su archivo de plantilla de MS Project.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Paso 3: leer el archivo de entrada como proyecto
Lea el archivo de entrada usando Aspose.Tasks y cárguelo como un objeto de Proyecto.
```java
Project project = new Project(dataDir + fileName);
```
## Paso 4: obtenga recursos por identificación
Recupere el recurso deseado del proyecto mediante su identificador único (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Paso 5: Imprimir datos en fases temporales para el trabajo de recursos
Imprima los datos de fases temporales para el trabajo de recursos.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Paso 6: Imprima datos de fases temporales para el costo de los recursos
Imprima los datos de fases temporales para el costo de los recursos.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Conclusión
En este tutorial, hemos aprendido cómo leer datos de fases temporales para recursos de MS Project usando Aspose.Tasks para Java. Si sigue estos pasos, podrá extraer de manera eficiente información valiosa de los archivos de su proyecto mediante programación.
## Preguntas frecuentes
### ¿Puede Aspose.Tasks manejar otros tipos de archivos de proyecto además de Microsoft Project?
Sí, Aspose.Tasks admite varios formatos de archivo, incluidos MPP, XML y CSV.
### ¿Aspose.Tasks es compatible con diferentes entornos de desarrollo Java?
Sí, Aspose.Tasks es compatible con todos los principales IDE y marcos de Java.
### ¿Puedo manipular datos del proyecto usando Aspose.Tasks?
Por supuesto, Aspose.Tasks proporciona amplias API para crear, modificar y analizar datos de proyectos.
### ¿Aspose.Tasks es adecuado para proyectos de nivel empresarial?
Sí, Aspose.Tasks se utiliza ampliamente en entornos empresariales debido a su confiabilidad y escalabilidad.
### ¿Dónde puedo encontrar soporte si tengo problemas al usar Aspose.Tasks?
 Puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener ayuda de la comunidad y del equipo de soporte.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
