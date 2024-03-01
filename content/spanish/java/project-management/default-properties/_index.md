---
title: Administre eficientemente las propiedades de MS Project en Aspose.Tasks
linktitle: Administrar las propiedades predeterminadas del proyecto en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a administrar las propiedades predeterminadas de MS Project usando Aspose.Tasks para Java. Optimice el flujo de trabajo de gestión de proyectos sin esfuerzo.
type: docs
weight: 11
url: /es/java/project-management/default-properties/
---
## Introducción
¿Está buscando optimizar su proceso de gestión de proyectos con Aspose.Tasks para Java? La gestión de propiedades predeterminadas en archivos de Microsoft Project puede mejorar significativamente la eficiencia. En este tutorial, veremos instrucciones paso a paso sobre cómo administrar las propiedades predeterminadas de MS Project usando Aspose.Tasks.
## Requisitos previos
Antes de profundizar en el tutorial, asegúrese de tener los siguientes requisitos previos:
### 1. Kit de desarrollo de Java (JDK)
   - Asegúrese de que JDK esté instalado en su sistema.
   -  Puedes descargarlo desde[aquí](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tasks para la biblioteca Java
   - Descargue e incluya la biblioteca Aspose.Tasks para Java en su proyecto.
   -  Puedes descargarlo desde el[sitio web](https://releases.aspose.com/tasks/java/).
## Importar paquetes
En primer lugar, importe los paquetes necesarios en su archivo Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
Dividamos el proceso en pasos manejables:
## Paso 1: cargar el archivo del proyecto
```java
// La ruta al directorio de documentos.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Paso 2: Mostrar propiedades predeterminadas
```java
// Mostrar propiedades predeterminadas
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## Paso 3: establecer propiedades predeterminadas
```java
// Establecer propiedades predeterminadas
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## Paso 4: guarde el proyecto en formato XML
```java
// Guarde el proyecto en formato XML.
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## Paso 5: Mostrar resultado
```java
// Mostrar el resultado de la conversión.
System.out.println("Process completed Successfully");
```
Si sigue estos pasos, puede administrar de manera eficiente las propiedades predeterminadas de MS Project usando Aspose.Tasks para Java.
## Conclusión
En este tutorial, aprendimos cómo administrar las propiedades predeterminadas de MS Project usando Aspose.Tasks para Java. Al utilizar estas técnicas, puede optimizar el flujo de trabajo de gestión de proyectos, mejorando la productividad y la organización.
## Preguntas frecuentes
### P1: ¿Puedo utilizar Aspose.Tasks con otros lenguajes de programación?
R1: Sí, Aspose.Tasks admite varios lenguajes de programación como .NET, Python y Java.
### P2: ¿Aspose.Tasks es adecuado tanto para uso personal como empresarial?
R2: ¡Absolutamente! Ya sea que esté gestionando pequeños proyectos personales o iniciativas empresariales a gran escala, Aspose.Tasks se adapta a todos.
### P3: ¿Aspose.Tasks ofrece atención al cliente?
R3: Sí, puede encontrar asistencia y apoyo comunitario en el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### P4: ¿Puedo probar Aspose.Tasks antes de comprar?
 R4: ¡Por supuesto! Puede aprovechar una prueba gratuita desde el[sitio web](https://releases.aspose.com/).
### P5: ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks?
 R5: Puede obtener una licencia temporal del[pagina de compra](https://purchase.aspose.com/temporary-license/) para fines de prueba y evaluación.